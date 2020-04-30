---
title: Número de pasaporte de la UE
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 56eb79dd067ca89600f92ea57eaaf01e562f9388
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938744"
---
# <a name="eu-passport-number"></a><span data-ttu-id="8b4bb-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="8b4bb-104">EU Passport Number</span></span>

<span data-ttu-id="8b4bb-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="8b4bb-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8b4bb-107">Austria</span><span class="sxs-lookup"><span data-stu-id="8b4bb-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-108">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-108">Format</span></span>

<span data-ttu-id="8b4bb-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-110">Pattern</span></span>

<span data-ttu-id="8b4bb-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="8b4bb-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8b4bb-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-113">One space (optional)</span></span>
    
- <span data-ttu-id="8b4bb-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-115">Checksum</span></span>

<span data-ttu-id="8b4bb-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8b4bb-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-117">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-117">Definition</span></span>

<span data-ttu-id="8b4bb-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-121">Keywords</span></span>

<span data-ttu-id="8b4bb-122">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-122">| |</span></span>
|<span data-ttu-id="8b4bb-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-124">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-124">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="8b4bb-125">austrian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-126">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="8b4bb-127">reisepass</span></span>  <br/> <span data-ttu-id="8b4bb-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="8b4bb-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8b4bb-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="8b4bb-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-130">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-130">Format</span></span>

<span data-ttu-id="8b4bb-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-132">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-132">Pattern</span></span>

<span data-ttu-id="8b4bb-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-134">Checksum</span></span>

<span data-ttu-id="8b4bb-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8b4bb-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-136">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-136">Definition</span></span>

<span data-ttu-id="8b4bb-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-140">Keywords</span></span>

<span data-ttu-id="8b4bb-141">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-141">| |</span></span>
|<span data-ttu-id="8b4bb-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-143">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-143">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="8b4bb-144">belgian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-145">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="8b4bb-146">paspoort</span></span>  <br/> <span data-ttu-id="8b4bb-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8b4bb-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="8b4bb-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="8b4bb-148">reisepass kein</span></span>  <br/> <span data-ttu-id="8b4bb-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="8b4bb-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8b4bb-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="8b4bb-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-151">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-151">Format</span></span>

<span data-ttu-id="8b4bb-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-153">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-153">Pattern</span></span>

 <span data-ttu-id="8b4bb-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-155">Checksum</span></span>

<span data-ttu-id="8b4bb-156">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-157">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-157">Definition</span></span>

<span data-ttu-id="8b4bb-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-161">Keywords</span></span>

<span data-ttu-id="8b4bb-162">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-162">| |</span></span>
|<span data-ttu-id="8b4bb-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-164">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-164">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="8b4bb-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-166">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="8b4bb-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8b4bb-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-169">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-169">Format</span></span>

<span data-ttu-id="8b4bb-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-171">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-171">Pattern</span></span>

 <span data-ttu-id="8b4bb-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-173">Checksum</span></span>

<span data-ttu-id="8b4bb-174">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-175">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-175">Definition</span></span>

<span data-ttu-id="8b4bb-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-179">Keywords</span></span>

<span data-ttu-id="8b4bb-180">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-180">| |</span></span>
|<span data-ttu-id="8b4bb-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-182">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-182">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="8b4bb-183">croatian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-184">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="8b4bb-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8b4bb-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="8b4bb-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-187">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-187">Format</span></span>

<span data-ttu-id="8b4bb-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-189">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-189">Pattern</span></span>

<span data-ttu-id="8b4bb-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-191">Checksum</span></span>

<span data-ttu-id="8b4bb-192">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-193">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-193">Definition</span></span>

<span data-ttu-id="8b4bb-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-197">Keywords</span></span>

<span data-ttu-id="8b4bb-198">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-198">| |</span></span>
|<span data-ttu-id="8b4bb-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-200">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-200">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="8b4bb-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="8b4bb-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-202">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="8b4bb-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8b4bb-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-205">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-205">Format</span></span>

<span data-ttu-id="8b4bb-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-207">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-207">Pattern</span></span>

<span data-ttu-id="8b4bb-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-209">Checksum</span></span>

<span data-ttu-id="8b4bb-210">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-211">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-211">Definition</span></span>

<span data-ttu-id="8b4bb-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-215">Keywords</span></span>

<span data-ttu-id="8b4bb-216">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-216">| |</span></span>
|<span data-ttu-id="8b4bb-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-218">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-218">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="8b4bb-219">czech passport number</span></span>  <br/> <span data-ttu-id="8b4bb-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-220">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="8b4bb-221">cestovní pas</span></span>  <br/> <span data-ttu-id="8b4bb-222">PAS</span><span class="sxs-lookup"><span data-stu-id="8b4bb-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8b4bb-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="8b4bb-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-224">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-224">Format</span></span>

<span data-ttu-id="8b4bb-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-226">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-226">Pattern</span></span>

 <span data-ttu-id="8b4bb-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-228">Checksum</span></span>

<span data-ttu-id="8b4bb-229">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-230">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-230">Definition</span></span>

<span data-ttu-id="8b4bb-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-234">Keywords</span></span>

<span data-ttu-id="8b4bb-235">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-235">| |</span></span>
|<span data-ttu-id="8b4bb-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-237">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-237">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="8b4bb-238">danish passport number</span></span>  <br/> <span data-ttu-id="8b4bb-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-239">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-240">PAS</span><span class="sxs-lookup"><span data-stu-id="8b4bb-240">pas</span></span>  <br/> <span data-ttu-id="8b4bb-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="8b4bb-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8b4bb-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-243">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-243">Format</span></span>

<span data-ttu-id="8b4bb-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-245">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-245">Pattern</span></span>

<span data-ttu-id="8b4bb-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-247">Checksum</span></span>

<span data-ttu-id="8b4bb-248">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-249">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-249">Definition</span></span>

<span data-ttu-id="8b4bb-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-253">Keywords</span></span>

<span data-ttu-id="8b4bb-254">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-254">| |</span></span>
|<span data-ttu-id="8b4bb-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-256">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-256">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="8b4bb-257">estonian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-258">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="8b4bb-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8b4bb-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-260">Finland</span></span>

<span data-ttu-id="8b4bb-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8b4bb-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="8b4bb-262">Francia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-262">France</span></span>

<span data-ttu-id="8b4bb-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8b4bb-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8b4bb-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="8b4bb-264">Germany</span></span>

<span data-ttu-id="8b4bb-265">Para obtener más información, consulte la sección "número de pasaporte en alemán" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8b4bb-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8b4bb-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-267">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-267">Format</span></span>

<span data-ttu-id="8b4bb-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-269">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-269">Pattern</span></span>

<span data-ttu-id="8b4bb-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-271">Checksum</span></span>

<span data-ttu-id="8b4bb-272">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-273">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-273">Definition</span></span>

<span data-ttu-id="8b4bb-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-277">Keywords</span></span>

<span data-ttu-id="8b4bb-278">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-278">| |</span></span>
|<span data-ttu-id="8b4bb-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-280">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-280">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="8b4bb-281">greek passport number</span></span>  <br/> <span data-ttu-id="8b4bb-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-282">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="8b4bb-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8b4bb-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="8b4bb-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-285">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-285">Format</span></span>

<span data-ttu-id="8b4bb-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-287">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-287">Pattern</span></span>

<span data-ttu-id="8b4bb-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-289">Checksum</span></span>

<span data-ttu-id="8b4bb-290">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-291">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-291">Definition</span></span>

<span data-ttu-id="8b4bb-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-295">Keywords</span></span>

<span data-ttu-id="8b4bb-296">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-296">| |</span></span>
|<span data-ttu-id="8b4bb-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-298">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-298">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="8b4bb-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-300">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="8b4bb-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8b4bb-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="8b4bb-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-303">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-303">Format</span></span>

<span data-ttu-id="8b4bb-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-305">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-305">Pattern</span></span>

<span data-ttu-id="8b4bb-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8b4bb-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8b4bb-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-309">Checksum</span></span>

<span data-ttu-id="8b4bb-310">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-311">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-311">Definition</span></span>

<span data-ttu-id="8b4bb-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-315">Keywords</span></span>

<span data-ttu-id="8b4bb-316">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-316">| |</span></span>
|<span data-ttu-id="8b4bb-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-318">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-318">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="8b4bb-319">irish passport number</span></span>  <br/> <span data-ttu-id="8b4bb-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-320">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-321">PAS</span><span class="sxs-lookup"><span data-stu-id="8b4bb-321">pas</span></span>  <br/> <span data-ttu-id="8b4bb-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="8b4bb-322">passport</span></span>  <br/> <span data-ttu-id="8b4bb-323">passeport</span><span class="sxs-lookup"><span data-stu-id="8b4bb-323">passeport</span></span>  <br/> <span data-ttu-id="8b4bb-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="8b4bb-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8b4bb-325">Italia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-326">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-326">Format</span></span>

<span data-ttu-id="8b4bb-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-328">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-328">Pattern</span></span>

<span data-ttu-id="8b4bb-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8b4bb-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8b4bb-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-332">Checksum</span></span>

<span data-ttu-id="8b4bb-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8b4bb-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-334">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-334">Definition</span></span>

<span data-ttu-id="8b4bb-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-338">Keywords</span></span>

<span data-ttu-id="8b4bb-339">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-339">| |</span></span>
|<span data-ttu-id="8b4bb-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="8b4bb-341">italian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="8b4bb-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="8b4bb-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="8b4bb-343">passaporto</span></span>  <br/> <span data-ttu-id="8b4bb-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="8b4bb-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="8b4bb-345">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-345">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8b4bb-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="8b4bb-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8b4bb-347">passaporto numero</span></span>  <br/> <span data-ttu-id="8b4bb-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="8b4bb-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="8b4bb-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="8b4bb-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="8b4bb-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-351">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-351">Format</span></span>

<span data-ttu-id="8b4bb-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-353">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-353">Pattern</span></span>

<span data-ttu-id="8b4bb-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8b4bb-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8b4bb-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-357">Checksum</span></span>

<span data-ttu-id="8b4bb-358">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-359">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-359">Definition</span></span>

<span data-ttu-id="8b4bb-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-363">Keywords</span></span>

<span data-ttu-id="8b4bb-364">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-364">| |</span></span>
|<span data-ttu-id="8b4bb-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-366">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-366">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="8b4bb-367">latvian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-368">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="8b4bb-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8b4bb-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="8b4bb-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-371">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-371">Format</span></span>

<span data-ttu-id="8b4bb-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-373">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-373">Pattern</span></span>

<span data-ttu-id="8b4bb-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-375">Checksum</span></span>

<span data-ttu-id="8b4bb-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8b4bb-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-377">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-377">Definition</span></span>

<span data-ttu-id="8b4bb-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-381">Keywords</span></span>

<span data-ttu-id="8b4bb-382">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-382">| |</span></span>
|<span data-ttu-id="8b4bb-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-384">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-384">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="8b4bb-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-386">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="8b4bb-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8b4bb-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="8b4bb-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-389">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-389">Format</span></span>

<span data-ttu-id="8b4bb-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-391">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-391">Pattern</span></span>

<span data-ttu-id="8b4bb-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-393">Checksum</span></span>

<span data-ttu-id="8b4bb-394">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-395">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-395">Definition</span></span>

<span data-ttu-id="8b4bb-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-399">Keywords</span></span>

<span data-ttu-id="8b4bb-400">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-400">| |</span></span>
|<span data-ttu-id="8b4bb-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-402">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-402">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="8b4bb-403">latvian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-404">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="8b4bb-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8b4bb-406">Malta</span><span class="sxs-lookup"><span data-stu-id="8b4bb-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-407">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-407">Format</span></span>

<span data-ttu-id="8b4bb-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-409">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-409">Pattern</span></span>

 <span data-ttu-id="8b4bb-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-411">Checksum</span></span>

<span data-ttu-id="8b4bb-412">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-413">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-413">Definition</span></span>

<span data-ttu-id="8b4bb-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-417">Keywords</span></span>

<span data-ttu-id="8b4bb-418">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-418">| |</span></span>
|<span data-ttu-id="8b4bb-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-420">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-420">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="8b4bb-421">maltese passport number</span></span>  <br/> <span data-ttu-id="8b4bb-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-422">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="8b4bb-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8b4bb-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-425">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-425">Format</span></span>

<span data-ttu-id="8b4bb-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-427">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-427">Pattern</span></span>

<span data-ttu-id="8b4bb-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-429">Checksum</span></span>

<span data-ttu-id="8b4bb-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8b4bb-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-431">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-431">Definition</span></span>

<span data-ttu-id="8b4bb-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-435">Keywords</span></span>

<span data-ttu-id="8b4bb-436">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-436">| |</span></span>
|<span data-ttu-id="8b4bb-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="8b4bb-438">dutch passport number</span></span>  <br/> <span data-ttu-id="8b4bb-439">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-439">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="8b4bb-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="8b4bb-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="8b4bb-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="8b4bb-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="8b4bb-442">paspoort</span></span>  <br/> <span data-ttu-id="8b4bb-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8b4bb-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="8b4bb-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8b4bb-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8b4bb-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-445">Poland</span></span>

<span data-ttu-id="8b4bb-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8b4bb-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8b4bb-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="8b4bb-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-448">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-448">Format</span></span>

<span data-ttu-id="8b4bb-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-450">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-450">Pattern</span></span>

<span data-ttu-id="8b4bb-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="8b4bb-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8b4bb-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-454">Checksum</span></span>

<span data-ttu-id="8b4bb-455">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-456">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-456">Definition</span></span>

<span data-ttu-id="8b4bb-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-460">Keywords</span></span>

<span data-ttu-id="8b4bb-461">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-461">| |</span></span>
|<span data-ttu-id="8b4bb-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-463">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-463">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="8b4bb-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="8b4bb-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-465">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8b4bb-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="8b4bb-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-468">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-468">Format</span></span>

<span data-ttu-id="8b4bb-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-470">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-470">Pattern</span></span>

<span data-ttu-id="8b4bb-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-472">Checksum</span></span>

<span data-ttu-id="8b4bb-473">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-474">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-474">Definition</span></span>

<span data-ttu-id="8b4bb-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-478">Keywords</span></span>

<span data-ttu-id="8b4bb-479">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-479">| |</span></span>
|<span data-ttu-id="8b4bb-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-481">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-481">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="8b4bb-482">romanian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-483">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="8b4bb-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8b4bb-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-486">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-486">Format</span></span>

<span data-ttu-id="8b4bb-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-488">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-488">Pattern</span></span>

<span data-ttu-id="8b4bb-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b4bb-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-490">Checksum</span></span>

<span data-ttu-id="8b4bb-491">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-492">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-492">Definition</span></span>

<span data-ttu-id="8b4bb-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-496">Keywords</span></span>

<span data-ttu-id="8b4bb-497">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-497">| |</span></span>
|<span data-ttu-id="8b4bb-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-499">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-499">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="8b4bb-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-501">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="8b4bb-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8b4bb-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-504">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-504">Format</span></span>

<span data-ttu-id="8b4bb-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-506">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-506">Pattern</span></span>

<span data-ttu-id="8b4bb-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="8b4bb-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="8b4bb-508">The letter "P"</span></span>
    
- <span data-ttu-id="8b4bb-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="8b4bb-509">One uppercase letter</span></span>
    
- <span data-ttu-id="8b4bb-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-511">Checksum</span></span>

<span data-ttu-id="8b4bb-512">No</span><span class="sxs-lookup"><span data-stu-id="8b4bb-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-513">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-513">Definition</span></span>

<span data-ttu-id="8b4bb-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-517">Keywords</span></span>

<span data-ttu-id="8b4bb-518">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-518">| |</span></span>
|<span data-ttu-id="8b4bb-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-520">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-520">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="8b4bb-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="8b4bb-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-522">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="8b4bb-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8b4bb-524">España</span><span class="sxs-lookup"><span data-stu-id="8b4bb-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8b4bb-525">Formato</span><span class="sxs-lookup"><span data-stu-id="8b4bb-525">Format</span></span>

<span data-ttu-id="8b4bb-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8b4bb-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b4bb-527">Pattern</span><span class="sxs-lookup"><span data-stu-id="8b4bb-527">Pattern</span></span>

<span data-ttu-id="8b4bb-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="8b4bb-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="8b4bb-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="8b4bb-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="8b4bb-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="8b4bb-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8b4bb-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b4bb-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8b4bb-532">Checksum</span></span>

<span data-ttu-id="8b4bb-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8b4bb-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b4bb-534">Definición</span><span class="sxs-lookup"><span data-stu-id="8b4bb-534">Definition</span></span>

<span data-ttu-id="8b4bb-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8b4bb-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b4bb-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b4bb-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8b4bb-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b4bb-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4bb-538">Keywords</span></span>

<span data-ttu-id="8b4bb-539">| |</span><span class="sxs-lookup"><span data-stu-id="8b4bb-539">| |</span></span>
|<span data-ttu-id="8b4bb-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b4bb-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b4bb-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="8b4bb-541">passport</span></span>  <br/> <span data-ttu-id="8b4bb-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="8b4bb-542">spain passport</span></span>  <br/> <span data-ttu-id="8b4bb-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="8b4bb-543">passport book</span></span>  <br/> <span data-ttu-id="8b4bb-544">passport number</span><span class="sxs-lookup"><span data-stu-id="8b4bb-544">passport number</span></span>  <br/> <span data-ttu-id="8b4bb-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-545">passport no</span></span>  <br/> <span data-ttu-id="8b4bb-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="8b4bb-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-547">número pasaporte</span></span>  <br/> <span data-ttu-id="8b4bb-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="8b4bb-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b4bb-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8b4bb-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="8b4bb-550">Sweden</span></span>

<span data-ttu-id="8b4bb-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8b4bb-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="8b4bb-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="8b4bb-552">UK</span></span>

<span data-ttu-id="8b4bb-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="8b4bb-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="8b4bb-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8b4bb-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b4bb-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b4bb-555">See also</span></span>

[<span data-ttu-id="8b4bb-556">Información que buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="8b4bb-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

