---
title: Pronalaženje sličnih klijenata pomoću AI
description: Pronađite slične segmente klijenata koristeći se umjetnom inteligencijom.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405326"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="4c0d3-103">Slični klijenti (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="4c0d3-103">Similar Customers (preview)</span></span>

<span data-ttu-id="4c0d3-104">Ova značajka omogućuje vam pronaći klijente u svojoj bazi klijenata koristeći se umjetnom inteligencijom.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="4c0d3-105">Za upotrebu ove značajke morate imati stvoren barem jedan segment.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="4c0d3-106">Proširenje kriterija postojećeg segmenta pomaže u pronalaženju klijenata koji su slični tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="4c0d3-107">*Nalaženje sličnih klijenata* koristi se automatiziranim sredstvima za procjenu podataka i daje predviđanja na temelju tih podataka, pa se stoga može koristiti kao metoda profiliranja, jer je taj pojam definiran Općom uredbom o zaštiti podataka („GDPR”).</span><span class="sxs-lookup"><span data-stu-id="4c0d3-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="4c0d3-108">Klijentova upotreba ove značajke za obradu podataka može biti podložna OUZP-u ili drugim zakonima ili propisima.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="4c0d3-109">Odgovorni ste osigurati da je da vaše korištenje Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="4c0d3-110">Nalaženje sličnih klijenata</span><span class="sxs-lookup"><span data-stu-id="4c0d3-110">Finding similar customers</span></span>

1. <span data-ttu-id="4c0d3-111">U uvidima u ciljnu skupinu idite na **Segmenti** i odaberite segment na kojem želite temeljiti svoj novi segment.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="4c0d3-112">To je vaš *izvorni segment*.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="4c0d3-113">Na akcijskoj traci odaberite **Nalaženje sličnih klijenata**.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="4c0d3-114">Pregledajte predloženi naziv za svoj novi segment i promijenite ga ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="4c0d3-115">Pregledajte polja koja definiraju vaš novi segment.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="4c0d3-116">Ova polja određuju osnovu na kojoj će sustav pokušati pronaći klijente slične vašem izvornom segmentu.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="4c0d3-117">Sustav će prema zadanim postavkama odabrati preporučena polja.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="4c0d3-118">Polja koja mogu značajno smanjiti učinak modela automatski se isključuju:</span><span class="sxs-lookup"><span data-stu-id="4c0d3-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="4c0d3-119">Polja sa sljedećim vrstama podataka: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="4c0d3-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="4c0d3-120">Polja s kardinalnošću (broj elemenata u polju) manjom od 2 ili većom od 30</span><span class="sxs-lookup"><span data-stu-id="4c0d3-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="4c0d3-121">Odaberite želite li da u novom segmentu budu uključeni **Svi klijenti** ili samo klijenti za **Specifični postojeći segment**.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="4c0d3-122">Isključite klijente iz svog izvornog segmenta odabirom potvrdnog okvira **Isključi sve iz izvornog segmenta**.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="4c0d3-123">Sustav prema zadanim postavkama predlaže da se u izlaz uključi samo 20% ciljne publike.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="4c0d3-124">Uredite ovaj prag ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-124">Edit this threshold as needed.</span></span> <span data-ttu-id="4c0d3-125">Povećanje praga smanjit će preciznost.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="4c0d3-126">Odaberite **Pokreni** pri dnu stranice kako biste pokrenuli zadatak binarne klasifikacije (metoda strojnog učenja) koji analizira skup podataka.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="4c0d3-127">Prikaz sličnog segmenta</span><span class="sxs-lookup"><span data-stu-id="4c0d3-127">View the similar segment</span></span>

<span data-ttu-id="4c0d3-128">Nakon obrade sličnog segmenta, novi ćete segment pronaći na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c0d3-129">![Segment sa sličnim klijentima](media/expanded-segment.png "Segment sa sličnim klijentima")</span><span class="sxs-lookup"><span data-stu-id="4c0d3-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="4c0d3-130">Odaberite **Prikaz** na akcijskoj traci kako bi se otvorile pojedinosti segmenta.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="4c0d3-131">Ovaj prikaz sadrži informacije o raspodjeli rezultata po različitim [ocjenama sličnosti](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="4c0d3-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="4c0d3-132">Vrijednosti ocjena sličnosti također ćete pronaći u **Pretpregled članova segmenta**.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="4c0d3-133">Upotrijebite izlaz sličnog segmenta</span><span class="sxs-lookup"><span data-stu-id="4c0d3-133">Use the output of a similar segment</span></span>

<span data-ttu-id="4c0d3-134">Možete [raditi s izlazom sličnog segmenta](segments.md) kao kod drugih segmenata.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="4c0d3-135">Na primjer, izvezite segment ili izradite mjeru.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="4c0d3-136">Osvježavanje i uređivanje sličnog segmenta</span><span class="sxs-lookup"><span data-stu-id="4c0d3-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="4c0d3-137">Da biste osvježili sličan segment, odaberite ga na stranici **Segmenti** i odaberite **Osvježi** u akcijskoj traci.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="4c0d3-138">Uređivanjem sličnog segmenta vaši će se podaci ponovno obraditi.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="4c0d3-139">Prethodno stvoreni segment ažurira se osvježenim podacima.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="4c0d3-140">Da biste uredili sličan segment, odaberite ga na stranici **Segmenti** i odaberite **Uredi** u akcijskoj traci.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="4c0d3-141">Primijenite promjene i odaberite **Pokreni** da biste započeli obradu.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="4c0d3-142">Brisanje sličnog segmenta</span><span class="sxs-lookup"><span data-stu-id="4c0d3-142">Delete a similar segment</span></span>

<span data-ttu-id="4c0d3-143">Odaberite segment na stranici **Segmenti** i odaberite **Izbriši** u akcijskoj traci.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="4c0d3-144">Zatim potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="4c0d3-145">O ocjenama sličnosti</span><span class="sxs-lookup"><span data-stu-id="4c0d3-145">About similarity scores</span></span>

<span data-ttu-id="4c0d3-146">Model strojnog učenja binarne klasifikacije dodjeljuje ocjene klijentima u sličnom segmentu.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="4c0d3-147">Ocjena se temelji na sličnosti s klijentima u izvornom segmentu.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="4c0d3-148">Ocjene sličnosti manje od 0,55 su klijenti koje je sustav klasificirao kao *neslične* klijentima u izvornom segmentu</span><span class="sxs-lookup"><span data-stu-id="4c0d3-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="4c0d3-149">Ocjene sličnosti između 0,55 i 0,7 klasificiraju se kao *donekle slični*</span><span class="sxs-lookup"><span data-stu-id="4c0d3-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="4c0d3-150">Ocjene sličnosti između 0,7 i 0,85 klasificiraju se kao *slični*</span><span class="sxs-lookup"><span data-stu-id="4c0d3-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="4c0d3-151">Ocjene sličnosti između 0,85 i 1 klijenti su koje je sustav klasificirao kao *vrlo slične*</span><span class="sxs-lookup"><span data-stu-id="4c0d3-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="4c0d3-152">Klijenti s ocjenama sličnosti manjim od 0,4 ne uvrštavaju se u izlaz modela.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="4c0d3-153">Sustav ih ne smatra dovoljno sličnim izvornom segmentu.</span><span class="sxs-lookup"><span data-stu-id="4c0d3-153">The system doesn't consider them similar enough to the source segment.</span></span>
