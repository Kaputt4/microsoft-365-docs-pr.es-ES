---
title: Número de identificación fiscal de la UE
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
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación de impuestos de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938676"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="c704a-104">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="c704a-104">EU Tax Identification Number</span></span>

<span data-ttu-id="c704a-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de identificación fiscal (CIF) de la UE.</span><span class="sxs-lookup"><span data-stu-id="c704a-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="c704a-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="c704a-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c704a-107">Austria</span><span class="sxs-lookup"><span data-stu-id="c704a-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c704a-108">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-108">Format</span></span>

<span data-ttu-id="c704a-109">Nueve dígitos con guión opcional y barra diagonal</span><span class="sxs-lookup"><span data-stu-id="c704a-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-110">Pattern</span></span>

<span data-ttu-id="c704a-111">Nueve dígitos con guión opcional y barra diagonal:</span><span class="sxs-lookup"><span data-stu-id="c704a-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="c704a-112">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-112">Two digits</span></span> 
    
- <span data-ttu-id="c704a-113">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="c704a-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="c704a-114">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-114">Three digits</span></span>
    
- <span data-ttu-id="c704a-115">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="c704a-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="c704a-116">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-117">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-117">Checksum</span></span>

<span data-ttu-id="c704a-118">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-119">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-119">Definition</span></span>

<span data-ttu-id="c704a-120">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-121">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-122">Se encuentra una `Keywords_austria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-123">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-124">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-125">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="c704a-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-127">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-127">tax number</span></span>
  
<span data-ttu-id="c704a-128">número</span><span class="sxs-lookup"><span data-stu-id="c704a-128">number</span></span>
  
<span data-ttu-id="c704a-129">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="c704a-129">tax registration number</span></span>
  
<span data-ttu-id="c704a-130">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-130">tax id</span></span>
  
<span data-ttu-id="c704a-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="c704a-131">st.nr.</span></span>
  
<span data-ttu-id="c704a-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c704a-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="c704a-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="c704a-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c704a-134">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-134">Format</span></span>

<span data-ttu-id="c704a-135">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-136">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-136">Pattern</span></span>

<span data-ttu-id="c704a-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-137">11 digits:</span></span>
  
- <span data-ttu-id="c704a-138">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-138">Two digits</span></span>
    
- <span data-ttu-id="c704a-139">Un "0" o "1"</span><span class="sxs-lookup"><span data-stu-id="c704a-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="c704a-140">Un dígito</span><span class="sxs-lookup"><span data-stu-id="c704a-140">One digit</span></span>
    
- <span data-ttu-id="c704a-141">Un "0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="c704a-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="c704a-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-143">Checksum</span></span>

<span data-ttu-id="c704a-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-145">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-145">Definition</span></span>

<span data-ttu-id="c704a-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-147">La expresión `Regex_belgium_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-148">Se encuentra una `Keywords_belgium_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c704a-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="c704a-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-151">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-151">tax number</span></span>
  
<span data-ttu-id="c704a-152">número de registro nacional</span><span class="sxs-lookup"><span data-stu-id="c704a-152">national registration number</span></span>
  
<span data-ttu-id="c704a-153">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="c704a-153">tax registration number</span></span>
  
<span data-ttu-id="c704a-154">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-154">tax id</span></span>
  
<span data-ttu-id="c704a-155">NIF</span><span class="sxs-lookup"><span data-stu-id="c704a-155">nif</span></span>
  
<span data-ttu-id="c704a-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="c704a-156">nif#</span></span>
  
<span data-ttu-id="c704a-157">numéro de registros nacionales</span><span class="sxs-lookup"><span data-stu-id="c704a-157">numéro de registre national</span></span>
  
<span data-ttu-id="c704a-158">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="c704a-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="c704a-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c704a-160">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-160">Format</span></span>

<span data-ttu-id="c704a-161">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-162">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-162">Pattern</span></span>

<span data-ttu-id="c704a-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-164">Checksum</span></span>

<span data-ttu-id="c704a-165">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-166">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-166">Definition</span></span>

<span data-ttu-id="c704a-167">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-168">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-169">Se encuentra una `Keywords_bulgaria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-170">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-171">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-172">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="c704a-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-174">bucn</span><span class="sxs-lookup"><span data-stu-id="c704a-174">bucn</span></span>
  
<span data-ttu-id="c704a-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="c704a-175">uniform civil number</span></span>
  
<span data-ttu-id="c704a-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="c704a-176">bucn#</span></span>
  
<span data-ttu-id="c704a-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="c704a-178">identificador civil uniforme</span><span class="sxs-lookup"><span data-stu-id="c704a-178">uniform civil id</span></span>
  
<span data-ttu-id="c704a-179">Uniform civil no</span><span class="sxs-lookup"><span data-stu-id="c704a-179">uniform civil no</span></span>
  
<span data-ttu-id="c704a-180">egn</span><span class="sxs-lookup"><span data-stu-id="c704a-180">egn</span></span>
  
<span data-ttu-id="c704a-181">número civil uniforme de búlgaro</span><span class="sxs-lookup"><span data-stu-id="c704a-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="c704a-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="c704a-182">uniformcivilno#</span></span>
  
<span data-ttu-id="c704a-183">egn #</span><span class="sxs-lookup"><span data-stu-id="c704a-183">egn#</span></span>
  
<span data-ttu-id="c704a-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="c704a-184">униформ граждански номер</span></span>
  
<span data-ttu-id="c704a-185">identificador униформ</span><span class="sxs-lookup"><span data-stu-id="c704a-185">униформ id</span></span>
  
<span data-ttu-id="c704a-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="c704a-186">униформ граждански id</span></span>
  
<span data-ttu-id="c704a-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="c704a-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="c704a-188">Croacia</span><span class="sxs-lookup"><span data-stu-id="c704a-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c704a-189">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-189">Format</span></span>

<span data-ttu-id="c704a-190">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-191">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-191">Pattern</span></span>

<span data-ttu-id="c704a-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-192">11 digits:</span></span>
  
- <span data-ttu-id="c704a-193">Diez dígitos, elegidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="c704a-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="c704a-194">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="c704a-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-195">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-195">Checksum</span></span>

<span data-ttu-id="c704a-196">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-197">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-197">Definition</span></span>

<span data-ttu-id="c704a-198">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-199">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-200">Se encuentra una `Keywords_croatia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-202">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-203">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="c704a-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-205">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-205">tax number</span></span>
  
<span data-ttu-id="c704a-206">Tax</span><span class="sxs-lookup"><span data-stu-id="c704a-206">tax</span></span>
  
<span data-ttu-id="c704a-207">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-207">tax id</span></span>
  
<span data-ttu-id="c704a-208">oid</span><span class="sxs-lookup"><span data-stu-id="c704a-208">oid</span></span>
  
<span data-ttu-id="c704a-209">OID #</span><span class="sxs-lookup"><span data-stu-id="c704a-209">oid#</span></span>
  
<span data-ttu-id="c704a-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="c704a-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="c704a-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="c704a-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c704a-212">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-212">Format</span></span>

<span data-ttu-id="c704a-213">Ocho dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c704a-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-214">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-214">Pattern</span></span>

<span data-ttu-id="c704a-215">Ocho dígitos y una letra:</span><span class="sxs-lookup"><span data-stu-id="c704a-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="c704a-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="c704a-216">A "0"</span></span> 
    
- <span data-ttu-id="c704a-217">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-217">Seven digits</span></span>
    
- <span data-ttu-id="c704a-218">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-219">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-219">Checksum</span></span>

<span data-ttu-id="c704a-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-221">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-221">Definition</span></span>

<span data-ttu-id="c704a-222">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-223">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-224">Se encuentra una `Keywords_cyprus_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-226">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="c704a-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-229">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-229">tax number</span></span>
  
<span data-ttu-id="c704a-230">Tax</span><span class="sxs-lookup"><span data-stu-id="c704a-230">tax</span></span>
  
<span data-ttu-id="c704a-231">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-231">tax id</span></span>
  
<span data-ttu-id="c704a-232">código de identificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-232">tax identification code</span></span>
  
<span data-ttu-id="c704a-233">verticales</span><span class="sxs-lookup"><span data-stu-id="c704a-233">tic</span></span>
  
<span data-ttu-id="c704a-234">verticales #</span><span class="sxs-lookup"><span data-stu-id="c704a-234">tic#</span></span>
  
<span data-ttu-id="c704a-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c704a-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="c704a-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="c704a-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="c704a-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c704a-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="c704a-238">Chequia</span><span class="sxs-lookup"><span data-stu-id="c704a-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c704a-239">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-239">Format</span></span>

<span data-ttu-id="c704a-240">Nueve o diez dígitos con una barra diagonal inversa opcional</span><span class="sxs-lookup"><span data-stu-id="c704a-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-241">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-241">Pattern</span></span>

<span data-ttu-id="c704a-242">Nueve o diez dígitos con una barra diagonal inversa opcional:</span><span class="sxs-lookup"><span data-stu-id="c704a-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="c704a-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-243">Six digits</span></span> 
    
- <span data-ttu-id="c704a-244">Una barra diagonal inversa (opcional)</span><span class="sxs-lookup"><span data-stu-id="c704a-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="c704a-245">Tres o cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-246">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-246">Checksum</span></span>

<span data-ttu-id="c704a-247">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-248">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-248">Definition</span></span>

<span data-ttu-id="c704a-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-250">La expresión `Regex_czech_republic_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-251">Se encuentra una `Keywords_czech_republic_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c704a-252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="c704a-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-254">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-254">tax number</span></span>
  
<span data-ttu-id="c704a-255">Tax</span><span class="sxs-lookup"><span data-stu-id="c704a-255">tax</span></span>
  
<span data-ttu-id="c704a-256">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-256">tax id</span></span>
  
<span data-ttu-id="c704a-257">número personal</span><span class="sxs-lookup"><span data-stu-id="c704a-257">personal number</span></span>
  
<span data-ttu-id="c704a-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="c704a-258">daňové číslo</span></span>
  
<span data-ttu-id="c704a-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="c704a-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="c704a-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="c704a-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c704a-261">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-261">Format</span></span>

<span data-ttu-id="c704a-262">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="c704a-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-263">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-263">Pattern</span></span>

<span data-ttu-id="c704a-264">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="c704a-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="c704a-265">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="c704a-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="c704a-266">Un guión </span><span class="sxs-lookup"><span data-stu-id="c704a-266">A hyphen</span></span>
    
- <span data-ttu-id="c704a-267">Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)</span><span class="sxs-lookup"><span data-stu-id="c704a-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-268">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-268">Checksum</span></span>

<span data-ttu-id="c704a-269">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-270">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-270">Definition</span></span>

<span data-ttu-id="c704a-271">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-272">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-273">Se encuentra una `Keywords_denmark_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-275">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-276">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="c704a-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-278">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-278">tax number</span></span>
  
<span data-ttu-id="c704a-279">Tax</span><span class="sxs-lookup"><span data-stu-id="c704a-279">tax</span></span>
  
<span data-ttu-id="c704a-280">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-280">tax id</span></span>
  
<span data-ttu-id="c704a-281">RCP número</span><span class="sxs-lookup"><span data-stu-id="c704a-281">cpr number</span></span>
  
<span data-ttu-id="c704a-282">RCP #</span><span class="sxs-lookup"><span data-stu-id="c704a-282">cpr#</span></span>
  
<span data-ttu-id="c704a-283">Nummer de patinaje</span><span class="sxs-lookup"><span data-stu-id="c704a-283">skat nummer</span></span>
  
<span data-ttu-id="c704a-284">identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="c704a-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="c704a-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="c704a-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c704a-286">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-286">Format</span></span>

<span data-ttu-id="c704a-287">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-288">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-288">Pattern</span></span>

<span data-ttu-id="c704a-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-289">11 digits:</span></span>
  
-  <span data-ttu-id="c704a-290">Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI</span><span class="sxs-lookup"><span data-stu-id="c704a-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="c704a-291">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="c704a-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="c704a-292">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="c704a-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="c704a-293">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="c704a-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-294">Checksum</span></span>

<span data-ttu-id="c704a-295">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-296">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-296">Definition</span></span>

<span data-ttu-id="c704a-297">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-298">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-299">Se encuentra una `Keywords_estonia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-301">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-302">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="c704a-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-304">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-304">tax number</span></span>
  
<span data-ttu-id="c704a-305">Tax</span><span class="sxs-lookup"><span data-stu-id="c704a-305">tax</span></span>
  
<span data-ttu-id="c704a-306">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-306">tax id</span></span>
  
<span data-ttu-id="c704a-307">código personal</span><span class="sxs-lookup"><span data-stu-id="c704a-307">personal code</span></span>
  
<span data-ttu-id="c704a-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="c704a-308">maksunumber</span></span>
  
<span data-ttu-id="c704a-309">identificador maksu</span><span class="sxs-lookup"><span data-stu-id="c704a-309">maksu id</span></span>
  
<span data-ttu-id="c704a-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="c704a-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="c704a-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="c704a-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="c704a-312">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-312">Format</span></span>

<span data-ttu-id="c704a-313">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos</span><span class="sxs-lookup"><span data-stu-id="c704a-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-314">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-314">Pattern</span></span>

<span data-ttu-id="c704a-315">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:</span><span class="sxs-lookup"><span data-stu-id="c704a-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="c704a-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-316">Six digits</span></span>
    
- <span data-ttu-id="c704a-317">Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior</span><span class="sxs-lookup"><span data-stu-id="c704a-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="c704a-318">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-318">Three digits</span></span>
    
- <span data-ttu-id="c704a-319">Una letra o un número</span><span class="sxs-lookup"><span data-stu-id="c704a-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-320">Checksum</span></span>

<span data-ttu-id="c704a-321">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-322">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-322">Definition</span></span>

<span data-ttu-id="c704a-323">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-324">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-325">Se encuentra una `Keywords_finland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-327">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-328">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="c704a-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-330">identification number</span><span class="sxs-lookup"><span data-stu-id="c704a-330">identification number</span></span>
  
<span data-ttu-id="c704a-331">identificador personal</span><span class="sxs-lookup"><span data-stu-id="c704a-331">personal id</span></span>
  
<span data-ttu-id="c704a-332">número de identidad</span><span class="sxs-lookup"><span data-stu-id="c704a-332">identity number</span></span>
  
<span data-ttu-id="c704a-333">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="c704a-333">finnish national id number</span></span>
  
<span data-ttu-id="c704a-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-334">personalidnumber#</span></span>
  
<span data-ttu-id="c704a-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="c704a-335">national identification number</span></span>
  
<span data-ttu-id="c704a-336">número de identificador</span><span class="sxs-lookup"><span data-stu-id="c704a-336">id number</span></span>
  
<span data-ttu-id="c704a-337">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="c704a-337">national id no.</span></span>
  
<span data-ttu-id="c704a-338">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="c704a-338">national id number</span></span>
  
<span data-ttu-id="c704a-339">identificador no</span><span class="sxs-lookup"><span data-stu-id="c704a-339">id no</span></span>
  
<span data-ttu-id="c704a-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="c704a-340">tunnistenumero</span></span>
  
<span data-ttu-id="c704a-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="c704a-341">henkilötunnus</span></span>
  
<span data-ttu-id="c704a-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="c704a-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="c704a-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="c704a-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="c704a-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="c704a-344">identiteetti numero</span></span>
  
<span data-ttu-id="c704a-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="c704a-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="c704a-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="c704a-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="c704a-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="c704a-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="c704a-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="c704a-348">tunnusnumero</span></span>
  
<span data-ttu-id="c704a-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="c704a-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="c704a-350">Francia</span><span class="sxs-lookup"><span data-stu-id="c704a-350">France</span></span>

### <a name="format"></a><span data-ttu-id="c704a-351">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-351">Format</span></span>

<span data-ttu-id="c704a-352">13 dígitos para personas y nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="c704a-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-353">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-353">Pattern</span></span>

<span data-ttu-id="c704a-354">13 dígitos para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="c704a-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="c704a-355">Un dígito que debe ser 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="c704a-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="c704a-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-356">12 digits</span></span>
    
<span data-ttu-id="c704a-357">Nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="c704a-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-358">Checksum</span></span>

<span data-ttu-id="c704a-359">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-360">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-360">Definition</span></span>

<span data-ttu-id="c704a-361">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-362">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-363">Se encuentra una `Keywords_france_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-365">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="c704a-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-368">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-368">tax identification number</span></span>
  
<span data-ttu-id="c704a-369">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-369">tax number</span></span>
  
<span data-ttu-id="c704a-370">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-370">tax id</span></span>
  
<span data-ttu-id="c704a-371">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="c704a-372">Alemania</span><span class="sxs-lookup"><span data-stu-id="c704a-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="c704a-373">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-373">Format</span></span>

<span data-ttu-id="c704a-374">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-375">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-375">Pattern</span></span>

<span data-ttu-id="c704a-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-376">11 digits :</span></span>
  
-  <span data-ttu-id="c704a-377">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-377">Ten digits</span></span> 
    
- <span data-ttu-id="c704a-378">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="c704a-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-379">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-379">Checksum</span></span>

<span data-ttu-id="c704a-380">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-381">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-381">Definition</span></span>

<span data-ttu-id="c704a-382">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-383">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-384">Se encuentra una `Keywords_germany_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-386">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="c704a-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-389">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-389">tax number</span></span>
  
<span data-ttu-id="c704a-390">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-390">tax no.</span></span>
  
<span data-ttu-id="c704a-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-391">taxno#</span></span>
  
<span data-ttu-id="c704a-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-392">taxnumber#</span></span>
  
<span data-ttu-id="c704a-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-393">taxnumber</span></span>
  
<span data-ttu-id="c704a-394">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-394">tax id</span></span>
  
<span data-ttu-id="c704a-395">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-395">taxid#</span></span>
  
<span data-ttu-id="c704a-396">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-396">tax identification number</span></span>
  
<span data-ttu-id="c704a-397">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-397">tax identification no.</span></span>
  
<span data-ttu-id="c704a-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c704a-398">steuernummer</span></span>
  
<span data-ttu-id="c704a-399">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="c704a-399">steuer id</span></span>
  
<span data-ttu-id="c704a-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c704a-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="c704a-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="c704a-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c704a-402">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-402">Format</span></span>

<span data-ttu-id="c704a-403">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-404">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-404">Pattern</span></span>

<span data-ttu-id="c704a-405">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-406">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-406">Checksum</span></span>

<span data-ttu-id="c704a-407">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-408">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-408">Definition</span></span>

<span data-ttu-id="c704a-409">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-410">La expresión `Regex_greece_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-411">Se encuentra una `Keywords_greece_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c704a-412">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="c704a-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-414">afm</span><span class="sxs-lookup"><span data-stu-id="c704a-414">afm</span></span>
  
<span data-ttu-id="c704a-415">/</span><span class="sxs-lookup"><span data-stu-id="c704a-415">tin</span></span>
  
<span data-ttu-id="c704a-416">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-416">tax id no.</span></span>
  
<span data-ttu-id="c704a-417">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-417">tax id no</span></span>
  
<span data-ttu-id="c704a-418">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-418">tax identification number</span></span>
  
<span data-ttu-id="c704a-419">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-419">tax registry number</span></span>
  
<span data-ttu-id="c704a-420">n.º de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-420">tax registry no.</span></span>
  
<span data-ttu-id="c704a-421">afm #</span><span class="sxs-lookup"><span data-stu-id="c704a-421">afm#</span></span>
  
<span data-ttu-id="c704a-422">/ #</span><span class="sxs-lookup"><span data-stu-id="c704a-422">tin#</span></span>
  
<span data-ttu-id="c704a-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="c704a-423">taxidno#</span></span>
  
<span data-ttu-id="c704a-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="c704a-424">taxregistryno#</span></span>
  
<span data-ttu-id="c704a-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c704a-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="c704a-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="c704a-426">aφμ</span></span>
  
<span data-ttu-id="c704a-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="c704a-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="c704a-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="c704a-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="c704a-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c704a-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="c704a-430">Hungría</span><span class="sxs-lookup"><span data-stu-id="c704a-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c704a-431">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-431">Format</span></span>

<span data-ttu-id="c704a-432">Diez dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-433">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-433">Pattern</span></span>

<span data-ttu-id="c704a-434">Diez dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-434">Ten digits:</span></span>
  
-  <span data-ttu-id="c704a-435">Un dígito que debe ser "8"</span><span class="sxs-lookup"><span data-stu-id="c704a-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="c704a-436">Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.</span><span class="sxs-lookup"><span data-stu-id="c704a-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="c704a-437">Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día</span><span class="sxs-lookup"><span data-stu-id="c704a-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="c704a-438">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="c704a-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-439">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-439">Checksum</span></span>

<span data-ttu-id="c704a-440">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-441">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-441">Definition</span></span>

<span data-ttu-id="c704a-442">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-443">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-444">Se encuentra una `Keywords_hungary_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-445">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-446">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-447">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="c704a-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-449">número de identificación fiscal húngara</span><span class="sxs-lookup"><span data-stu-id="c704a-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="c704a-450">NIF Húngaro</span><span class="sxs-lookup"><span data-stu-id="c704a-450">hungarian tin</span></span>
  
<span data-ttu-id="c704a-451">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-451">tax id number</span></span>
  
<span data-ttu-id="c704a-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="c704a-452">vat number</span></span>
  
<span data-ttu-id="c704a-453">n.º de autoridad fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-453">tax authority no</span></span>
  
<span data-ttu-id="c704a-454">número de identidad fiscal de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-454">tax id tax identity number</span></span>
  
<span data-ttu-id="c704a-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-455">taxidnumber#</span></span>
  
<span data-ttu-id="c704a-456">/ #</span><span class="sxs-lookup"><span data-stu-id="c704a-456">tin#</span></span>
  
<span data-ttu-id="c704a-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="c704a-457">hungatiantin#</span></span>
  
<span data-ttu-id="c704a-458">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-458">tax identification no</span></span>
  
<span data-ttu-id="c704a-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="c704a-459">taxidno#</span></span>
  
<span data-ttu-id="c704a-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="c704a-460">adóazonosító szám</span></span>
  
<span data-ttu-id="c704a-461">adószám</span><span class="sxs-lookup"><span data-stu-id="c704a-461">adószám</span></span>
  
<span data-ttu-id="c704a-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="c704a-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="c704a-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="c704a-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c704a-464">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-464">Format</span></span>

<span data-ttu-id="c704a-465">Siete dígitos seguidos de una letra sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-466">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-466">Pattern</span></span>

<span data-ttu-id="c704a-467">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="c704a-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="c704a-468">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-468">Seven digits</span></span> 
    
- <span data-ttu-id="c704a-469">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-470">Checksum</span></span>

<span data-ttu-id="c704a-471">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-472">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-472">Definition</span></span>

<span data-ttu-id="c704a-473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-474">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-475">Se encuentra una `Keywords_ireland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-476">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-477">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="c704a-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-480">n.º de servicio público</span><span class="sxs-lookup"><span data-stu-id="c704a-480">public service no</span></span>
  
<span data-ttu-id="c704a-481">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="c704a-481">personal public service no</span></span>
  
<span data-ttu-id="c704a-482">n.º de PPS</span><span class="sxs-lookup"><span data-stu-id="c704a-482">pps no</span></span>
  
<span data-ttu-id="c704a-483">n.º de servicio personal</span><span class="sxs-lookup"><span data-stu-id="c704a-483">personal service no</span></span>
  
<span data-ttu-id="c704a-484">n.º de servicio de PPS</span><span class="sxs-lookup"><span data-stu-id="c704a-484">pps service no</span></span>
  
<span data-ttu-id="c704a-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="c704a-485">ppsno#</span></span>
  
<span data-ttu-id="c704a-486">n.º de PPS irlandés</span><span class="sxs-lookup"><span data-stu-id="c704a-486">irish pps no</span></span>
  
<span data-ttu-id="c704a-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="c704a-487">publicserviceno#</span></span>
  
<span data-ttu-id="c704a-488">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="c704a-488">personal public service number</span></span>
  
<span data-ttu-id="c704a-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="c704a-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="c704a-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="c704a-490">pps uimh</span></span>
  
<span data-ttu-id="c704a-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="c704a-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="c704a-492">Italia</span><span class="sxs-lookup"><span data-stu-id="c704a-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="c704a-493">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-493">Format</span></span>

<span data-ttu-id="c704a-494">16 letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c704a-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-495">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-495">Pattern</span></span>

<span data-ttu-id="c704a-496">16 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="c704a-497">Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="c704a-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="c704a-498">Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre</span><span class="sxs-lookup"><span data-stu-id="c704a-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="c704a-499">Dos dígitos que corresponden a los últimos dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="c704a-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="c704a-500">Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="c704a-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="c704a-501">Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos</span><span class="sxs-lookup"><span data-stu-id="c704a-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="c704a-502">Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).</span><span class="sxs-lookup"><span data-stu-id="c704a-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="c704a-503">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="c704a-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-504">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-504">Checksum</span></span>

<span data-ttu-id="c704a-505">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-506">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-506">Definition</span></span>

<span data-ttu-id="c704a-507">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-508">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-509">Se encuentra una `Keywords_italy_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-510">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-511">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-512">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="c704a-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-514">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-514">tax number</span></span>
  
<span data-ttu-id="c704a-515">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-515">tax no.</span></span>
  
<span data-ttu-id="c704a-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-516">taxno#</span></span>
  
<span data-ttu-id="c704a-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-517">taxnumber#</span></span>
  
<span data-ttu-id="c704a-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-518">taxnumber</span></span>
  
<span data-ttu-id="c704a-519">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-519">tax id</span></span>
  
<span data-ttu-id="c704a-520">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-520">taxid#</span></span>
  
<span data-ttu-id="c704a-521">Código fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-521">fiscal code</span></span>
  
<span data-ttu-id="c704a-522">Codice fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="c704a-523">Letonia</span><span class="sxs-lookup"><span data-stu-id="c704a-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c704a-524">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-524">Format</span></span>

<span data-ttu-id="c704a-525">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-526">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-526">Pattern</span></span>

<span data-ttu-id="c704a-527">11 dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c704a-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="c704a-528">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="c704a-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="c704a-529">Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.</span><span class="sxs-lookup"><span data-stu-id="c704a-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="c704a-530">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-531">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-531">Checksum</span></span>

<span data-ttu-id="c704a-532">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-533">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-533">Definition</span></span>

<span data-ttu-id="c704a-534">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-535">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-536">Se encuentra una `Keywords_latvia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-537">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-538">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-539">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="c704a-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-541">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-541">tax number</span></span>
  
<span data-ttu-id="c704a-542">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-542">tax no.</span></span>
  
<span data-ttu-id="c704a-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-543">taxno#</span></span>
  
<span data-ttu-id="c704a-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-544">taxnumber#</span></span>
  
<span data-ttu-id="c704a-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-545">taxnumber</span></span>
  
<span data-ttu-id="c704a-546">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-546">tax id</span></span>
  
<span data-ttu-id="c704a-547">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-547">taxid#</span></span>
  
<span data-ttu-id="c704a-548">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-548">tax identification number</span></span>
  
<span data-ttu-id="c704a-549">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-549">tax identification no.</span></span>
  
<span data-ttu-id="c704a-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="c704a-550">nodokļa numurs</span></span>
  
<span data-ttu-id="c704a-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="c704a-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="c704a-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="c704a-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="c704a-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="c704a-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c704a-554">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-554">Format</span></span>

<span data-ttu-id="c704a-555">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-556">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-556">Pattern</span></span>

<span data-ttu-id="c704a-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-558">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-558">Checksum</span></span>

<span data-ttu-id="c704a-559">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-560">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-560">Definition</span></span>

<span data-ttu-id="c704a-561">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-562">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-563">Se encuentra una `Keywords_lithuania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-564">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-565">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-566">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="c704a-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-568">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-568">tax number</span></span>
  
<span data-ttu-id="c704a-569">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-569">tax no.</span></span>
  
<span data-ttu-id="c704a-570">Nº de impuestos #</span><span class="sxs-lookup"><span data-stu-id="c704a-570">tax no#</span></span>
  
<span data-ttu-id="c704a-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-571">taxnumber#</span></span>
  
<span data-ttu-id="c704a-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-572">taxnumber</span></span>
  
<span data-ttu-id="c704a-573">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-573">tax id</span></span>
  
<span data-ttu-id="c704a-574">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-574">taxid#</span></span>
  
<span data-ttu-id="c704a-575">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-575">tax identification number</span></span>
  
<span data-ttu-id="c704a-576">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-576">tax identification no.</span></span>
  
<span data-ttu-id="c704a-577">identificador mokesčių</span><span class="sxs-lookup"><span data-stu-id="c704a-577">mokesčių id</span></span>
  
<span data-ttu-id="c704a-578">numeración mokesčių</span><span class="sxs-lookup"><span data-stu-id="c704a-578">mokesčių numeris</span></span>
  
<span data-ttu-id="c704a-579">mokesčių identifikavimas número</span><span class="sxs-lookup"><span data-stu-id="c704a-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="c704a-580">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="c704a-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c704a-581">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-581">Format</span></span>

<span data-ttu-id="c704a-582">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-583">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-583">Pattern</span></span>

<span data-ttu-id="c704a-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="c704a-584">13 digits:</span></span>
  
-  <span data-ttu-id="c704a-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-585">11 digits</span></span> 
    
- <span data-ttu-id="c704a-586">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="c704a-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-587">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-587">Checksum</span></span>

<span data-ttu-id="c704a-588">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-589">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-589">Definition</span></span>

<span data-ttu-id="c704a-590">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-591">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-592">Se encuentra una `Keywords_luxemburg_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-593">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-594">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-595">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="c704a-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-597">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-597">tax number</span></span>
  
<span data-ttu-id="c704a-598">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-598">tax no.</span></span>
  
<span data-ttu-id="c704a-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-599">taxno#</span></span>
  
<span data-ttu-id="c704a-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-600">taxnumber#</span></span>
  
<span data-ttu-id="c704a-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-601">taxnumber</span></span>
  
<span data-ttu-id="c704a-602">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-602">tax id</span></span>
  
<span data-ttu-id="c704a-603">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-603">taxid#</span></span>
  
<span data-ttu-id="c704a-604">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-604">tax identification number</span></span>
  
<span data-ttu-id="c704a-605">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-605">tax identification no.</span></span>
  
<span data-ttu-id="c704a-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c704a-606">steuernummer</span></span>
  
<span data-ttu-id="c704a-607">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="c704a-607">steuer id</span></span>
  
<span data-ttu-id="c704a-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c704a-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="c704a-609">Malta</span><span class="sxs-lookup"><span data-stu-id="c704a-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c704a-610">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-610">Format</span></span>

<span data-ttu-id="c704a-611">Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c704a-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="c704a-612">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-613">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-613">Pattern</span></span>

<span data-ttu-id="c704a-614">Nacionales de Malta: 7 dígitos y una letra</span><span class="sxs-lookup"><span data-stu-id="c704a-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="c704a-615">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-615">Seven digits</span></span> 
    
- <span data-ttu-id="c704a-616">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="c704a-617">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="c704a-618">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c704a-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-619">Checksum</span></span>

<span data-ttu-id="c704a-620">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-621">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-621">Definition</span></span>

<span data-ttu-id="c704a-622">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-623">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-624">Se encuentra una `Keywords_malta_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-626">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-627">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="c704a-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-629">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-629">tax number</span></span>
  
<span data-ttu-id="c704a-630">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-630">tax no.</span></span>
  
<span data-ttu-id="c704a-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-631">taxno#</span></span>
  
<span data-ttu-id="c704a-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-632">taxnumber#</span></span>
  
<span data-ttu-id="c704a-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-633">taxnumber</span></span>
  
<span data-ttu-id="c704a-634">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-634">tax id</span></span>
  
<span data-ttu-id="c704a-635">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-635">taxid#</span></span>
  
<span data-ttu-id="c704a-636">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-636">tax identification number</span></span>
  
<span data-ttu-id="c704a-637">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-637">tax identification no.</span></span>
  
<span data-ttu-id="c704a-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="c704a-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="c704a-639">identificador TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="c704a-639">id tat-taxxa</span></span>
  
<span data-ttu-id="c704a-640">numru ta ' identifikazzjoni TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="c704a-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="c704a-641">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="c704a-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c704a-642">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-642">Format</span></span>

<span data-ttu-id="c704a-643">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-644">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-644">Pattern</span></span>

<span data-ttu-id="c704a-645">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c704a-646">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-646">Checksum</span></span>

<span data-ttu-id="c704a-647">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-648">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-648">Definition</span></span>

<span data-ttu-id="c704a-649">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-650">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-651">Se encuentra una `Keywords_netherlands_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-652">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-653">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-654">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="c704a-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-656">número de identificación fiscal de países bajos</span><span class="sxs-lookup"><span data-stu-id="c704a-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="c704a-657">identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="c704a-657">netherlands tax identification</span></span>
  
<span data-ttu-id="c704a-658">número de identificación fiscal de Netherland</span><span class="sxs-lookup"><span data-stu-id="c704a-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="c704a-659">identificación de impuestos de Netherland</span><span class="sxs-lookup"><span data-stu-id="c704a-659">netherland's tax identification</span></span>
  
<span data-ttu-id="c704a-660">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-660">tax identification number</span></span>
  
<span data-ttu-id="c704a-661">identificador fiscal holandés</span><span class="sxs-lookup"><span data-stu-id="c704a-661">dutch tax id</span></span>
  
<span data-ttu-id="c704a-662">número de identificación fiscal holandes</span><span class="sxs-lookup"><span data-stu-id="c704a-662">dutch tax identification number</span></span>
  
<span data-ttu-id="c704a-663">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-663">tax id</span></span>
  
<span data-ttu-id="c704a-664">identificador de impuesto #</span><span class="sxs-lookup"><span data-stu-id="c704a-664">tax id#</span></span>
  
<span data-ttu-id="c704a-665">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-665">tax number</span></span>
  
<span data-ttu-id="c704a-666">Nº de impuestos #</span><span class="sxs-lookup"><span data-stu-id="c704a-666">tax no#</span></span>
  
<span data-ttu-id="c704a-667">Tax #</span><span class="sxs-lookup"><span data-stu-id="c704a-667">tax#</span></span>
  
<span data-ttu-id="c704a-668">/</span><span class="sxs-lookup"><span data-stu-id="c704a-668">tin</span></span>
  
<span data-ttu-id="c704a-669">/ #</span><span class="sxs-lookup"><span data-stu-id="c704a-669">tin#</span></span>
  
<span data-ttu-id="c704a-670">NIF-Países Bajos</span><span class="sxs-lookup"><span data-stu-id="c704a-670">netherlands tin</span></span>
  
<span data-ttu-id="c704a-671">estaño de Netherland</span><span class="sxs-lookup"><span data-stu-id="c704a-671">netherland's tin</span></span>
  
<span data-ttu-id="c704a-672">último países de la identificatienummer</span><span class="sxs-lookup"><span data-stu-id="c704a-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="c704a-673">identificatienummerto de furgoneta</span><span class="sxs-lookup"><span data-stu-id="c704a-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="c704a-674">identificatienummer en último lugar</span><span class="sxs-lookup"><span data-stu-id="c704a-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="c704a-675">último países de la identificatie</span><span class="sxs-lookup"><span data-stu-id="c704a-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="c704a-676">último identificador de Nummer de países bajos</span><span class="sxs-lookup"><span data-stu-id="c704a-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="c704a-677">Países Bajos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="c704a-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="c704a-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="c704a-678">btw nummer</span></span>
  
<span data-ttu-id="c704a-679">Nederlandse de la última identificatie</span><span class="sxs-lookup"><span data-stu-id="c704a-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="c704a-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="c704a-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="c704a-681">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-681">Format</span></span>

<span data-ttu-id="c704a-682">Once dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-683">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-683">Pattern</span></span>

<span data-ttu-id="c704a-684">Once dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-685">Checksum</span></span>

<span data-ttu-id="c704a-686">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-687">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-687">Definition</span></span>

<span data-ttu-id="c704a-688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-689">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-690">Se encuentra una `Keywords_poland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-691">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-692">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-693">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="c704a-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-695">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-695">tax number</span></span>
  
<span data-ttu-id="c704a-696">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-696">tax no.</span></span>
  
<span data-ttu-id="c704a-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-697">taxno#</span></span>
  
<span data-ttu-id="c704a-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-698">taxnumber#</span></span>
  
<span data-ttu-id="c704a-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-699">taxnumber</span></span>
  
<span data-ttu-id="c704a-700">nip</span><span class="sxs-lookup"><span data-stu-id="c704a-700">nip</span></span>
  
<span data-ttu-id="c704a-701">nip #</span><span class="sxs-lookup"><span data-stu-id="c704a-701">nip#</span></span>
  
<span data-ttu-id="c704a-702">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-702">tax id</span></span>
  
<span data-ttu-id="c704a-703">identificador de impuesto #</span><span class="sxs-lookup"><span data-stu-id="c704a-703">tax id#</span></span>
  
<span data-ttu-id="c704a-704">identificador NIP</span><span class="sxs-lookup"><span data-stu-id="c704a-704">nip id</span></span>
  
<span data-ttu-id="c704a-705">identificador NIP #</span><span class="sxs-lookup"><span data-stu-id="c704a-705">nip id#</span></span>
  
<span data-ttu-id="c704a-706">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-706">tax identification number</span></span>
  
<span data-ttu-id="c704a-707">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-707">tax identification no.</span></span>
  
<span data-ttu-id="c704a-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="c704a-708">vat number</span></span>
  
<span data-ttu-id="c704a-709">n.º de IVA</span><span class="sxs-lookup"><span data-stu-id="c704a-709">vat no.</span></span>
  
<span data-ttu-id="c704a-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="c704a-710">vatno#</span></span>
  
<span data-ttu-id="c704a-711">NIF</span><span class="sxs-lookup"><span data-stu-id="c704a-711">vat id</span></span>
  
<span data-ttu-id="c704a-712">NIF #</span><span class="sxs-lookup"><span data-stu-id="c704a-712">vat id#</span></span>
  
<span data-ttu-id="c704a-713">numerar identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="c704a-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="c704a-714">Polski número de identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="c704a-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="c704a-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="c704a-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="c704a-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="c704a-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c704a-717">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-717">Format</span></span>

<span data-ttu-id="c704a-718">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-719">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-719">Pattern</span></span>

<span data-ttu-id="c704a-720">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-721">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-721">Checksum</span></span>

<span data-ttu-id="c704a-722">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-723">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-723">Definition</span></span>

<span data-ttu-id="c704a-724">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-725">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-726">Se encuentra una `Keywords_portugal_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-728">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-729">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="c704a-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-731">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-731">tax number</span></span>
  
<span data-ttu-id="c704a-732">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-732">tax no.</span></span>
  
<span data-ttu-id="c704a-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-733">taxno#</span></span>
  
<span data-ttu-id="c704a-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c704a-734">taxnumber#</span></span>
  
<span data-ttu-id="c704a-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c704a-735">taxnumber</span></span>
  
<span data-ttu-id="c704a-736">NIF</span><span class="sxs-lookup"><span data-stu-id="c704a-736">nif</span></span>
  
<span data-ttu-id="c704a-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="c704a-737">nif#</span></span>
  
<span data-ttu-id="c704a-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="c704a-738">numero fiscal</span></span>
  
<span data-ttu-id="c704a-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="c704a-740">Rumania</span><span class="sxs-lookup"><span data-stu-id="c704a-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c704a-741">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-741">Format</span></span>

<span data-ttu-id="c704a-742">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-743">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-743">Pattern</span></span>

<span data-ttu-id="c704a-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-745">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-745">Checksum</span></span>

<span data-ttu-id="c704a-746">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-747">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-747">Definition</span></span>

<span data-ttu-id="c704a-748">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-749">La expresión `Regex_romania_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-750">Se encuentra una `Keywords_romania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c704a-751">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="c704a-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-753">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-753">tax id</span></span>
  
<span data-ttu-id="c704a-754">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-754">tax id number</span></span>
  
<span data-ttu-id="c704a-755">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-755">tax file no</span></span>
  
<span data-ttu-id="c704a-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="c704a-756">tax file number</span></span>
  
<span data-ttu-id="c704a-757">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-757">tax no</span></span>
  
<span data-ttu-id="c704a-758">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-758">tax number</span></span>
  
<span data-ttu-id="c704a-759">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-759">taxid#</span></span>
  
<span data-ttu-id="c704a-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-760">taxno#</span></span>
  
<span data-ttu-id="c704a-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="c704a-761">id-ul taxei</span></span>
  
<span data-ttu-id="c704a-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="c704a-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="c704a-763">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="c704a-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c704a-764">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-764">Format</span></span>

<span data-ttu-id="c704a-765">10 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-766">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-766">Pattern</span></span>

<span data-ttu-id="c704a-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-768">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-768">Checksum</span></span>

<span data-ttu-id="c704a-769">No aplicable</span><span class="sxs-lookup"><span data-stu-id="c704a-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-770">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-770">Definition</span></span>

<span data-ttu-id="c704a-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-772">La expresión `Regex_slovakia_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-773">Se encuentra una `Keywords_slovakia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c704a-774">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="c704a-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-776">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-776">tax id</span></span>
  
<span data-ttu-id="c704a-777">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-777">tax id number</span></span>
  
<span data-ttu-id="c704a-778">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="c704a-778">tin id</span></span>
  
<span data-ttu-id="c704a-779">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="c704a-779">tin no</span></span>
  
<span data-ttu-id="c704a-780">ID de estaño de eslovaco</span><span class="sxs-lookup"><span data-stu-id="c704a-780">slovakian tin id</span></span>
  
<span data-ttu-id="c704a-781">/</span><span class="sxs-lookup"><span data-stu-id="c704a-781">tin</span></span>
  
<span data-ttu-id="c704a-782">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-782">tax file no</span></span>
  
<span data-ttu-id="c704a-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="c704a-783">tax file number</span></span>
  
<span data-ttu-id="c704a-784">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-784">tax no</span></span>
  
<span data-ttu-id="c704a-785">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-785">tax number</span></span>
  
<span data-ttu-id="c704a-786">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-786">taxid#</span></span>
  
<span data-ttu-id="c704a-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-787">taxno#</span></span>
  
<span data-ttu-id="c704a-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="c704a-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="c704a-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="c704a-789">daňové číslo</span></span>
  
<span data-ttu-id="c704a-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="c704a-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="c704a-791">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="c704a-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c704a-792">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-792">Format</span></span>

<span data-ttu-id="c704a-793">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-794">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-794">Pattern</span></span>

<span data-ttu-id="c704a-795">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-796">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-796">Checksum</span></span>

<span data-ttu-id="c704a-797">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-798">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-798">Definition</span></span>

<span data-ttu-id="c704a-799">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-800">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-801">Se encuentra una `Keywords_slovenia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-802">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-803">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-804">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="c704a-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-806">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-806">tax id</span></span>
  
<span data-ttu-id="c704a-807">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-807">tax id number</span></span>
  
<span data-ttu-id="c704a-808">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="c704a-808">tin id</span></span>
  
<span data-ttu-id="c704a-809">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="c704a-809">tin no</span></span>
  
<span data-ttu-id="c704a-810">ID de estaño de esloveno</span><span class="sxs-lookup"><span data-stu-id="c704a-810">slovenian tin id</span></span>
  
<span data-ttu-id="c704a-811">/</span><span class="sxs-lookup"><span data-stu-id="c704a-811">tin</span></span>
  
<span data-ttu-id="c704a-812">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-812">tax file no</span></span>
  
<span data-ttu-id="c704a-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="c704a-813">tax file number</span></span>
  
<span data-ttu-id="c704a-814">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-814">tax no</span></span>
  
<span data-ttu-id="c704a-815">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-815">tax number</span></span>
  
<span data-ttu-id="c704a-816">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-816">taxid#</span></span>
  
<span data-ttu-id="c704a-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-817">taxno#</span></span>
  
<span data-ttu-id="c704a-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="c704a-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="c704a-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="c704a-819">davčna številka</span></span>
  
<span data-ttu-id="c704a-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="c704a-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="c704a-821">España</span><span class="sxs-lookup"><span data-stu-id="c704a-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c704a-822">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-822">Format</span></span>

<span data-ttu-id="c704a-823">Siete u ocho dígitos y una o dos letras en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c704a-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-824">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-824">Pattern</span></span>

<span data-ttu-id="c704a-825">Personas físicas españolas con una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="c704a-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="c704a-826">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-826">Eight digits</span></span> 
    
- <span data-ttu-id="c704a-827">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c704a-828">Spaniards no residente sin una tarjeta de identidad nacional de España</span><span class="sxs-lookup"><span data-stu-id="c704a-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="c704a-829">Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="c704a-830">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-830">Seven digits</span></span>
    
- <span data-ttu-id="c704a-831">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c704a-832">Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="c704a-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="c704a-833">Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="c704a-834">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-834">Seven digits</span></span> 
    
- <span data-ttu-id="c704a-835">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="c704a-836">Foreigners con un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="c704a-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="c704a-837">Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="c704a-838">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-838">Seven digits</span></span>
    
- <span data-ttu-id="c704a-839">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c704a-840">Foreigners sin un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="c704a-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="c704a-841">Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="c704a-842">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="c704a-842">Seven digits</span></span>
    
- <span data-ttu-id="c704a-843">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c704a-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c704a-844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-844">Checksum</span></span>

<span data-ttu-id="c704a-845">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-846">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-846">Definition</span></span>

<span data-ttu-id="c704a-847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-848">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-849">Se encuentra una `Keywords_spain_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-850">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-851">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-852">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="c704a-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-854">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-854">tax id</span></span>
  
<span data-ttu-id="c704a-855">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-855">tax id number</span></span>
  
<span data-ttu-id="c704a-856">identificador CIF</span><span class="sxs-lookup"><span data-stu-id="c704a-856">cif id</span></span>
  
<span data-ttu-id="c704a-857">n.º CIF</span><span class="sxs-lookup"><span data-stu-id="c704a-857">cif no</span></span>
  
<span data-ttu-id="c704a-858">identificador CIF en Español</span><span class="sxs-lookup"><span data-stu-id="c704a-858">spanish cif id</span></span>
  
<span data-ttu-id="c704a-859">precio</span><span class="sxs-lookup"><span data-stu-id="c704a-859">cif</span></span>
  
<span data-ttu-id="c704a-860">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-860">tax file no</span></span>
  
<span data-ttu-id="c704a-861">Número CIF en Español</span><span class="sxs-lookup"><span data-stu-id="c704a-861">spanish cif number</span></span>
  
<span data-ttu-id="c704a-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="c704a-862">tax file number</span></span>
  
<span data-ttu-id="c704a-863">Número CIF de Español</span><span class="sxs-lookup"><span data-stu-id="c704a-863">spanish cif no</span></span>
  
<span data-ttu-id="c704a-864">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-864">tax no</span></span>
  
<span data-ttu-id="c704a-865">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="c704a-865">tax number</span></span>
  
<span data-ttu-id="c704a-866">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-866">taxid#</span></span>
  
<span data-ttu-id="c704a-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="c704a-867">taxno#</span></span>
  
<span data-ttu-id="c704a-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="c704a-868">cifid#</span></span>
  
<span data-ttu-id="c704a-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="c704a-869">spanishcifid#</span></span>
  
<span data-ttu-id="c704a-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="c704a-870">spanishcifno#</span></span>
  
<span data-ttu-id="c704a-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="c704a-871">número de contribuyente</span></span>
  
<span data-ttu-id="c704a-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="c704a-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="c704a-873">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="c704a-874">Número CIF</span><span class="sxs-lookup"><span data-stu-id="c704a-874">cif número</span></span>
  
<span data-ttu-id="c704a-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="c704a-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="c704a-876">Suecia</span><span class="sxs-lookup"><span data-stu-id="c704a-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="c704a-877">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-877">Format</span></span>

<span data-ttu-id="c704a-878">Diez dígitos y un símbolo en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c704a-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-879">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-879">Pattern</span></span>

<span data-ttu-id="c704a-880">Diez dígitos y un símbolo:</span><span class="sxs-lookup"><span data-stu-id="c704a-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="c704a-881">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="c704a-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="c704a-882">Un signo más, un signo menos o una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="c704a-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="c704a-883">Tres dígitos que hacen que el número de identificación sea único donde:</span><span class="sxs-lookup"><span data-stu-id="c704a-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="c704a-884">Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero</span><span class="sxs-lookup"><span data-stu-id="c704a-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="c704a-885">El dígito en la novena posición indica el género, ya sea impar o incluso para hembras</span><span class="sxs-lookup"><span data-stu-id="c704a-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="c704a-886">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="c704a-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c704a-887">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-887">Checksum</span></span>

<span data-ttu-id="c704a-888">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-889">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-889">Definition</span></span>

<span data-ttu-id="c704a-890">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-891">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-892">Se encuentra una `Keywords_sweden_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c704a-893">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-894">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c704a-895">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="c704a-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-897">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-897">tax id</span></span>
  
<span data-ttu-id="c704a-898">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-898">tax id no.</span></span>
  
<span data-ttu-id="c704a-899">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-899">tax id number</span></span>
  
<span data-ttu-id="c704a-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="c704a-900">tax identification</span></span>
  
<span data-ttu-id="c704a-901">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="c704a-901">tax identification#</span></span>
  
<span data-ttu-id="c704a-902">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-902">tax no.</span></span>
  
<span data-ttu-id="c704a-903">Tax #</span><span class="sxs-lookup"><span data-stu-id="c704a-903">tax#</span></span>
  
<span data-ttu-id="c704a-904">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-904">taxid#</span></span>
  
<span data-ttu-id="c704a-905">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-905">tax file</span></span>
  
<span data-ttu-id="c704a-906">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-906">tax file no.</span></span>
  
<span data-ttu-id="c704a-907">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="c704a-907">personal id number</span></span>
  
<span data-ttu-id="c704a-908">Nummer de identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="c704a-908">skatt id nummer</span></span>
  
<span data-ttu-id="c704a-909">Identifikation de patinaje</span><span class="sxs-lookup"><span data-stu-id="c704a-909">skatt identifikation</span></span>
  
<span data-ttu-id="c704a-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="c704a-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="c704a-911">LIBRA</span><span class="sxs-lookup"><span data-stu-id="c704a-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="c704a-912">Formato</span><span class="sxs-lookup"><span data-stu-id="c704a-912">Format</span></span>

<span data-ttu-id="c704a-913">Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c704a-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="c704a-914">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="c704a-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="c704a-915">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c704a-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c704a-916">Pattern</span><span class="sxs-lookup"><span data-stu-id="c704a-916">Pattern</span></span>

<span data-ttu-id="c704a-917">Referencia de contribuyente única (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="c704a-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="c704a-918">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="c704a-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="c704a-919">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c704a-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c704a-920">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c704a-920">Checksum</span></span>

<span data-ttu-id="c704a-921">Sí</span><span class="sxs-lookup"><span data-stu-id="c704a-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c704a-922">Definición</span><span class="sxs-lookup"><span data-stu-id="c704a-922">Definition</span></span>

<span data-ttu-id="c704a-923">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c704a-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c704a-924">La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c704a-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c704a-925">Se encuentra una `Keywords_uk_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c704a-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c704a-926">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c704a-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="c704a-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c704a-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="c704a-928">tax id</span><span class="sxs-lookup"><span data-stu-id="c704a-928">tax id</span></span>
  
<span data-ttu-id="c704a-929">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-929">tax id no.</span></span>
  
<span data-ttu-id="c704a-930">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="c704a-930">tax id number</span></span>
  
<span data-ttu-id="c704a-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="c704a-931">tax identification</span></span>
  
<span data-ttu-id="c704a-932">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="c704a-932">tax identification#</span></span>
  
<span data-ttu-id="c704a-933">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-933">tax no.</span></span>
  
<span data-ttu-id="c704a-934">Tax #</span><span class="sxs-lookup"><span data-stu-id="c704a-934">tax#</span></span>
  
<span data-ttu-id="c704a-935">taxi #</span><span class="sxs-lookup"><span data-stu-id="c704a-935">taxid#</span></span>
  
<span data-ttu-id="c704a-936">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="c704a-936">tax file</span></span>
  
<span data-ttu-id="c704a-937">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="c704a-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c704a-938">Vea también</span><span class="sxs-lookup"><span data-stu-id="c704a-938">See also</span></span>

[<span data-ttu-id="c704a-939">Información que buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c704a-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

