---
title: Número de pasaporte de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092472"
---
# <a name="eu-passport-number"></a><span data-ttu-id="1061e-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="1061e-104">EU Passport Number</span></span>

<span data-ttu-id="1061e-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="1061e-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="1061e-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="1061e-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1061e-107">Austria</span><span class="sxs-lookup"><span data-stu-id="1061e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1061e-108">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-108">Format</span></span>

<span data-ttu-id="1061e-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-110">Pattern</span></span>

<span data-ttu-id="1061e-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="1061e-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="1061e-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1061e-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="1061e-113">One space (optional)</span></span>
    
- <span data-ttu-id="1061e-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-115">Checksum</span></span>

<span data-ttu-id="1061e-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1061e-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-117">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-117">Definition</span></span>

<span data-ttu-id="1061e-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-121">Keywords</span></span>

<span data-ttu-id="1061e-122">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-122"></span></span>
|<span data-ttu-id="1061e-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-124">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-124">passport number</span></span>  <br/> <span data-ttu-id="1061e-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="1061e-125">austrian passport number</span></span>  <br/> <span data-ttu-id="1061e-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-126">passport no</span></span>  <br/> <span data-ttu-id="1061e-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="1061e-127">reisepass</span></span>  <br/> <span data-ttu-id="1061e-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="1061e-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="1061e-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="1061e-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1061e-130">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-130">Format</span></span>

<span data-ttu-id="1061e-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-132">Pattern</span></span>

<span data-ttu-id="1061e-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-134">Checksum</span></span>

<span data-ttu-id="1061e-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1061e-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-136">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-136">Definition</span></span>

<span data-ttu-id="1061e-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-140">Keywords</span></span>

<span data-ttu-id="1061e-141">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-141"></span></span>
|<span data-ttu-id="1061e-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-143">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-143">passport number</span></span>  <br/> <span data-ttu-id="1061e-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="1061e-144">belgian passport number</span></span>  <br/> <span data-ttu-id="1061e-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-145">passport no</span></span>  <br/> <span data-ttu-id="1061e-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="1061e-146">paspoort</span></span>  <br/> <span data-ttu-id="1061e-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1061e-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="1061e-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="1061e-148">reisepass kein</span></span>  <br/> <span data-ttu-id="1061e-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="1061e-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="1061e-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="1061e-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="1061e-151">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-151">Format</span></span>

<span data-ttu-id="1061e-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-153">Pattern</span></span>

 <span data-ttu-id="1061e-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1061e-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-155">Checksum</span></span>

<span data-ttu-id="1061e-156">No</span><span class="sxs-lookup"><span data-stu-id="1061e-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-157">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-157">Definition</span></span>

<span data-ttu-id="1061e-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-161">Keywords</span></span>

<span data-ttu-id="1061e-162">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-162"></span></span>
|<span data-ttu-id="1061e-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-164">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-164">passport number</span></span>  <br/> <span data-ttu-id="1061e-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="1061e-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="1061e-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-166">passport no</span></span>  <br/> <span data-ttu-id="1061e-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="1061e-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="1061e-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="1061e-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1061e-169">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-169">Format</span></span>

<span data-ttu-id="1061e-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-171">Pattern</span></span>

 <span data-ttu-id="1061e-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1061e-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-173">Checksum</span></span>

<span data-ttu-id="1061e-174">No</span><span class="sxs-lookup"><span data-stu-id="1061e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-175">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-175">Definition</span></span>

<span data-ttu-id="1061e-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-179">Keywords</span></span>

<span data-ttu-id="1061e-180">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-180"></span></span>
|<span data-ttu-id="1061e-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-182">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-182">passport number</span></span>  <br/> <span data-ttu-id="1061e-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="1061e-183">croatian passport number</span></span>  <br/> <span data-ttu-id="1061e-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-184">passport no</span></span>  <br/> <span data-ttu-id="1061e-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="1061e-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="1061e-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="1061e-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="1061e-187">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-187">Format</span></span>

<span data-ttu-id="1061e-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-189">Pattern</span></span>

<span data-ttu-id="1061e-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-191">Checksum</span></span>

<span data-ttu-id="1061e-192">No</span><span class="sxs-lookup"><span data-stu-id="1061e-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-193">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-193">Definition</span></span>

<span data-ttu-id="1061e-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-197">Keywords</span></span>

<span data-ttu-id="1061e-198">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-198"></span></span>
|<span data-ttu-id="1061e-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-200">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-200">passport number</span></span>  <br/> <span data-ttu-id="1061e-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="1061e-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="1061e-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-202">passport no</span></span>  <br/> <span data-ttu-id="1061e-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="1061e-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="1061e-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="1061e-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1061e-205">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-205">Format</span></span>

<span data-ttu-id="1061e-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-207">Pattern</span></span>

<span data-ttu-id="1061e-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-209">Checksum</span></span>

<span data-ttu-id="1061e-210">No</span><span class="sxs-lookup"><span data-stu-id="1061e-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-211">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-211">Definition</span></span>

<span data-ttu-id="1061e-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-215">Keywords</span></span>

<span data-ttu-id="1061e-216">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-216"></span></span>
|<span data-ttu-id="1061e-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-218">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-218">passport number</span></span>  <br/> <span data-ttu-id="1061e-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="1061e-219">czech passport number</span></span>  <br/> <span data-ttu-id="1061e-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-220">passport no</span></span>  <br/> <span data-ttu-id="1061e-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="1061e-221">cestovní pas</span></span>  <br/> <span data-ttu-id="1061e-222">PAS</span><span class="sxs-lookup"><span data-stu-id="1061e-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="1061e-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="1061e-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1061e-224">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-224">Format</span></span>

<span data-ttu-id="1061e-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-226">Pattern</span></span>

 <span data-ttu-id="1061e-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1061e-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-228">Checksum</span></span>

<span data-ttu-id="1061e-229">No</span><span class="sxs-lookup"><span data-stu-id="1061e-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-230">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-230">Definition</span></span>

<span data-ttu-id="1061e-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-234">Keywords</span></span>

<span data-ttu-id="1061e-235">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-235"></span></span>
|<span data-ttu-id="1061e-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-237">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-237">passport number</span></span>  <br/> <span data-ttu-id="1061e-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="1061e-238">danish passport number</span></span>  <br/> <span data-ttu-id="1061e-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-239">passport no</span></span>  <br/> <span data-ttu-id="1061e-240">PAS</span><span class="sxs-lookup"><span data-stu-id="1061e-240">pas</span></span>  <br/> <span data-ttu-id="1061e-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="1061e-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="1061e-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="1061e-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="1061e-243">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-243">Format</span></span>

<span data-ttu-id="1061e-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-245">Pattern</span></span>

<span data-ttu-id="1061e-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-247">Checksum</span></span>

<span data-ttu-id="1061e-248">No</span><span class="sxs-lookup"><span data-stu-id="1061e-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-249">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-249">Definition</span></span>

<span data-ttu-id="1061e-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-253">Keywords</span></span>

<span data-ttu-id="1061e-254">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-254"></span></span>
|<span data-ttu-id="1061e-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-256">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-256">passport number</span></span>  <br/> <span data-ttu-id="1061e-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="1061e-257">estonian passport number</span></span>  <br/> <span data-ttu-id="1061e-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-258">passport no</span></span>  <br/> <span data-ttu-id="1061e-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="1061e-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="1061e-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="1061e-260">Finland</span></span>

<span data-ttu-id="1061e-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1061e-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="1061e-262">Francia</span><span class="sxs-lookup"><span data-stu-id="1061e-262">France</span></span>

<span data-ttu-id="1061e-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1061e-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1061e-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="1061e-264">Germany</span></span>

<span data-ttu-id="1061e-265">Para obtener más información, consulte la sección "número de pasaporte de Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1061e-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1061e-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="1061e-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="1061e-267">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-267">Format</span></span>

<span data-ttu-id="1061e-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-269">Pattern</span></span>

<span data-ttu-id="1061e-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-271">Checksum</span></span>

<span data-ttu-id="1061e-272">No</span><span class="sxs-lookup"><span data-stu-id="1061e-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-273">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-273">Definition</span></span>

<span data-ttu-id="1061e-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-277">Keywords</span></span>

<span data-ttu-id="1061e-278">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-278"></span></span>
|<span data-ttu-id="1061e-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-280">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-280">passport number</span></span>  <br/> <span data-ttu-id="1061e-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="1061e-281">greek passport number</span></span>  <br/> <span data-ttu-id="1061e-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-282">passport no</span></span>  <br/> <span data-ttu-id="1061e-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="1061e-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="1061e-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="1061e-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1061e-285">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-285">Format</span></span>

<span data-ttu-id="1061e-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-287">Pattern</span></span>

<span data-ttu-id="1061e-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-289">Checksum</span></span>

<span data-ttu-id="1061e-290">No</span><span class="sxs-lookup"><span data-stu-id="1061e-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-291">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-291">Definition</span></span>

<span data-ttu-id="1061e-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-295">Keywords</span></span>

<span data-ttu-id="1061e-296">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-296"></span></span>
|<span data-ttu-id="1061e-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-298">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-298">passport number</span></span>  <br/> <span data-ttu-id="1061e-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="1061e-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="1061e-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-300">passport no</span></span>  <br/> <span data-ttu-id="1061e-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="1061e-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="1061e-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="1061e-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="1061e-303">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-303">Format</span></span>

<span data-ttu-id="1061e-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-305">Pattern</span></span>

<span data-ttu-id="1061e-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="1061e-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1061e-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1061e-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-309">Checksum</span></span>

<span data-ttu-id="1061e-310">No</span><span class="sxs-lookup"><span data-stu-id="1061e-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-311">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-311">Definition</span></span>

<span data-ttu-id="1061e-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-315">Keywords</span></span>

<span data-ttu-id="1061e-316">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-316"></span></span>
|<span data-ttu-id="1061e-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-318">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-318">passport number</span></span>  <br/> <span data-ttu-id="1061e-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="1061e-319">irish passport number</span></span>  <br/> <span data-ttu-id="1061e-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-320">passport no</span></span>  <br/> <span data-ttu-id="1061e-321">PAS</span><span class="sxs-lookup"><span data-stu-id="1061e-321">pas</span></span>  <br/> <span data-ttu-id="1061e-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="1061e-322">passport</span></span>  <br/> <span data-ttu-id="1061e-323">passeport</span><span class="sxs-lookup"><span data-stu-id="1061e-323">passeport</span></span>  <br/> <span data-ttu-id="1061e-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="1061e-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="1061e-325">Italia</span><span class="sxs-lookup"><span data-stu-id="1061e-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="1061e-326">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-326">Format</span></span>

<span data-ttu-id="1061e-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-328">Pattern</span></span>

<span data-ttu-id="1061e-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="1061e-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1061e-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1061e-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-332">Checksum</span></span>

<span data-ttu-id="1061e-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1061e-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-334">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-334">Definition</span></span>

<span data-ttu-id="1061e-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-338">Keywords</span></span>

<span data-ttu-id="1061e-339">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-339"></span></span>
|<span data-ttu-id="1061e-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="1061e-341">italian passport number</span></span>  <br/> <span data-ttu-id="1061e-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="1061e-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="1061e-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="1061e-343">passaporto</span></span>  <br/> <span data-ttu-id="1061e-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="1061e-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="1061e-345">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-345">passport number</span></span>  <br/> <span data-ttu-id="1061e-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1061e-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="1061e-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1061e-347">passaporto numero</span></span>  <br/> <span data-ttu-id="1061e-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="1061e-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="1061e-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="1061e-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="1061e-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="1061e-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="1061e-351">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-351">Format</span></span>

<span data-ttu-id="1061e-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-353">Pattern</span></span>

<span data-ttu-id="1061e-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="1061e-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1061e-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1061e-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-357">Checksum</span></span>

<span data-ttu-id="1061e-358">No</span><span class="sxs-lookup"><span data-stu-id="1061e-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-359">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-359">Definition</span></span>

<span data-ttu-id="1061e-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-363">Keywords</span></span>

<span data-ttu-id="1061e-364">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-364"></span></span>
|<span data-ttu-id="1061e-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-366">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-366">passport number</span></span>  <br/> <span data-ttu-id="1061e-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="1061e-367">latvian passport number</span></span>  <br/> <span data-ttu-id="1061e-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-368">passport no</span></span>  <br/> <span data-ttu-id="1061e-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="1061e-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="1061e-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="1061e-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="1061e-371">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-371">Format</span></span>

<span data-ttu-id="1061e-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-373">Pattern</span></span>

<span data-ttu-id="1061e-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-375">Checksum</span></span>

<span data-ttu-id="1061e-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1061e-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-377">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-377">Definition</span></span>

<span data-ttu-id="1061e-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-381">Keywords</span></span>

<span data-ttu-id="1061e-382">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-382"></span></span>
|<span data-ttu-id="1061e-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-384">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-384">passport number</span></span>  <br/> <span data-ttu-id="1061e-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="1061e-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="1061e-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-386">passport no</span></span>  <br/> <span data-ttu-id="1061e-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="1061e-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="1061e-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="1061e-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="1061e-389">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-389">Format</span></span>

<span data-ttu-id="1061e-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-391">Pattern</span></span>

<span data-ttu-id="1061e-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-393">Checksum</span></span>

<span data-ttu-id="1061e-394">No</span><span class="sxs-lookup"><span data-stu-id="1061e-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-395">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-395">Definition</span></span>

<span data-ttu-id="1061e-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-399">Keywords</span></span>

<span data-ttu-id="1061e-400">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-400"></span></span>
|<span data-ttu-id="1061e-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-402">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-402">passport number</span></span>  <br/> <span data-ttu-id="1061e-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="1061e-403">latvian passport number</span></span>  <br/> <span data-ttu-id="1061e-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-404">passport no</span></span>  <br/> <span data-ttu-id="1061e-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="1061e-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="1061e-406">Malta</span><span class="sxs-lookup"><span data-stu-id="1061e-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="1061e-407">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-407">Format</span></span>

<span data-ttu-id="1061e-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-409">Pattern</span></span>

 <span data-ttu-id="1061e-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1061e-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-411">Checksum</span></span>

<span data-ttu-id="1061e-412">No</span><span class="sxs-lookup"><span data-stu-id="1061e-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-413">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-413">Definition</span></span>

<span data-ttu-id="1061e-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-417">Keywords</span></span>

<span data-ttu-id="1061e-418">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-418"></span></span>
|<span data-ttu-id="1061e-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-420">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-420">passport number</span></span>  <br/> <span data-ttu-id="1061e-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="1061e-421">maltese passport number</span></span>  <br/> <span data-ttu-id="1061e-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-422">passport no</span></span>  <br/> <span data-ttu-id="1061e-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="1061e-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="1061e-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="1061e-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="1061e-425">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-425">Format</span></span>

<span data-ttu-id="1061e-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-427">Pattern</span></span>

<span data-ttu-id="1061e-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-429">Checksum</span></span>

<span data-ttu-id="1061e-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1061e-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-431">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-431">Definition</span></span>

<span data-ttu-id="1061e-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-435">Keywords</span></span>

<span data-ttu-id="1061e-436">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-436"></span></span>
|<span data-ttu-id="1061e-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="1061e-438">dutch passport number</span></span>  <br/> <span data-ttu-id="1061e-439">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-439">passport number</span></span>  <br/> <span data-ttu-id="1061e-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="1061e-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="1061e-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="1061e-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="1061e-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="1061e-442">paspoort</span></span>  <br/> <span data-ttu-id="1061e-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1061e-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="1061e-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1061e-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="1061e-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="1061e-445">Poland</span></span>

<span data-ttu-id="1061e-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1061e-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1061e-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="1061e-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="1061e-448">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-448">Format</span></span>

<span data-ttu-id="1061e-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-450">Pattern</span></span>

<span data-ttu-id="1061e-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="1061e-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="1061e-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1061e-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1061e-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-454">Checksum</span></span>

<span data-ttu-id="1061e-455">No</span><span class="sxs-lookup"><span data-stu-id="1061e-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-456">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-456">Definition</span></span>

<span data-ttu-id="1061e-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-460">Keywords</span></span>

<span data-ttu-id="1061e-461">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-461"></span></span>
|<span data-ttu-id="1061e-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-463">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-463">passport number</span></span>  <br/> <span data-ttu-id="1061e-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="1061e-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="1061e-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-465">passport no</span></span>  <br/> <span data-ttu-id="1061e-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="1061e-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="1061e-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="1061e-468">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-468">Format</span></span>

<span data-ttu-id="1061e-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-470">Pattern</span></span>

<span data-ttu-id="1061e-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-472">Checksum</span></span>

<span data-ttu-id="1061e-473">No</span><span class="sxs-lookup"><span data-stu-id="1061e-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-474">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-474">Definition</span></span>

<span data-ttu-id="1061e-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-478">Keywords</span></span>

<span data-ttu-id="1061e-479">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-479"></span></span>
|<span data-ttu-id="1061e-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-481">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-481">passport number</span></span>  <br/> <span data-ttu-id="1061e-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="1061e-482">romanian passport number</span></span>  <br/> <span data-ttu-id="1061e-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-483">passport no</span></span>  <br/> <span data-ttu-id="1061e-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="1061e-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="1061e-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="1061e-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="1061e-486">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-486">Format</span></span>

<span data-ttu-id="1061e-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-488">Pattern</span></span>

<span data-ttu-id="1061e-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1061e-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-490">Checksum</span></span>

<span data-ttu-id="1061e-491">No</span><span class="sxs-lookup"><span data-stu-id="1061e-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-492">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-492">Definition</span></span>

<span data-ttu-id="1061e-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-496">Keywords</span></span>

<span data-ttu-id="1061e-497">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-497"></span></span>
|<span data-ttu-id="1061e-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-499">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-499">passport number</span></span>  <br/> <span data-ttu-id="1061e-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="1061e-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="1061e-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-501">passport no</span></span>  <br/> <span data-ttu-id="1061e-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="1061e-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="1061e-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="1061e-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="1061e-504">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-504">Format</span></span>

<span data-ttu-id="1061e-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-506">Pattern</span></span>

<span data-ttu-id="1061e-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="1061e-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="1061e-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="1061e-508">The letter "P"</span></span>
    
- <span data-ttu-id="1061e-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="1061e-509">One uppercase letter</span></span>
    
- <span data-ttu-id="1061e-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-511">Checksum</span></span>

<span data-ttu-id="1061e-512">No</span><span class="sxs-lookup"><span data-stu-id="1061e-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-513">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-513">Definition</span></span>

<span data-ttu-id="1061e-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-517">Keywords</span></span>

<span data-ttu-id="1061e-518">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-518"></span></span>
|<span data-ttu-id="1061e-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-520">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-520">passport number</span></span>  <br/> <span data-ttu-id="1061e-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="1061e-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="1061e-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-522">passport no</span></span>  <br/> <span data-ttu-id="1061e-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="1061e-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="1061e-524">España</span><span class="sxs-lookup"><span data-stu-id="1061e-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="1061e-525">Formato</span><span class="sxs-lookup"><span data-stu-id="1061e-525">Format</span></span>

<span data-ttu-id="1061e-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="1061e-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1061e-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="1061e-527">Pattern</span></span>

<span data-ttu-id="1061e-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="1061e-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="1061e-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="1061e-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="1061e-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="1061e-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1061e-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1061e-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1061e-532">Checksum</span></span>

<span data-ttu-id="1061e-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1061e-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1061e-534">Definición</span><span class="sxs-lookup"><span data-stu-id="1061e-534">Definition</span></span>

<span data-ttu-id="1061e-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1061e-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1061e-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1061e-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1061e-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="1061e-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1061e-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1061e-538">Keywords</span></span>

<span data-ttu-id="1061e-539">| |</span><span class="sxs-lookup"><span data-stu-id="1061e-539"></span></span>
|<span data-ttu-id="1061e-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1061e-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1061e-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="1061e-541">passport</span></span>  <br/> <span data-ttu-id="1061e-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="1061e-542">spain passport</span></span>  <br/> <span data-ttu-id="1061e-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="1061e-543">passport book</span></span>  <br/> <span data-ttu-id="1061e-544">passport number</span><span class="sxs-lookup"><span data-stu-id="1061e-544">passport number</span></span>  <br/> <span data-ttu-id="1061e-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-545">passport no</span></span>  <br/> <span data-ttu-id="1061e-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="1061e-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-547">número pasaporte</span></span>  <br/> <span data-ttu-id="1061e-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="1061e-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="1061e-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="1061e-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="1061e-550">Sweden</span></span>

<span data-ttu-id="1061e-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1061e-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="1061e-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="1061e-552">UK</span></span>

<span data-ttu-id="1061e-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="1061e-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="1061e-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1061e-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1061e-555">Ver también</span><span class="sxs-lookup"><span data-stu-id="1061e-555">See also</span></span>

[<span data-ttu-id="1061e-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="1061e-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

