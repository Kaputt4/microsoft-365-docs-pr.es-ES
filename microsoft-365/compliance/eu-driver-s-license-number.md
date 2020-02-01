---
title: Número de permiso de conducción de la UE
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592661"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="5c465-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="5c465-104">EU Driver's License Number</span></span>

<span data-ttu-id="5c465-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE.</span><span class="sxs-lookup"><span data-stu-id="5c465-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="5c465-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="5c465-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5c465-107">Austria</span><span class="sxs-lookup"><span data-stu-id="5c465-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5c465-108">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-108">Format</span></span>

<span data-ttu-id="5c465-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-110">Pattern</span></span>

<span data-ttu-id="5c465-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-112">Checksum</span></span>

<span data-ttu-id="5c465-113">No</span><span class="sxs-lookup"><span data-stu-id="5c465-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-114">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-114">Definition</span></span>

<span data-ttu-id="5c465-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="5c465-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-118">Keywords</span></span>

<span data-ttu-id="5c465-119">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-119">| |</span></span>
|<span data-ttu-id="5c465-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-121">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-121">dl#</span></span>  <br/> <span data-ttu-id="5c465-122">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-122">driver license</span></span>  <br/> <span data-ttu-id="5c465-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-123">driver license number</span></span>  <br/> <span data-ttu-id="5c465-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-124">driver licence</span></span>  <br/> <span data-ttu-id="5c465-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-125">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-126">drivers license</span></span>  <br/> <span data-ttu-id="5c465-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5c465-127">driver's licence</span></span>  <br/> <span data-ttu-id="5c465-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-128">driver's license</span></span>  <br/> <span data-ttu-id="5c465-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-129">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="5c465-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-131">driving license number</span></span>  <br/> <span data-ttu-id="5c465-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-132">dlno#</span></span>  <br/> <span data-ttu-id="5c465-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="5c465-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="5c465-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="5c465-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="5c465-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="5c465-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5c465-136">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-136">Format</span></span>

<span data-ttu-id="5c465-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-138">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-138">Pattern</span></span>

<span data-ttu-id="5c465-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-140">Checksum</span></span>

<span data-ttu-id="5c465-141">No</span><span class="sxs-lookup"><span data-stu-id="5c465-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-142">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-142">Definition</span></span>

<span data-ttu-id="5c465-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5c465-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-146">Keywords</span></span>

<span data-ttu-id="5c465-147">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-147">| |</span></span>
|<span data-ttu-id="5c465-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-149">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-149">dl#</span></span>  <br/> <span data-ttu-id="5c465-150">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-150">driver license</span></span>  <br/> <span data-ttu-id="5c465-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-151">driver license number</span></span>  <br/> <span data-ttu-id="5c465-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-152">driver licence</span></span>  <br/> <span data-ttu-id="5c465-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-153">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-154">drivers license</span></span>  <br/> <span data-ttu-id="5c465-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-155">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-156">driver's license</span></span>  <br/> <span data-ttu-id="5c465-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-157">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-158">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-159">dlno#</span></span>  <br/> <span data-ttu-id="5c465-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5c465-160">rijbewijs</span></span>  <br/> <span data-ttu-id="5c465-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5c465-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="5c465-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5c465-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="5c465-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5c465-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="5c465-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5c465-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="5c465-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5c465-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="5c465-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5c465-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="5c465-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5c465-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="5c465-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="5c465-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5c465-169">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-169">Format</span></span>

<span data-ttu-id="5c465-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-171">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-171">Pattern</span></span>

<span data-ttu-id="5c465-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-173">Checksum</span></span>

<span data-ttu-id="5c465-174">No</span><span class="sxs-lookup"><span data-stu-id="5c465-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-175">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-175">Definition</span></span>

<span data-ttu-id="5c465-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="5c465-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-179">Keywords</span></span>

<span data-ttu-id="5c465-180">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-180">| |</span></span>
|<span data-ttu-id="5c465-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-182">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-182">dl#</span></span>  <br/> <span data-ttu-id="5c465-183">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-183">driver license</span></span>  <br/> <span data-ttu-id="5c465-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-184">driver license number</span></span>  <br/> <span data-ttu-id="5c465-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-185">driver licence</span></span>  <br/> <span data-ttu-id="5c465-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-186">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-187">drivers license</span></span>  <br/> <span data-ttu-id="5c465-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-188">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-189">driver's license</span></span>  <br/> <span data-ttu-id="5c465-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-190">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-191">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-192">driving license number</span></span>  <br/> <span data-ttu-id="5c465-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-193">dlno#</span></span>  <br/> <span data-ttu-id="5c465-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="5c465-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="5c465-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="5c465-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="5c465-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="5c465-196">сумпс</span></span>  <br/> <span data-ttu-id="5c465-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="5c465-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="5c465-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="5c465-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5c465-199">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-199">Format</span></span>

<span data-ttu-id="5c465-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-201">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-201">Pattern</span></span>

<span data-ttu-id="5c465-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-203">Checksum</span></span>

<span data-ttu-id="5c465-204">No</span><span class="sxs-lookup"><span data-stu-id="5c465-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-205">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-205">Definition</span></span>

<span data-ttu-id="5c465-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5c465-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-209">Keywords</span></span>

<span data-ttu-id="5c465-210">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-210">| |</span></span>
|<span data-ttu-id="5c465-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-212">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-212">dl#</span></span>  <br/> <span data-ttu-id="5c465-213">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-213">driver license</span></span>  <br/> <span data-ttu-id="5c465-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-214">driver license number</span></span>  <br/> <span data-ttu-id="5c465-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-215">driver licence</span></span>  <br/> <span data-ttu-id="5c465-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-216">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-217">drivers license</span></span>  <br/> <span data-ttu-id="5c465-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-218">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-219">driver's license</span></span>  <br/> <span data-ttu-id="5c465-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-220">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-221">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-222">driving license number</span></span>  <br/> <span data-ttu-id="5c465-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-223">dlno#</span></span>  <br/> <span data-ttu-id="5c465-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="5c465-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="5c465-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="5c465-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5c465-226">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-226">Format</span></span>

<span data-ttu-id="5c465-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-228">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-228">Pattern</span></span>

<span data-ttu-id="5c465-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-230">Checksum</span></span>

<span data-ttu-id="5c465-231">No</span><span class="sxs-lookup"><span data-stu-id="5c465-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-232">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-232">Definition</span></span>

<span data-ttu-id="5c465-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-236">Keywords</span></span>

<span data-ttu-id="5c465-237">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-237">| |</span></span>
|<span data-ttu-id="5c465-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-239">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-239">dl#</span></span>  <br/> <span data-ttu-id="5c465-240">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-240">driver license</span></span>  <br/> <span data-ttu-id="5c465-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-241">driver license number</span></span>  <br/> <span data-ttu-id="5c465-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-242">driver licence</span></span>  <br/> <span data-ttu-id="5c465-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-243">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-244">drivers license</span></span>  <br/> <span data-ttu-id="5c465-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-245">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-246">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-247">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-248">driving license number</span></span>  <br/> <span data-ttu-id="5c465-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-249">dlno#</span></span>  <br/> <span data-ttu-id="5c465-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5c465-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="5c465-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="5c465-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5c465-252">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-252">Format</span></span>

<span data-ttu-id="5c465-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-254">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-254">Pattern</span></span>

<span data-ttu-id="5c465-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="5c465-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="5c465-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="5c465-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5c465-257">A space (optional)</span></span>
    
- <span data-ttu-id="5c465-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-259">Checksum</span></span>

<span data-ttu-id="5c465-260">No</span><span class="sxs-lookup"><span data-stu-id="5c465-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-261">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-261">Definition</span></span>

<span data-ttu-id="5c465-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5c465-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-265">Keywords</span></span>

<span data-ttu-id="5c465-266">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-266">| |</span></span>
|<span data-ttu-id="5c465-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-268">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-268">dl#</span></span>  <br/> <span data-ttu-id="5c465-269">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-269">driver license</span></span>  <br/> <span data-ttu-id="5c465-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-270">driver license number</span></span>  <br/> <span data-ttu-id="5c465-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-271">driver licence</span></span>  <br/> <span data-ttu-id="5c465-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-272">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-273">drivers license</span></span>  <br/> <span data-ttu-id="5c465-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-274">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-275">driver's license</span></span>  <br/> <span data-ttu-id="5c465-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-276">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-277">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-278">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-279">driving license number</span></span>  <br/> <span data-ttu-id="5c465-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-280">dlno#</span></span>  <br/> <span data-ttu-id="5c465-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="5c465-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="5c465-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="5c465-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5c465-283">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-283">Format</span></span>

<span data-ttu-id="5c465-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-285">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-285">Pattern</span></span>

<span data-ttu-id="5c465-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-287">Checksum</span></span>

<span data-ttu-id="5c465-288">Sí</span><span class="sxs-lookup"><span data-stu-id="5c465-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-289">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-289">Definition</span></span>

<span data-ttu-id="5c465-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5c465-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-293">Keywords</span></span>

<span data-ttu-id="5c465-294">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-294">| |</span></span>
|<span data-ttu-id="5c465-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-296">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-296">dl#</span></span>  <br/> <span data-ttu-id="5c465-297">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-297">driver license</span></span>  <br/> <span data-ttu-id="5c465-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-298">driver license number</span></span>  <br/> <span data-ttu-id="5c465-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-299">driver licence</span></span>  <br/> <span data-ttu-id="5c465-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-300">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-301">drivers license</span></span>  <br/> <span data-ttu-id="5c465-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-302">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-303">driver's license</span></span>  <br/> <span data-ttu-id="5c465-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-304">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-305">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-306">driving license number</span></span>  <br/> <span data-ttu-id="5c465-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-307">dlno#</span></span>  <br/> <span data-ttu-id="5c465-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="5c465-308">kørekort</span></span>  <br/> <span data-ttu-id="5c465-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="5c465-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="5c465-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="5c465-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5c465-311">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-311">Format</span></span>

<span data-ttu-id="5c465-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-313">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-313">Pattern</span></span>

<span data-ttu-id="5c465-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5c465-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5c465-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5c465-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-317">Checksum</span></span>

<span data-ttu-id="5c465-318">No</span><span class="sxs-lookup"><span data-stu-id="5c465-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-319">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-319">Definition</span></span>

<span data-ttu-id="5c465-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-323">Keywords</span></span>

<span data-ttu-id="5c465-324">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-324">| |</span></span>
|<span data-ttu-id="5c465-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-326">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-326">dl#</span></span>  <br/> <span data-ttu-id="5c465-327">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-327">driver license</span></span>  <br/> <span data-ttu-id="5c465-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-328">driver license number</span></span>  <br/> <span data-ttu-id="5c465-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-329">driver license number</span></span>  <br/> <span data-ttu-id="5c465-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-330">driver licence</span></span>  <br/> <span data-ttu-id="5c465-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-331">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-332">drivers license</span></span>  <br/> <span data-ttu-id="5c465-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-333">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-334">driver's license</span></span>  <br/> <span data-ttu-id="5c465-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-335">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-336">driving license number</span></span>  <br/> <span data-ttu-id="5c465-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-337">dlno#</span></span>  <br/> <span data-ttu-id="5c465-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5c465-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="5c465-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="5c465-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="5c465-340">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-340">Format</span></span>

<span data-ttu-id="5c465-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="5c465-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-342">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-342">Pattern</span></span>

<span data-ttu-id="5c465-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="5c465-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5c465-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-344">Six digits</span></span> 
    
- <span data-ttu-id="5c465-345">Un guión</span><span class="sxs-lookup"><span data-stu-id="5c465-345">A hyphen</span></span>
    
-  <span data-ttu-id="5c465-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5c465-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-347">Checksum</span></span>

<span data-ttu-id="5c465-348">No</span><span class="sxs-lookup"><span data-stu-id="5c465-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-349">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-349">Definition</span></span>

<span data-ttu-id="5c465-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-353">Keywords</span></span>

<span data-ttu-id="5c465-354">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-354">| |</span></span>
|<span data-ttu-id="5c465-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-356">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-356">dl#</span></span>  <br/> <span data-ttu-id="5c465-357">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-357">driver license</span></span>  <br/> <span data-ttu-id="5c465-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-358">driver license number</span></span>  <br/> <span data-ttu-id="5c465-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-359">driver licence</span></span>  <br/> <span data-ttu-id="5c465-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-360">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-361">drivers license</span></span>  <br/> <span data-ttu-id="5c465-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-362">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-363">driver's license</span></span>  <br/> <span data-ttu-id="5c465-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-364">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-365">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-366">driving license number</span></span>  <br/> <span data-ttu-id="5c465-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-367">dlno#</span></span>  <br/> <span data-ttu-id="5c465-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="5c465-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="5c465-369">Francia</span><span class="sxs-lookup"><span data-stu-id="5c465-369">France</span></span>

<span data-ttu-id="5c465-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5c465-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="5c465-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="5c465-371">Germany</span></span>

<span data-ttu-id="5c465-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5c465-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="5c465-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="5c465-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5c465-374">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-374">Format</span></span>

<span data-ttu-id="5c465-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-376">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-376">Pattern</span></span>

 <span data-ttu-id="5c465-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5c465-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-378">Checksum</span></span>

<span data-ttu-id="5c465-379">No</span><span class="sxs-lookup"><span data-stu-id="5c465-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-380">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-380">Definition</span></span>

<span data-ttu-id="5c465-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-384">Keywords</span></span>

<span data-ttu-id="5c465-385">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-385">| |</span></span>
|<span data-ttu-id="5c465-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-387">Biblioteca #</span><span class="sxs-lookup"><span data-stu-id="5c465-387">dlL#</span></span>  <br/> <span data-ttu-id="5c465-388">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-388">driver license</span></span>  <br/> <span data-ttu-id="5c465-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-389">driver license number</span></span>  <br/> <span data-ttu-id="5c465-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-390">driver licence</span></span>  <br/> <span data-ttu-id="5c465-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-391">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-392">drivers license</span></span>  <br/> <span data-ttu-id="5c465-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-393">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-394">driver's license</span></span>  <br/> <span data-ttu-id="5c465-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-395">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-396">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-397">driving license number</span></span>  <br/> <span data-ttu-id="5c465-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-398">dlno#</span></span>  <br/> <span data-ttu-id="5c465-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5c465-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="5c465-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="5c465-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="5c465-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="5c465-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5c465-402">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-402">Format</span></span>

<span data-ttu-id="5c465-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-404">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-404">Pattern</span></span>

<span data-ttu-id="5c465-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5c465-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5c465-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5c465-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-408">Checksum</span></span>

<span data-ttu-id="5c465-409">No</span><span class="sxs-lookup"><span data-stu-id="5c465-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-410">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-410">Definition</span></span>

<span data-ttu-id="5c465-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-414">Keywords</span></span>

<span data-ttu-id="5c465-415">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-415">| |</span></span>
|<span data-ttu-id="5c465-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-417">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-417">dl#</span></span>  <br/> <span data-ttu-id="5c465-418">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-418">driver license</span></span>  <br/> <span data-ttu-id="5c465-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-419">driver license number</span></span>  <br/> <span data-ttu-id="5c465-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-420">driver licence</span></span>  <br/> <span data-ttu-id="5c465-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-421">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-422">drivers license</span></span>  <br/> <span data-ttu-id="5c465-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-423">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-424">driver's license</span></span>  <br/> <span data-ttu-id="5c465-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-425">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-426">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-427">driving license number</span></span>  <br/> <span data-ttu-id="5c465-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-428">dlno#</span></span>  <br/> <span data-ttu-id="5c465-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="5c465-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="5c465-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="5c465-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5c465-431">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-431">Format</span></span>

<span data-ttu-id="5c465-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="5c465-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-433">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-433">Pattern</span></span>

<span data-ttu-id="5c465-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="5c465-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="5c465-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-435">Six digits</span></span>
    
- <span data-ttu-id="5c465-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-437">Checksum</span></span>

<span data-ttu-id="5c465-438">No</span><span class="sxs-lookup"><span data-stu-id="5c465-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-439">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-439">Definition</span></span>

<span data-ttu-id="5c465-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-443">Keywords</span></span>

<span data-ttu-id="5c465-444">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-444">| |</span></span>
|<span data-ttu-id="5c465-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-446">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-446">dl#</span></span>  <br/> <span data-ttu-id="5c465-447">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-447">driver license</span></span>  <br/> <span data-ttu-id="5c465-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-448">driver license number</span></span>  <br/> <span data-ttu-id="5c465-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-449">driver licence</span></span>  <br/> <span data-ttu-id="5c465-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-450">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-451">drivers license</span></span>  <br/> <span data-ttu-id="5c465-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-452">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-453">driver's license</span></span>  <br/> <span data-ttu-id="5c465-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-454">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-455">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-456">driving license number</span></span>  <br/> <span data-ttu-id="5c465-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-457">dlno#</span></span>  <br/> <span data-ttu-id="5c465-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="5c465-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="5c465-459">Italia</span><span class="sxs-lookup"><span data-stu-id="5c465-459">Italy</span></span>

<span data-ttu-id="5c465-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5c465-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="5c465-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="5c465-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5c465-462">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-462">Format</span></span>

<span data-ttu-id="5c465-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-464">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-464">Pattern</span></span>

<span data-ttu-id="5c465-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5c465-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="5c465-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5c465-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-468">Checksum</span></span>

<span data-ttu-id="5c465-469">No</span><span class="sxs-lookup"><span data-stu-id="5c465-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-470">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-470">Definition</span></span>

<span data-ttu-id="5c465-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-474">Keywords</span></span>

<span data-ttu-id="5c465-475">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-475">| |</span></span>
|<span data-ttu-id="5c465-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-477">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-477">dl#</span></span>  <br/> <span data-ttu-id="5c465-478">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-478">driver license</span></span>  <br/> <span data-ttu-id="5c465-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-479">driver license number</span></span>  <br/> <span data-ttu-id="5c465-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-480">driver licence</span></span>  <br/> <span data-ttu-id="5c465-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-481">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-482">drivers license</span></span>  <br/> <span data-ttu-id="5c465-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-483">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-484">driver's license</span></span>  <br/> <span data-ttu-id="5c465-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-485">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-486">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-487">driving license number</span></span>  <br/> <span data-ttu-id="5c465-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-488">dlno#</span></span>  <br/> <span data-ttu-id="5c465-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="5c465-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="5c465-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="5c465-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5c465-491">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-491">Format</span></span>

<span data-ttu-id="5c465-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-493">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-493">Pattern</span></span>

 <span data-ttu-id="5c465-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5c465-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-495">Checksum</span></span>

<span data-ttu-id="5c465-496">No</span><span class="sxs-lookup"><span data-stu-id="5c465-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-497">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-497">Definition</span></span>

<span data-ttu-id="5c465-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-501">Keywords</span></span>

<span data-ttu-id="5c465-502">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-502">| |</span></span>
|<span data-ttu-id="5c465-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-504">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-504">dl#</span></span>  <br/> <span data-ttu-id="5c465-505">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-505">driver license</span></span>  <br/> <span data-ttu-id="5c465-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-506">driver license number</span></span>  <br/> <span data-ttu-id="5c465-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-507">driver licence</span></span>  <br/> <span data-ttu-id="5c465-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-508">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-509">drivers license</span></span>  <br/> <span data-ttu-id="5c465-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-510">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-511">driver's license</span></span>  <br/> <span data-ttu-id="5c465-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-512">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-513">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-514">driving license number</span></span>  <br/> <span data-ttu-id="5c465-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-515">dlno#</span></span>  <br/> <span data-ttu-id="5c465-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="5c465-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="5c465-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="5c465-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5c465-518">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-518">Format</span></span>

<span data-ttu-id="5c465-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-520">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-520">Pattern</span></span>

 <span data-ttu-id="5c465-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5c465-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-522">Checksum</span></span>

<span data-ttu-id="5c465-523">No</span><span class="sxs-lookup"><span data-stu-id="5c465-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-524">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-524">Definition</span></span>

<span data-ttu-id="5c465-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-528">Keywords</span></span>

<span data-ttu-id="5c465-529">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-529">| |</span></span>
|<span data-ttu-id="5c465-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-531">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-531">dl#</span></span>  <br/> <span data-ttu-id="5c465-532">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-532">driver license</span></span>  <br/> <span data-ttu-id="5c465-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-533">driver license number</span></span>  <br/> <span data-ttu-id="5c465-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-534">driver licence</span></span>  <br/> <span data-ttu-id="5c465-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-535">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-536">drivers license</span></span>  <br/> <span data-ttu-id="5c465-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-537">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-538">driver's license</span></span>  <br/> <span data-ttu-id="5c465-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-539">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-540">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-541">driving license number</span></span>  <br/> <span data-ttu-id="5c465-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-542">dlno#</span></span>  <br/> <span data-ttu-id="5c465-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="5c465-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="5c465-544">Malta</span><span class="sxs-lookup"><span data-stu-id="5c465-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5c465-545">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-545">Format</span></span>

<span data-ttu-id="5c465-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="5c465-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-547">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-547">Pattern</span></span>

<span data-ttu-id="5c465-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5c465-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="5c465-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="5c465-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5c465-550">A space (optional)</span></span>
    
- <span data-ttu-id="5c465-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-551">Three digits</span></span>
    
- <span data-ttu-id="5c465-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5c465-552">A space (optional)</span></span>
    
- <span data-ttu-id="5c465-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-554">Checksum</span></span>

<span data-ttu-id="5c465-555">No</span><span class="sxs-lookup"><span data-stu-id="5c465-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-556">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-556">Definition</span></span>

<span data-ttu-id="5c465-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-560">Keywords</span></span>

<span data-ttu-id="5c465-561">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-561">| |</span></span>
|<span data-ttu-id="5c465-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-563">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-563">dl#</span></span>  <br/> <span data-ttu-id="5c465-564">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-564">driver license</span></span>  <br/> <span data-ttu-id="5c465-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-565">driver license number</span></span>  <br/> <span data-ttu-id="5c465-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-566">driver licence</span></span>  <br/> <span data-ttu-id="5c465-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-567">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-568">drivers license</span></span>  <br/> <span data-ttu-id="5c465-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-569">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-570">driver's license</span></span>  <br/> <span data-ttu-id="5c465-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-571">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-572">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-573">driving license number</span></span>  <br/> <span data-ttu-id="5c465-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-574">dlno#</span></span>  <br/> <span data-ttu-id="5c465-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="5c465-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="5c465-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="5c465-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5c465-577">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-577">Format</span></span>

<span data-ttu-id="5c465-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-579">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-579">Pattern</span></span>

<span data-ttu-id="5c465-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-581">Checksum</span></span>

<span data-ttu-id="5c465-582">No</span><span class="sxs-lookup"><span data-stu-id="5c465-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-583">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-583">Definition</span></span>

<span data-ttu-id="5c465-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-587">Keywords</span></span>

<span data-ttu-id="5c465-588">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-588">| |</span></span>
|<span data-ttu-id="5c465-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-590">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-590">dl#</span></span>  <br/> <span data-ttu-id="5c465-591">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-591">driver license</span></span>  <br/> <span data-ttu-id="5c465-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-592">driver license number</span></span>  <br/> <span data-ttu-id="5c465-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-593">driver licence</span></span>  <br/> <span data-ttu-id="5c465-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-594">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-595">drivers license</span></span>  <br/> <span data-ttu-id="5c465-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-596">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-597">driver's license</span></span>  <br/> <span data-ttu-id="5c465-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-598">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-599">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-600">driving license number</span></span>  <br/> <span data-ttu-id="5c465-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-601">dlno#</span></span>  <br/> <span data-ttu-id="5c465-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5c465-602">permis de conduire</span></span>  <br/> <span data-ttu-id="5c465-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5c465-603">rijbewijs</span></span>  <br/> <span data-ttu-id="5c465-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5c465-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="5c465-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="5c465-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="5c465-606">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-606">Format</span></span>

<span data-ttu-id="5c465-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="5c465-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-608">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-608">Pattern</span></span>

<span data-ttu-id="5c465-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="5c465-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="5c465-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-610">Five digits</span></span> 
    
- <span data-ttu-id="5c465-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="5c465-611">A forward slash</span></span>
    
- <span data-ttu-id="5c465-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-612">Two digits</span></span>
    
- <span data-ttu-id="5c465-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="5c465-613">A forward slash</span></span>
    
- <span data-ttu-id="5c465-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-615">Checksum</span></span>

<span data-ttu-id="5c465-616">No</span><span class="sxs-lookup"><span data-stu-id="5c465-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-617">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-617">Definition</span></span>

<span data-ttu-id="5c465-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-621">Keywords</span></span>

<span data-ttu-id="5c465-622">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-622">| |</span></span>
|<span data-ttu-id="5c465-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-624">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-624">dl#</span></span>  <br/> <span data-ttu-id="5c465-625">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-625">driver license</span></span>  <br/> <span data-ttu-id="5c465-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-626">driver license number</span></span>  <br/> <span data-ttu-id="5c465-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-627">driver licence</span></span>  <br/> <span data-ttu-id="5c465-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-628">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-629">drivers license</span></span>  <br/> <span data-ttu-id="5c465-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-630">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-631">driver's license</span></span>  <br/> <span data-ttu-id="5c465-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-632">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-633">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-634">driving license number</span></span>  <br/> <span data-ttu-id="5c465-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-635">dlno#</span></span>  <br/> <span data-ttu-id="5c465-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="5c465-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="5c465-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="5c465-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5c465-638">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-638">Format</span></span>

<span data-ttu-id="5c465-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="5c465-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-640">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-640">Pattern</span></span>

<span data-ttu-id="5c465-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="5c465-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="5c465-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5c465-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="5c465-643">A hyphen</span></span>
    
- <span data-ttu-id="5c465-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-644">Six digits</span></span>
    
- <span data-ttu-id="5c465-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="5c465-645">A space</span></span>
    
- <span data-ttu-id="5c465-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="5c465-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-647">Checksum</span></span>

<span data-ttu-id="5c465-648">No</span><span class="sxs-lookup"><span data-stu-id="5c465-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-649">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-649">Definition</span></span>

<span data-ttu-id="5c465-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-653">Keywords</span></span>

<span data-ttu-id="5c465-654">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-654">| |</span></span>
|<span data-ttu-id="5c465-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-656">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-656">dl#</span></span>  <br/> <span data-ttu-id="5c465-657">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-657">driver license</span></span>  <br/> <span data-ttu-id="5c465-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-658">driver license number</span></span>  <br/> <span data-ttu-id="5c465-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-659">driver licence</span></span>  <br/> <span data-ttu-id="5c465-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-660">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-661">drivers license</span></span>  <br/> <span data-ttu-id="5c465-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-662">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-663">driver's license</span></span>  <br/> <span data-ttu-id="5c465-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-664">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-665">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-666">driving license number</span></span>  <br/> <span data-ttu-id="5c465-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-667">dlno#</span></span>  <br/> <span data-ttu-id="5c465-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="5c465-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="5c465-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="5c465-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5c465-670">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-670">Format</span></span>

<span data-ttu-id="5c465-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-672">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-672">Pattern</span></span>

<span data-ttu-id="5c465-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="5c465-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="5c465-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="5c465-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="5c465-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-676">Checksum</span></span>

<span data-ttu-id="5c465-677">No</span><span class="sxs-lookup"><span data-stu-id="5c465-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-678">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-678">Definition</span></span>

<span data-ttu-id="5c465-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-682">Keywords</span></span>

<span data-ttu-id="5c465-683">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-683">| |</span></span>
|<span data-ttu-id="5c465-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-685">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-685">dl#</span></span>  <br/> <span data-ttu-id="5c465-686">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-686">driver license</span></span>  <br/> <span data-ttu-id="5c465-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-687">driver license number</span></span>  <br/> <span data-ttu-id="5c465-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-688">driver licence</span></span>  <br/> <span data-ttu-id="5c465-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-689">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-690">drivers license</span></span>  <br/> <span data-ttu-id="5c465-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-691">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-692">driver's license</span></span>  <br/> <span data-ttu-id="5c465-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-693">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-694">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-695">driving license number</span></span>  <br/> <span data-ttu-id="5c465-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-696">dlno#</span></span>  <br/> <span data-ttu-id="5c465-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="5c465-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="5c465-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="5c465-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5c465-699">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-699">Format</span></span>

<span data-ttu-id="5c465-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-701">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-701">Pattern</span></span>

<span data-ttu-id="5c465-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="5c465-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="5c465-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="5c465-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5c465-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-705">Checksum</span></span>

<span data-ttu-id="5c465-706">No</span><span class="sxs-lookup"><span data-stu-id="5c465-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-707">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-707">Definition</span></span>

<span data-ttu-id="5c465-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-711">Keywords</span></span>

<span data-ttu-id="5c465-712">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-712">| |</span></span>
|<span data-ttu-id="5c465-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-714">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-714">dl#</span></span>  <br/> <span data-ttu-id="5c465-715">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-715">driver license</span></span>  <br/> <span data-ttu-id="5c465-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-716">driver license number</span></span>  <br/> <span data-ttu-id="5c465-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-717">driver licence</span></span>  <br/> <span data-ttu-id="5c465-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-718">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-719">drivers license</span></span>  <br/> <span data-ttu-id="5c465-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-720">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-721">driver's license</span></span>  <br/> <span data-ttu-id="5c465-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-722">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-723">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-724">driving license number</span></span>  <br/> <span data-ttu-id="5c465-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-725">dlno#</span></span>  <br/> <span data-ttu-id="5c465-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="5c465-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="5c465-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="5c465-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5c465-728">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-728">Format</span></span>

<span data-ttu-id="5c465-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5c465-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-730">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-730">Pattern</span></span>

<span data-ttu-id="5c465-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5c465-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-732">Checksum</span></span>

<span data-ttu-id="5c465-733">No</span><span class="sxs-lookup"><span data-stu-id="5c465-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-734">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-734">Definition</span></span>

<span data-ttu-id="5c465-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-738">Keywords</span></span>

<span data-ttu-id="5c465-739">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-739">| |</span></span>
|<span data-ttu-id="5c465-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-741">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-741">dl#</span></span>  <br/> <span data-ttu-id="5c465-742">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-742">driver license</span></span>  <br/> <span data-ttu-id="5c465-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-743">driver license number</span></span>  <br/> <span data-ttu-id="5c465-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-744">driver licence</span></span>  <br/> <span data-ttu-id="5c465-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-745">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-746">drivers license</span></span>  <br/> <span data-ttu-id="5c465-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-747">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-748">driver's license</span></span>  <br/> <span data-ttu-id="5c465-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-749">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-750">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-751">driving license number</span></span>  <br/> <span data-ttu-id="5c465-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-752">dlno#</span></span>  <br/> <span data-ttu-id="5c465-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="5c465-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="5c465-754">España</span><span class="sxs-lookup"><span data-stu-id="5c465-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5c465-755">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-755">Format</span></span>

<span data-ttu-id="5c465-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="5c465-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-757">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-757">Pattern</span></span>

<span data-ttu-id="5c465-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="5c465-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="5c465-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-759">Eight digits</span></span> 
    
- <span data-ttu-id="5c465-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5c465-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-761">Checksum</span></span>

<span data-ttu-id="5c465-762">Sí</span><span class="sxs-lookup"><span data-stu-id="5c465-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-763">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-763">Definition</span></span>

<span data-ttu-id="5c465-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5c465-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-767">Keywords</span></span>

<span data-ttu-id="5c465-768">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-768">| |</span></span>
|<span data-ttu-id="5c465-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-770">dlno#</span></span>  <br/> <span data-ttu-id="5c465-771">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-771">dl#</span></span>  <br/> <span data-ttu-id="5c465-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-772">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-773">driver licence</span></span>  <br/> <span data-ttu-id="5c465-774">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-774">driver license</span></span>  <br/> <span data-ttu-id="5c465-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-775">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-776">drivers license</span></span>  <br/> <span data-ttu-id="5c465-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5c465-777">driver's licence</span></span>  <br/> <span data-ttu-id="5c465-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-778">driver's license</span></span>  <br/> <span data-ttu-id="5c465-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="5c465-779">driving licence</span></span>  <br/> <span data-ttu-id="5c465-780">driving license</span><span class="sxs-lookup"><span data-stu-id="5c465-780">driving license</span></span>  <br/> <span data-ttu-id="5c465-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-781">driver licence number</span></span>  <br/> <span data-ttu-id="5c465-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-782">driver license number</span></span>  <br/> <span data-ttu-id="5c465-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="5c465-783">drivers licence number</span></span>  <br/> <span data-ttu-id="5c465-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="5c465-784">drivers license number</span></span>  <br/> <span data-ttu-id="5c465-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-785">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-786">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-787">driving licence number</span></span>  <br/> <span data-ttu-id="5c465-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-788">driving license number</span></span>  <br/> <span data-ttu-id="5c465-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-789">driving permit</span></span>  <br/> <span data-ttu-id="5c465-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-790">driving permit number</span></span>  <br/> <span data-ttu-id="5c465-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="5c465-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-792">permiso conducción</span></span>  <br/> <span data-ttu-id="5c465-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="5c465-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="5c465-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="5c465-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="5c465-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-796">licencia conducir</span></span>  <br/> <span data-ttu-id="5c465-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="5c465-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="5c465-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="5c465-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-800">permiso conducir</span></span>  <br/> <span data-ttu-id="5c465-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="5c465-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="5c465-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="5c465-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="5c465-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="5c465-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="5c465-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="5c465-805">Formato</span><span class="sxs-lookup"><span data-stu-id="5c465-805">Format</span></span>

<span data-ttu-id="5c465-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="5c465-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5c465-807">Pattern</span><span class="sxs-lookup"><span data-stu-id="5c465-807">Pattern</span></span>

<span data-ttu-id="5c465-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="5c465-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5c465-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-809">Six digits</span></span> 
    
- <span data-ttu-id="5c465-810">Un guión</span><span class="sxs-lookup"><span data-stu-id="5c465-810">A hyphen</span></span>
    
- <span data-ttu-id="5c465-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="5c465-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5c465-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5c465-812">Checksum</span></span>

<span data-ttu-id="5c465-813">No</span><span class="sxs-lookup"><span data-stu-id="5c465-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5c465-814">Definición</span><span class="sxs-lookup"><span data-stu-id="5c465-814">Definition</span></span>

<span data-ttu-id="5c465-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c465-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5c465-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5c465-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5c465-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5c465-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="5c465-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c465-818">Keywords</span></span>

<span data-ttu-id="5c465-819">| |</span><span class="sxs-lookup"><span data-stu-id="5c465-819">| |</span></span>
|<span data-ttu-id="5c465-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="5c465-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5c465-821">listas #</span><span class="sxs-lookup"><span data-stu-id="5c465-821">dl#</span></span>  <br/> <span data-ttu-id="5c465-822">driver license</span><span class="sxs-lookup"><span data-stu-id="5c465-822">driver license</span></span>  <br/> <span data-ttu-id="5c465-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5c465-823">driver license number</span></span>  <br/> <span data-ttu-id="5c465-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-824">driver licence</span></span>  <br/> <span data-ttu-id="5c465-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5c465-825">drivers lic.</span></span>  <br/> <span data-ttu-id="5c465-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="5c465-826">drivers license</span></span>  <br/> <span data-ttu-id="5c465-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5c465-827">drivers licence</span></span>  <br/> <span data-ttu-id="5c465-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="5c465-828">driver's license</span></span>  <br/> <span data-ttu-id="5c465-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-829">driver's license number</span></span>  <br/> <span data-ttu-id="5c465-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5c465-830">driver's licence number</span></span>  <br/> <span data-ttu-id="5c465-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5c465-831">driving license number</span></span>  <br/> <span data-ttu-id="5c465-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="5c465-832">dlno#</span></span>  <br/> <span data-ttu-id="5c465-833">körkort</span><span class="sxs-lookup"><span data-stu-id="5c465-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="5c465-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="5c465-834">UK</span></span>

<span data-ttu-id="5c465-835">Para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="5c465-835">For details, see the section "U.K.</span></span> <span data-ttu-id="5c465-836">Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5c465-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c465-837">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c465-837">See also</span></span>

[<span data-ttu-id="5c465-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="5c465-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

