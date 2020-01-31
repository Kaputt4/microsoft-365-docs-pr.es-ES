---
title: Número de identificación fiscal de la UE
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
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación de impuestos de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591021"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="8437d-104">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="8437d-104">EU Tax Identification Number</span></span>

<span data-ttu-id="8437d-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de identificación fiscal (CIF) de la UE.</span><span class="sxs-lookup"><span data-stu-id="8437d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="8437d-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="8437d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8437d-107">Austria</span><span class="sxs-lookup"><span data-stu-id="8437d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8437d-108">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-108">Format</span></span>

<span data-ttu-id="8437d-109">Nueve dígitos con guión opcional y barra diagonal</span><span class="sxs-lookup"><span data-stu-id="8437d-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-110">Pattern</span></span>

<span data-ttu-id="8437d-111">Nueve dígitos con guión opcional y barra diagonal:</span><span class="sxs-lookup"><span data-stu-id="8437d-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="8437d-112">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-112">Two digits</span></span> 
    
- <span data-ttu-id="8437d-113">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="8437d-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="8437d-114">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-114">Three digits</span></span>
    
- <span data-ttu-id="8437d-115">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="8437d-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="8437d-116">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-117">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-117">Checksum</span></span>

<span data-ttu-id="8437d-118">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-119">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-119">Definition</span></span>

<span data-ttu-id="8437d-120">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-121">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-122">Se encuentra una `Keywords_austria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-123">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-124">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-125">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="8437d-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-127">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-127">tax number</span></span>
  
<span data-ttu-id="8437d-128">número</span><span class="sxs-lookup"><span data-stu-id="8437d-128">number</span></span>
  
<span data-ttu-id="8437d-129">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="8437d-129">tax registration number</span></span>
  
<span data-ttu-id="8437d-130">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-130">tax id</span></span>
  
<span data-ttu-id="8437d-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="8437d-131">st.nr.</span></span>
  
<span data-ttu-id="8437d-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="8437d-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="8437d-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="8437d-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8437d-134">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-134">Format</span></span>

<span data-ttu-id="8437d-135">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-136">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-136">Pattern</span></span>

<span data-ttu-id="8437d-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-137">11 digits:</span></span>
  
- <span data-ttu-id="8437d-138">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-138">Two digits</span></span>
    
- <span data-ttu-id="8437d-139">Un "0" o "1"</span><span class="sxs-lookup"><span data-stu-id="8437d-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="8437d-140">Un dígito</span><span class="sxs-lookup"><span data-stu-id="8437d-140">One digit</span></span>
    
- <span data-ttu-id="8437d-141">Un "0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="8437d-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="8437d-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-143">Checksum</span></span>

<span data-ttu-id="8437d-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-145">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-145">Definition</span></span>

<span data-ttu-id="8437d-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-147">La expresión `Regex_belgium_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-148">Se encuentra una `Keywords_belgium_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="8437d-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-151">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-151">tax number</span></span>
  
<span data-ttu-id="8437d-152">número de registro nacional</span><span class="sxs-lookup"><span data-stu-id="8437d-152">national registration number</span></span>
  
<span data-ttu-id="8437d-153">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="8437d-153">tax registration number</span></span>
  
<span data-ttu-id="8437d-154">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-154">tax id</span></span>
  
<span data-ttu-id="8437d-155">NIF</span><span class="sxs-lookup"><span data-stu-id="8437d-155">nif</span></span>
  
<span data-ttu-id="8437d-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="8437d-156">nif#</span></span>
  
<span data-ttu-id="8437d-157">numéro de registros nacionales</span><span class="sxs-lookup"><span data-stu-id="8437d-157">numéro de registre national</span></span>
  
<span data-ttu-id="8437d-158">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="8437d-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="8437d-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8437d-160">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-160">Format</span></span>

<span data-ttu-id="8437d-161">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-162">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-162">Pattern</span></span>

<span data-ttu-id="8437d-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-164">Checksum</span></span>

<span data-ttu-id="8437d-165">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-166">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-166">Definition</span></span>

<span data-ttu-id="8437d-167">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-168">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-169">Se encuentra una `Keywords_bulgaria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-170">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-171">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-172">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="8437d-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-174">bucn</span><span class="sxs-lookup"><span data-stu-id="8437d-174">bucn</span></span>
  
<span data-ttu-id="8437d-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="8437d-175">uniform civil number</span></span>
  
<span data-ttu-id="8437d-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="8437d-176">bucn#</span></span>
  
<span data-ttu-id="8437d-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="8437d-178">identificador civil uniforme</span><span class="sxs-lookup"><span data-stu-id="8437d-178">uniform civil id</span></span>
  
<span data-ttu-id="8437d-179">Uniform civil no</span><span class="sxs-lookup"><span data-stu-id="8437d-179">uniform civil no</span></span>
  
<span data-ttu-id="8437d-180">egn</span><span class="sxs-lookup"><span data-stu-id="8437d-180">egn</span></span>
  
<span data-ttu-id="8437d-181">número civil uniforme de búlgaro</span><span class="sxs-lookup"><span data-stu-id="8437d-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="8437d-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="8437d-182">uniformcivilno#</span></span>
  
<span data-ttu-id="8437d-183">egn #</span><span class="sxs-lookup"><span data-stu-id="8437d-183">egn#</span></span>
  
<span data-ttu-id="8437d-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="8437d-184">униформ граждански номер</span></span>
  
<span data-ttu-id="8437d-185">identificador униформ</span><span class="sxs-lookup"><span data-stu-id="8437d-185">униформ id</span></span>
  
<span data-ttu-id="8437d-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="8437d-186">униформ граждански id</span></span>
  
<span data-ttu-id="8437d-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="8437d-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="8437d-188">Croacia</span><span class="sxs-lookup"><span data-stu-id="8437d-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8437d-189">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-189">Format</span></span>

<span data-ttu-id="8437d-190">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-191">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-191">Pattern</span></span>

<span data-ttu-id="8437d-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-192">11 digits:</span></span>
  
- <span data-ttu-id="8437d-193">Diez dígitos, elegidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="8437d-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="8437d-194">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="8437d-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-195">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-195">Checksum</span></span>

<span data-ttu-id="8437d-196">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-197">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-197">Definition</span></span>

<span data-ttu-id="8437d-198">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-199">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-200">Se encuentra una `Keywords_croatia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-202">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-203">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="8437d-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-205">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-205">tax number</span></span>
  
<span data-ttu-id="8437d-206">Tax</span><span class="sxs-lookup"><span data-stu-id="8437d-206">tax</span></span>
  
<span data-ttu-id="8437d-207">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-207">tax id</span></span>
  
<span data-ttu-id="8437d-208">oid</span><span class="sxs-lookup"><span data-stu-id="8437d-208">oid</span></span>
  
<span data-ttu-id="8437d-209">OID #</span><span class="sxs-lookup"><span data-stu-id="8437d-209">oid#</span></span>
  
<span data-ttu-id="8437d-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="8437d-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="8437d-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="8437d-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8437d-212">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-212">Format</span></span>

<span data-ttu-id="8437d-213">Ocho dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="8437d-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-214">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-214">Pattern</span></span>

<span data-ttu-id="8437d-215">Ocho dígitos y una letra:</span><span class="sxs-lookup"><span data-stu-id="8437d-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="8437d-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="8437d-216">A "0"</span></span> 
    
- <span data-ttu-id="8437d-217">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-217">Seven digits</span></span>
    
- <span data-ttu-id="8437d-218">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-219">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-219">Checksum</span></span>

<span data-ttu-id="8437d-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-221">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-221">Definition</span></span>

<span data-ttu-id="8437d-222">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-223">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-224">Se encuentra una `Keywords_cyprus_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-226">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="8437d-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-229">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-229">tax number</span></span>
  
<span data-ttu-id="8437d-230">Tax</span><span class="sxs-lookup"><span data-stu-id="8437d-230">tax</span></span>
  
<span data-ttu-id="8437d-231">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-231">tax id</span></span>
  
<span data-ttu-id="8437d-232">código de identificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-232">tax identification code</span></span>
  
<span data-ttu-id="8437d-233">verticales</span><span class="sxs-lookup"><span data-stu-id="8437d-233">tic</span></span>
  
<span data-ttu-id="8437d-234">verticales #</span><span class="sxs-lookup"><span data-stu-id="8437d-234">tic#</span></span>
  
<span data-ttu-id="8437d-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="8437d-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="8437d-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="8437d-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="8437d-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="8437d-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="8437d-238">Chequia</span><span class="sxs-lookup"><span data-stu-id="8437d-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8437d-239">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-239">Format</span></span>

<span data-ttu-id="8437d-240">Nueve o diez dígitos con una barra diagonal inversa opcional</span><span class="sxs-lookup"><span data-stu-id="8437d-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-241">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-241">Pattern</span></span>

<span data-ttu-id="8437d-242">Nueve o diez dígitos con una barra diagonal inversa opcional:</span><span class="sxs-lookup"><span data-stu-id="8437d-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="8437d-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-243">Six digits</span></span> 
    
- <span data-ttu-id="8437d-244">Una barra diagonal inversa (opcional)</span><span class="sxs-lookup"><span data-stu-id="8437d-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="8437d-245">Tres o cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-246">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-246">Checksum</span></span>

<span data-ttu-id="8437d-247">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-248">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-248">Definition</span></span>

<span data-ttu-id="8437d-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-250">La expresión `Regex_czech_republic_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-251">Se encuentra una `Keywords_czech_republic_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="8437d-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-254">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-254">tax number</span></span>
  
<span data-ttu-id="8437d-255">Tax</span><span class="sxs-lookup"><span data-stu-id="8437d-255">tax</span></span>
  
<span data-ttu-id="8437d-256">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-256">tax id</span></span>
  
<span data-ttu-id="8437d-257">número personal</span><span class="sxs-lookup"><span data-stu-id="8437d-257">personal number</span></span>
  
<span data-ttu-id="8437d-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="8437d-258">daňové číslo</span></span>
  
<span data-ttu-id="8437d-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="8437d-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="8437d-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="8437d-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8437d-261">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-261">Format</span></span>

<span data-ttu-id="8437d-262">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="8437d-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-263">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-263">Pattern</span></span>

<span data-ttu-id="8437d-264">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="8437d-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="8437d-265">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="8437d-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="8437d-266">Un guión </span><span class="sxs-lookup"><span data-stu-id="8437d-266">A hyphen</span></span>
    
- <span data-ttu-id="8437d-267">Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)</span><span class="sxs-lookup"><span data-stu-id="8437d-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-268">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-268">Checksum</span></span>

<span data-ttu-id="8437d-269">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-270">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-270">Definition</span></span>

<span data-ttu-id="8437d-271">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-272">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-273">Se encuentra una `Keywords_denmark_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-275">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-276">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="8437d-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-278">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-278">tax number</span></span>
  
<span data-ttu-id="8437d-279">Tax</span><span class="sxs-lookup"><span data-stu-id="8437d-279">tax</span></span>
  
<span data-ttu-id="8437d-280">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-280">tax id</span></span>
  
<span data-ttu-id="8437d-281">RCP número</span><span class="sxs-lookup"><span data-stu-id="8437d-281">cpr number</span></span>
  
<span data-ttu-id="8437d-282">RCP #</span><span class="sxs-lookup"><span data-stu-id="8437d-282">cpr#</span></span>
  
<span data-ttu-id="8437d-283">Nummer de patinaje</span><span class="sxs-lookup"><span data-stu-id="8437d-283">skat nummer</span></span>
  
<span data-ttu-id="8437d-284">identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="8437d-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="8437d-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="8437d-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8437d-286">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-286">Format</span></span>

<span data-ttu-id="8437d-287">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-288">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-288">Pattern</span></span>

<span data-ttu-id="8437d-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-289">11 digits:</span></span>
  
-  <span data-ttu-id="8437d-290">Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI</span><span class="sxs-lookup"><span data-stu-id="8437d-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="8437d-291">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="8437d-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="8437d-292">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="8437d-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="8437d-293">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="8437d-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-294">Checksum</span></span>

<span data-ttu-id="8437d-295">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-296">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-296">Definition</span></span>

<span data-ttu-id="8437d-297">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-298">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-299">Se encuentra una `Keywords_estonia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-301">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-302">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="8437d-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-304">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-304">tax number</span></span>
  
<span data-ttu-id="8437d-305">Tax</span><span class="sxs-lookup"><span data-stu-id="8437d-305">tax</span></span>
  
<span data-ttu-id="8437d-306">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-306">tax id</span></span>
  
<span data-ttu-id="8437d-307">código personal</span><span class="sxs-lookup"><span data-stu-id="8437d-307">personal code</span></span>
  
<span data-ttu-id="8437d-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="8437d-308">maksunumber</span></span>
  
<span data-ttu-id="8437d-309">identificador maksu</span><span class="sxs-lookup"><span data-stu-id="8437d-309">maksu id</span></span>
  
<span data-ttu-id="8437d-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="8437d-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="8437d-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="8437d-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="8437d-312">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-312">Format</span></span>

<span data-ttu-id="8437d-313">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos</span><span class="sxs-lookup"><span data-stu-id="8437d-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-314">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-314">Pattern</span></span>

<span data-ttu-id="8437d-315">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:</span><span class="sxs-lookup"><span data-stu-id="8437d-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="8437d-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-316">Six digits</span></span>
    
- <span data-ttu-id="8437d-317">Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior</span><span class="sxs-lookup"><span data-stu-id="8437d-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="8437d-318">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-318">Three digits</span></span>
    
- <span data-ttu-id="8437d-319">Una letra o un número</span><span class="sxs-lookup"><span data-stu-id="8437d-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-320">Checksum</span></span>

<span data-ttu-id="8437d-321">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-322">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-322">Definition</span></span>

<span data-ttu-id="8437d-323">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-324">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-325">Se encuentra una `Keywords_finland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-327">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-328">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="8437d-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-330">identification number</span><span class="sxs-lookup"><span data-stu-id="8437d-330">identification number</span></span>
  
<span data-ttu-id="8437d-331">identificador personal</span><span class="sxs-lookup"><span data-stu-id="8437d-331">personal id</span></span>
  
<span data-ttu-id="8437d-332">número de identidad</span><span class="sxs-lookup"><span data-stu-id="8437d-332">identity number</span></span>
  
<span data-ttu-id="8437d-333">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="8437d-333">finnish national id number</span></span>
  
<span data-ttu-id="8437d-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-334">personalidnumber#</span></span>
  
<span data-ttu-id="8437d-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="8437d-335">national identification number</span></span>
  
<span data-ttu-id="8437d-336">número de identificador</span><span class="sxs-lookup"><span data-stu-id="8437d-336">id number</span></span>
  
<span data-ttu-id="8437d-337">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="8437d-337">national id no.</span></span>
  
<span data-ttu-id="8437d-338">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="8437d-338">national id number</span></span>
  
<span data-ttu-id="8437d-339">identificador no</span><span class="sxs-lookup"><span data-stu-id="8437d-339">id no</span></span>
  
<span data-ttu-id="8437d-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="8437d-340">tunnistenumero</span></span>
  
<span data-ttu-id="8437d-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="8437d-341">henkilötunnus</span></span>
  
<span data-ttu-id="8437d-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="8437d-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="8437d-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="8437d-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="8437d-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="8437d-344">identiteetti numero</span></span>
  
<span data-ttu-id="8437d-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="8437d-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="8437d-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="8437d-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="8437d-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="8437d-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="8437d-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="8437d-348">tunnusnumero</span></span>
  
<span data-ttu-id="8437d-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="8437d-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="8437d-350">Francia</span><span class="sxs-lookup"><span data-stu-id="8437d-350">France</span></span>

### <a name="format"></a><span data-ttu-id="8437d-351">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-351">Format</span></span>

<span data-ttu-id="8437d-352">13 dígitos para personas y nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="8437d-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-353">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-353">Pattern</span></span>

<span data-ttu-id="8437d-354">13 dígitos para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8437d-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="8437d-355">Un dígito que debe ser 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="8437d-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="8437d-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-356">12 digits</span></span>
    
<span data-ttu-id="8437d-357">Nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="8437d-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-358">Checksum</span></span>

<span data-ttu-id="8437d-359">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-360">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-360">Definition</span></span>

<span data-ttu-id="8437d-361">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-362">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-363">Se encuentra una `Keywords_france_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-365">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="8437d-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-368">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-368">tax identification number</span></span>
  
<span data-ttu-id="8437d-369">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-369">tax number</span></span>
  
<span data-ttu-id="8437d-370">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-370">tax id</span></span>
  
<span data-ttu-id="8437d-371">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="8437d-372">Alemania</span><span class="sxs-lookup"><span data-stu-id="8437d-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="8437d-373">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-373">Format</span></span>

<span data-ttu-id="8437d-374">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-375">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-375">Pattern</span></span>

<span data-ttu-id="8437d-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-376">11 digits :</span></span>
  
-  <span data-ttu-id="8437d-377">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-377">Ten digits</span></span> 
    
- <span data-ttu-id="8437d-378">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="8437d-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-379">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-379">Checksum</span></span>

<span data-ttu-id="8437d-380">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-381">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-381">Definition</span></span>

<span data-ttu-id="8437d-382">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-383">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-384">Se encuentra una `Keywords_germany_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-386">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="8437d-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-389">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-389">tax number</span></span>
  
<span data-ttu-id="8437d-390">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-390">tax no.</span></span>
  
<span data-ttu-id="8437d-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-391">taxno#</span></span>
  
<span data-ttu-id="8437d-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-392">taxnumber#</span></span>
  
<span data-ttu-id="8437d-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-393">taxnumber</span></span>
  
<span data-ttu-id="8437d-394">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-394">tax id</span></span>
  
<span data-ttu-id="8437d-395">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-395">taxid#</span></span>
  
<span data-ttu-id="8437d-396">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-396">tax identification number</span></span>
  
<span data-ttu-id="8437d-397">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-397">tax identification no.</span></span>
  
<span data-ttu-id="8437d-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="8437d-398">steuernummer</span></span>
  
<span data-ttu-id="8437d-399">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="8437d-399">steuer id</span></span>
  
<span data-ttu-id="8437d-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8437d-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="8437d-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="8437d-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8437d-402">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-402">Format</span></span>

<span data-ttu-id="8437d-403">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-404">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-404">Pattern</span></span>

<span data-ttu-id="8437d-405">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-406">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-406">Checksum</span></span>

<span data-ttu-id="8437d-407">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-408">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-408">Definition</span></span>

<span data-ttu-id="8437d-409">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-410">La expresión `Regex_greece_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-411">Se encuentra una `Keywords_greece_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-412">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="8437d-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-414">afm</span><span class="sxs-lookup"><span data-stu-id="8437d-414">afm</span></span>
  
<span data-ttu-id="8437d-415">/</span><span class="sxs-lookup"><span data-stu-id="8437d-415">tin</span></span>
  
<span data-ttu-id="8437d-416">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-416">tax id no.</span></span>
  
<span data-ttu-id="8437d-417">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-417">tax id no</span></span>
  
<span data-ttu-id="8437d-418">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-418">tax identification number</span></span>
  
<span data-ttu-id="8437d-419">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-419">tax registry number</span></span>
  
<span data-ttu-id="8437d-420">n.º de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-420">tax registry no.</span></span>
  
<span data-ttu-id="8437d-421">afm #</span><span class="sxs-lookup"><span data-stu-id="8437d-421">afm#</span></span>
  
<span data-ttu-id="8437d-422">/ #</span><span class="sxs-lookup"><span data-stu-id="8437d-422">tin#</span></span>
  
<span data-ttu-id="8437d-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="8437d-423">taxidno#</span></span>
  
<span data-ttu-id="8437d-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="8437d-424">taxregistryno#</span></span>
  
<span data-ttu-id="8437d-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="8437d-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="8437d-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="8437d-426">aφμ</span></span>
  
<span data-ttu-id="8437d-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="8437d-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="8437d-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="8437d-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="8437d-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="8437d-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="8437d-430">Hungría</span><span class="sxs-lookup"><span data-stu-id="8437d-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8437d-431">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-431">Format</span></span>

<span data-ttu-id="8437d-432">Diez dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-433">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-433">Pattern</span></span>

<span data-ttu-id="8437d-434">Diez dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-434">Ten digits:</span></span>
  
-  <span data-ttu-id="8437d-435">Un dígito que debe ser "8"</span><span class="sxs-lookup"><span data-stu-id="8437d-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="8437d-436">Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.</span><span class="sxs-lookup"><span data-stu-id="8437d-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="8437d-437">Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día</span><span class="sxs-lookup"><span data-stu-id="8437d-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="8437d-438">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="8437d-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-439">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-439">Checksum</span></span>

<span data-ttu-id="8437d-440">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-441">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-441">Definition</span></span>

<span data-ttu-id="8437d-442">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-443">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-444">Se encuentra una `Keywords_hungary_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-445">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-446">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-447">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="8437d-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-449">número de identificación fiscal húngara</span><span class="sxs-lookup"><span data-stu-id="8437d-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="8437d-450">NIF Húngaro</span><span class="sxs-lookup"><span data-stu-id="8437d-450">hungarian tin</span></span>
  
<span data-ttu-id="8437d-451">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-451">tax id number</span></span>
  
<span data-ttu-id="8437d-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="8437d-452">vat number</span></span>
  
<span data-ttu-id="8437d-453">n.º de autoridad fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-453">tax authority no</span></span>
  
<span data-ttu-id="8437d-454">número de identidad fiscal de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-454">tax id tax identity number</span></span>
  
<span data-ttu-id="8437d-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-455">taxidnumber#</span></span>
  
<span data-ttu-id="8437d-456">/ #</span><span class="sxs-lookup"><span data-stu-id="8437d-456">tin#</span></span>
  
<span data-ttu-id="8437d-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="8437d-457">hungatiantin#</span></span>
  
<span data-ttu-id="8437d-458">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-458">tax identification no</span></span>
  
<span data-ttu-id="8437d-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="8437d-459">taxidno#</span></span>
  
<span data-ttu-id="8437d-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="8437d-460">adóazonosító szám</span></span>
  
<span data-ttu-id="8437d-461">adószám</span><span class="sxs-lookup"><span data-stu-id="8437d-461">adószám</span></span>
  
<span data-ttu-id="8437d-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="8437d-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="8437d-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="8437d-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8437d-464">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-464">Format</span></span>

<span data-ttu-id="8437d-465">Siete dígitos seguidos de una letra sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-466">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-466">Pattern</span></span>

<span data-ttu-id="8437d-467">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="8437d-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="8437d-468">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-468">Seven digits</span></span> 
    
- <span data-ttu-id="8437d-469">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-470">Checksum</span></span>

<span data-ttu-id="8437d-471">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-472">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-472">Definition</span></span>

<span data-ttu-id="8437d-473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-474">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-475">Se encuentra una `Keywords_ireland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-476">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-477">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="8437d-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-480">n.º de servicio público</span><span class="sxs-lookup"><span data-stu-id="8437d-480">public service no</span></span>
  
<span data-ttu-id="8437d-481">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="8437d-481">personal public service no</span></span>
  
<span data-ttu-id="8437d-482">n.º de PPS</span><span class="sxs-lookup"><span data-stu-id="8437d-482">pps no</span></span>
  
<span data-ttu-id="8437d-483">n.º de servicio personal</span><span class="sxs-lookup"><span data-stu-id="8437d-483">personal service no</span></span>
  
<span data-ttu-id="8437d-484">n.º de servicio de PPS</span><span class="sxs-lookup"><span data-stu-id="8437d-484">pps service no</span></span>
  
<span data-ttu-id="8437d-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="8437d-485">ppsno#</span></span>
  
<span data-ttu-id="8437d-486">n.º de PPS irlandés</span><span class="sxs-lookup"><span data-stu-id="8437d-486">irish pps no</span></span>
  
<span data-ttu-id="8437d-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="8437d-487">publicserviceno#</span></span>
  
<span data-ttu-id="8437d-488">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="8437d-488">personal public service number</span></span>
  
<span data-ttu-id="8437d-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="8437d-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="8437d-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="8437d-490">pps uimh</span></span>
  
<span data-ttu-id="8437d-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="8437d-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="8437d-492">Italia</span><span class="sxs-lookup"><span data-stu-id="8437d-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8437d-493">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-493">Format</span></span>

<span data-ttu-id="8437d-494">16 letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="8437d-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-495">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-495">Pattern</span></span>

<span data-ttu-id="8437d-496">16 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="8437d-497">Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="8437d-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="8437d-498">Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre</span><span class="sxs-lookup"><span data-stu-id="8437d-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="8437d-499">Dos dígitos que corresponden a los últimos dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="8437d-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="8437d-500">Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="8437d-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="8437d-501">Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos</span><span class="sxs-lookup"><span data-stu-id="8437d-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="8437d-502">Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).</span><span class="sxs-lookup"><span data-stu-id="8437d-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="8437d-503">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="8437d-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-504">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-504">Checksum</span></span>

<span data-ttu-id="8437d-505">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-506">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-506">Definition</span></span>

<span data-ttu-id="8437d-507">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-508">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-509">Se encuentra una `Keywords_italy_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-510">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-511">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-512">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="8437d-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-514">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-514">tax number</span></span>
  
<span data-ttu-id="8437d-515">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-515">tax no.</span></span>
  
<span data-ttu-id="8437d-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-516">taxno#</span></span>
  
<span data-ttu-id="8437d-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-517">taxnumber#</span></span>
  
<span data-ttu-id="8437d-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-518">taxnumber</span></span>
  
<span data-ttu-id="8437d-519">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-519">tax id</span></span>
  
<span data-ttu-id="8437d-520">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-520">taxid#</span></span>
  
<span data-ttu-id="8437d-521">Código fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-521">fiscal code</span></span>
  
<span data-ttu-id="8437d-522">Codice fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="8437d-523">Letonia</span><span class="sxs-lookup"><span data-stu-id="8437d-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8437d-524">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-524">Format</span></span>

<span data-ttu-id="8437d-525">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-526">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-526">Pattern</span></span>

<span data-ttu-id="8437d-527">11 dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="8437d-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="8437d-528">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="8437d-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="8437d-529">Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.</span><span class="sxs-lookup"><span data-stu-id="8437d-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="8437d-530">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-531">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-531">Checksum</span></span>

<span data-ttu-id="8437d-532">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-533">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-533">Definition</span></span>

<span data-ttu-id="8437d-534">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-535">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-536">Se encuentra una `Keywords_latvia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-537">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-538">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-539">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="8437d-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-541">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-541">tax number</span></span>
  
<span data-ttu-id="8437d-542">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-542">tax no.</span></span>
  
<span data-ttu-id="8437d-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-543">taxno#</span></span>
  
<span data-ttu-id="8437d-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-544">taxnumber#</span></span>
  
<span data-ttu-id="8437d-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-545">taxnumber</span></span>
  
<span data-ttu-id="8437d-546">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-546">tax id</span></span>
  
<span data-ttu-id="8437d-547">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-547">taxid#</span></span>
  
<span data-ttu-id="8437d-548">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-548">tax identification number</span></span>
  
<span data-ttu-id="8437d-549">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-549">tax identification no.</span></span>
  
<span data-ttu-id="8437d-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="8437d-550">nodokļa numurs</span></span>
  
<span data-ttu-id="8437d-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="8437d-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="8437d-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="8437d-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="8437d-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="8437d-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8437d-554">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-554">Format</span></span>

<span data-ttu-id="8437d-555">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-556">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-556">Pattern</span></span>

<span data-ttu-id="8437d-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-558">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-558">Checksum</span></span>

<span data-ttu-id="8437d-559">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-560">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-560">Definition</span></span>

<span data-ttu-id="8437d-561">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-562">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-563">Se encuentra una `Keywords_lithuania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-564">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-565">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-566">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="8437d-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-568">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-568">tax number</span></span>
  
<span data-ttu-id="8437d-569">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-569">tax no.</span></span>
  
<span data-ttu-id="8437d-570">Nº de impuestos #</span><span class="sxs-lookup"><span data-stu-id="8437d-570">tax no#</span></span>
  
<span data-ttu-id="8437d-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-571">taxnumber#</span></span>
  
<span data-ttu-id="8437d-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-572">taxnumber</span></span>
  
<span data-ttu-id="8437d-573">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-573">tax id</span></span>
  
<span data-ttu-id="8437d-574">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-574">taxid#</span></span>
  
<span data-ttu-id="8437d-575">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-575">tax identification number</span></span>
  
<span data-ttu-id="8437d-576">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-576">tax identification no.</span></span>
  
<span data-ttu-id="8437d-577">identificador mokesčių</span><span class="sxs-lookup"><span data-stu-id="8437d-577">mokesčių id</span></span>
  
<span data-ttu-id="8437d-578">numeración mokesčių</span><span class="sxs-lookup"><span data-stu-id="8437d-578">mokesčių numeris</span></span>
  
<span data-ttu-id="8437d-579">mokesčių identifikavimas número</span><span class="sxs-lookup"><span data-stu-id="8437d-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="8437d-580">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="8437d-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8437d-581">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-581">Format</span></span>

<span data-ttu-id="8437d-582">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-583">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-583">Pattern</span></span>

<span data-ttu-id="8437d-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="8437d-584">13 digits:</span></span>
  
-  <span data-ttu-id="8437d-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-585">11 digits</span></span> 
    
- <span data-ttu-id="8437d-586">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="8437d-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-587">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-587">Checksum</span></span>

<span data-ttu-id="8437d-588">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-589">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-589">Definition</span></span>

<span data-ttu-id="8437d-590">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-591">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-592">Se encuentra una `Keywords_luxemburg_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-593">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-594">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-595">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="8437d-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-597">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-597">tax number</span></span>
  
<span data-ttu-id="8437d-598">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-598">tax no.</span></span>
  
<span data-ttu-id="8437d-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-599">taxno#</span></span>
  
<span data-ttu-id="8437d-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-600">taxnumber#</span></span>
  
<span data-ttu-id="8437d-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-601">taxnumber</span></span>
  
<span data-ttu-id="8437d-602">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-602">tax id</span></span>
  
<span data-ttu-id="8437d-603">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-603">taxid#</span></span>
  
<span data-ttu-id="8437d-604">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-604">tax identification number</span></span>
  
<span data-ttu-id="8437d-605">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-605">tax identification no.</span></span>
  
<span data-ttu-id="8437d-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="8437d-606">steuernummer</span></span>
  
<span data-ttu-id="8437d-607">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="8437d-607">steuer id</span></span>
  
<span data-ttu-id="8437d-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8437d-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="8437d-609">Malta</span><span class="sxs-lookup"><span data-stu-id="8437d-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8437d-610">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-610">Format</span></span>

<span data-ttu-id="8437d-611">Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="8437d-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="8437d-612">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-613">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-613">Pattern</span></span>

<span data-ttu-id="8437d-614">Nacionales de Malta: 7 dígitos y una letra</span><span class="sxs-lookup"><span data-stu-id="8437d-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="8437d-615">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-615">Seven digits</span></span> 
    
- <span data-ttu-id="8437d-616">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="8437d-617">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="8437d-618">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8437d-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-619">Checksum</span></span>

<span data-ttu-id="8437d-620">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-621">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-621">Definition</span></span>

<span data-ttu-id="8437d-622">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-623">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-624">Se encuentra una `Keywords_malta_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-626">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-627">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="8437d-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-629">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-629">tax number</span></span>
  
<span data-ttu-id="8437d-630">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-630">tax no.</span></span>
  
<span data-ttu-id="8437d-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-631">taxno#</span></span>
  
<span data-ttu-id="8437d-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-632">taxnumber#</span></span>
  
<span data-ttu-id="8437d-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-633">taxnumber</span></span>
  
<span data-ttu-id="8437d-634">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-634">tax id</span></span>
  
<span data-ttu-id="8437d-635">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-635">taxid#</span></span>
  
<span data-ttu-id="8437d-636">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-636">tax identification number</span></span>
  
<span data-ttu-id="8437d-637">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-637">tax identification no.</span></span>
  
<span data-ttu-id="8437d-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="8437d-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="8437d-639">identificador TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="8437d-639">id tat-taxxa</span></span>
  
<span data-ttu-id="8437d-640">numru ta ' identifikazzjoni TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="8437d-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="8437d-641">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="8437d-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8437d-642">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-642">Format</span></span>

<span data-ttu-id="8437d-643">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-644">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-644">Pattern</span></span>

<span data-ttu-id="8437d-645">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8437d-646">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-646">Checksum</span></span>

<span data-ttu-id="8437d-647">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-648">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-648">Definition</span></span>

<span data-ttu-id="8437d-649">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-650">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-651">Se encuentra una `Keywords_netherlands_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-652">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-653">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-654">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="8437d-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-656">número de identificación fiscal de países bajos</span><span class="sxs-lookup"><span data-stu-id="8437d-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="8437d-657">identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="8437d-657">netherlands tax identification</span></span>
  
<span data-ttu-id="8437d-658">número de identificación fiscal de Netherland</span><span class="sxs-lookup"><span data-stu-id="8437d-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="8437d-659">identificación de impuestos de Netherland</span><span class="sxs-lookup"><span data-stu-id="8437d-659">netherland's tax identification</span></span>
  
<span data-ttu-id="8437d-660">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-660">tax identification number</span></span>
  
<span data-ttu-id="8437d-661">identificador fiscal holandés</span><span class="sxs-lookup"><span data-stu-id="8437d-661">dutch tax id</span></span>
  
<span data-ttu-id="8437d-662">número de identificación fiscal holandes</span><span class="sxs-lookup"><span data-stu-id="8437d-662">dutch tax identification number</span></span>
  
<span data-ttu-id="8437d-663">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-663">tax id</span></span>
  
<span data-ttu-id="8437d-664">identificador de impuesto #</span><span class="sxs-lookup"><span data-stu-id="8437d-664">tax id#</span></span>
  
<span data-ttu-id="8437d-665">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-665">tax number</span></span>
  
<span data-ttu-id="8437d-666">Nº de impuestos #</span><span class="sxs-lookup"><span data-stu-id="8437d-666">tax no#</span></span>
  
<span data-ttu-id="8437d-667">Tax #</span><span class="sxs-lookup"><span data-stu-id="8437d-667">tax#</span></span>
  
<span data-ttu-id="8437d-668">/</span><span class="sxs-lookup"><span data-stu-id="8437d-668">tin</span></span>
  
<span data-ttu-id="8437d-669">/ #</span><span class="sxs-lookup"><span data-stu-id="8437d-669">tin#</span></span>
  
<span data-ttu-id="8437d-670">NIF-Países Bajos</span><span class="sxs-lookup"><span data-stu-id="8437d-670">netherlands tin</span></span>
  
<span data-ttu-id="8437d-671">estaño de Netherland</span><span class="sxs-lookup"><span data-stu-id="8437d-671">netherland's tin</span></span>
  
<span data-ttu-id="8437d-672">último países de la identificatienummer</span><span class="sxs-lookup"><span data-stu-id="8437d-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="8437d-673">identificatienummerto de furgoneta</span><span class="sxs-lookup"><span data-stu-id="8437d-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="8437d-674">identificatienummer en último lugar</span><span class="sxs-lookup"><span data-stu-id="8437d-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="8437d-675">último países de la identificatie</span><span class="sxs-lookup"><span data-stu-id="8437d-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="8437d-676">último identificador de Nummer de países bajos</span><span class="sxs-lookup"><span data-stu-id="8437d-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="8437d-677">Países Bajos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="8437d-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="8437d-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="8437d-678">btw nummer</span></span>
  
<span data-ttu-id="8437d-679">Nederlandse de la última identificatie</span><span class="sxs-lookup"><span data-stu-id="8437d-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="8437d-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="8437d-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="8437d-681">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-681">Format</span></span>

<span data-ttu-id="8437d-682">Once dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-683">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-683">Pattern</span></span>

<span data-ttu-id="8437d-684">Once dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-685">Checksum</span></span>

<span data-ttu-id="8437d-686">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-687">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-687">Definition</span></span>

<span data-ttu-id="8437d-688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-689">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-690">Se encuentra una `Keywords_poland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-691">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-692">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-693">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="8437d-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-695">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-695">tax number</span></span>
  
<span data-ttu-id="8437d-696">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-696">tax no.</span></span>
  
<span data-ttu-id="8437d-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-697">taxno#</span></span>
  
<span data-ttu-id="8437d-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-698">taxnumber#</span></span>
  
<span data-ttu-id="8437d-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-699">taxnumber</span></span>
  
<span data-ttu-id="8437d-700">nip</span><span class="sxs-lookup"><span data-stu-id="8437d-700">nip</span></span>
  
<span data-ttu-id="8437d-701">nip #</span><span class="sxs-lookup"><span data-stu-id="8437d-701">nip#</span></span>
  
<span data-ttu-id="8437d-702">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-702">tax id</span></span>
  
<span data-ttu-id="8437d-703">identificador de impuesto #</span><span class="sxs-lookup"><span data-stu-id="8437d-703">tax id#</span></span>
  
<span data-ttu-id="8437d-704">identificador NIP</span><span class="sxs-lookup"><span data-stu-id="8437d-704">nip id</span></span>
  
<span data-ttu-id="8437d-705">identificador NIP #</span><span class="sxs-lookup"><span data-stu-id="8437d-705">nip id#</span></span>
  
<span data-ttu-id="8437d-706">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-706">tax identification number</span></span>
  
<span data-ttu-id="8437d-707">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-707">tax identification no.</span></span>
  
<span data-ttu-id="8437d-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="8437d-708">vat number</span></span>
  
<span data-ttu-id="8437d-709">n.º de IVA</span><span class="sxs-lookup"><span data-stu-id="8437d-709">vat no.</span></span>
  
<span data-ttu-id="8437d-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="8437d-710">vatno#</span></span>
  
<span data-ttu-id="8437d-711">NIF</span><span class="sxs-lookup"><span data-stu-id="8437d-711">vat id</span></span>
  
<span data-ttu-id="8437d-712">NIF #</span><span class="sxs-lookup"><span data-stu-id="8437d-712">vat id#</span></span>
  
<span data-ttu-id="8437d-713">numerar identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="8437d-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="8437d-714">Polski número de identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="8437d-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="8437d-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="8437d-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8437d-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="8437d-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8437d-717">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-717">Format</span></span>

<span data-ttu-id="8437d-718">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-719">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-719">Pattern</span></span>

<span data-ttu-id="8437d-720">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-721">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-721">Checksum</span></span>

<span data-ttu-id="8437d-722">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-723">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-723">Definition</span></span>

<span data-ttu-id="8437d-724">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-725">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-726">Se encuentra una `Keywords_portugal_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-728">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-729">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="8437d-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-731">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-731">tax number</span></span>
  
<span data-ttu-id="8437d-732">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-732">tax no.</span></span>
  
<span data-ttu-id="8437d-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-733">taxno#</span></span>
  
<span data-ttu-id="8437d-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="8437d-734">taxnumber#</span></span>
  
<span data-ttu-id="8437d-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="8437d-735">taxnumber</span></span>
  
<span data-ttu-id="8437d-736">NIF</span><span class="sxs-lookup"><span data-stu-id="8437d-736">nif</span></span>
  
<span data-ttu-id="8437d-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="8437d-737">nif#</span></span>
  
<span data-ttu-id="8437d-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="8437d-738">numero fiscal</span></span>
  
<span data-ttu-id="8437d-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="8437d-740">Rumania</span><span class="sxs-lookup"><span data-stu-id="8437d-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8437d-741">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-741">Format</span></span>

<span data-ttu-id="8437d-742">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-743">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-743">Pattern</span></span>

<span data-ttu-id="8437d-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-745">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-745">Checksum</span></span>

<span data-ttu-id="8437d-746">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-747">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-747">Definition</span></span>

<span data-ttu-id="8437d-748">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-749">La expresión `Regex_romania_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-750">Se encuentra una `Keywords_romania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-751">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="8437d-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-753">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-753">tax id</span></span>
  
<span data-ttu-id="8437d-754">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-754">tax id number</span></span>
  
<span data-ttu-id="8437d-755">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-755">tax file no</span></span>
  
<span data-ttu-id="8437d-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="8437d-756">tax file number</span></span>
  
<span data-ttu-id="8437d-757">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-757">tax no</span></span>
  
<span data-ttu-id="8437d-758">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-758">tax number</span></span>
  
<span data-ttu-id="8437d-759">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-759">taxid#</span></span>
  
<span data-ttu-id="8437d-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-760">taxno#</span></span>
  
<span data-ttu-id="8437d-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="8437d-761">id-ul taxei</span></span>
  
<span data-ttu-id="8437d-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="8437d-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="8437d-763">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="8437d-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8437d-764">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-764">Format</span></span>

<span data-ttu-id="8437d-765">10 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-766">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-766">Pattern</span></span>

<span data-ttu-id="8437d-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-768">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-768">Checksum</span></span>

<span data-ttu-id="8437d-769">No aplicable</span><span class="sxs-lookup"><span data-stu-id="8437d-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-770">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-770">Definition</span></span>

<span data-ttu-id="8437d-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-772">La expresión `Regex_slovakia_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-773">Se encuentra una `Keywords_slovakia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-774">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="8437d-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-776">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-776">tax id</span></span>
  
<span data-ttu-id="8437d-777">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-777">tax id number</span></span>
  
<span data-ttu-id="8437d-778">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="8437d-778">tin id</span></span>
  
<span data-ttu-id="8437d-779">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="8437d-779">tin no</span></span>
  
<span data-ttu-id="8437d-780">ID de estaño de eslovaco</span><span class="sxs-lookup"><span data-stu-id="8437d-780">slovakian tin id</span></span>
  
<span data-ttu-id="8437d-781">/</span><span class="sxs-lookup"><span data-stu-id="8437d-781">tin</span></span>
  
<span data-ttu-id="8437d-782">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-782">tax file no</span></span>
  
<span data-ttu-id="8437d-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="8437d-783">tax file number</span></span>
  
<span data-ttu-id="8437d-784">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-784">tax no</span></span>
  
<span data-ttu-id="8437d-785">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-785">tax number</span></span>
  
<span data-ttu-id="8437d-786">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-786">taxid#</span></span>
  
<span data-ttu-id="8437d-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-787">taxno#</span></span>
  
<span data-ttu-id="8437d-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="8437d-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="8437d-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="8437d-789">daňové číslo</span></span>
  
<span data-ttu-id="8437d-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="8437d-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="8437d-791">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="8437d-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8437d-792">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-792">Format</span></span>

<span data-ttu-id="8437d-793">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-794">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-794">Pattern</span></span>

<span data-ttu-id="8437d-795">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-796">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-796">Checksum</span></span>

<span data-ttu-id="8437d-797">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-798">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-798">Definition</span></span>

<span data-ttu-id="8437d-799">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-800">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-801">Se encuentra una `Keywords_slovenia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-802">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-803">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-804">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="8437d-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-806">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-806">tax id</span></span>
  
<span data-ttu-id="8437d-807">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-807">tax id number</span></span>
  
<span data-ttu-id="8437d-808">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="8437d-808">tin id</span></span>
  
<span data-ttu-id="8437d-809">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="8437d-809">tin no</span></span>
  
<span data-ttu-id="8437d-810">ID de estaño de esloveno</span><span class="sxs-lookup"><span data-stu-id="8437d-810">slovenian tin id</span></span>
  
<span data-ttu-id="8437d-811">/</span><span class="sxs-lookup"><span data-stu-id="8437d-811">tin</span></span>
  
<span data-ttu-id="8437d-812">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-812">tax file no</span></span>
  
<span data-ttu-id="8437d-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="8437d-813">tax file number</span></span>
  
<span data-ttu-id="8437d-814">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-814">tax no</span></span>
  
<span data-ttu-id="8437d-815">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-815">tax number</span></span>
  
<span data-ttu-id="8437d-816">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-816">taxid#</span></span>
  
<span data-ttu-id="8437d-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-817">taxno#</span></span>
  
<span data-ttu-id="8437d-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="8437d-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="8437d-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="8437d-819">davčna številka</span></span>
  
<span data-ttu-id="8437d-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="8437d-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="8437d-821">España</span><span class="sxs-lookup"><span data-stu-id="8437d-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8437d-822">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-822">Format</span></span>

<span data-ttu-id="8437d-823">Siete u ocho dígitos y una o dos letras en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="8437d-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-824">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-824">Pattern</span></span>

<span data-ttu-id="8437d-825">Personas físicas españolas con una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="8437d-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="8437d-826">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-826">Eight digits</span></span> 
    
- <span data-ttu-id="8437d-827">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="8437d-828">Spaniards no residente sin una tarjeta de identidad nacional de España</span><span class="sxs-lookup"><span data-stu-id="8437d-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="8437d-829">Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="8437d-830">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-830">Seven digits</span></span>
    
- <span data-ttu-id="8437d-831">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="8437d-832">Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="8437d-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="8437d-833">Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="8437d-834">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-834">Seven digits</span></span> 
    
- <span data-ttu-id="8437d-835">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="8437d-836">Foreigners con un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="8437d-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="8437d-837">Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="8437d-838">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-838">Seven digits</span></span>
    
- <span data-ttu-id="8437d-839">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="8437d-840">Foreigners sin un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="8437d-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="8437d-841">Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="8437d-842">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="8437d-842">Seven digits</span></span>
    
- <span data-ttu-id="8437d-843">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="8437d-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8437d-844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-844">Checksum</span></span>

<span data-ttu-id="8437d-845">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-846">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-846">Definition</span></span>

<span data-ttu-id="8437d-847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-848">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-849">Se encuentra una `Keywords_spain_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-850">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-851">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-852">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="8437d-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-854">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-854">tax id</span></span>
  
<span data-ttu-id="8437d-855">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-855">tax id number</span></span>
  
<span data-ttu-id="8437d-856">identificador CIF</span><span class="sxs-lookup"><span data-stu-id="8437d-856">cif id</span></span>
  
<span data-ttu-id="8437d-857">n.º CIF</span><span class="sxs-lookup"><span data-stu-id="8437d-857">cif no</span></span>
  
<span data-ttu-id="8437d-858">identificador CIF en Español</span><span class="sxs-lookup"><span data-stu-id="8437d-858">spanish cif id</span></span>
  
<span data-ttu-id="8437d-859">precio</span><span class="sxs-lookup"><span data-stu-id="8437d-859">cif</span></span>
  
<span data-ttu-id="8437d-860">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-860">tax file no</span></span>
  
<span data-ttu-id="8437d-861">Número CIF en Español</span><span class="sxs-lookup"><span data-stu-id="8437d-861">spanish cif number</span></span>
  
<span data-ttu-id="8437d-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="8437d-862">tax file number</span></span>
  
<span data-ttu-id="8437d-863">Número CIF de Español</span><span class="sxs-lookup"><span data-stu-id="8437d-863">spanish cif no</span></span>
  
<span data-ttu-id="8437d-864">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-864">tax no</span></span>
  
<span data-ttu-id="8437d-865">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="8437d-865">tax number</span></span>
  
<span data-ttu-id="8437d-866">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-866">taxid#</span></span>
  
<span data-ttu-id="8437d-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="8437d-867">taxno#</span></span>
  
<span data-ttu-id="8437d-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="8437d-868">cifid#</span></span>
  
<span data-ttu-id="8437d-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="8437d-869">spanishcifid#</span></span>
  
<span data-ttu-id="8437d-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="8437d-870">spanishcifno#</span></span>
  
<span data-ttu-id="8437d-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="8437d-871">número de contribuyente</span></span>
  
<span data-ttu-id="8437d-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="8437d-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="8437d-873">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="8437d-874">Número CIF</span><span class="sxs-lookup"><span data-stu-id="8437d-874">cif número</span></span>
  
<span data-ttu-id="8437d-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="8437d-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="8437d-876">Suecia</span><span class="sxs-lookup"><span data-stu-id="8437d-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="8437d-877">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-877">Format</span></span>

<span data-ttu-id="8437d-878">Diez dígitos y un símbolo en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="8437d-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-879">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-879">Pattern</span></span>

<span data-ttu-id="8437d-880">Diez dígitos y un símbolo:</span><span class="sxs-lookup"><span data-stu-id="8437d-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="8437d-881">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="8437d-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="8437d-882">Un signo más, un signo menos o una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="8437d-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="8437d-883">Tres dígitos que hacen que el número de identificación sea único donde:</span><span class="sxs-lookup"><span data-stu-id="8437d-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="8437d-884">Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero</span><span class="sxs-lookup"><span data-stu-id="8437d-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="8437d-885">El dígito en la novena posición indica el género, ya sea impar o incluso para hembras</span><span class="sxs-lookup"><span data-stu-id="8437d-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="8437d-886">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="8437d-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8437d-887">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-887">Checksum</span></span>

<span data-ttu-id="8437d-888">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-889">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-889">Definition</span></span>

<span data-ttu-id="8437d-890">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-891">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-892">Se encuentra una `Keywords_sweden_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="8437d-893">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-894">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-895">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="8437d-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-897">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-897">tax id</span></span>
  
<span data-ttu-id="8437d-898">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-898">tax id no.</span></span>
  
<span data-ttu-id="8437d-899">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-899">tax id number</span></span>
  
<span data-ttu-id="8437d-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="8437d-900">tax identification</span></span>
  
<span data-ttu-id="8437d-901">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="8437d-901">tax identification#</span></span>
  
<span data-ttu-id="8437d-902">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-902">tax no.</span></span>
  
<span data-ttu-id="8437d-903">Tax #</span><span class="sxs-lookup"><span data-stu-id="8437d-903">tax#</span></span>
  
<span data-ttu-id="8437d-904">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-904">taxid#</span></span>
  
<span data-ttu-id="8437d-905">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-905">tax file</span></span>
  
<span data-ttu-id="8437d-906">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-906">tax file no.</span></span>
  
<span data-ttu-id="8437d-907">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="8437d-907">personal id number</span></span>
  
<span data-ttu-id="8437d-908">Nummer de identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="8437d-908">skatt id nummer</span></span>
  
<span data-ttu-id="8437d-909">Identifikation de patinaje</span><span class="sxs-lookup"><span data-stu-id="8437d-909">skatt identifikation</span></span>
  
<span data-ttu-id="8437d-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="8437d-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="8437d-911">LIBRA</span><span class="sxs-lookup"><span data-stu-id="8437d-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="8437d-912">Formato</span><span class="sxs-lookup"><span data-stu-id="8437d-912">Format</span></span>

<span data-ttu-id="8437d-913">Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="8437d-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="8437d-914">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="8437d-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="8437d-915">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8437d-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8437d-916">Pattern</span><span class="sxs-lookup"><span data-stu-id="8437d-916">Pattern</span></span>

<span data-ttu-id="8437d-917">Referencia de contribuyente única (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="8437d-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="8437d-918">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="8437d-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="8437d-919">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8437d-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8437d-920">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="8437d-920">Checksum</span></span>

<span data-ttu-id="8437d-921">Sí</span><span class="sxs-lookup"><span data-stu-id="8437d-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8437d-922">Definición</span><span class="sxs-lookup"><span data-stu-id="8437d-922">Definition</span></span>

<span data-ttu-id="8437d-923">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="8437d-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8437d-924">La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="8437d-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8437d-925">Se encuentra una `Keywords_uk_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="8437d-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8437d-926">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8437d-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="8437d-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="8437d-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="8437d-928">tax id</span><span class="sxs-lookup"><span data-stu-id="8437d-928">tax id</span></span>
  
<span data-ttu-id="8437d-929">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-929">tax id no.</span></span>
  
<span data-ttu-id="8437d-930">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="8437d-930">tax id number</span></span>
  
<span data-ttu-id="8437d-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="8437d-931">tax identification</span></span>
  
<span data-ttu-id="8437d-932">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="8437d-932">tax identification#</span></span>
  
<span data-ttu-id="8437d-933">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-933">tax no.</span></span>
  
<span data-ttu-id="8437d-934">Tax #</span><span class="sxs-lookup"><span data-stu-id="8437d-934">tax#</span></span>
  
<span data-ttu-id="8437d-935">taxi #</span><span class="sxs-lookup"><span data-stu-id="8437d-935">taxid#</span></span>
  
<span data-ttu-id="8437d-936">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="8437d-936">tax file</span></span>
  
<span data-ttu-id="8437d-937">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="8437d-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8437d-938">Vea también</span><span class="sxs-lookup"><span data-stu-id="8437d-938">See also</span></span>

[<span data-ttu-id="8437d-939">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="8437d-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

