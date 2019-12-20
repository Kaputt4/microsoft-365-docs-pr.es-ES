---
title: Número de pasaporte de la UE
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
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805953"
---
# <a name="eu-passport-number"></a><span data-ttu-id="9e3c5-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="9e3c5-104">EU Passport Number</span></span>

<span data-ttu-id="9e3c5-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="9e3c5-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9e3c5-107">Austria</span><span class="sxs-lookup"><span data-stu-id="9e3c5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-108">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-108">Format</span></span>

<span data-ttu-id="9e3c5-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-110">Pattern</span></span>

<span data-ttu-id="9e3c5-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="9e3c5-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="9e3c5-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-113">One space (optional)</span></span>
    
- <span data-ttu-id="9e3c5-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-115">Checksum</span></span>

<span data-ttu-id="9e3c5-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="9e3c5-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-117">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-117">Definition</span></span>

<span data-ttu-id="9e3c5-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-121">Keywords</span></span>

<span data-ttu-id="9e3c5-122">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-122"></span></span>
|<span data-ttu-id="9e3c5-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-124">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-124">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="9e3c5-125">austrian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-126">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="9e3c5-127">reisepass</span></span>  <br/> <span data-ttu-id="9e3c5-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="9e3c5-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="9e3c5-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="9e3c5-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-130">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-130">Format</span></span>

<span data-ttu-id="9e3c5-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-132">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-132">Pattern</span></span>

<span data-ttu-id="9e3c5-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-134">Checksum</span></span>

<span data-ttu-id="9e3c5-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="9e3c5-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-136">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-136">Definition</span></span>

<span data-ttu-id="9e3c5-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-140">Keywords</span></span>

<span data-ttu-id="9e3c5-141">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-141"></span></span>
|<span data-ttu-id="9e3c5-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-143">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-143">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="9e3c5-144">belgian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-145">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="9e3c5-146">paspoort</span></span>  <br/> <span data-ttu-id="9e3c5-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="9e3c5-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="9e3c5-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="9e3c5-148">reisepass kein</span></span>  <br/> <span data-ttu-id="9e3c5-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="9e3c5-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="9e3c5-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="9e3c5-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-151">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-151">Format</span></span>

<span data-ttu-id="9e3c5-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-153">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-153">Pattern</span></span>

 <span data-ttu-id="9e3c5-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-155">Checksum</span></span>

<span data-ttu-id="9e3c5-156">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-157">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-157">Definition</span></span>

<span data-ttu-id="9e3c5-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-161">Keywords</span></span>

<span data-ttu-id="9e3c5-162">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-162"></span></span>
|<span data-ttu-id="9e3c5-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-164">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-164">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="9e3c5-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-166">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="9e3c5-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="9e3c5-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-169">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-169">Format</span></span>

<span data-ttu-id="9e3c5-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-171">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-171">Pattern</span></span>

 <span data-ttu-id="9e3c5-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-173">Checksum</span></span>

<span data-ttu-id="9e3c5-174">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-175">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-175">Definition</span></span>

<span data-ttu-id="9e3c5-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-179">Keywords</span></span>

<span data-ttu-id="9e3c5-180">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-180"></span></span>
|<span data-ttu-id="9e3c5-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-182">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-182">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="9e3c5-183">croatian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-184">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="9e3c5-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="9e3c5-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="9e3c5-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-187">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-187">Format</span></span>

<span data-ttu-id="9e3c5-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-189">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-189">Pattern</span></span>

<span data-ttu-id="9e3c5-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-191">Checksum</span></span>

<span data-ttu-id="9e3c5-192">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-193">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-193">Definition</span></span>

<span data-ttu-id="9e3c5-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-197">Keywords</span></span>

<span data-ttu-id="9e3c5-198">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-198"></span></span>
|<span data-ttu-id="9e3c5-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-200">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-200">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="9e3c5-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="9e3c5-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-202">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="9e3c5-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="9e3c5-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-205">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-205">Format</span></span>

<span data-ttu-id="9e3c5-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-207">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-207">Pattern</span></span>

<span data-ttu-id="9e3c5-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-209">Checksum</span></span>

<span data-ttu-id="9e3c5-210">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-211">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-211">Definition</span></span>

<span data-ttu-id="9e3c5-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-215">Keywords</span></span>

<span data-ttu-id="9e3c5-216">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-216"></span></span>
|<span data-ttu-id="9e3c5-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-218">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-218">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="9e3c5-219">czech passport number</span></span>  <br/> <span data-ttu-id="9e3c5-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-220">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="9e3c5-221">cestovní pas</span></span>  <br/> <span data-ttu-id="9e3c5-222">PAS</span><span class="sxs-lookup"><span data-stu-id="9e3c5-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="9e3c5-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="9e3c5-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-224">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-224">Format</span></span>

<span data-ttu-id="9e3c5-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-226">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-226">Pattern</span></span>

 <span data-ttu-id="9e3c5-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-228">Checksum</span></span>

<span data-ttu-id="9e3c5-229">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-230">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-230">Definition</span></span>

<span data-ttu-id="9e3c5-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-234">Keywords</span></span>

<span data-ttu-id="9e3c5-235">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-235"></span></span>
|<span data-ttu-id="9e3c5-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-237">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-237">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="9e3c5-238">danish passport number</span></span>  <br/> <span data-ttu-id="9e3c5-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-239">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-240">PAS</span><span class="sxs-lookup"><span data-stu-id="9e3c5-240">pas</span></span>  <br/> <span data-ttu-id="9e3c5-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="9e3c5-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="9e3c5-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-243">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-243">Format</span></span>

<span data-ttu-id="9e3c5-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-245">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-245">Pattern</span></span>

<span data-ttu-id="9e3c5-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-247">Checksum</span></span>

<span data-ttu-id="9e3c5-248">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-249">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-249">Definition</span></span>

<span data-ttu-id="9e3c5-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-253">Keywords</span></span>

<span data-ttu-id="9e3c5-254">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-254"></span></span>
|<span data-ttu-id="9e3c5-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-256">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-256">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="9e3c5-257">estonian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-258">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="9e3c5-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="9e3c5-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-260">Finland</span></span>

<span data-ttu-id="9e3c5-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c5-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="9e3c5-262">Francia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-262">France</span></span>

<span data-ttu-id="9e3c5-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c5-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9e3c5-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="9e3c5-264">Germany</span></span>

<span data-ttu-id="9e3c5-265">Para obtener más información, consulte la sección "número de pasaporte en alemán" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c5-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9e3c5-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-267">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-267">Format</span></span>

<span data-ttu-id="9e3c5-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-269">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-269">Pattern</span></span>

<span data-ttu-id="9e3c5-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-271">Checksum</span></span>

<span data-ttu-id="9e3c5-272">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-273">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-273">Definition</span></span>

<span data-ttu-id="9e3c5-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-277">Keywords</span></span>

<span data-ttu-id="9e3c5-278">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-278"></span></span>
|<span data-ttu-id="9e3c5-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-280">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-280">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="9e3c5-281">greek passport number</span></span>  <br/> <span data-ttu-id="9e3c5-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-282">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="9e3c5-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="9e3c5-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="9e3c5-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-285">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-285">Format</span></span>

<span data-ttu-id="9e3c5-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-287">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-287">Pattern</span></span>

<span data-ttu-id="9e3c5-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-289">Checksum</span></span>

<span data-ttu-id="9e3c5-290">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-291">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-291">Definition</span></span>

<span data-ttu-id="9e3c5-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-295">Keywords</span></span>

<span data-ttu-id="9e3c5-296">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-296"></span></span>
|<span data-ttu-id="9e3c5-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-298">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-298">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="9e3c5-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-300">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="9e3c5-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="9e3c5-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="9e3c5-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-303">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-303">Format</span></span>

<span data-ttu-id="9e3c5-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-305">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-305">Pattern</span></span>

<span data-ttu-id="9e3c5-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="9e3c5-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="9e3c5-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-309">Checksum</span></span>

<span data-ttu-id="9e3c5-310">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-311">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-311">Definition</span></span>

<span data-ttu-id="9e3c5-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-315">Keywords</span></span>

<span data-ttu-id="9e3c5-316">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-316"></span></span>
|<span data-ttu-id="9e3c5-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-318">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-318">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="9e3c5-319">irish passport number</span></span>  <br/> <span data-ttu-id="9e3c5-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-320">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-321">PAS</span><span class="sxs-lookup"><span data-stu-id="9e3c5-321">pas</span></span>  <br/> <span data-ttu-id="9e3c5-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="9e3c5-322">passport</span></span>  <br/> <span data-ttu-id="9e3c5-323">passeport</span><span class="sxs-lookup"><span data-stu-id="9e3c5-323">passeport</span></span>  <br/> <span data-ttu-id="9e3c5-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="9e3c5-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="9e3c5-325">Italia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-326">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-326">Format</span></span>

<span data-ttu-id="9e3c5-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-328">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-328">Pattern</span></span>

<span data-ttu-id="9e3c5-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="9e3c5-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="9e3c5-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-332">Checksum</span></span>

<span data-ttu-id="9e3c5-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="9e3c5-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-334">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-334">Definition</span></span>

<span data-ttu-id="9e3c5-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-338">Keywords</span></span>

<span data-ttu-id="9e3c5-339">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-339"></span></span>
|<span data-ttu-id="9e3c5-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="9e3c5-341">italian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="9e3c5-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="9e3c5-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="9e3c5-343">passaporto</span></span>  <br/> <span data-ttu-id="9e3c5-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="9e3c5-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="9e3c5-345">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-345">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="9e3c5-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="9e3c5-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="9e3c5-347">passaporto numero</span></span>  <br/> <span data-ttu-id="9e3c5-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="9e3c5-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="9e3c5-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="9e3c5-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="9e3c5-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-351">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-351">Format</span></span>

<span data-ttu-id="9e3c5-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-353">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-353">Pattern</span></span>

<span data-ttu-id="9e3c5-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="9e3c5-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="9e3c5-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-357">Checksum</span></span>

<span data-ttu-id="9e3c5-358">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-359">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-359">Definition</span></span>

<span data-ttu-id="9e3c5-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-363">Keywords</span></span>

<span data-ttu-id="9e3c5-364">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-364"></span></span>
|<span data-ttu-id="9e3c5-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-366">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-366">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="9e3c5-367">latvian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-368">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="9e3c5-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="9e3c5-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="9e3c5-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-371">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-371">Format</span></span>

<span data-ttu-id="9e3c5-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-373">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-373">Pattern</span></span>

<span data-ttu-id="9e3c5-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-375">Checksum</span></span>

<span data-ttu-id="9e3c5-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="9e3c5-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-377">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-377">Definition</span></span>

<span data-ttu-id="9e3c5-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-381">Keywords</span></span>

<span data-ttu-id="9e3c5-382">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-382"></span></span>
|<span data-ttu-id="9e3c5-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-384">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-384">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="9e3c5-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-386">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="9e3c5-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="9e3c5-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="9e3c5-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-389">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-389">Format</span></span>

<span data-ttu-id="9e3c5-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-391">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-391">Pattern</span></span>

<span data-ttu-id="9e3c5-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-393">Checksum</span></span>

<span data-ttu-id="9e3c5-394">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-395">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-395">Definition</span></span>

<span data-ttu-id="9e3c5-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-399">Keywords</span></span>

<span data-ttu-id="9e3c5-400">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-400"></span></span>
|<span data-ttu-id="9e3c5-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-402">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-402">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="9e3c5-403">latvian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-404">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="9e3c5-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="9e3c5-406">Malta</span><span class="sxs-lookup"><span data-stu-id="9e3c5-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-407">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-407">Format</span></span>

<span data-ttu-id="9e3c5-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-409">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-409">Pattern</span></span>

 <span data-ttu-id="9e3c5-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-411">Checksum</span></span>

<span data-ttu-id="9e3c5-412">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-413">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-413">Definition</span></span>

<span data-ttu-id="9e3c5-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-417">Keywords</span></span>

<span data-ttu-id="9e3c5-418">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-418"></span></span>
|<span data-ttu-id="9e3c5-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-420">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-420">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="9e3c5-421">maltese passport number</span></span>  <br/> <span data-ttu-id="9e3c5-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-422">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="9e3c5-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="9e3c5-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-425">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-425">Format</span></span>

<span data-ttu-id="9e3c5-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-427">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-427">Pattern</span></span>

<span data-ttu-id="9e3c5-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-429">Checksum</span></span>

<span data-ttu-id="9e3c5-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="9e3c5-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-431">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-431">Definition</span></span>

<span data-ttu-id="9e3c5-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-435">Keywords</span></span>

<span data-ttu-id="9e3c5-436">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-436"></span></span>
|<span data-ttu-id="9e3c5-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="9e3c5-438">dutch passport number</span></span>  <br/> <span data-ttu-id="9e3c5-439">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-439">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="9e3c5-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="9e3c5-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="9e3c5-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="9e3c5-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="9e3c5-442">paspoort</span></span>  <br/> <span data-ttu-id="9e3c5-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="9e3c5-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="9e3c5-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="9e3c5-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="9e3c5-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-445">Poland</span></span>

<span data-ttu-id="9e3c5-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c5-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="9e3c5-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="9e3c5-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-448">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-448">Format</span></span>

<span data-ttu-id="9e3c5-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-450">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-450">Pattern</span></span>

<span data-ttu-id="9e3c5-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="9e3c5-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="9e3c5-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-454">Checksum</span></span>

<span data-ttu-id="9e3c5-455">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-456">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-456">Definition</span></span>

<span data-ttu-id="9e3c5-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-460">Keywords</span></span>

<span data-ttu-id="9e3c5-461">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-461"></span></span>
|<span data-ttu-id="9e3c5-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-463">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-463">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="9e3c5-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="9e3c5-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-465">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="9e3c5-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="9e3c5-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-468">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-468">Format</span></span>

<span data-ttu-id="9e3c5-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-470">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-470">Pattern</span></span>

<span data-ttu-id="9e3c5-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-472">Checksum</span></span>

<span data-ttu-id="9e3c5-473">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-474">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-474">Definition</span></span>

<span data-ttu-id="9e3c5-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-478">Keywords</span></span>

<span data-ttu-id="9e3c5-479">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-479"></span></span>
|<span data-ttu-id="9e3c5-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-481">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-481">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="9e3c5-482">romanian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-483">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="9e3c5-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="9e3c5-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-486">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-486">Format</span></span>

<span data-ttu-id="9e3c5-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-488">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-488">Pattern</span></span>

<span data-ttu-id="9e3c5-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e3c5-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-490">Checksum</span></span>

<span data-ttu-id="9e3c5-491">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-492">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-492">Definition</span></span>

<span data-ttu-id="9e3c5-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-496">Keywords</span></span>

<span data-ttu-id="9e3c5-497">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-497"></span></span>
|<span data-ttu-id="9e3c5-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-499">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-499">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="9e3c5-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-501">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="9e3c5-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="9e3c5-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-504">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-504">Format</span></span>

<span data-ttu-id="9e3c5-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-506">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-506">Pattern</span></span>

<span data-ttu-id="9e3c5-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="9e3c5-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="9e3c5-508">The letter "P"</span></span>
    
- <span data-ttu-id="9e3c5-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="9e3c5-509">One uppercase letter</span></span>
    
- <span data-ttu-id="9e3c5-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-511">Checksum</span></span>

<span data-ttu-id="9e3c5-512">No</span><span class="sxs-lookup"><span data-stu-id="9e3c5-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-513">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-513">Definition</span></span>

<span data-ttu-id="9e3c5-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-517">Keywords</span></span>

<span data-ttu-id="9e3c5-518">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-518"></span></span>
|<span data-ttu-id="9e3c5-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-520">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-520">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="9e3c5-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="9e3c5-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-522">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="9e3c5-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="9e3c5-524">España</span><span class="sxs-lookup"><span data-stu-id="9e3c5-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="9e3c5-525">Formato</span><span class="sxs-lookup"><span data-stu-id="9e3c5-525">Format</span></span>

<span data-ttu-id="9e3c5-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9e3c5-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e3c5-527">Pattern</span><span class="sxs-lookup"><span data-stu-id="9e3c5-527">Pattern</span></span>

<span data-ttu-id="9e3c5-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="9e3c5-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="9e3c5-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="9e3c5-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="9e3c5-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="9e3c5-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="9e3c5-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e3c5-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9e3c5-532">Checksum</span></span>

<span data-ttu-id="9e3c5-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="9e3c5-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e3c5-534">Definición</span><span class="sxs-lookup"><span data-stu-id="9e3c5-534">Definition</span></span>

<span data-ttu-id="9e3c5-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9e3c5-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e3c5-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e3c5-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9e3c5-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9e3c5-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9e3c5-538">Keywords</span></span>

<span data-ttu-id="9e3c5-539">| |</span><span class="sxs-lookup"><span data-stu-id="9e3c5-539"></span></span>
|<span data-ttu-id="9e3c5-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="9e3c5-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="9e3c5-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="9e3c5-541">passport</span></span>  <br/> <span data-ttu-id="9e3c5-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="9e3c5-542">spain passport</span></span>  <br/> <span data-ttu-id="9e3c5-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="9e3c5-543">passport book</span></span>  <br/> <span data-ttu-id="9e3c5-544">passport number</span><span class="sxs-lookup"><span data-stu-id="9e3c5-544">passport number</span></span>  <br/> <span data-ttu-id="9e3c5-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-545">passport no</span></span>  <br/> <span data-ttu-id="9e3c5-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="9e3c5-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-547">número pasaporte</span></span>  <br/> <span data-ttu-id="9e3c5-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="9e3c5-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="9e3c5-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="9e3c5-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="9e3c5-550">Sweden</span></span>

<span data-ttu-id="9e3c5-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c5-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="9e3c5-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="9e3c5-552">UK</span></span>

<span data-ttu-id="9e3c5-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="9e3c5-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="9e3c5-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c5-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e3c5-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e3c5-555">See also</span></span>

[<span data-ttu-id="9e3c5-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="9e3c5-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

