---
title: Número de permiso de conducción de la UE
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
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805963"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="f0af9-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="f0af9-104">EU Driver's License Number</span></span>

<span data-ttu-id="f0af9-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE.</span><span class="sxs-lookup"><span data-stu-id="f0af9-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="f0af9-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="f0af9-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f0af9-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f0af9-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-108">Format</span></span>

<span data-ttu-id="f0af9-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-110">Pattern</span></span>

<span data-ttu-id="f0af9-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-112">Checksum</span></span>

<span data-ttu-id="f0af9-113">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-114">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-114">Definition</span></span>

<span data-ttu-id="f0af9-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="f0af9-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-118">Keywords</span></span>

<span data-ttu-id="f0af9-119">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-119"></span></span>
|<span data-ttu-id="f0af9-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-121">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-121">dl#</span></span>  <br/> <span data-ttu-id="f0af9-122">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-122">driver license</span></span>  <br/> <span data-ttu-id="f0af9-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-123">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-124">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-125">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-126">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-127">driver's licence</span></span>  <br/> <span data-ttu-id="f0af9-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-128">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-129">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="f0af9-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-131">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-132">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="f0af9-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="f0af9-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="f0af9-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="f0af9-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="f0af9-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-136">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-136">Format</span></span>

<span data-ttu-id="f0af9-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-138">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-138">Pattern</span></span>

<span data-ttu-id="f0af9-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-140">Checksum</span></span>

<span data-ttu-id="f0af9-141">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-142">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-142">Definition</span></span>

<span data-ttu-id="f0af9-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f0af9-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-146">Keywords</span></span>

<span data-ttu-id="f0af9-147">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-147"></span></span>
|<span data-ttu-id="f0af9-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-149">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-149">dl#</span></span>  <br/> <span data-ttu-id="f0af9-150">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-150">driver license</span></span>  <br/> <span data-ttu-id="f0af9-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-151">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-152">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-153">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-154">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-155">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-156">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-157">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-158">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-159">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="f0af9-160">rijbewijs</span></span>  <br/> <span data-ttu-id="f0af9-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="f0af9-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="f0af9-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f0af9-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="f0af9-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f0af9-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="f0af9-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f0af9-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="f0af9-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="f0af9-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="f0af9-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="f0af9-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="f0af9-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="f0af9-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="f0af9-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f0af9-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-169">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-169">Format</span></span>

<span data-ttu-id="f0af9-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-171">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-171">Pattern</span></span>

<span data-ttu-id="f0af9-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-173">Checksum</span></span>

<span data-ttu-id="f0af9-174">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-175">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-175">Definition</span></span>

<span data-ttu-id="f0af9-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="f0af9-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-179">Keywords</span></span>

<span data-ttu-id="f0af9-180">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-180"></span></span>
|<span data-ttu-id="f0af9-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-182">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-182">dl#</span></span>  <br/> <span data-ttu-id="f0af9-183">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-183">driver license</span></span>  <br/> <span data-ttu-id="f0af9-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-184">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-185">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-186">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-187">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-188">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-189">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-190">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-191">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-192">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-193">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="f0af9-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="f0af9-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="f0af9-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="f0af9-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="f0af9-196">сумпс</span></span>  <br/> <span data-ttu-id="f0af9-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="f0af9-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="f0af9-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="f0af9-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-199">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-199">Format</span></span>

<span data-ttu-id="f0af9-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-201">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-201">Pattern</span></span>

<span data-ttu-id="f0af9-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-203">Checksum</span></span>

<span data-ttu-id="f0af9-204">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-205">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-205">Definition</span></span>

<span data-ttu-id="f0af9-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f0af9-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-209">Keywords</span></span>

<span data-ttu-id="f0af9-210">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-210"></span></span>
|<span data-ttu-id="f0af9-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-212">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-212">dl#</span></span>  <br/> <span data-ttu-id="f0af9-213">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-213">driver license</span></span>  <br/> <span data-ttu-id="f0af9-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-214">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-215">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-216">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-217">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-218">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-219">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-220">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-221">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-222">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-223">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="f0af9-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="f0af9-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="f0af9-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-226">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-226">Format</span></span>

<span data-ttu-id="f0af9-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-228">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-228">Pattern</span></span>

<span data-ttu-id="f0af9-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-230">Checksum</span></span>

<span data-ttu-id="f0af9-231">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-232">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-232">Definition</span></span>

<span data-ttu-id="f0af9-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-236">Keywords</span></span>

<span data-ttu-id="f0af9-237">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-237"></span></span>
|<span data-ttu-id="f0af9-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-239">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-239">dl#</span></span>  <br/> <span data-ttu-id="f0af9-240">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-240">driver license</span></span>  <br/> <span data-ttu-id="f0af9-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-241">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-242">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-243">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-244">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-245">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-246">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-247">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-248">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-249">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="f0af9-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="f0af9-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="f0af9-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-252">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-252">Format</span></span>

<span data-ttu-id="f0af9-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-254">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-254">Pattern</span></span>

<span data-ttu-id="f0af9-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="f0af9-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="f0af9-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="f0af9-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="f0af9-257">A space (optional)</span></span>
    
- <span data-ttu-id="f0af9-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-259">Checksum</span></span>

<span data-ttu-id="f0af9-260">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-261">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-261">Definition</span></span>

<span data-ttu-id="f0af9-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f0af9-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-265">Keywords</span></span>

<span data-ttu-id="f0af9-266">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-266"></span></span>
|<span data-ttu-id="f0af9-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-268">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-268">dl#</span></span>  <br/> <span data-ttu-id="f0af9-269">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-269">driver license</span></span>  <br/> <span data-ttu-id="f0af9-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-270">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-271">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-272">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-273">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-274">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-275">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-276">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-277">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-278">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-279">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-280">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="f0af9-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="f0af9-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="f0af9-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-283">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-283">Format</span></span>

<span data-ttu-id="f0af9-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-285">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-285">Pattern</span></span>

<span data-ttu-id="f0af9-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-287">Checksum</span></span>

<span data-ttu-id="f0af9-288">Sí</span><span class="sxs-lookup"><span data-stu-id="f0af9-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-289">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-289">Definition</span></span>

<span data-ttu-id="f0af9-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f0af9-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-293">Keywords</span></span>

<span data-ttu-id="f0af9-294">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-294"></span></span>
|<span data-ttu-id="f0af9-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-296">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-296">dl#</span></span>  <br/> <span data-ttu-id="f0af9-297">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-297">driver license</span></span>  <br/> <span data-ttu-id="f0af9-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-298">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-299">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-300">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-301">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-302">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-303">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-304">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-305">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-306">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-307">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="f0af9-308">kørekort</span></span>  <br/> <span data-ttu-id="f0af9-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="f0af9-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="f0af9-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="f0af9-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-311">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-311">Format</span></span>

<span data-ttu-id="f0af9-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-313">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-313">Pattern</span></span>

<span data-ttu-id="f0af9-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f0af9-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="f0af9-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f0af9-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-317">Checksum</span></span>

<span data-ttu-id="f0af9-318">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-319">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-319">Definition</span></span>

<span data-ttu-id="f0af9-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-323">Keywords</span></span>

<span data-ttu-id="f0af9-324">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-324"></span></span>
|<span data-ttu-id="f0af9-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-326">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-326">dl#</span></span>  <br/> <span data-ttu-id="f0af9-327">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-327">driver license</span></span>  <br/> <span data-ttu-id="f0af9-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-328">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-329">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-330">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-331">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-332">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-333">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-334">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-335">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-336">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-337">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="f0af9-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="f0af9-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f0af9-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-340">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-340">Format</span></span>

<span data-ttu-id="f0af9-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="f0af9-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-342">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-342">Pattern</span></span>

<span data-ttu-id="f0af9-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="f0af9-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="f0af9-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-344">Six digits</span></span> 
    
- <span data-ttu-id="f0af9-345">Un guión</span><span class="sxs-lookup"><span data-stu-id="f0af9-345">A hyphen</span></span>
    
-  <span data-ttu-id="f0af9-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f0af9-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-347">Checksum</span></span>

<span data-ttu-id="f0af9-348">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-349">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-349">Definition</span></span>

<span data-ttu-id="f0af9-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-353">Keywords</span></span>

<span data-ttu-id="f0af9-354">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-354"></span></span>
|<span data-ttu-id="f0af9-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-356">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-356">dl#</span></span>  <br/> <span data-ttu-id="f0af9-357">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-357">driver license</span></span>  <br/> <span data-ttu-id="f0af9-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-358">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-359">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-360">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-361">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-362">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-363">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-364">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-365">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-366">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-367">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="f0af9-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="f0af9-369">Francia</span><span class="sxs-lookup"><span data-stu-id="f0af9-369">France</span></span>

<span data-ttu-id="f0af9-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0af9-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="f0af9-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="f0af9-371">Germany</span></span>

<span data-ttu-id="f0af9-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0af9-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="f0af9-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="f0af9-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-374">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-374">Format</span></span>

<span data-ttu-id="f0af9-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-376">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-376">Pattern</span></span>

 <span data-ttu-id="f0af9-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0af9-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-378">Checksum</span></span>

<span data-ttu-id="f0af9-379">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-380">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-380">Definition</span></span>

<span data-ttu-id="f0af9-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-384">Keywords</span></span>

<span data-ttu-id="f0af9-385">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-385"></span></span>
|<span data-ttu-id="f0af9-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-387">Biblioteca #</span><span class="sxs-lookup"><span data-stu-id="f0af9-387">dlL#</span></span>  <br/> <span data-ttu-id="f0af9-388">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-388">driver license</span></span>  <br/> <span data-ttu-id="f0af9-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-389">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-390">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-391">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-392">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-393">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-394">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-395">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-396">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-397">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-398">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="f0af9-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="f0af9-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="f0af9-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="f0af9-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="f0af9-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-402">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-402">Format</span></span>

<span data-ttu-id="f0af9-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-404">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-404">Pattern</span></span>

<span data-ttu-id="f0af9-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f0af9-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="f0af9-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f0af9-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-408">Checksum</span></span>

<span data-ttu-id="f0af9-409">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-410">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-410">Definition</span></span>

<span data-ttu-id="f0af9-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-414">Keywords</span></span>

<span data-ttu-id="f0af9-415">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-415"></span></span>
|<span data-ttu-id="f0af9-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-417">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-417">dl#</span></span>  <br/> <span data-ttu-id="f0af9-418">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-418">driver license</span></span>  <br/> <span data-ttu-id="f0af9-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-419">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-420">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-421">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-422">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-423">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-424">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-425">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-426">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-427">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-428">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="f0af9-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="f0af9-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f0af9-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-431">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-431">Format</span></span>

<span data-ttu-id="f0af9-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="f0af9-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-433">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-433">Pattern</span></span>

<span data-ttu-id="f0af9-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="f0af9-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="f0af9-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-435">Six digits</span></span>
    
- <span data-ttu-id="f0af9-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-437">Checksum</span></span>

<span data-ttu-id="f0af9-438">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-439">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-439">Definition</span></span>

<span data-ttu-id="f0af9-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-443">Keywords</span></span>

<span data-ttu-id="f0af9-444">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-444"></span></span>
|<span data-ttu-id="f0af9-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-446">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-446">dl#</span></span>  <br/> <span data-ttu-id="f0af9-447">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-447">driver license</span></span>  <br/> <span data-ttu-id="f0af9-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-448">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-449">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-450">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-451">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-452">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-453">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-454">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-455">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-456">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-457">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="f0af9-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="f0af9-459">Italia</span><span class="sxs-lookup"><span data-stu-id="f0af9-459">Italy</span></span>

<span data-ttu-id="f0af9-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0af9-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="f0af9-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="f0af9-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-462">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-462">Format</span></span>

<span data-ttu-id="f0af9-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-464">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-464">Pattern</span></span>

<span data-ttu-id="f0af9-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f0af9-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="f0af9-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f0af9-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-468">Checksum</span></span>

<span data-ttu-id="f0af9-469">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-470">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-470">Definition</span></span>

<span data-ttu-id="f0af9-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-474">Keywords</span></span>

<span data-ttu-id="f0af9-475">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-475"></span></span>
|<span data-ttu-id="f0af9-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-477">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-477">dl#</span></span>  <br/> <span data-ttu-id="f0af9-478">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-478">driver license</span></span>  <br/> <span data-ttu-id="f0af9-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-479">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-480">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-481">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-482">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-483">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-484">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-485">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-486">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-487">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-488">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="f0af9-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="f0af9-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="f0af9-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-491">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-491">Format</span></span>

<span data-ttu-id="f0af9-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-493">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-493">Pattern</span></span>

 <span data-ttu-id="f0af9-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0af9-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-495">Checksum</span></span>

<span data-ttu-id="f0af9-496">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-497">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-497">Definition</span></span>

<span data-ttu-id="f0af9-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-501">Keywords</span></span>

<span data-ttu-id="f0af9-502">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-502"></span></span>
|<span data-ttu-id="f0af9-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-504">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-504">dl#</span></span>  <br/> <span data-ttu-id="f0af9-505">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-505">driver license</span></span>  <br/> <span data-ttu-id="f0af9-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-506">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-507">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-508">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-509">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-510">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-511">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-512">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-513">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-514">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-515">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="f0af9-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="f0af9-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="f0af9-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-518">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-518">Format</span></span>

<span data-ttu-id="f0af9-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-520">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-520">Pattern</span></span>

 <span data-ttu-id="f0af9-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0af9-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-522">Checksum</span></span>

<span data-ttu-id="f0af9-523">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-524">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-524">Definition</span></span>

<span data-ttu-id="f0af9-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-528">Keywords</span></span>

<span data-ttu-id="f0af9-529">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-529"></span></span>
|<span data-ttu-id="f0af9-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-531">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-531">dl#</span></span>  <br/> <span data-ttu-id="f0af9-532">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-532">driver license</span></span>  <br/> <span data-ttu-id="f0af9-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-533">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-534">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-535">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-536">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-537">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-538">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-539">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-540">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-541">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-542">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="f0af9-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="f0af9-544">Malta</span><span class="sxs-lookup"><span data-stu-id="f0af9-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-545">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-545">Format</span></span>

<span data-ttu-id="f0af9-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f0af9-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-547">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-547">Pattern</span></span>

<span data-ttu-id="f0af9-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f0af9-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="f0af9-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="f0af9-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="f0af9-550">A space (optional)</span></span>
    
- <span data-ttu-id="f0af9-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-551">Three digits</span></span>
    
- <span data-ttu-id="f0af9-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="f0af9-552">A space (optional)</span></span>
    
- <span data-ttu-id="f0af9-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-554">Checksum</span></span>

<span data-ttu-id="f0af9-555">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-556">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-556">Definition</span></span>

<span data-ttu-id="f0af9-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-560">Keywords</span></span>

<span data-ttu-id="f0af9-561">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-561"></span></span>
|<span data-ttu-id="f0af9-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-563">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-563">dl#</span></span>  <br/> <span data-ttu-id="f0af9-564">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-564">driver license</span></span>  <br/> <span data-ttu-id="f0af9-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-565">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-566">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-567">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-568">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-569">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-570">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-571">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-572">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-573">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-574">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="f0af9-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="f0af9-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="f0af9-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-577">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-577">Format</span></span>

<span data-ttu-id="f0af9-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-579">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-579">Pattern</span></span>

<span data-ttu-id="f0af9-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-581">Checksum</span></span>

<span data-ttu-id="f0af9-582">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-583">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-583">Definition</span></span>

<span data-ttu-id="f0af9-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-587">Keywords</span></span>

<span data-ttu-id="f0af9-588">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-588"></span></span>
|<span data-ttu-id="f0af9-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-590">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-590">dl#</span></span>  <br/> <span data-ttu-id="f0af9-591">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-591">driver license</span></span>  <br/> <span data-ttu-id="f0af9-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-592">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-593">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-594">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-595">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-596">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-597">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-598">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-599">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-600">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-601">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="f0af9-602">permis de conduire</span></span>  <br/> <span data-ttu-id="f0af9-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="f0af9-603">rijbewijs</span></span>  <br/> <span data-ttu-id="f0af9-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="f0af9-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="f0af9-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="f0af9-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-606">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-606">Format</span></span>

<span data-ttu-id="f0af9-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="f0af9-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-608">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-608">Pattern</span></span>

<span data-ttu-id="f0af9-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="f0af9-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="f0af9-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-610">Five digits</span></span> 
    
- <span data-ttu-id="f0af9-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="f0af9-611">A forward slash</span></span>
    
- <span data-ttu-id="f0af9-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-612">Two digits</span></span>
    
- <span data-ttu-id="f0af9-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="f0af9-613">A forward slash</span></span>
    
- <span data-ttu-id="f0af9-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-615">Checksum</span></span>

<span data-ttu-id="f0af9-616">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-617">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-617">Definition</span></span>

<span data-ttu-id="f0af9-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-621">Keywords</span></span>

<span data-ttu-id="f0af9-622">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-622"></span></span>
|<span data-ttu-id="f0af9-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-624">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-624">dl#</span></span>  <br/> <span data-ttu-id="f0af9-625">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-625">driver license</span></span>  <br/> <span data-ttu-id="f0af9-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-626">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-627">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-628">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-629">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-630">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-631">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-632">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-633">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-634">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-635">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="f0af9-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="f0af9-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="f0af9-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-638">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-638">Format</span></span>

<span data-ttu-id="f0af9-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f0af9-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-640">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-640">Pattern</span></span>

<span data-ttu-id="f0af9-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="f0af9-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="f0af9-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f0af9-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="f0af9-643">A hyphen</span></span>
    
- <span data-ttu-id="f0af9-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-644">Six digits</span></span>
    
- <span data-ttu-id="f0af9-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="f0af9-645">A space</span></span>
    
- <span data-ttu-id="f0af9-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="f0af9-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-647">Checksum</span></span>

<span data-ttu-id="f0af9-648">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-649">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-649">Definition</span></span>

<span data-ttu-id="f0af9-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-653">Keywords</span></span>

<span data-ttu-id="f0af9-654">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-654"></span></span>
|<span data-ttu-id="f0af9-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-656">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-656">dl#</span></span>  <br/> <span data-ttu-id="f0af9-657">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-657">driver license</span></span>  <br/> <span data-ttu-id="f0af9-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-658">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-659">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-660">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-661">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-662">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-663">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-664">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-665">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-666">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-667">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="f0af9-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="f0af9-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="f0af9-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-670">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-670">Format</span></span>

<span data-ttu-id="f0af9-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-672">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-672">Pattern</span></span>

<span data-ttu-id="f0af9-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="f0af9-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="f0af9-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="f0af9-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="f0af9-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-676">Checksum</span></span>

<span data-ttu-id="f0af9-677">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-678">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-678">Definition</span></span>

<span data-ttu-id="f0af9-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-682">Keywords</span></span>

<span data-ttu-id="f0af9-683">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-683"></span></span>
|<span data-ttu-id="f0af9-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-685">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-685">dl#</span></span>  <br/> <span data-ttu-id="f0af9-686">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-686">driver license</span></span>  <br/> <span data-ttu-id="f0af9-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-687">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-688">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-689">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-690">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-691">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-692">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-693">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-694">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-695">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-696">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="f0af9-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="f0af9-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="f0af9-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-699">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-699">Format</span></span>

<span data-ttu-id="f0af9-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-701">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-701">Pattern</span></span>

<span data-ttu-id="f0af9-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="f0af9-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="f0af9-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="f0af9-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f0af9-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-705">Checksum</span></span>

<span data-ttu-id="f0af9-706">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-707">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-707">Definition</span></span>

<span data-ttu-id="f0af9-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-711">Keywords</span></span>

<span data-ttu-id="f0af9-712">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-712"></span></span>
|<span data-ttu-id="f0af9-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-714">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-714">dl#</span></span>  <br/> <span data-ttu-id="f0af9-715">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-715">driver license</span></span>  <br/> <span data-ttu-id="f0af9-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-716">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-717">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-718">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-719">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-720">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-721">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-722">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-723">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-724">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-725">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="f0af9-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="f0af9-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="f0af9-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-728">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-728">Format</span></span>

<span data-ttu-id="f0af9-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f0af9-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-730">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-730">Pattern</span></span>

<span data-ttu-id="f0af9-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0af9-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-732">Checksum</span></span>

<span data-ttu-id="f0af9-733">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-734">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-734">Definition</span></span>

<span data-ttu-id="f0af9-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-738">Keywords</span></span>

<span data-ttu-id="f0af9-739">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-739"></span></span>
|<span data-ttu-id="f0af9-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-741">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-741">dl#</span></span>  <br/> <span data-ttu-id="f0af9-742">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-742">driver license</span></span>  <br/> <span data-ttu-id="f0af9-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-743">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-744">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-745">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-746">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-747">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-748">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-749">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-750">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-751">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-752">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="f0af9-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="f0af9-754">España</span><span class="sxs-lookup"><span data-stu-id="f0af9-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-755">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-755">Format</span></span>

<span data-ttu-id="f0af9-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="f0af9-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-757">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-757">Pattern</span></span>

<span data-ttu-id="f0af9-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="f0af9-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="f0af9-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-759">Eight digits</span></span> 
    
- <span data-ttu-id="f0af9-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f0af9-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-761">Checksum</span></span>

<span data-ttu-id="f0af9-762">Sí</span><span class="sxs-lookup"><span data-stu-id="f0af9-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-763">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-763">Definition</span></span>

<span data-ttu-id="f0af9-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0af9-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-767">Keywords</span></span>

<span data-ttu-id="f0af9-768">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-768"></span></span>
|<span data-ttu-id="f0af9-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-770">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-771">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-771">dl#</span></span>  <br/> <span data-ttu-id="f0af9-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-772">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-773">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-774">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-774">driver license</span></span>  <br/> <span data-ttu-id="f0af9-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-775">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-776">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-777">driver's licence</span></span>  <br/> <span data-ttu-id="f0af9-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-778">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-779">driving licence</span></span>  <br/> <span data-ttu-id="f0af9-780">driving license</span><span class="sxs-lookup"><span data-stu-id="f0af9-780">driving license</span></span>  <br/> <span data-ttu-id="f0af9-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-781">driver licence number</span></span>  <br/> <span data-ttu-id="f0af9-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-782">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="f0af9-783">drivers licence number</span></span>  <br/> <span data-ttu-id="f0af9-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="f0af9-784">drivers license number</span></span>  <br/> <span data-ttu-id="f0af9-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-785">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-786">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-787">driving licence number</span></span>  <br/> <span data-ttu-id="f0af9-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-788">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-789">driving permit</span></span>  <br/> <span data-ttu-id="f0af9-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-790">driving permit number</span></span>  <br/> <span data-ttu-id="f0af9-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="f0af9-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-792">permiso conducción</span></span>  <br/> <span data-ttu-id="f0af9-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="f0af9-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="f0af9-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="f0af9-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="f0af9-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-796">licencia conducir</span></span>  <br/> <span data-ttu-id="f0af9-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="f0af9-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="f0af9-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="f0af9-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-800">permiso conducir</span></span>  <br/> <span data-ttu-id="f0af9-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="f0af9-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="f0af9-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="f0af9-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="f0af9-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="f0af9-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="f0af9-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="f0af9-805">Formato</span><span class="sxs-lookup"><span data-stu-id="f0af9-805">Format</span></span>

<span data-ttu-id="f0af9-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="f0af9-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0af9-807">Pattern</span><span class="sxs-lookup"><span data-stu-id="f0af9-807">Pattern</span></span>

<span data-ttu-id="f0af9-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="f0af9-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="f0af9-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-809">Six digits</span></span> 
    
- <span data-ttu-id="f0af9-810">Un guión</span><span class="sxs-lookup"><span data-stu-id="f0af9-810">A hyphen</span></span>
    
- <span data-ttu-id="f0af9-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f0af9-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0af9-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0af9-812">Checksum</span></span>

<span data-ttu-id="f0af9-813">No</span><span class="sxs-lookup"><span data-stu-id="f0af9-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0af9-814">Definición</span><span class="sxs-lookup"><span data-stu-id="f0af9-814">Definition</span></span>

<span data-ttu-id="f0af9-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f0af9-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0af9-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f0af9-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0af9-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f0af9-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="f0af9-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0af9-818">Keywords</span></span>

<span data-ttu-id="f0af9-819">| |</span><span class="sxs-lookup"><span data-stu-id="f0af9-819"></span></span>
|<span data-ttu-id="f0af9-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f0af9-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f0af9-821">listas #</span><span class="sxs-lookup"><span data-stu-id="f0af9-821">dl#</span></span>  <br/> <span data-ttu-id="f0af9-822">driver license</span><span class="sxs-lookup"><span data-stu-id="f0af9-822">driver license</span></span>  <br/> <span data-ttu-id="f0af9-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="f0af9-823">driver license number</span></span>  <br/> <span data-ttu-id="f0af9-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-824">driver licence</span></span>  <br/> <span data-ttu-id="f0af9-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="f0af9-825">drivers lic.</span></span>  <br/> <span data-ttu-id="f0af9-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="f0af9-826">drivers license</span></span>  <br/> <span data-ttu-id="f0af9-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f0af9-827">drivers licence</span></span>  <br/> <span data-ttu-id="f0af9-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="f0af9-828">driver's license</span></span>  <br/> <span data-ttu-id="f0af9-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-829">driver's license number</span></span>  <br/> <span data-ttu-id="f0af9-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f0af9-830">driver's licence number</span></span>  <br/> <span data-ttu-id="f0af9-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="f0af9-831">driving license number</span></span>  <br/> <span data-ttu-id="f0af9-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="f0af9-832">dlno#</span></span>  <br/> <span data-ttu-id="f0af9-833">körkort</span><span class="sxs-lookup"><span data-stu-id="f0af9-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="f0af9-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="f0af9-834">UK</span></span>

<span data-ttu-id="f0af9-835">Para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="f0af9-835">For details, see the section "U.K.</span></span> <span data-ttu-id="f0af9-836">Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0af9-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f0af9-837">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0af9-837">See also</span></span>

[<span data-ttu-id="f0af9-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="f0af9-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

