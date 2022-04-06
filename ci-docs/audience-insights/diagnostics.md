---
title: Nadzor Dynamics 365 Customer Insights s azure monitorom
description: Saznajte kako poslati zapisnike na Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523659"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prijava prosljeđivanja Dynamics 365 Customer Insights pomoću servisa Azure Monitor (pretpregled)

Dynamics 365 Customer Insights pruža izravnu integraciju s azure monitorom. Zapisnici resursa azure Monitor omogućuju vam praćenje i slanje zapisnika u [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) ili njihovo strujanje na [Azure Središta događaja](https://azure.microsoft.com/services/event-hubs/).

Customer Insights šalje sljedeće zapisnike događaja:

- **Događaji nadzora**
  - **APIEvent** - omogućuje praćenje promjena putem korisničkog Dynamics 365 Customer Insights sučelja.
- **Operativni događaji**
  - **WorkflowEvent** - Tijek rada omogućuje postavljanje [izvora](data-sources.md) podataka, [objedinjavanje](data-unification.md) i obogaćivanje [i](enrichment-hub.md) konačno [izvoz](export-destinations.md) podataka u druge sustave. Svi ti koraci mogu se obaviti pojedinačno (npr. pokrenuti jedan izvoz) ili orkestrirani (npr. osvježavanje podataka iz izvora podataka koji pokreću postupak ujedinjenja koji će povući dodatna obogaćivanja i nakon što se provedu izvoziti podatke u drugi sustav). Dodatne informacije potražite u shemi [WorkflowEvent Sheme](#workflow-event-schema).
  - **APIEvent** - svi API pozivi klijentima instanca na Dynamics 365 Customer Insights. Za više detalja pogledajte [APIEvent shemu](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Postavljanje dijagnostičkih postavki

### <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali dijagnostiku u korisničkim uvidima, moraju se ispuniti sljedeći preduvjeti:

- Imate aktivnu [pretplatu](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) na Azure.
- Imate [administratorske](permissions.md#admin) dozvole u customer insights.
- Na odredišnom resursu na servisu Azure imate ulogu administratora **suradnik** **i** administratora korisničkog pristupa. Resurs može biti račun za pohranu servisa Azure, središte događaja azure ili radni prostor analitike azure loga. Dodatne informacije potražite u članku [Dodavanje ili uklanjanje dodjela uloga servisa Azure pomoću portala](/azure/role-based-access-control/role-assignments-portal) azure.
- [Destination requirements](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) for Azure Storage, Azure Event Hub ili Azure Log Analytics met.
- Imate barem **Čitatelj** ulogu u grupi resursa kojoj resurs pripada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Postavljanje dijagnostike pomoću servisa Azure Monitor

1. U odjeljku Customer Insights odaberite **SystemDiagnostics** > **da** biste vidjeli odredišta dijagnostike konfigurirana za ovu instancu.

1. Odaberite **Dodaj odredište**.

   > [!div class="mx-imgBorder"]
   > ![Dijagnostička veza](media/diagnostics-pane.png "Dijagnostička veza")

1. Navedite naziv u **polju Naziv odredišta** dijagnostike.

1. **Odaberite Klijent** pretplate na Azure s odredišnim resursom i odaberite **Prijava**.

1. **Odaberite vrstu** resursa (račun za pohranu, središte događaja ili analitika zapisnika).

1. Odaberite pretplatu **za** odredišni resurs.

1. Odaberite grupu **Resursi** za odredišni resurs.

1. **Odaberite Resurs**.

1. Potvrdite izjavu o privatnosti i usklađenosti **podataka**.

1. Odaberite **Poveži se sa sustavom** da biste se povezali s odredišnim resursom. Zapisnici se počinju pojavljivati na odredištu nakon 15 minuta, ako se API koristi i generira događaje.

### <a name="remove-a-destination"></a>Uklanjanje odredišta

1. Idite na **SystemDiagnostics** > **·**.

1. Na popisu odaberite odredište dijagnostike.

1. U stupcu **Akcije** odaberite ikonu **Izbriši**.

1. Potvrdite brisanje da biste zaustavili prosljeđivanje zapisnika. Resurs na pretplati na Azure neće se izbrisati. Vezu u stupcu **Akcije** možete odabrati da biste otvorili portal servisa Azure za odabrani resurs i tamo ga izbrisali.

## <a name="log-categories-and-event-schemas"></a>Evidentiraj kategorije i sheme događaja

Trenutno [su podržani događaji](apis.md) IPI-ja i događaji tijeka rada te se primjenjuju sljedeće kategorije i sheme.
Shema zapisnika slijedi uobičajenu shemu [Azure Monitora](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorije

Customer Insights nudi dvije kategorije:

- **Događaji** nadzora: [događaji](#api-event-schema) API-ja za praćenje promjena konfiguracije na usluzi. `POST|PUT|DELETE|PATCH` operacije ulaze u ovu kategoriju.
- **Operativni događaji**: [događaji](#api-event-schema) API-ja ili [događaji tijeka](#workflow-event-schema) rada generirani tijekom korištenja usluge.  Na primjer, `GET` zahtjevi ili događaji izvršenja tijeka rada.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracija odredišnog resursa

Na temelju vašeg izbora na vrsti resursa automatski će se primjenjivati sljedeći koraci:

### <a name="storage-account"></a>Račun za pohranu

Voditelj usluge Customer Insights dobiva **dozvolu za suradnik** računa za pohranu na odabranom resursu i stvara dva spremnika u odabranom prostoru naziva:

- `insight-logs-audit` koji sadržavaju **događaje revizije**
- `insight-logs-operational` koji sadrže operativne **događaje**

### <a name="event-hub"></a>Središte događaja

Upravitelj servisa Customer Insights dobiva **dozvolu vlasnika** podataka servisa Azure Središta događaja za resurs i stvorit će dva Središta događaja u odabranom prostoru naziva:

- `insight-logs-audit` koji sadržavaju **događaje revizije**
- `insight-logs-operational` koji sadrže operativne **događaje**

### <a name="log-analytics"></a>Log Analytics

Direktor usluge Customer Insights dobiva **dopuštenje za suradnik** log analyticsa za resurs. Zapisnici će biti dostupni u odjeljku **LogsTablesLog** > **·** > **Management** na odabranom radnom prostoru Log Analyticsa. Proširite **rješenje za upravljanje zapisnicima** i pronađite tablice `CIEventsAudit` i `CIEventsOperational`.

- `CIEventsAudit` koji sadržavaju **događaje revizije**
- `CIEventsOperational` koji sadrže operativne **događaje**

**U prozoru Upiti proširite** rješenje nadzora **i** pronađite primjere upita koje pruža traženje `CIEvents`.

## <a name="event-schemas"></a>Sheme događaja

Događaji i događaji tijeka rada API-ja imaju zajedničku strukturu i detalje u kojima se razlikuju, pogledajte [shemu događaja](#api-event-schema) API-ja ili [shemu događaja tijeka](#workflow-event-schema) rada.

### <a name="api-event-schema"></a>Shema događaja API-ja

| Polje             | DataType  | Obavezno/neobavezno | Opis       | Primjer        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Podaci vremenske oznake | Obvezno          | Vremenska oznaka događaja (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obvezno          | ResourceId instance koja je emitirala događaj         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obvezno          | Naziv operacije predstavljene ovim događajem.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obvezno          | Kategorija zapisnika događaja. Ili `Operational` ili `Audit`. Svi POST/PUT/PATCH/DELETE HTTP Zahtjevi su označeni sa `Audit`, sve ostalo s`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obvezno          | Stanje događaja. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobavezno          | Stanje rezultata događaja. Ako operacija odgovara REST API pozivu, to je HTTP kod stanja.        | `200`             |
| `durationMs`      | Dugi      | Neobavezno          | Trajanje operacije u milisekundama.     | `133`     |
| `callerIpAddress` | String    | Neobavezno          | IP adresa pozivatelja, ako operacija odgovara API pozivu koji dolazi s javno dostupne IP adrese.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobavezno          | JSON objekt koji opisuje identitet korisnika ili aplikacije koja je izvršila operaciju.       | Pogledajte [odjeljak Identitet](#identity-schema).     |  
| `properties`      | String    | Neobavezno          | JSON objekt s više svojstava u određenu kategoriju događaja.      | Pogledajte [odjeljak Svojstva](#api-properties-schema).    |
| `level`           | String    | Obvezno          | Razina ozbiljnosti događaja.    | `Informational`, `Warning`, `Error` ili `Critical`.           |
| `uri`             | String    | Neobavezno          | Apsolutni zahtjev URI.    |               |

#### <a name="identity-schema"></a>Shema identiteta

`identity` JSON objekt ima sljedeću strukturu

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Polje                         | Opis                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Dodijeljena uloga korisniku ili aplikaciji. Dodatne informacije potražite u korisničkim [dozvolama](permissions.md).                                     |
| `Authorization.RequiredRoles` | Potrebne uloge za izvođenje operacije. `Admin` uloga je dopuštena za obavljanje svih operacija.                                                    |
| `Claims`                      | Potraživanja korisnika ili aplikacije JSON web token (JWT). Svojstva zahtjeva razlikuju se ovisno o organizaciji i konfiguraciji Azure Active Directory. |

#### <a name="api-properties-schema"></a>Shema svojstava API-ja

[Događaji API-ja](apis.md) imaju sljedeća svojstva.

| Polje                        | Opis                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Uvijek `ApiEvent`, označavajući događaj zapisnika kao API događaj.                                                                 |
| `properties.userAgent`       | Agent preglednika koji šalje zahtjev ili `unknown`.                                                                        |
| `properties.method`          | HTTP metoda:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativni put zahtjeva.                                                                                          |
| `properties.origin`          | URI koji pokazuje odakle dolazi dohvat ili `unknown`.                                                                  |
| `properties.operationStatus` | `Success` za HTTP kod stanja < 400 <br> `ClientError` za HTTP kod stanja < 500 <br> `Error` za HTTP status >= 500 |
| `properties.tenantId`        | ID organizacije                                                                                                        |
| `properties.tenantName`      | Naziv organizacije.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId pozivatelja.                                                                         |
| `properties.instanceId`      | Uvidi kupaca`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Shema događaja tijeka rada

Tijek rada sadrži više koraka. [Unos izvora](data-sources.md) podataka, [objedinjavanje](data-unification.md), [obogaćivanje](enrichment-hub.md) i [izvoz](export-destinations.md) podataka. Svi ti koraci mogu se izvoditi pojedinačno ili orkestrirano sljedećim procesima. 

#### <a name="operation-types"></a>Vrste operacija

| OperationType     | Grupiraj                                     |
| ----------------- | ----------------------------------------- |
| Unos         | [Izvori podataka](data-sources.md)           |
| Usporedba podataka   | [Izvori podataka](data-sources.md)           |
| Mapa               | [Objedinjavanje podataka](data-unification.md)   |
| Usklađivanje             | [Objedinjavanje podataka](data-unification.md)   |
| Spoji             | [Objedinjavanje podataka](data-unification.md)   |
| ProfileStore      | [Profili klijenata](customer-profiles.md) |
| Traži            | [Profili klijenata](customer-profiles.md) |
| Aktivnost          | [Aktivnosti](activities.md)                  |
| AttributeMeasures | [Segmenti i mjere](segments.md)      |
| EntityMeasures    | [Segmenti i mjere](segments.md)      |
| Mjerila          | [Segmenti i mjere](segments.md)      |
| Segmentacija      | [Segmenti i mjere](segments.md)      |
| Obogaćivanje        | [Obogaćivanje](enrichment-hub.md)                                          |
| Intelligence      | [Predviđanja](predictions-overview.md)                                          |
| AiBuilder         | [Predviđanja](predictions-overview.md)                                          |
| Uvidi          | [Predviđanja](predictions-overview.md)                                          |
| Export            | [Izvozi](export-destinations.md)                                          |
| ModelManagement   | [Predviđanja](custom-models.md)                                           |
| Odnos      | [Objedinjavanje podataka](relationships.md)                                           |

#### <a name="field-description"></a>Opis polja

| Polje           | DataType  | Obavezno/neobavezno | Opis                                                                                                                                                   | Primjer                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Podaci vremenske oznake | Obvezno          | Vremenska oznaka događaja (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obvezno          | ResourceId instance koja je emitirala događaj.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obvezno          | Naziv operacije predstavljene ovim događajem. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Za referencu pogledajte [Vrste](#operation-types) operacija. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obvezno          | Kategorija zapisnika događaja. Uvijek `Operational` za događaje tijeka rada                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Obvezno          | Stanje događaja. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dugi      | Neobavezno          | Trajanje operacije u milisekundama.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobavezno          | JSON objekt s više svojstava u određenu kategoriju događaja.                                                                                        | Pogledajte svojstva tijeka rada [pododjeljka](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obvezno          | Razina ozbiljnosti događaja.                                                                                                                                  | `Informational`, `Warning` ili `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Shema svojstava tijeka rada

Događaji tijeka rada imaju sljedeća svojstva.

| Polje              | Workflow | Zadatak | Opis            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jest      | Jest  | Uvijek `WorkflowEvent` označite događaj kao događaj tijeka rada.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jest      | Jest  | Identifikator pokretanja tijeka rada. Svi događaji toka posla i zadataka unutar izvršavanja toka posla imaju isti `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jest      | Jest  | Identifikator operacije potražite u članku [Vrste](#operation-types) operacija.                                                                                                                                                                               |
| `properties.tasksCount`                      | Jest      | No   | Samo tijek rada. Broj zadataka koje tijek rada pokreće.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jest      | No   | Nije obavezno. Samo događaji tijeka rada. ObjectId Azure Active Directory [korisnika](/azure/marketplace/find-tenant-object-id#find-user-object-id) koji je pokrenuo tijek rada, pogledajte i `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jest      | No   | `full` ili `incremental` osvježiti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jest      | No   | `OnDemand` ili `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jest      | No   | `Running` ili `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jest      | Jest  | Uvidi kupaca`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Jest  | - Za OperationType = `Export` identifikator je guid konfiguracije izvoza. <br> - Za OperationType = `Enrichment`, to je guid obogaćivanja <br> - Za OperationType `Measures` i `Segmentation` identifikator je naziv entiteta. |
| `properties.friendlyName`                    | No       | Jest  | Korisničko ime izvoza ili obrađenog entiteta.                                                                                                                                                                                           |
| `properties.error`                           | No       | Jest  | Nije obavezno. Poruka o pogrešci s više detalja.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Jest  | Nije obavezno. Samo za OperationType `Export`. Identificira vrstu izvoza. Dodatne informacije potražite [u pregledu izvoznih odredišta](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Jest  | Nije obavezno. Samo za OperationType `Export`. Sadrži popis konfiguriranih entiteta u izvozu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Jest  | Nije obavezno. Samo za OperationType `Export`. Detaljna poruka za izvoz.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Jest  | Nije obavezno. Samo za OperationType `Segmentation`. Označava ukupan broj članova koje segment ima.                                                                                                                                                    |
