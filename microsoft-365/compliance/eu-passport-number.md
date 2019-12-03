---
title: Número de pasaporte de la UE
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662805"
---
# <a name="eu-passport-number"></a><span data-ttu-id="f32b8-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="f32b8-104">EU Passport Number</span></span>

<span data-ttu-id="f32b8-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="f32b8-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="f32b8-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="f32b8-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f32b8-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f32b8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-108">Format</span></span>

<span data-ttu-id="f32b8-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-110">Pattern</span></span>

<span data-ttu-id="f32b8-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="f32b8-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="f32b8-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="f32b8-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="f32b8-113">One space (optional)</span></span>
    
- <span data-ttu-id="f32b8-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-115">Checksum</span></span>

<span data-ttu-id="f32b8-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f32b8-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-117">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-117">Definition</span></span>

<span data-ttu-id="f32b8-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-121">Keywords</span></span>

<span data-ttu-id="f32b8-122">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-122"></span></span>
|<span data-ttu-id="f32b8-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-124">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-124">passport number</span></span>  <br/> <span data-ttu-id="f32b8-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="f32b8-125">austrian passport number</span></span>  <br/> <span data-ttu-id="f32b8-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-126">passport no</span></span>  <br/> <span data-ttu-id="f32b8-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="f32b8-127">reisepass</span></span>  <br/> <span data-ttu-id="f32b8-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="f32b8-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="f32b8-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="f32b8-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-130">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-130">Format</span></span>

<span data-ttu-id="f32b8-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-132">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-132">Pattern</span></span>

<span data-ttu-id="f32b8-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-134">Checksum</span></span>

<span data-ttu-id="f32b8-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f32b8-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-136">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-136">Definition</span></span>

<span data-ttu-id="f32b8-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-140">Keywords</span></span>

<span data-ttu-id="f32b8-141">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-141"></span></span>
|<span data-ttu-id="f32b8-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-143">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-143">passport number</span></span>  <br/> <span data-ttu-id="f32b8-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="f32b8-144">belgian passport number</span></span>  <br/> <span data-ttu-id="f32b8-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-145">passport no</span></span>  <br/> <span data-ttu-id="f32b8-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="f32b8-146">paspoort</span></span>  <br/> <span data-ttu-id="f32b8-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f32b8-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="f32b8-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="f32b8-148">reisepass kein</span></span>  <br/> <span data-ttu-id="f32b8-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="f32b8-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="f32b8-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f32b8-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-151">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-151">Format</span></span>

<span data-ttu-id="f32b8-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-153">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-153">Pattern</span></span>

 <span data-ttu-id="f32b8-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f32b8-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-155">Checksum</span></span>

<span data-ttu-id="f32b8-156">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-157">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-157">Definition</span></span>

<span data-ttu-id="f32b8-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-161">Keywords</span></span>

<span data-ttu-id="f32b8-162">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-162"></span></span>
|<span data-ttu-id="f32b8-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-164">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-164">passport number</span></span>  <br/> <span data-ttu-id="f32b8-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="f32b8-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="f32b8-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-166">passport no</span></span>  <br/> <span data-ttu-id="f32b8-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="f32b8-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="f32b8-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="f32b8-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-169">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-169">Format</span></span>

<span data-ttu-id="f32b8-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-171">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-171">Pattern</span></span>

 <span data-ttu-id="f32b8-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f32b8-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-173">Checksum</span></span>

<span data-ttu-id="f32b8-174">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-175">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-175">Definition</span></span>

<span data-ttu-id="f32b8-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-179">Keywords</span></span>

<span data-ttu-id="f32b8-180">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-180"></span></span>
|<span data-ttu-id="f32b8-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-182">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-182">passport number</span></span>  <br/> <span data-ttu-id="f32b8-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="f32b8-183">croatian passport number</span></span>  <br/> <span data-ttu-id="f32b8-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-184">passport no</span></span>  <br/> <span data-ttu-id="f32b8-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="f32b8-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="f32b8-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="f32b8-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-187">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-187">Format</span></span>

<span data-ttu-id="f32b8-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-189">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-189">Pattern</span></span>

<span data-ttu-id="f32b8-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-191">Checksum</span></span>

<span data-ttu-id="f32b8-192">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-193">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-193">Definition</span></span>

<span data-ttu-id="f32b8-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-197">Keywords</span></span>

<span data-ttu-id="f32b8-198">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-198"></span></span>
|<span data-ttu-id="f32b8-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-200">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-200">passport number</span></span>  <br/> <span data-ttu-id="f32b8-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="f32b8-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="f32b8-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-202">passport no</span></span>  <br/> <span data-ttu-id="f32b8-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="f32b8-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="f32b8-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="f32b8-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-205">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-205">Format</span></span>

<span data-ttu-id="f32b8-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-207">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-207">Pattern</span></span>

<span data-ttu-id="f32b8-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-209">Checksum</span></span>

<span data-ttu-id="f32b8-210">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-211">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-211">Definition</span></span>

<span data-ttu-id="f32b8-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-215">Keywords</span></span>

<span data-ttu-id="f32b8-216">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-216"></span></span>
|<span data-ttu-id="f32b8-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-218">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-218">passport number</span></span>  <br/> <span data-ttu-id="f32b8-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="f32b8-219">czech passport number</span></span>  <br/> <span data-ttu-id="f32b8-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-220">passport no</span></span>  <br/> <span data-ttu-id="f32b8-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="f32b8-221">cestovní pas</span></span>  <br/> <span data-ttu-id="f32b8-222">PAS</span><span class="sxs-lookup"><span data-stu-id="f32b8-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="f32b8-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="f32b8-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-224">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-224">Format</span></span>

<span data-ttu-id="f32b8-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-226">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-226">Pattern</span></span>

 <span data-ttu-id="f32b8-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f32b8-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-228">Checksum</span></span>

<span data-ttu-id="f32b8-229">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-230">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-230">Definition</span></span>

<span data-ttu-id="f32b8-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-234">Keywords</span></span>

<span data-ttu-id="f32b8-235">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-235"></span></span>
|<span data-ttu-id="f32b8-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-237">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-237">passport number</span></span>  <br/> <span data-ttu-id="f32b8-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="f32b8-238">danish passport number</span></span>  <br/> <span data-ttu-id="f32b8-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-239">passport no</span></span>  <br/> <span data-ttu-id="f32b8-240">PAS</span><span class="sxs-lookup"><span data-stu-id="f32b8-240">pas</span></span>  <br/> <span data-ttu-id="f32b8-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="f32b8-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="f32b8-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="f32b8-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-243">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-243">Format</span></span>

<span data-ttu-id="f32b8-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-245">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-245">Pattern</span></span>

<span data-ttu-id="f32b8-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-247">Checksum</span></span>

<span data-ttu-id="f32b8-248">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-249">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-249">Definition</span></span>

<span data-ttu-id="f32b8-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-253">Keywords</span></span>

<span data-ttu-id="f32b8-254">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-254"></span></span>
|<span data-ttu-id="f32b8-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-256">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-256">passport number</span></span>  <br/> <span data-ttu-id="f32b8-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="f32b8-257">estonian passport number</span></span>  <br/> <span data-ttu-id="f32b8-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-258">passport no</span></span>  <br/> <span data-ttu-id="f32b8-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="f32b8-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="f32b8-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f32b8-260">Finland</span></span>

<span data-ttu-id="f32b8-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f32b8-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="f32b8-262">Francia</span><span class="sxs-lookup"><span data-stu-id="f32b8-262">France</span></span>

<span data-ttu-id="f32b8-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f32b8-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="f32b8-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="f32b8-264">Germany</span></span>

<span data-ttu-id="f32b8-265">Para obtener más información, consulte la sección "número de pasaporte en alemán" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f32b8-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="f32b8-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="f32b8-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-267">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-267">Format</span></span>

<span data-ttu-id="f32b8-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-269">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-269">Pattern</span></span>

<span data-ttu-id="f32b8-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-271">Checksum</span></span>

<span data-ttu-id="f32b8-272">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-273">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-273">Definition</span></span>

<span data-ttu-id="f32b8-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-277">Keywords</span></span>

<span data-ttu-id="f32b8-278">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-278"></span></span>
|<span data-ttu-id="f32b8-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-280">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-280">passport number</span></span>  <br/> <span data-ttu-id="f32b8-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="f32b8-281">greek passport number</span></span>  <br/> <span data-ttu-id="f32b8-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-282">passport no</span></span>  <br/> <span data-ttu-id="f32b8-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="f32b8-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="f32b8-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="f32b8-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-285">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-285">Format</span></span>

<span data-ttu-id="f32b8-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-287">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-287">Pattern</span></span>

<span data-ttu-id="f32b8-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-289">Checksum</span></span>

<span data-ttu-id="f32b8-290">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-291">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-291">Definition</span></span>

<span data-ttu-id="f32b8-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-295">Keywords</span></span>

<span data-ttu-id="f32b8-296">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-296"></span></span>
|<span data-ttu-id="f32b8-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-298">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-298">passport number</span></span>  <br/> <span data-ttu-id="f32b8-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="f32b8-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="f32b8-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-300">passport no</span></span>  <br/> <span data-ttu-id="f32b8-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="f32b8-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="f32b8-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f32b8-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-303">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-303">Format</span></span>

<span data-ttu-id="f32b8-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-305">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-305">Pattern</span></span>

<span data-ttu-id="f32b8-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f32b8-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f32b8-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f32b8-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-309">Checksum</span></span>

<span data-ttu-id="f32b8-310">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-311">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-311">Definition</span></span>

<span data-ttu-id="f32b8-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-315">Keywords</span></span>

<span data-ttu-id="f32b8-316">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-316"></span></span>
|<span data-ttu-id="f32b8-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-318">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-318">passport number</span></span>  <br/> <span data-ttu-id="f32b8-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="f32b8-319">irish passport number</span></span>  <br/> <span data-ttu-id="f32b8-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-320">passport no</span></span>  <br/> <span data-ttu-id="f32b8-321">PAS</span><span class="sxs-lookup"><span data-stu-id="f32b8-321">pas</span></span>  <br/> <span data-ttu-id="f32b8-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="f32b8-322">passport</span></span>  <br/> <span data-ttu-id="f32b8-323">passeport</span><span class="sxs-lookup"><span data-stu-id="f32b8-323">passeport</span></span>  <br/> <span data-ttu-id="f32b8-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="f32b8-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="f32b8-325">Italia</span><span class="sxs-lookup"><span data-stu-id="f32b8-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-326">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-326">Format</span></span>

<span data-ttu-id="f32b8-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-328">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-328">Pattern</span></span>

<span data-ttu-id="f32b8-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f32b8-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f32b8-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f32b8-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-332">Checksum</span></span>

<span data-ttu-id="f32b8-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f32b8-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-334">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-334">Definition</span></span>

<span data-ttu-id="f32b8-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-338">Keywords</span></span>

<span data-ttu-id="f32b8-339">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-339"></span></span>
|<span data-ttu-id="f32b8-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="f32b8-341">italian passport number</span></span>  <br/> <span data-ttu-id="f32b8-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="f32b8-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="f32b8-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="f32b8-343">passaporto</span></span>  <br/> <span data-ttu-id="f32b8-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="f32b8-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="f32b8-345">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-345">passport number</span></span>  <br/> <span data-ttu-id="f32b8-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="f32b8-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="f32b8-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="f32b8-347">passaporto numero</span></span>  <br/> <span data-ttu-id="f32b8-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="f32b8-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="f32b8-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="f32b8-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="f32b8-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="f32b8-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-351">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-351">Format</span></span>

<span data-ttu-id="f32b8-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-353">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-353">Pattern</span></span>

<span data-ttu-id="f32b8-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f32b8-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f32b8-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f32b8-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-357">Checksum</span></span>

<span data-ttu-id="f32b8-358">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-359">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-359">Definition</span></span>

<span data-ttu-id="f32b8-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-363">Keywords</span></span>

<span data-ttu-id="f32b8-364">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-364"></span></span>
|<span data-ttu-id="f32b8-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-366">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-366">passport number</span></span>  <br/> <span data-ttu-id="f32b8-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="f32b8-367">latvian passport number</span></span>  <br/> <span data-ttu-id="f32b8-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-368">passport no</span></span>  <br/> <span data-ttu-id="f32b8-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="f32b8-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="f32b8-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="f32b8-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-371">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-371">Format</span></span>

<span data-ttu-id="f32b8-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-373">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-373">Pattern</span></span>

<span data-ttu-id="f32b8-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-375">Checksum</span></span>

<span data-ttu-id="f32b8-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f32b8-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-377">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-377">Definition</span></span>

<span data-ttu-id="f32b8-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-381">Keywords</span></span>

<span data-ttu-id="f32b8-382">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-382"></span></span>
|<span data-ttu-id="f32b8-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-384">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-384">passport number</span></span>  <br/> <span data-ttu-id="f32b8-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="f32b8-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="f32b8-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-386">passport no</span></span>  <br/> <span data-ttu-id="f32b8-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="f32b8-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="f32b8-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="f32b8-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-389">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-389">Format</span></span>

<span data-ttu-id="f32b8-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-391">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-391">Pattern</span></span>

<span data-ttu-id="f32b8-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-393">Checksum</span></span>

<span data-ttu-id="f32b8-394">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-395">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-395">Definition</span></span>

<span data-ttu-id="f32b8-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-399">Keywords</span></span>

<span data-ttu-id="f32b8-400">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-400"></span></span>
|<span data-ttu-id="f32b8-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-402">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-402">passport number</span></span>  <br/> <span data-ttu-id="f32b8-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="f32b8-403">latvian passport number</span></span>  <br/> <span data-ttu-id="f32b8-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-404">passport no</span></span>  <br/> <span data-ttu-id="f32b8-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="f32b8-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="f32b8-406">Malta</span><span class="sxs-lookup"><span data-stu-id="f32b8-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-407">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-407">Format</span></span>

<span data-ttu-id="f32b8-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-409">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-409">Pattern</span></span>

 <span data-ttu-id="f32b8-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f32b8-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-411">Checksum</span></span>

<span data-ttu-id="f32b8-412">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-413">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-413">Definition</span></span>

<span data-ttu-id="f32b8-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-417">Keywords</span></span>

<span data-ttu-id="f32b8-418">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-418"></span></span>
|<span data-ttu-id="f32b8-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-420">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-420">passport number</span></span>  <br/> <span data-ttu-id="f32b8-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="f32b8-421">maltese passport number</span></span>  <br/> <span data-ttu-id="f32b8-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-422">passport no</span></span>  <br/> <span data-ttu-id="f32b8-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="f32b8-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="f32b8-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="f32b8-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-425">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-425">Format</span></span>

<span data-ttu-id="f32b8-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-427">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-427">Pattern</span></span>

<span data-ttu-id="f32b8-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-429">Checksum</span></span>

<span data-ttu-id="f32b8-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f32b8-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-431">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-431">Definition</span></span>

<span data-ttu-id="f32b8-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-435">Keywords</span></span>

<span data-ttu-id="f32b8-436">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-436"></span></span>
|<span data-ttu-id="f32b8-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="f32b8-438">dutch passport number</span></span>  <br/> <span data-ttu-id="f32b8-439">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-439">passport number</span></span>  <br/> <span data-ttu-id="f32b8-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="f32b8-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="f32b8-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="f32b8-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="f32b8-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="f32b8-442">paspoort</span></span>  <br/> <span data-ttu-id="f32b8-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f32b8-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="f32b8-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f32b8-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="f32b8-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="f32b8-445">Poland</span></span>

<span data-ttu-id="f32b8-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f32b8-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="f32b8-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="f32b8-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-448">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-448">Format</span></span>

<span data-ttu-id="f32b8-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-450">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-450">Pattern</span></span>

<span data-ttu-id="f32b8-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f32b8-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="f32b8-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f32b8-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="f32b8-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-454">Checksum</span></span>

<span data-ttu-id="f32b8-455">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-456">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-456">Definition</span></span>

<span data-ttu-id="f32b8-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-460">Keywords</span></span>

<span data-ttu-id="f32b8-461">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-461"></span></span>
|<span data-ttu-id="f32b8-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-463">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-463">passport number</span></span>  <br/> <span data-ttu-id="f32b8-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="f32b8-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="f32b8-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-465">passport no</span></span>  <br/> <span data-ttu-id="f32b8-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="f32b8-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="f32b8-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-468">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-468">Format</span></span>

<span data-ttu-id="f32b8-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-470">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-470">Pattern</span></span>

<span data-ttu-id="f32b8-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-472">Checksum</span></span>

<span data-ttu-id="f32b8-473">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-474">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-474">Definition</span></span>

<span data-ttu-id="f32b8-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-478">Keywords</span></span>

<span data-ttu-id="f32b8-479">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-479"></span></span>
|<span data-ttu-id="f32b8-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-481">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-481">passport number</span></span>  <br/> <span data-ttu-id="f32b8-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="f32b8-482">romanian passport number</span></span>  <br/> <span data-ttu-id="f32b8-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-483">passport no</span></span>  <br/> <span data-ttu-id="f32b8-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="f32b8-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="f32b8-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="f32b8-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-486">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-486">Format</span></span>

<span data-ttu-id="f32b8-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-488">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-488">Pattern</span></span>

<span data-ttu-id="f32b8-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f32b8-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-490">Checksum</span></span>

<span data-ttu-id="f32b8-491">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-492">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-492">Definition</span></span>

<span data-ttu-id="f32b8-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-496">Keywords</span></span>

<span data-ttu-id="f32b8-497">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-497"></span></span>
|<span data-ttu-id="f32b8-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-499">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-499">passport number</span></span>  <br/> <span data-ttu-id="f32b8-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="f32b8-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="f32b8-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-501">passport no</span></span>  <br/> <span data-ttu-id="f32b8-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="f32b8-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="f32b8-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="f32b8-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-504">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-504">Format</span></span>

<span data-ttu-id="f32b8-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-506">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-506">Pattern</span></span>

<span data-ttu-id="f32b8-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f32b8-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="f32b8-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="f32b8-508">The letter "P"</span></span>
    
- <span data-ttu-id="f32b8-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="f32b8-509">One uppercase letter</span></span>
    
- <span data-ttu-id="f32b8-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-511">Checksum</span></span>

<span data-ttu-id="f32b8-512">No</span><span class="sxs-lookup"><span data-stu-id="f32b8-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-513">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-513">Definition</span></span>

<span data-ttu-id="f32b8-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-517">Keywords</span></span>

<span data-ttu-id="f32b8-518">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-518"></span></span>
|<span data-ttu-id="f32b8-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-520">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-520">passport number</span></span>  <br/> <span data-ttu-id="f32b8-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="f32b8-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="f32b8-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-522">passport no</span></span>  <br/> <span data-ttu-id="f32b8-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="f32b8-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="f32b8-524">España</span><span class="sxs-lookup"><span data-stu-id="f32b8-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f32b8-525">Formato</span><span class="sxs-lookup"><span data-stu-id="f32b8-525">Format</span></span>

<span data-ttu-id="f32b8-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f32b8-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f32b8-527">Pattern</span><span class="sxs-lookup"><span data-stu-id="f32b8-527">Pattern</span></span>

<span data-ttu-id="f32b8-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="f32b8-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="f32b8-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="f32b8-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="f32b8-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="f32b8-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f32b8-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f32b8-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f32b8-532">Checksum</span></span>

<span data-ttu-id="f32b8-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f32b8-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f32b8-534">Definición</span><span class="sxs-lookup"><span data-stu-id="f32b8-534">Definition</span></span>

<span data-ttu-id="f32b8-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f32b8-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f32b8-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f32b8-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f32b8-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f32b8-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f32b8-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f32b8-538">Keywords</span></span>

<span data-ttu-id="f32b8-539">| |</span><span class="sxs-lookup"><span data-stu-id="f32b8-539"></span></span>
|<span data-ttu-id="f32b8-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f32b8-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f32b8-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="f32b8-541">passport</span></span>  <br/> <span data-ttu-id="f32b8-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="f32b8-542">spain passport</span></span>  <br/> <span data-ttu-id="f32b8-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="f32b8-543">passport book</span></span>  <br/> <span data-ttu-id="f32b8-544">passport number</span><span class="sxs-lookup"><span data-stu-id="f32b8-544">passport number</span></span>  <br/> <span data-ttu-id="f32b8-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-545">passport no</span></span>  <br/> <span data-ttu-id="f32b8-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="f32b8-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-547">número pasaporte</span></span>  <br/> <span data-ttu-id="f32b8-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="f32b8-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="f32b8-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="f32b8-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="f32b8-550">Sweden</span></span>

<span data-ttu-id="f32b8-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f32b8-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="f32b8-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="f32b8-552">UK</span></span>

<span data-ttu-id="f32b8-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="f32b8-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="f32b8-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f32b8-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f32b8-555">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f32b8-555">See also</span></span>

[<span data-ttu-id="f32b8-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="f32b8-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

