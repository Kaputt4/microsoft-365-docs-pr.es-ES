---
title: Número de permiso de conducción de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092484"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="5be06-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="5be06-104">EU Driver's License Number</span></span>

<span data-ttu-id="5be06-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE.</span><span class="sxs-lookup"><span data-stu-id="5be06-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="5be06-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="5be06-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5be06-107">Austria</span><span class="sxs-lookup"><span data-stu-id="5be06-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5be06-108">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-108">Format</span></span>

<span data-ttu-id="5be06-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-110">Pattern</span></span>

<span data-ttu-id="5be06-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-112">Checksum</span></span>

<span data-ttu-id="5be06-113">No</span><span class="sxs-lookup"><span data-stu-id="5be06-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-114">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-114">Definition</span></span>

<span data-ttu-id="5be06-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="5be06-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-118">Keywords</span></span>

<span data-ttu-id="5be06-119">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-119"></span></span>
|<span data-ttu-id="5be06-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-121">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-121">dl#</span></span>  <br/> <span data-ttu-id="5be06-122">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-122">driver license</span></span>  <br/> <span data-ttu-id="5be06-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-123">driver license number</span></span>  <br/> <span data-ttu-id="5be06-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-124">driver licence</span></span>  <br/> <span data-ttu-id="5be06-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-125">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-126">drivers license</span></span>  <br/> <span data-ttu-id="5be06-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5be06-127">driver's licence</span></span>  <br/> <span data-ttu-id="5be06-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-128">driver's license</span></span>  <br/> <span data-ttu-id="5be06-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-129">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="5be06-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-131">driving license number</span></span>  <br/> <span data-ttu-id="5be06-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-132">dlno#</span></span>  <br/> <span data-ttu-id="5be06-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="5be06-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="5be06-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="5be06-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="5be06-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="5be06-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5be06-136">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-136">Format</span></span>

<span data-ttu-id="5be06-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-138">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-138">Pattern</span></span>

<span data-ttu-id="5be06-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-140">Checksum</span></span>

<span data-ttu-id="5be06-141">No</span><span class="sxs-lookup"><span data-stu-id="5be06-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-142">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-142">Definition</span></span>

<span data-ttu-id="5be06-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5be06-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-146">Keywords</span></span>

<span data-ttu-id="5be06-147">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-147"></span></span>
|<span data-ttu-id="5be06-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-149">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-149">dl#</span></span>  <br/> <span data-ttu-id="5be06-150">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-150">driver license</span></span>  <br/> <span data-ttu-id="5be06-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-151">driver license number</span></span>  <br/> <span data-ttu-id="5be06-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-152">driver licence</span></span>  <br/> <span data-ttu-id="5be06-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-153">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-154">drivers license</span></span>  <br/> <span data-ttu-id="5be06-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-155">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-156">driver's license</span></span>  <br/> <span data-ttu-id="5be06-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-157">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-158">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-159">dlno#</span></span>  <br/> <span data-ttu-id="5be06-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5be06-160">rijbewijs</span></span>  <br/> <span data-ttu-id="5be06-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5be06-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="5be06-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5be06-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="5be06-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5be06-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="5be06-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5be06-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="5be06-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5be06-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="5be06-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5be06-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="5be06-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5be06-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="5be06-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="5be06-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5be06-169">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-169">Format</span></span>

<span data-ttu-id="5be06-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-171">Pattern</span></span>

<span data-ttu-id="5be06-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-173">Checksum</span></span>

<span data-ttu-id="5be06-174">No</span><span class="sxs-lookup"><span data-stu-id="5be06-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-175">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-175">Definition</span></span>

<span data-ttu-id="5be06-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="5be06-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-179">Keywords</span></span>

<span data-ttu-id="5be06-180">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-180"></span></span>
|<span data-ttu-id="5be06-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-182">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-182">dl#</span></span>  <br/> <span data-ttu-id="5be06-183">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-183">driver license</span></span>  <br/> <span data-ttu-id="5be06-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-184">driver license number</span></span>  <br/> <span data-ttu-id="5be06-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-185">driver licence</span></span>  <br/> <span data-ttu-id="5be06-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-186">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-187">drivers license</span></span>  <br/> <span data-ttu-id="5be06-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-188">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-189">driver's license</span></span>  <br/> <span data-ttu-id="5be06-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-190">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-191">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-192">driving license number</span></span>  <br/> <span data-ttu-id="5be06-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-193">dlno#</span></span>  <br/> <span data-ttu-id="5be06-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="5be06-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="5be06-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="5be06-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="5be06-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="5be06-196">сумпс</span></span>  <br/> <span data-ttu-id="5be06-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="5be06-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="5be06-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="5be06-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5be06-199">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-199">Format</span></span>

<span data-ttu-id="5be06-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-201">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-201">Pattern</span></span>

<span data-ttu-id="5be06-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-203">Checksum</span></span>

<span data-ttu-id="5be06-204">No</span><span class="sxs-lookup"><span data-stu-id="5be06-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-205">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-205">Definition</span></span>

<span data-ttu-id="5be06-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5be06-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-209">Keywords</span></span>

<span data-ttu-id="5be06-210">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-210"></span></span>
|<span data-ttu-id="5be06-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-212">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-212">dl#</span></span>  <br/> <span data-ttu-id="5be06-213">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-213">driver license</span></span>  <br/> <span data-ttu-id="5be06-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-214">driver license number</span></span>  <br/> <span data-ttu-id="5be06-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-215">driver licence</span></span>  <br/> <span data-ttu-id="5be06-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-216">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-217">drivers license</span></span>  <br/> <span data-ttu-id="5be06-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-218">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-219">driver's license</span></span>  <br/> <span data-ttu-id="5be06-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-220">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-221">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-222">driving license number</span></span>  <br/> <span data-ttu-id="5be06-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-223">dlno#</span></span>  <br/> <span data-ttu-id="5be06-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="5be06-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="5be06-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="5be06-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5be06-226">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-226">Format</span></span>

<span data-ttu-id="5be06-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-228">Pattern</span></span>

<span data-ttu-id="5be06-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-230">Checksum</span></span>

<span data-ttu-id="5be06-231">No</span><span class="sxs-lookup"><span data-stu-id="5be06-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-232">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-232">Definition</span></span>

<span data-ttu-id="5be06-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-236">Keywords</span></span>

<span data-ttu-id="5be06-237">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-237"></span></span>
|<span data-ttu-id="5be06-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-239">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-239">dl#</span></span>  <br/> <span data-ttu-id="5be06-240">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-240">driver license</span></span>  <br/> <span data-ttu-id="5be06-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-241">driver license number</span></span>  <br/> <span data-ttu-id="5be06-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-242">driver licence</span></span>  <br/> <span data-ttu-id="5be06-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-243">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-244">drivers license</span></span>  <br/> <span data-ttu-id="5be06-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-245">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-246">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-247">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-248">driving license number</span></span>  <br/> <span data-ttu-id="5be06-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-249">dlno#</span></span>  <br/> <span data-ttu-id="5be06-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5be06-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="5be06-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="5be06-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5be06-252">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-252">Format</span></span>

<span data-ttu-id="5be06-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-254">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-254">Pattern</span></span>

<span data-ttu-id="5be06-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="5be06-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="5be06-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="5be06-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5be06-257">A space (optional)</span></span>
    
- <span data-ttu-id="5be06-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-259">Checksum</span></span>

<span data-ttu-id="5be06-260">No</span><span class="sxs-lookup"><span data-stu-id="5be06-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-261">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-261">Definition</span></span>

<span data-ttu-id="5be06-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5be06-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-265">Keywords</span></span>

<span data-ttu-id="5be06-266">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-266"></span></span>
|<span data-ttu-id="5be06-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-268">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-268">dl#</span></span>  <br/> <span data-ttu-id="5be06-269">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-269">driver license</span></span>  <br/> <span data-ttu-id="5be06-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-270">driver license number</span></span>  <br/> <span data-ttu-id="5be06-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-271">driver licence</span></span>  <br/> <span data-ttu-id="5be06-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-272">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-273">drivers license</span></span>  <br/> <span data-ttu-id="5be06-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-274">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-275">driver's license</span></span>  <br/> <span data-ttu-id="5be06-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-276">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-277">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-278">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-279">driving license number</span></span>  <br/> <span data-ttu-id="5be06-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-280">dlno#</span></span>  <br/> <span data-ttu-id="5be06-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="5be06-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="5be06-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="5be06-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5be06-283">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-283">Format</span></span>

<span data-ttu-id="5be06-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-285">Pattern</span></span>

<span data-ttu-id="5be06-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-287">Checksum</span></span>

<span data-ttu-id="5be06-288">Sí</span><span class="sxs-lookup"><span data-stu-id="5be06-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-289">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-289">Definition</span></span>

<span data-ttu-id="5be06-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5be06-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-293">Keywords</span></span>

<span data-ttu-id="5be06-294">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-294"></span></span>
|<span data-ttu-id="5be06-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-296">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-296">dl#</span></span>  <br/> <span data-ttu-id="5be06-297">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-297">driver license</span></span>  <br/> <span data-ttu-id="5be06-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-298">driver license number</span></span>  <br/> <span data-ttu-id="5be06-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-299">driver licence</span></span>  <br/> <span data-ttu-id="5be06-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-300">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-301">drivers license</span></span>  <br/> <span data-ttu-id="5be06-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-302">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-303">driver's license</span></span>  <br/> <span data-ttu-id="5be06-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-304">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-305">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-306">driving license number</span></span>  <br/> <span data-ttu-id="5be06-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-307">dlno#</span></span>  <br/> <span data-ttu-id="5be06-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="5be06-308">kørekort</span></span>  <br/> <span data-ttu-id="5be06-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="5be06-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="5be06-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="5be06-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5be06-311">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-311">Format</span></span>

<span data-ttu-id="5be06-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-313">Pattern</span></span>

<span data-ttu-id="5be06-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5be06-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5be06-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5be06-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-317">Checksum</span></span>

<span data-ttu-id="5be06-318">No</span><span class="sxs-lookup"><span data-stu-id="5be06-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-319">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-319">Definition</span></span>

<span data-ttu-id="5be06-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-323">Keywords</span></span>

<span data-ttu-id="5be06-324">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-324"></span></span>
|<span data-ttu-id="5be06-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-326">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-326">dl#</span></span>  <br/> <span data-ttu-id="5be06-327">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-327">driver license</span></span>  <br/> <span data-ttu-id="5be06-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-328">driver license number</span></span>  <br/> <span data-ttu-id="5be06-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-329">driver license number</span></span>  <br/> <span data-ttu-id="5be06-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-330">driver licence</span></span>  <br/> <span data-ttu-id="5be06-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-331">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-332">drivers license</span></span>  <br/> <span data-ttu-id="5be06-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-333">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-334">driver's license</span></span>  <br/> <span data-ttu-id="5be06-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-335">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-336">driving license number</span></span>  <br/> <span data-ttu-id="5be06-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-337">dlno#</span></span>  <br/> <span data-ttu-id="5be06-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5be06-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="5be06-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="5be06-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="5be06-340">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-340">Format</span></span>

<span data-ttu-id="5be06-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="5be06-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-342">Pattern</span></span>

<span data-ttu-id="5be06-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="5be06-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5be06-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-344">Six digits</span></span> 
    
- <span data-ttu-id="5be06-345">Un guión</span><span class="sxs-lookup"><span data-stu-id="5be06-345">A hyphen</span></span>
    
-  <span data-ttu-id="5be06-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5be06-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-347">Checksum</span></span>

<span data-ttu-id="5be06-348">No</span><span class="sxs-lookup"><span data-stu-id="5be06-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-349">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-349">Definition</span></span>

<span data-ttu-id="5be06-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-353">Keywords</span></span>

<span data-ttu-id="5be06-354">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-354"></span></span>
|<span data-ttu-id="5be06-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-356">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-356">dl#</span></span>  <br/> <span data-ttu-id="5be06-357">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-357">driver license</span></span>  <br/> <span data-ttu-id="5be06-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-358">driver license number</span></span>  <br/> <span data-ttu-id="5be06-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-359">driver licence</span></span>  <br/> <span data-ttu-id="5be06-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-360">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-361">drivers license</span></span>  <br/> <span data-ttu-id="5be06-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-362">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-363">driver's license</span></span>  <br/> <span data-ttu-id="5be06-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-364">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-365">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-366">driving license number</span></span>  <br/> <span data-ttu-id="5be06-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-367">dlno#</span></span>  <br/> <span data-ttu-id="5be06-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="5be06-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="5be06-369">Francia</span><span class="sxs-lookup"><span data-stu-id="5be06-369">France</span></span>

<span data-ttu-id="5be06-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5be06-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="5be06-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="5be06-371">Germany</span></span>

<span data-ttu-id="5be06-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5be06-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="5be06-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="5be06-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5be06-374">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-374">Format</span></span>

<span data-ttu-id="5be06-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-376">Pattern</span></span>

 <span data-ttu-id="5be06-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5be06-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-378">Checksum</span></span>

<span data-ttu-id="5be06-379">No</span><span class="sxs-lookup"><span data-stu-id="5be06-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-380">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-380">Definition</span></span>

<span data-ttu-id="5be06-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-384">Keywords</span></span>

<span data-ttu-id="5be06-385">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-385"></span></span>
|<span data-ttu-id="5be06-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-387">Biblioteca #</span><span class="sxs-lookup"><span data-stu-id="5be06-387">dlL#</span></span>  <br/> <span data-ttu-id="5be06-388">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-388">driver license</span></span>  <br/> <span data-ttu-id="5be06-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-389">driver license number</span></span>  <br/> <span data-ttu-id="5be06-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-390">driver licence</span></span>  <br/> <span data-ttu-id="5be06-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-391">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-392">drivers license</span></span>  <br/> <span data-ttu-id="5be06-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-393">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-394">driver's license</span></span>  <br/> <span data-ttu-id="5be06-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-395">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-396">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-397">driving license number</span></span>  <br/> <span data-ttu-id="5be06-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-398">dlno#</span></span>  <br/> <span data-ttu-id="5be06-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5be06-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="5be06-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="5be06-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="5be06-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="5be06-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5be06-402">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-402">Format</span></span>

<span data-ttu-id="5be06-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-404">Pattern</span></span>

<span data-ttu-id="5be06-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5be06-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5be06-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5be06-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-408">Checksum</span></span>

<span data-ttu-id="5be06-409">No</span><span class="sxs-lookup"><span data-stu-id="5be06-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-410">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-410">Definition</span></span>

<span data-ttu-id="5be06-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-414">Keywords</span></span>

<span data-ttu-id="5be06-415">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-415"></span></span>
|<span data-ttu-id="5be06-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-417">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-417">dl#</span></span>  <br/> <span data-ttu-id="5be06-418">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-418">driver license</span></span>  <br/> <span data-ttu-id="5be06-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-419">driver license number</span></span>  <br/> <span data-ttu-id="5be06-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-420">driver licence</span></span>  <br/> <span data-ttu-id="5be06-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-421">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-422">drivers license</span></span>  <br/> <span data-ttu-id="5be06-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-423">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-424">driver's license</span></span>  <br/> <span data-ttu-id="5be06-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-425">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-426">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-427">driving license number</span></span>  <br/> <span data-ttu-id="5be06-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-428">dlno#</span></span>  <br/> <span data-ttu-id="5be06-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="5be06-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="5be06-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="5be06-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5be06-431">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-431">Format</span></span>

<span data-ttu-id="5be06-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="5be06-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-433">Pattern</span></span>

<span data-ttu-id="5be06-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="5be06-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="5be06-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-435">Six digits</span></span>
    
- <span data-ttu-id="5be06-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-437">Checksum</span></span>

<span data-ttu-id="5be06-438">No</span><span class="sxs-lookup"><span data-stu-id="5be06-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-439">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-439">Definition</span></span>

<span data-ttu-id="5be06-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-443">Keywords</span></span>

<span data-ttu-id="5be06-444">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-444"></span></span>
|<span data-ttu-id="5be06-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-446">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-446">dl#</span></span>  <br/> <span data-ttu-id="5be06-447">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-447">driver license</span></span>  <br/> <span data-ttu-id="5be06-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-448">driver license number</span></span>  <br/> <span data-ttu-id="5be06-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-449">driver licence</span></span>  <br/> <span data-ttu-id="5be06-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-450">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-451">drivers license</span></span>  <br/> <span data-ttu-id="5be06-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-452">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-453">driver's license</span></span>  <br/> <span data-ttu-id="5be06-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-454">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-455">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-456">driving license number</span></span>  <br/> <span data-ttu-id="5be06-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-457">dlno#</span></span>  <br/> <span data-ttu-id="5be06-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="5be06-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="5be06-459">Italia</span><span class="sxs-lookup"><span data-stu-id="5be06-459">Italy</span></span>

<span data-ttu-id="5be06-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5be06-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="5be06-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="5be06-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5be06-462">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-462">Format</span></span>

<span data-ttu-id="5be06-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-464">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-464">Pattern</span></span>

<span data-ttu-id="5be06-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5be06-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="5be06-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5be06-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-468">Checksum</span></span>

<span data-ttu-id="5be06-469">No</span><span class="sxs-lookup"><span data-stu-id="5be06-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-470">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-470">Definition</span></span>

<span data-ttu-id="5be06-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-474">Keywords</span></span>

<span data-ttu-id="5be06-475">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-475"></span></span>
|<span data-ttu-id="5be06-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-477">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-477">dl#</span></span>  <br/> <span data-ttu-id="5be06-478">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-478">driver license</span></span>  <br/> <span data-ttu-id="5be06-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-479">driver license number</span></span>  <br/> <span data-ttu-id="5be06-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-480">driver licence</span></span>  <br/> <span data-ttu-id="5be06-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-481">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-482">drivers license</span></span>  <br/> <span data-ttu-id="5be06-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-483">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-484">driver's license</span></span>  <br/> <span data-ttu-id="5be06-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-485">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-486">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-487">driving license number</span></span>  <br/> <span data-ttu-id="5be06-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-488">dlno#</span></span>  <br/> <span data-ttu-id="5be06-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="5be06-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="5be06-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="5be06-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5be06-491">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-491">Format</span></span>

<span data-ttu-id="5be06-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-493">Pattern</span></span>

 <span data-ttu-id="5be06-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5be06-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-495">Checksum</span></span>

<span data-ttu-id="5be06-496">No</span><span class="sxs-lookup"><span data-stu-id="5be06-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-497">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-497">Definition</span></span>

<span data-ttu-id="5be06-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-501">Keywords</span></span>

<span data-ttu-id="5be06-502">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-502"></span></span>
|<span data-ttu-id="5be06-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-504">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-504">dl#</span></span>  <br/> <span data-ttu-id="5be06-505">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-505">driver license</span></span>  <br/> <span data-ttu-id="5be06-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-506">driver license number</span></span>  <br/> <span data-ttu-id="5be06-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-507">driver licence</span></span>  <br/> <span data-ttu-id="5be06-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-508">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-509">drivers license</span></span>  <br/> <span data-ttu-id="5be06-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-510">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-511">driver's license</span></span>  <br/> <span data-ttu-id="5be06-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-512">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-513">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-514">driving license number</span></span>  <br/> <span data-ttu-id="5be06-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-515">dlno#</span></span>  <br/> <span data-ttu-id="5be06-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="5be06-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="5be06-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="5be06-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5be06-518">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-518">Format</span></span>

<span data-ttu-id="5be06-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-520">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-520">Pattern</span></span>

 <span data-ttu-id="5be06-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5be06-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-522">Checksum</span></span>

<span data-ttu-id="5be06-523">No</span><span class="sxs-lookup"><span data-stu-id="5be06-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-524">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-524">Definition</span></span>

<span data-ttu-id="5be06-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-528">Keywords</span></span>

<span data-ttu-id="5be06-529">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-529"></span></span>
|<span data-ttu-id="5be06-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-531">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-531">dl#</span></span>  <br/> <span data-ttu-id="5be06-532">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-532">driver license</span></span>  <br/> <span data-ttu-id="5be06-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-533">driver license number</span></span>  <br/> <span data-ttu-id="5be06-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-534">driver licence</span></span>  <br/> <span data-ttu-id="5be06-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-535">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-536">drivers license</span></span>  <br/> <span data-ttu-id="5be06-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-537">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-538">driver's license</span></span>  <br/> <span data-ttu-id="5be06-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-539">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-540">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-541">driving license number</span></span>  <br/> <span data-ttu-id="5be06-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-542">dlno#</span></span>  <br/> <span data-ttu-id="5be06-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="5be06-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="5be06-544">Malta</span><span class="sxs-lookup"><span data-stu-id="5be06-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5be06-545">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-545">Format</span></span>

<span data-ttu-id="5be06-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="5be06-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-547">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-547">Pattern</span></span>

<span data-ttu-id="5be06-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5be06-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="5be06-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="5be06-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5be06-550">A space (optional)</span></span>
    
- <span data-ttu-id="5be06-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-551">Three digits</span></span>
    
- <span data-ttu-id="5be06-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5be06-552">A space (optional)</span></span>
    
- <span data-ttu-id="5be06-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-554">Checksum</span></span>

<span data-ttu-id="5be06-555">No</span><span class="sxs-lookup"><span data-stu-id="5be06-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-556">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-556">Definition</span></span>

<span data-ttu-id="5be06-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-560">Keywords</span></span>

<span data-ttu-id="5be06-561">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-561"></span></span>
|<span data-ttu-id="5be06-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-563">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-563">dl#</span></span>  <br/> <span data-ttu-id="5be06-564">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-564">driver license</span></span>  <br/> <span data-ttu-id="5be06-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-565">driver license number</span></span>  <br/> <span data-ttu-id="5be06-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-566">driver licence</span></span>  <br/> <span data-ttu-id="5be06-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-567">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-568">drivers license</span></span>  <br/> <span data-ttu-id="5be06-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-569">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-570">driver's license</span></span>  <br/> <span data-ttu-id="5be06-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-571">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-572">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-573">driving license number</span></span>  <br/> <span data-ttu-id="5be06-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-574">dlno#</span></span>  <br/> <span data-ttu-id="5be06-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="5be06-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="5be06-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="5be06-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5be06-577">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-577">Format</span></span>

<span data-ttu-id="5be06-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-579">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-579">Pattern</span></span>

<span data-ttu-id="5be06-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-581">Checksum</span></span>

<span data-ttu-id="5be06-582">No</span><span class="sxs-lookup"><span data-stu-id="5be06-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-583">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-583">Definition</span></span>

<span data-ttu-id="5be06-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-587">Keywords</span></span>

<span data-ttu-id="5be06-588">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-588"></span></span>
|<span data-ttu-id="5be06-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-590">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-590">dl#</span></span>  <br/> <span data-ttu-id="5be06-591">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-591">driver license</span></span>  <br/> <span data-ttu-id="5be06-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-592">driver license number</span></span>  <br/> <span data-ttu-id="5be06-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-593">driver licence</span></span>  <br/> <span data-ttu-id="5be06-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-594">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-595">drivers license</span></span>  <br/> <span data-ttu-id="5be06-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-596">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-597">driver's license</span></span>  <br/> <span data-ttu-id="5be06-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-598">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-599">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-600">driving license number</span></span>  <br/> <span data-ttu-id="5be06-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-601">dlno#</span></span>  <br/> <span data-ttu-id="5be06-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5be06-602">permis de conduire</span></span>  <br/> <span data-ttu-id="5be06-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5be06-603">rijbewijs</span></span>  <br/> <span data-ttu-id="5be06-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5be06-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="5be06-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="5be06-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="5be06-606">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-606">Format</span></span>

<span data-ttu-id="5be06-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="5be06-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-608">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-608">Pattern</span></span>

<span data-ttu-id="5be06-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="5be06-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="5be06-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-610">Five digits</span></span> 
    
- <span data-ttu-id="5be06-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="5be06-611">A forward slash</span></span>
    
- <span data-ttu-id="5be06-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-612">Two digits</span></span>
    
- <span data-ttu-id="5be06-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="5be06-613">A forward slash</span></span>
    
- <span data-ttu-id="5be06-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-615">Checksum</span></span>

<span data-ttu-id="5be06-616">No</span><span class="sxs-lookup"><span data-stu-id="5be06-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-617">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-617">Definition</span></span>

<span data-ttu-id="5be06-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-621">Keywords</span></span>

<span data-ttu-id="5be06-622">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-622"></span></span>
|<span data-ttu-id="5be06-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-624">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-624">dl#</span></span>  <br/> <span data-ttu-id="5be06-625">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-625">driver license</span></span>  <br/> <span data-ttu-id="5be06-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-626">driver license number</span></span>  <br/> <span data-ttu-id="5be06-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-627">driver licence</span></span>  <br/> <span data-ttu-id="5be06-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-628">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-629">drivers license</span></span>  <br/> <span data-ttu-id="5be06-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-630">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-631">driver's license</span></span>  <br/> <span data-ttu-id="5be06-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-632">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-633">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-634">driving license number</span></span>  <br/> <span data-ttu-id="5be06-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-635">dlno#</span></span>  <br/> <span data-ttu-id="5be06-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="5be06-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="5be06-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="5be06-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5be06-638">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-638">Format</span></span>

<span data-ttu-id="5be06-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="5be06-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-640">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-640">Pattern</span></span>

<span data-ttu-id="5be06-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="5be06-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="5be06-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5be06-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="5be06-643">A hyphen</span></span>
    
- <span data-ttu-id="5be06-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-644">Six digits</span></span>
    
- <span data-ttu-id="5be06-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="5be06-645">A space</span></span>
    
- <span data-ttu-id="5be06-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="5be06-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-647">Checksum</span></span>

<span data-ttu-id="5be06-648">No</span><span class="sxs-lookup"><span data-stu-id="5be06-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-649">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-649">Definition</span></span>

<span data-ttu-id="5be06-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-653">Keywords</span></span>

<span data-ttu-id="5be06-654">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-654"></span></span>
|<span data-ttu-id="5be06-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-656">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-656">dl#</span></span>  <br/> <span data-ttu-id="5be06-657">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-657">driver license</span></span>  <br/> <span data-ttu-id="5be06-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-658">driver license number</span></span>  <br/> <span data-ttu-id="5be06-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-659">driver licence</span></span>  <br/> <span data-ttu-id="5be06-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-660">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-661">drivers license</span></span>  <br/> <span data-ttu-id="5be06-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-662">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-663">driver's license</span></span>  <br/> <span data-ttu-id="5be06-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-664">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-665">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-666">driving license number</span></span>  <br/> <span data-ttu-id="5be06-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-667">dlno#</span></span>  <br/> <span data-ttu-id="5be06-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="5be06-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="5be06-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="5be06-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5be06-670">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-670">Format</span></span>

<span data-ttu-id="5be06-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-672">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-672">Pattern</span></span>

<span data-ttu-id="5be06-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="5be06-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="5be06-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="5be06-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="5be06-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-676">Checksum</span></span>

<span data-ttu-id="5be06-677">No</span><span class="sxs-lookup"><span data-stu-id="5be06-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-678">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-678">Definition</span></span>

<span data-ttu-id="5be06-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-682">Keywords</span></span>

<span data-ttu-id="5be06-683">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-683"></span></span>
|<span data-ttu-id="5be06-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-685">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-685">dl#</span></span>  <br/> <span data-ttu-id="5be06-686">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-686">driver license</span></span>  <br/> <span data-ttu-id="5be06-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-687">driver license number</span></span>  <br/> <span data-ttu-id="5be06-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-688">driver licence</span></span>  <br/> <span data-ttu-id="5be06-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-689">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-690">drivers license</span></span>  <br/> <span data-ttu-id="5be06-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-691">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-692">driver's license</span></span>  <br/> <span data-ttu-id="5be06-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-693">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-694">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-695">driving license number</span></span>  <br/> <span data-ttu-id="5be06-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-696">dlno#</span></span>  <br/> <span data-ttu-id="5be06-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="5be06-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="5be06-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="5be06-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5be06-699">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-699">Format</span></span>

<span data-ttu-id="5be06-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-701">Pattern</span></span>

<span data-ttu-id="5be06-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="5be06-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="5be06-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="5be06-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5be06-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-705">Checksum</span></span>

<span data-ttu-id="5be06-706">No</span><span class="sxs-lookup"><span data-stu-id="5be06-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-707">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-707">Definition</span></span>

<span data-ttu-id="5be06-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-711">Keywords</span></span>

<span data-ttu-id="5be06-712">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-712"></span></span>
|<span data-ttu-id="5be06-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-714">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-714">dl#</span></span>  <br/> <span data-ttu-id="5be06-715">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-715">driver license</span></span>  <br/> <span data-ttu-id="5be06-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-716">driver license number</span></span>  <br/> <span data-ttu-id="5be06-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-717">driver licence</span></span>  <br/> <span data-ttu-id="5be06-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-718">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-719">drivers license</span></span>  <br/> <span data-ttu-id="5be06-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-720">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-721">driver's license</span></span>  <br/> <span data-ttu-id="5be06-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-722">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-723">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-724">driving license number</span></span>  <br/> <span data-ttu-id="5be06-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-725">dlno#</span></span>  <br/> <span data-ttu-id="5be06-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="5be06-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="5be06-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="5be06-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5be06-728">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-728">Format</span></span>

<span data-ttu-id="5be06-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5be06-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-730">Pattern</span></span>

<span data-ttu-id="5be06-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5be06-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-732">Checksum</span></span>

<span data-ttu-id="5be06-733">No</span><span class="sxs-lookup"><span data-stu-id="5be06-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-734">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-734">Definition</span></span>

<span data-ttu-id="5be06-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-738">Keywords</span></span>

<span data-ttu-id="5be06-739">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-739"></span></span>
|<span data-ttu-id="5be06-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-741">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-741">dl#</span></span>  <br/> <span data-ttu-id="5be06-742">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-742">driver license</span></span>  <br/> <span data-ttu-id="5be06-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-743">driver license number</span></span>  <br/> <span data-ttu-id="5be06-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-744">driver licence</span></span>  <br/> <span data-ttu-id="5be06-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-745">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-746">drivers license</span></span>  <br/> <span data-ttu-id="5be06-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-747">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-748">driver's license</span></span>  <br/> <span data-ttu-id="5be06-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-749">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-750">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-751">driving license number</span></span>  <br/> <span data-ttu-id="5be06-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-752">dlno#</span></span>  <br/> <span data-ttu-id="5be06-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="5be06-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="5be06-754">España</span><span class="sxs-lookup"><span data-stu-id="5be06-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5be06-755">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-755">Format</span></span>

<span data-ttu-id="5be06-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="5be06-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-757">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-757">Pattern</span></span>

<span data-ttu-id="5be06-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="5be06-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="5be06-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-759">Eight digits</span></span> 
    
- <span data-ttu-id="5be06-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5be06-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-761">Checksum</span></span>

<span data-ttu-id="5be06-762">Sí</span><span class="sxs-lookup"><span data-stu-id="5be06-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-763">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-763">Definition</span></span>

<span data-ttu-id="5be06-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5be06-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-767">Keywords</span></span>

<span data-ttu-id="5be06-768">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-768"></span></span>
|<span data-ttu-id="5be06-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-770">dlno#</span></span>  <br/> <span data-ttu-id="5be06-771">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-771">dl#</span></span>  <br/> <span data-ttu-id="5be06-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-772">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-773">driver licence</span></span>  <br/> <span data-ttu-id="5be06-774">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-774">driver license</span></span>  <br/> <span data-ttu-id="5be06-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-775">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-776">drivers license</span></span>  <br/> <span data-ttu-id="5be06-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5be06-777">driver's licence</span></span>  <br/> <span data-ttu-id="5be06-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-778">driver's license</span></span>  <br/> <span data-ttu-id="5be06-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="5be06-779">driving licence</span></span>  <br/> <span data-ttu-id="5be06-780">driving license</span><span class="sxs-lookup"><span data-stu-id="5be06-780">driving license</span></span>  <br/> <span data-ttu-id="5be06-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-781">driver licence number</span></span>  <br/> <span data-ttu-id="5be06-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-782">driver license number</span></span>  <br/> <span data-ttu-id="5be06-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="5be06-783">drivers licence number</span></span>  <br/> <span data-ttu-id="5be06-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="5be06-784">drivers license number</span></span>  <br/> <span data-ttu-id="5be06-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-785">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-786">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-787">driving licence number</span></span>  <br/> <span data-ttu-id="5be06-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-788">driving license number</span></span>  <br/> <span data-ttu-id="5be06-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-789">driving permit</span></span>  <br/> <span data-ttu-id="5be06-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-790">driving permit number</span></span>  <br/> <span data-ttu-id="5be06-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="5be06-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-792">permiso conducción</span></span>  <br/> <span data-ttu-id="5be06-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="5be06-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="5be06-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="5be06-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="5be06-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-796">licencia conducir</span></span>  <br/> <span data-ttu-id="5be06-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="5be06-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="5be06-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="5be06-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-800">permiso conducir</span></span>  <br/> <span data-ttu-id="5be06-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="5be06-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="5be06-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="5be06-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="5be06-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="5be06-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="5be06-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="5be06-805">Formato</span><span class="sxs-lookup"><span data-stu-id="5be06-805">Format</span></span>

<span data-ttu-id="5be06-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="5be06-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5be06-807">Patrón</span><span class="sxs-lookup"><span data-stu-id="5be06-807">Pattern</span></span>

<span data-ttu-id="5be06-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="5be06-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5be06-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-809">Six digits</span></span> 
    
- <span data-ttu-id="5be06-810">Un guión</span><span class="sxs-lookup"><span data-stu-id="5be06-810">A hyphen</span></span>
    
- <span data-ttu-id="5be06-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="5be06-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5be06-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5be06-812">Checksum</span></span>

<span data-ttu-id="5be06-813">No</span><span class="sxs-lookup"><span data-stu-id="5be06-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5be06-814">Definición</span><span class="sxs-lookup"><span data-stu-id="5be06-814">Definition</span></span>

<span data-ttu-id="5be06-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be06-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5be06-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5be06-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5be06-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5be06-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="5be06-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5be06-818">Keywords</span></span>

<span data-ttu-id="5be06-819">| |</span><span class="sxs-lookup"><span data-stu-id="5be06-819"></span></span>
|<span data-ttu-id="5be06-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5be06-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5be06-821">listas #</span><span class="sxs-lookup"><span data-stu-id="5be06-821">dl#</span></span>  <br/> <span data-ttu-id="5be06-822">driver license</span><span class="sxs-lookup"><span data-stu-id="5be06-822">driver license</span></span>  <br/> <span data-ttu-id="5be06-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5be06-823">driver license number</span></span>  <br/> <span data-ttu-id="5be06-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-824">driver licence</span></span>  <br/> <span data-ttu-id="5be06-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5be06-825">drivers lic.</span></span>  <br/> <span data-ttu-id="5be06-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="5be06-826">drivers license</span></span>  <br/> <span data-ttu-id="5be06-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5be06-827">drivers licence</span></span>  <br/> <span data-ttu-id="5be06-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="5be06-828">driver's license</span></span>  <br/> <span data-ttu-id="5be06-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-829">driver's license number</span></span>  <br/> <span data-ttu-id="5be06-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5be06-830">driver's licence number</span></span>  <br/> <span data-ttu-id="5be06-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5be06-831">driving license number</span></span>  <br/> <span data-ttu-id="5be06-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="5be06-832">dlno#</span></span>  <br/> <span data-ttu-id="5be06-833">körkort</span><span class="sxs-lookup"><span data-stu-id="5be06-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="5be06-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="5be06-834">UK</span></span>

<span data-ttu-id="5be06-835">Para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="5be06-835">For details, see the section "U.K.</span></span> <span data-ttu-id="5be06-836">Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5be06-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5be06-837">Ver también</span><span class="sxs-lookup"><span data-stu-id="5be06-837">See also</span></span>

[<span data-ttu-id="5be06-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="5be06-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

