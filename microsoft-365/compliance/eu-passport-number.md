---
title: Número de pasaporte de la UE
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592121"
---
# <a name="eu-passport-number"></a><span data-ttu-id="2e1c4-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="2e1c4-104">EU Passport Number</span></span>

<span data-ttu-id="2e1c4-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="2e1c4-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2e1c4-107">Austria</span><span class="sxs-lookup"><span data-stu-id="2e1c4-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-108">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-108">Format</span></span>

<span data-ttu-id="2e1c4-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-110">Pattern</span></span>

<span data-ttu-id="2e1c4-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="2e1c4-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="2e1c4-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-113">One space (optional)</span></span>
    
- <span data-ttu-id="2e1c4-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-115">Checksum</span></span>

<span data-ttu-id="2e1c4-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2e1c4-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-117">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-117">Definition</span></span>

<span data-ttu-id="2e1c4-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-121">Keywords</span></span>

<span data-ttu-id="2e1c4-122">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-122">| |</span></span>
|<span data-ttu-id="2e1c4-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-124">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-124">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="2e1c4-125">austrian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-126">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="2e1c4-127">reisepass</span></span>  <br/> <span data-ttu-id="2e1c4-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="2e1c4-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="2e1c4-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="2e1c4-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-130">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-130">Format</span></span>

<span data-ttu-id="2e1c4-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-132">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-132">Pattern</span></span>

<span data-ttu-id="2e1c4-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-134">Checksum</span></span>

<span data-ttu-id="2e1c4-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2e1c4-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-136">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-136">Definition</span></span>

<span data-ttu-id="2e1c4-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-140">Keywords</span></span>

<span data-ttu-id="2e1c4-141">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-141">| |</span></span>
|<span data-ttu-id="2e1c4-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-143">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-143">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="2e1c4-144">belgian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-145">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="2e1c4-146">paspoort</span></span>  <br/> <span data-ttu-id="2e1c4-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="2e1c4-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="2e1c4-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="2e1c4-148">reisepass kein</span></span>  <br/> <span data-ttu-id="2e1c4-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="2e1c4-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="2e1c4-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="2e1c4-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-151">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-151">Format</span></span>

<span data-ttu-id="2e1c4-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-153">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-153">Pattern</span></span>

 <span data-ttu-id="2e1c4-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-155">Checksum</span></span>

<span data-ttu-id="2e1c4-156">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-157">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-157">Definition</span></span>

<span data-ttu-id="2e1c4-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-161">Keywords</span></span>

<span data-ttu-id="2e1c4-162">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-162">| |</span></span>
|<span data-ttu-id="2e1c4-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-164">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-164">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="2e1c4-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-166">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="2e1c4-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="2e1c4-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-169">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-169">Format</span></span>

<span data-ttu-id="2e1c4-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-171">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-171">Pattern</span></span>

 <span data-ttu-id="2e1c4-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-173">Checksum</span></span>

<span data-ttu-id="2e1c4-174">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-175">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-175">Definition</span></span>

<span data-ttu-id="2e1c4-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-179">Keywords</span></span>

<span data-ttu-id="2e1c4-180">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-180">| |</span></span>
|<span data-ttu-id="2e1c4-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-182">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-182">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="2e1c4-183">croatian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-184">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="2e1c4-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="2e1c4-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="2e1c4-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-187">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-187">Format</span></span>

<span data-ttu-id="2e1c4-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-189">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-189">Pattern</span></span>

<span data-ttu-id="2e1c4-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-191">Checksum</span></span>

<span data-ttu-id="2e1c4-192">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-193">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-193">Definition</span></span>

<span data-ttu-id="2e1c4-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-197">Keywords</span></span>

<span data-ttu-id="2e1c4-198">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-198">| |</span></span>
|<span data-ttu-id="2e1c4-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-200">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-200">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="2e1c4-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="2e1c4-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-202">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="2e1c4-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="2e1c4-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-205">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-205">Format</span></span>

<span data-ttu-id="2e1c4-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-207">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-207">Pattern</span></span>

<span data-ttu-id="2e1c4-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-209">Checksum</span></span>

<span data-ttu-id="2e1c4-210">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-211">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-211">Definition</span></span>

<span data-ttu-id="2e1c4-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-215">Keywords</span></span>

<span data-ttu-id="2e1c4-216">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-216">| |</span></span>
|<span data-ttu-id="2e1c4-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-218">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-218">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="2e1c4-219">czech passport number</span></span>  <br/> <span data-ttu-id="2e1c4-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-220">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="2e1c4-221">cestovní pas</span></span>  <br/> <span data-ttu-id="2e1c4-222">PAS</span><span class="sxs-lookup"><span data-stu-id="2e1c4-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="2e1c4-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="2e1c4-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-224">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-224">Format</span></span>

<span data-ttu-id="2e1c4-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-226">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-226">Pattern</span></span>

 <span data-ttu-id="2e1c4-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-228">Checksum</span></span>

<span data-ttu-id="2e1c4-229">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-230">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-230">Definition</span></span>

<span data-ttu-id="2e1c4-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-234">Keywords</span></span>

<span data-ttu-id="2e1c4-235">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-235">| |</span></span>
|<span data-ttu-id="2e1c4-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-237">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-237">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="2e1c4-238">danish passport number</span></span>  <br/> <span data-ttu-id="2e1c4-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-239">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-240">PAS</span><span class="sxs-lookup"><span data-stu-id="2e1c4-240">pas</span></span>  <br/> <span data-ttu-id="2e1c4-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="2e1c4-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="2e1c4-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-243">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-243">Format</span></span>

<span data-ttu-id="2e1c4-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-245">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-245">Pattern</span></span>

<span data-ttu-id="2e1c4-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-247">Checksum</span></span>

<span data-ttu-id="2e1c4-248">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-249">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-249">Definition</span></span>

<span data-ttu-id="2e1c4-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-253">Keywords</span></span>

<span data-ttu-id="2e1c4-254">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-254">| |</span></span>
|<span data-ttu-id="2e1c4-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-256">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-256">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="2e1c4-257">estonian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-258">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="2e1c4-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="2e1c4-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-260">Finland</span></span>

<span data-ttu-id="2e1c4-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e1c4-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="2e1c4-262">Francia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-262">France</span></span>

<span data-ttu-id="2e1c4-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e1c4-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="2e1c4-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="2e1c4-264">Germany</span></span>

<span data-ttu-id="2e1c4-265">Para obtener más información, consulte la sección "número de pasaporte en alemán" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e1c4-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="2e1c4-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-267">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-267">Format</span></span>

<span data-ttu-id="2e1c4-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-269">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-269">Pattern</span></span>

<span data-ttu-id="2e1c4-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-271">Checksum</span></span>

<span data-ttu-id="2e1c4-272">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-273">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-273">Definition</span></span>

<span data-ttu-id="2e1c4-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-277">Keywords</span></span>

<span data-ttu-id="2e1c4-278">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-278">| |</span></span>
|<span data-ttu-id="2e1c4-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-280">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-280">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="2e1c4-281">greek passport number</span></span>  <br/> <span data-ttu-id="2e1c4-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-282">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="2e1c4-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="2e1c4-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="2e1c4-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-285">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-285">Format</span></span>

<span data-ttu-id="2e1c4-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-287">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-287">Pattern</span></span>

<span data-ttu-id="2e1c4-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-289">Checksum</span></span>

<span data-ttu-id="2e1c4-290">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-291">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-291">Definition</span></span>

<span data-ttu-id="2e1c4-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-295">Keywords</span></span>

<span data-ttu-id="2e1c4-296">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-296">| |</span></span>
|<span data-ttu-id="2e1c4-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-298">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-298">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="2e1c4-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-300">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="2e1c4-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="2e1c4-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="2e1c4-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-303">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-303">Format</span></span>

<span data-ttu-id="2e1c4-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-305">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-305">Pattern</span></span>

<span data-ttu-id="2e1c4-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="2e1c4-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="2e1c4-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-309">Checksum</span></span>

<span data-ttu-id="2e1c4-310">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-311">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-311">Definition</span></span>

<span data-ttu-id="2e1c4-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-315">Keywords</span></span>

<span data-ttu-id="2e1c4-316">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-316">| |</span></span>
|<span data-ttu-id="2e1c4-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-318">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-318">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="2e1c4-319">irish passport number</span></span>  <br/> <span data-ttu-id="2e1c4-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-320">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-321">PAS</span><span class="sxs-lookup"><span data-stu-id="2e1c4-321">pas</span></span>  <br/> <span data-ttu-id="2e1c4-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="2e1c4-322">passport</span></span>  <br/> <span data-ttu-id="2e1c4-323">passeport</span><span class="sxs-lookup"><span data-stu-id="2e1c4-323">passeport</span></span>  <br/> <span data-ttu-id="2e1c4-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="2e1c4-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="2e1c4-325">Italia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-326">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-326">Format</span></span>

<span data-ttu-id="2e1c4-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-328">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-328">Pattern</span></span>

<span data-ttu-id="2e1c4-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="2e1c4-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="2e1c4-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-332">Checksum</span></span>

<span data-ttu-id="2e1c4-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2e1c4-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-334">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-334">Definition</span></span>

<span data-ttu-id="2e1c4-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-338">Keywords</span></span>

<span data-ttu-id="2e1c4-339">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-339">| |</span></span>
|<span data-ttu-id="2e1c4-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="2e1c4-341">italian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="2e1c4-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="2e1c4-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="2e1c4-343">passaporto</span></span>  <br/> <span data-ttu-id="2e1c4-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="2e1c4-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="2e1c4-345">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-345">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="2e1c4-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="2e1c4-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="2e1c4-347">passaporto numero</span></span>  <br/> <span data-ttu-id="2e1c4-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="2e1c4-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="2e1c4-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="2e1c4-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="2e1c4-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-351">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-351">Format</span></span>

<span data-ttu-id="2e1c4-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-353">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-353">Pattern</span></span>

<span data-ttu-id="2e1c4-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="2e1c4-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="2e1c4-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-357">Checksum</span></span>

<span data-ttu-id="2e1c4-358">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-359">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-359">Definition</span></span>

<span data-ttu-id="2e1c4-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-363">Keywords</span></span>

<span data-ttu-id="2e1c4-364">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-364">| |</span></span>
|<span data-ttu-id="2e1c4-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-366">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-366">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="2e1c4-367">latvian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-368">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="2e1c4-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="2e1c4-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="2e1c4-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-371">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-371">Format</span></span>

<span data-ttu-id="2e1c4-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-373">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-373">Pattern</span></span>

<span data-ttu-id="2e1c4-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-375">Checksum</span></span>

<span data-ttu-id="2e1c4-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2e1c4-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-377">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-377">Definition</span></span>

<span data-ttu-id="2e1c4-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-381">Keywords</span></span>

<span data-ttu-id="2e1c4-382">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-382">| |</span></span>
|<span data-ttu-id="2e1c4-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-384">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-384">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="2e1c4-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-386">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="2e1c4-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="2e1c4-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="2e1c4-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-389">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-389">Format</span></span>

<span data-ttu-id="2e1c4-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-391">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-391">Pattern</span></span>

<span data-ttu-id="2e1c4-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-393">Checksum</span></span>

<span data-ttu-id="2e1c4-394">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-395">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-395">Definition</span></span>

<span data-ttu-id="2e1c4-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-399">Keywords</span></span>

<span data-ttu-id="2e1c4-400">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-400">| |</span></span>
|<span data-ttu-id="2e1c4-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-402">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-402">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="2e1c4-403">latvian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-404">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="2e1c4-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="2e1c4-406">Malta</span><span class="sxs-lookup"><span data-stu-id="2e1c4-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-407">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-407">Format</span></span>

<span data-ttu-id="2e1c4-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-409">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-409">Pattern</span></span>

 <span data-ttu-id="2e1c4-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-411">Checksum</span></span>

<span data-ttu-id="2e1c4-412">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-413">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-413">Definition</span></span>

<span data-ttu-id="2e1c4-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-417">Keywords</span></span>

<span data-ttu-id="2e1c4-418">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-418">| |</span></span>
|<span data-ttu-id="2e1c4-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-420">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-420">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="2e1c4-421">maltese passport number</span></span>  <br/> <span data-ttu-id="2e1c4-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-422">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="2e1c4-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="2e1c4-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-425">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-425">Format</span></span>

<span data-ttu-id="2e1c4-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-427">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-427">Pattern</span></span>

<span data-ttu-id="2e1c4-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-429">Checksum</span></span>

<span data-ttu-id="2e1c4-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2e1c4-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-431">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-431">Definition</span></span>

<span data-ttu-id="2e1c4-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-435">Keywords</span></span>

<span data-ttu-id="2e1c4-436">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-436">| |</span></span>
|<span data-ttu-id="2e1c4-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="2e1c4-438">dutch passport number</span></span>  <br/> <span data-ttu-id="2e1c4-439">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-439">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="2e1c4-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="2e1c4-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="2e1c4-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="2e1c4-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="2e1c4-442">paspoort</span></span>  <br/> <span data-ttu-id="2e1c4-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="2e1c4-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="2e1c4-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="2e1c4-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="2e1c4-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-445">Poland</span></span>

<span data-ttu-id="2e1c4-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e1c4-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2e1c4-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="2e1c4-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-448">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-448">Format</span></span>

<span data-ttu-id="2e1c4-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-450">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-450">Pattern</span></span>

<span data-ttu-id="2e1c4-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="2e1c4-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="2e1c4-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-454">Checksum</span></span>

<span data-ttu-id="2e1c4-455">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-456">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-456">Definition</span></span>

<span data-ttu-id="2e1c4-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-460">Keywords</span></span>

<span data-ttu-id="2e1c4-461">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-461">| |</span></span>
|<span data-ttu-id="2e1c4-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-463">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-463">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="2e1c4-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="2e1c4-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-465">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="2e1c4-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="2e1c4-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-468">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-468">Format</span></span>

<span data-ttu-id="2e1c4-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-470">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-470">Pattern</span></span>

<span data-ttu-id="2e1c4-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-472">Checksum</span></span>

<span data-ttu-id="2e1c4-473">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-474">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-474">Definition</span></span>

<span data-ttu-id="2e1c4-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-478">Keywords</span></span>

<span data-ttu-id="2e1c4-479">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-479">| |</span></span>
|<span data-ttu-id="2e1c4-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-481">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-481">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="2e1c4-482">romanian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-483">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="2e1c4-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="2e1c4-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-486">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-486">Format</span></span>

<span data-ttu-id="2e1c4-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-488">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-488">Pattern</span></span>

<span data-ttu-id="2e1c4-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e1c4-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-490">Checksum</span></span>

<span data-ttu-id="2e1c4-491">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-492">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-492">Definition</span></span>

<span data-ttu-id="2e1c4-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-496">Keywords</span></span>

<span data-ttu-id="2e1c4-497">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-497">| |</span></span>
|<span data-ttu-id="2e1c4-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-499">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-499">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="2e1c4-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-501">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="2e1c4-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="2e1c4-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-504">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-504">Format</span></span>

<span data-ttu-id="2e1c4-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-506">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-506">Pattern</span></span>

<span data-ttu-id="2e1c4-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="2e1c4-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="2e1c4-508">The letter "P"</span></span>
    
- <span data-ttu-id="2e1c4-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="2e1c4-509">One uppercase letter</span></span>
    
- <span data-ttu-id="2e1c4-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-511">Checksum</span></span>

<span data-ttu-id="2e1c4-512">No</span><span class="sxs-lookup"><span data-stu-id="2e1c4-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-513">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-513">Definition</span></span>

<span data-ttu-id="2e1c4-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-517">Keywords</span></span>

<span data-ttu-id="2e1c4-518">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-518">| |</span></span>
|<span data-ttu-id="2e1c4-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-520">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-520">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="2e1c4-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="2e1c4-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-522">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="2e1c4-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="2e1c4-524">España</span><span class="sxs-lookup"><span data-stu-id="2e1c4-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2e1c4-525">Formato</span><span class="sxs-lookup"><span data-stu-id="2e1c4-525">Format</span></span>

<span data-ttu-id="2e1c4-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e1c4-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e1c4-527">Pattern</span><span class="sxs-lookup"><span data-stu-id="2e1c4-527">Pattern</span></span>

<span data-ttu-id="2e1c4-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="2e1c4-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="2e1c4-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="2e1c4-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="2e1c4-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="2e1c4-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="2e1c4-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e1c4-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2e1c4-532">Checksum</span></span>

<span data-ttu-id="2e1c4-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2e1c4-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e1c4-534">Definición</span><span class="sxs-lookup"><span data-stu-id="2e1c4-534">Definition</span></span>

<span data-ttu-id="2e1c4-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e1c4-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e1c4-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e1c4-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="2e1c4-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e1c4-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2e1c4-538">Keywords</span></span>

<span data-ttu-id="2e1c4-539">| |</span><span class="sxs-lookup"><span data-stu-id="2e1c4-539">| |</span></span>
|<span data-ttu-id="2e1c4-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2e1c4-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2e1c4-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="2e1c4-541">passport</span></span>  <br/> <span data-ttu-id="2e1c4-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="2e1c4-542">spain passport</span></span>  <br/> <span data-ttu-id="2e1c4-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="2e1c4-543">passport book</span></span>  <br/> <span data-ttu-id="2e1c4-544">passport number</span><span class="sxs-lookup"><span data-stu-id="2e1c4-544">passport number</span></span>  <br/> <span data-ttu-id="2e1c4-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-545">passport no</span></span>  <br/> <span data-ttu-id="2e1c4-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="2e1c4-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-547">número pasaporte</span></span>  <br/> <span data-ttu-id="2e1c4-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="2e1c4-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="2e1c4-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="2e1c4-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="2e1c4-550">Sweden</span></span>

<span data-ttu-id="2e1c4-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e1c4-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="2e1c4-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="2e1c4-552">UK</span></span>

<span data-ttu-id="2e1c4-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="2e1c4-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="2e1c4-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e1c4-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e1c4-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e1c4-555">See also</span></span>

[<span data-ttu-id="2e1c4-556">Información que buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="2e1c4-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

