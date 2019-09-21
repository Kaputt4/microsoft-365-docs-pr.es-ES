---
title: Número de identificación fiscal de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación de impuestos de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092464"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="f7f9c-104">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="f7f9c-104">EU Tax Identification Number</span></span>

<span data-ttu-id="f7f9c-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de identificación fiscal (CIF) de la UE.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="f7f9c-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f7f9c-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f7f9c-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-108">Format</span></span>

<span data-ttu-id="f7f9c-109">Nueve dígitos con guión opcional y barra diagonal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-110">Pattern</span></span>

<span data-ttu-id="f7f9c-111">Nueve dígitos con guión opcional y barra diagonal:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="f7f9c-112">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-112">Two digits</span></span> 
    
- <span data-ttu-id="f7f9c-113">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="f7f9c-114">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-114">Three digits</span></span>
    
- <span data-ttu-id="f7f9c-115">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="f7f9c-116">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-117">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-117">Checksum</span></span>

<span data-ttu-id="f7f9c-118">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-119">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-119">Definition</span></span>

<span data-ttu-id="f7f9c-120">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-121">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-122">Se encuentra una `Keywords_austria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-123">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-124">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-125">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="f7f9c-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-127">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-127">tax number</span></span>
  
<span data-ttu-id="f7f9c-128">número</span><span class="sxs-lookup"><span data-stu-id="f7f9c-128">number</span></span>
  
<span data-ttu-id="f7f9c-129">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-129">tax registration number</span></span>
  
<span data-ttu-id="f7f9c-130">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-130">tax id</span></span>
  
<span data-ttu-id="f7f9c-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-131">st.nr.</span></span>
  
<span data-ttu-id="f7f9c-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="f7f9c-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="f7f9c-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-134">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-134">Format</span></span>

<span data-ttu-id="f7f9c-135">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-136">Pattern</span></span>

<span data-ttu-id="f7f9c-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-137">11 digits:</span></span>
  
- <span data-ttu-id="f7f9c-138">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-138">Two digits</span></span>
    
- <span data-ttu-id="f7f9c-139">Un "0" o "1"</span><span class="sxs-lookup"><span data-stu-id="f7f9c-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="f7f9c-140">Un dígito</span><span class="sxs-lookup"><span data-stu-id="f7f9c-140">One digit</span></span>
    
- <span data-ttu-id="f7f9c-141">Un "0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="f7f9c-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="f7f9c-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-143">Checksum</span></span>

<span data-ttu-id="f7f9c-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-145">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-145">Definition</span></span>

<span data-ttu-id="f7f9c-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-147">La expresión `Regex_belgium_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-148">Se encuentra una `Keywords_belgium_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f7f9c-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="f7f9c-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-151">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-151">tax number</span></span>
  
<span data-ttu-id="f7f9c-152">número de registro nacional</span><span class="sxs-lookup"><span data-stu-id="f7f9c-152">national registration number</span></span>
  
<span data-ttu-id="f7f9c-153">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-153">tax registration number</span></span>
  
<span data-ttu-id="f7f9c-154">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-154">tax id</span></span>
  
<span data-ttu-id="f7f9c-155">NIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-155">nif</span></span>
  
<span data-ttu-id="f7f9c-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-156">nif#</span></span>
  
<span data-ttu-id="f7f9c-157">numéro de registros nacionales</span><span class="sxs-lookup"><span data-stu-id="f7f9c-157">numéro de registre national</span></span>
  
<span data-ttu-id="f7f9c-158">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="f7f9c-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f7f9c-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-160">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-160">Format</span></span>

<span data-ttu-id="f7f9c-161">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-162">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-162">Pattern</span></span>

<span data-ttu-id="f7f9c-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-164">Checksum</span></span>

<span data-ttu-id="f7f9c-165">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-166">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-166">Definition</span></span>

<span data-ttu-id="f7f9c-167">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-168">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-169">Se encuentra una `Keywords_bulgaria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-170">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-171">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-172">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="f7f9c-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-174">bucn</span><span class="sxs-lookup"><span data-stu-id="f7f9c-174">bucn</span></span>
  
<span data-ttu-id="f7f9c-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="f7f9c-175">uniform civil number</span></span>
  
<span data-ttu-id="f7f9c-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-176">bucn#</span></span>
  
<span data-ttu-id="f7f9c-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="f7f9c-178">identificador civil uniforme</span><span class="sxs-lookup"><span data-stu-id="f7f9c-178">uniform civil id</span></span>
  
<span data-ttu-id="f7f9c-179">Uniform civil no</span><span class="sxs-lookup"><span data-stu-id="f7f9c-179">uniform civil no</span></span>
  
<span data-ttu-id="f7f9c-180">egn</span><span class="sxs-lookup"><span data-stu-id="f7f9c-180">egn</span></span>
  
<span data-ttu-id="f7f9c-181">número civil uniforme de búlgaro</span><span class="sxs-lookup"><span data-stu-id="f7f9c-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="f7f9c-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-182">uniformcivilno#</span></span>
  
<span data-ttu-id="f7f9c-183">egn #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-183">egn#</span></span>
  
<span data-ttu-id="f7f9c-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="f7f9c-184">униформ граждански номер</span></span>
  
<span data-ttu-id="f7f9c-185">identificador униформ</span><span class="sxs-lookup"><span data-stu-id="f7f9c-185">униформ id</span></span>
  
<span data-ttu-id="f7f9c-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="f7f9c-186">униформ граждански id</span></span>
  
<span data-ttu-id="f7f9c-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="f7f9c-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="f7f9c-188">Croacia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-189">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-189">Format</span></span>

<span data-ttu-id="f7f9c-190">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-191">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-191">Pattern</span></span>

<span data-ttu-id="f7f9c-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-192">11 digits:</span></span>
  
- <span data-ttu-id="f7f9c-193">Diez dígitos, elegidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="f7f9c-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="f7f9c-194">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-195">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-195">Checksum</span></span>

<span data-ttu-id="f7f9c-196">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-197">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-197">Definition</span></span>

<span data-ttu-id="f7f9c-198">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-199">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-200">Se encuentra una `Keywords_croatia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-202">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-203">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="f7f9c-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-205">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-205">tax number</span></span>
  
<span data-ttu-id="f7f9c-206">Tax</span><span class="sxs-lookup"><span data-stu-id="f7f9c-206">tax</span></span>
  
<span data-ttu-id="f7f9c-207">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-207">tax id</span></span>
  
<span data-ttu-id="f7f9c-208">oid</span><span class="sxs-lookup"><span data-stu-id="f7f9c-208">oid</span></span>
  
<span data-ttu-id="f7f9c-209">OID #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-209">oid#</span></span>
  
<span data-ttu-id="f7f9c-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="f7f9c-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="f7f9c-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="f7f9c-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-212">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-212">Format</span></span>

<span data-ttu-id="f7f9c-213">Ocho dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f7f9c-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-214">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-214">Pattern</span></span>

<span data-ttu-id="f7f9c-215">Ocho dígitos y una letra:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="f7f9c-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="f7f9c-216">A "0"</span></span> 
    
- <span data-ttu-id="f7f9c-217">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-217">Seven digits</span></span>
    
- <span data-ttu-id="f7f9c-218">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-219">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-219">Checksum</span></span>

<span data-ttu-id="f7f9c-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-221">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-221">Definition</span></span>

<span data-ttu-id="f7f9c-222">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-223">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-224">Se encuentra una `Keywords_cyprus_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-226">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="f7f9c-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-229">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-229">tax number</span></span>
  
<span data-ttu-id="f7f9c-230">Tax</span><span class="sxs-lookup"><span data-stu-id="f7f9c-230">tax</span></span>
  
<span data-ttu-id="f7f9c-231">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-231">tax id</span></span>
  
<span data-ttu-id="f7f9c-232">código de identificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-232">tax identification code</span></span>
  
<span data-ttu-id="f7f9c-233">verticales</span><span class="sxs-lookup"><span data-stu-id="f7f9c-233">tic</span></span>
  
<span data-ttu-id="f7f9c-234">verticales #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-234">tic#</span></span>
  
<span data-ttu-id="f7f9c-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f7f9c-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="f7f9c-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="f7f9c-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="f7f9c-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f7f9c-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="f7f9c-238">Chequia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-239">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-239">Format</span></span>

<span data-ttu-id="f7f9c-240">Nueve o diez dígitos con una barra diagonal inversa opcional</span><span class="sxs-lookup"><span data-stu-id="f7f9c-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-241">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-241">Pattern</span></span>

<span data-ttu-id="f7f9c-242">Nueve o diez dígitos con una barra diagonal inversa opcional:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="f7f9c-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-243">Six digits</span></span> 
    
- <span data-ttu-id="f7f9c-244">Una barra diagonal inversa (opcional)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="f7f9c-245">Tres o cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-246">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-246">Checksum</span></span>

<span data-ttu-id="f7f9c-247">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-248">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-248">Definition</span></span>

<span data-ttu-id="f7f9c-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-250">La expresión `Regex_czech_republic_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-251">Se encuentra una `Keywords_czech_republic_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f7f9c-252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="f7f9c-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-254">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-254">tax number</span></span>
  
<span data-ttu-id="f7f9c-255">Tax</span><span class="sxs-lookup"><span data-stu-id="f7f9c-255">tax</span></span>
  
<span data-ttu-id="f7f9c-256">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-256">tax id</span></span>
  
<span data-ttu-id="f7f9c-257">número personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-257">personal number</span></span>
  
<span data-ttu-id="f7f9c-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="f7f9c-258">daňové číslo</span></span>
  
<span data-ttu-id="f7f9c-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="f7f9c-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="f7f9c-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="f7f9c-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-261">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-261">Format</span></span>

<span data-ttu-id="f7f9c-262">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="f7f9c-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-263">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-263">Pattern</span></span>

<span data-ttu-id="f7f9c-264">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="f7f9c-265">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="f7f9c-266">Un guión </span><span class="sxs-lookup"><span data-stu-id="f7f9c-266">A hyphen</span></span>
    
- <span data-ttu-id="f7f9c-267">Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-268">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-268">Checksum</span></span>

<span data-ttu-id="f7f9c-269">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-270">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-270">Definition</span></span>

<span data-ttu-id="f7f9c-271">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-272">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-273">Se encuentra una `Keywords_denmark_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-275">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-276">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="f7f9c-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-278">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-278">tax number</span></span>
  
<span data-ttu-id="f7f9c-279">Tax</span><span class="sxs-lookup"><span data-stu-id="f7f9c-279">tax</span></span>
  
<span data-ttu-id="f7f9c-280">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-280">tax id</span></span>
  
<span data-ttu-id="f7f9c-281">RCP número</span><span class="sxs-lookup"><span data-stu-id="f7f9c-281">cpr number</span></span>
  
<span data-ttu-id="f7f9c-282">RCP #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-282">cpr#</span></span>
  
<span data-ttu-id="f7f9c-283">Nummer de patinaje</span><span class="sxs-lookup"><span data-stu-id="f7f9c-283">skat nummer</span></span>
  
<span data-ttu-id="f7f9c-284">identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="f7f9c-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="f7f9c-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-286">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-286">Format</span></span>

<span data-ttu-id="f7f9c-287">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-288">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-288">Pattern</span></span>

<span data-ttu-id="f7f9c-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-289">11 digits:</span></span>
  
-  <span data-ttu-id="f7f9c-290">Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI</span><span class="sxs-lookup"><span data-stu-id="f7f9c-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="f7f9c-291">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="f7f9c-292">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="f7f9c-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="f7f9c-293">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-294">Checksum</span></span>

<span data-ttu-id="f7f9c-295">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-296">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-296">Definition</span></span>

<span data-ttu-id="f7f9c-297">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-298">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-299">Se encuentra una `Keywords_estonia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-301">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-302">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="f7f9c-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-304">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-304">tax number</span></span>
  
<span data-ttu-id="f7f9c-305">Tax</span><span class="sxs-lookup"><span data-stu-id="f7f9c-305">tax</span></span>
  
<span data-ttu-id="f7f9c-306">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-306">tax id</span></span>
  
<span data-ttu-id="f7f9c-307">código personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-307">personal code</span></span>
  
<span data-ttu-id="f7f9c-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-308">maksunumber</span></span>
  
<span data-ttu-id="f7f9c-309">identificador maksu</span><span class="sxs-lookup"><span data-stu-id="f7f9c-309">maksu id</span></span>
  
<span data-ttu-id="f7f9c-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="f7f9c-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="f7f9c-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-312">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-312">Format</span></span>

<span data-ttu-id="f7f9c-313">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-314">Pattern</span></span>

<span data-ttu-id="f7f9c-315">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="f7f9c-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-316">Six digits</span></span>
    
- <span data-ttu-id="f7f9c-317">Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior</span><span class="sxs-lookup"><span data-stu-id="f7f9c-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="f7f9c-318">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-318">Three digits</span></span>
    
- <span data-ttu-id="f7f9c-319">Una letra o un número</span><span class="sxs-lookup"><span data-stu-id="f7f9c-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-320">Checksum</span></span>

<span data-ttu-id="f7f9c-321">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-322">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-322">Definition</span></span>

<span data-ttu-id="f7f9c-323">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-324">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-325">Se encuentra una `Keywords_finland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-327">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-328">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="f7f9c-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-330">identification number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-330">identification number</span></span>
  
<span data-ttu-id="f7f9c-331">identificador personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-331">personal id</span></span>
  
<span data-ttu-id="f7f9c-332">número de identidad</span><span class="sxs-lookup"><span data-stu-id="f7f9c-332">identity number</span></span>
  
<span data-ttu-id="f7f9c-333">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="f7f9c-333">finnish national id number</span></span>
  
<span data-ttu-id="f7f9c-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-334">personalidnumber#</span></span>
  
<span data-ttu-id="f7f9c-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-335">national identification number</span></span>
  
<span data-ttu-id="f7f9c-336">número de identificador</span><span class="sxs-lookup"><span data-stu-id="f7f9c-336">id number</span></span>
  
<span data-ttu-id="f7f9c-337">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="f7f9c-337">national id no.</span></span>
  
<span data-ttu-id="f7f9c-338">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="f7f9c-338">national id number</span></span>
  
<span data-ttu-id="f7f9c-339">identificador no</span><span class="sxs-lookup"><span data-stu-id="f7f9c-339">id no</span></span>
  
<span data-ttu-id="f7f9c-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-340">tunnistenumero</span></span>
  
<span data-ttu-id="f7f9c-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="f7f9c-341">henkilötunnus</span></span>
  
<span data-ttu-id="f7f9c-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="f7f9c-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="f7f9c-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="f7f9c-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-344">identiteetti numero</span></span>
  
<span data-ttu-id="f7f9c-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="f7f9c-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="f7f9c-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="f7f9c-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="f7f9c-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-348">tunnusnumero</span></span>
  
<span data-ttu-id="f7f9c-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="f7f9c-350">Francia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-350">France</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-351">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-351">Format</span></span>

<span data-ttu-id="f7f9c-352">13 dígitos para personas y nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="f7f9c-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-353">Pattern</span></span>

<span data-ttu-id="f7f9c-354">13 dígitos para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="f7f9c-355">Un dígito que debe ser 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="f7f9c-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="f7f9c-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-356">12 digits</span></span>
    
<span data-ttu-id="f7f9c-357">Nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="f7f9c-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-358">Checksum</span></span>

<span data-ttu-id="f7f9c-359">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-360">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-360">Definition</span></span>

<span data-ttu-id="f7f9c-361">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-362">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-363">Se encuentra una `Keywords_france_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-365">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="f7f9c-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-368">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-368">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-369">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-369">tax number</span></span>
  
<span data-ttu-id="f7f9c-370">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-370">tax id</span></span>
  
<span data-ttu-id="f7f9c-371">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="f7f9c-372">Alemania</span><span class="sxs-lookup"><span data-stu-id="f7f9c-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-373">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-373">Format</span></span>

<span data-ttu-id="f7f9c-374">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-375">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-375">Pattern</span></span>

<span data-ttu-id="f7f9c-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-376">11 digits :</span></span>
  
-  <span data-ttu-id="f7f9c-377">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-377">Ten digits</span></span> 
    
- <span data-ttu-id="f7f9c-378">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-379">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-379">Checksum</span></span>

<span data-ttu-id="f7f9c-380">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-381">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-381">Definition</span></span>

<span data-ttu-id="f7f9c-382">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-383">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-384">Se encuentra una `Keywords_germany_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-386">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="f7f9c-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-389">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-389">tax number</span></span>
  
<span data-ttu-id="f7f9c-390">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-390">tax no.</span></span>
  
<span data-ttu-id="f7f9c-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-391">taxno#</span></span>
  
<span data-ttu-id="f7f9c-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-392">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-393">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-394">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-394">tax id</span></span>
  
<span data-ttu-id="f7f9c-395">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-395">taxid#</span></span>
  
<span data-ttu-id="f7f9c-396">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-396">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-397">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-397">tax identification no.</span></span>
  
<span data-ttu-id="f7f9c-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-398">steuernummer</span></span>
  
<span data-ttu-id="f7f9c-399">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-399">steuer id</span></span>
  
<span data-ttu-id="f7f9c-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="f7f9c-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-402">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-402">Format</span></span>

<span data-ttu-id="f7f9c-403">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-404">Pattern</span></span>

<span data-ttu-id="f7f9c-405">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-406">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-406">Checksum</span></span>

<span data-ttu-id="f7f9c-407">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-408">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-408">Definition</span></span>

<span data-ttu-id="f7f9c-409">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-410">La expresión `Regex_greece_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-411">Se encuentra una `Keywords_greece_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f7f9c-412">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="f7f9c-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-414">afm</span><span class="sxs-lookup"><span data-stu-id="f7f9c-414">afm</span></span>
  
<span data-ttu-id="f7f9c-415">/</span><span class="sxs-lookup"><span data-stu-id="f7f9c-415">tin</span></span>
  
<span data-ttu-id="f7f9c-416">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-416">tax id no.</span></span>
  
<span data-ttu-id="f7f9c-417">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-417">tax id no</span></span>
  
<span data-ttu-id="f7f9c-418">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-418">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-419">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-419">tax registry number</span></span>
  
<span data-ttu-id="f7f9c-420">n.º de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-420">tax registry no.</span></span>
  
<span data-ttu-id="f7f9c-421">afm #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-421">afm#</span></span>
  
<span data-ttu-id="f7f9c-422">/ #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-422">tin#</span></span>
  
<span data-ttu-id="f7f9c-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-423">taxidno#</span></span>
  
<span data-ttu-id="f7f9c-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-424">taxregistryno#</span></span>
  
<span data-ttu-id="f7f9c-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f7f9c-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="f7f9c-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="f7f9c-426">aφμ</span></span>
  
<span data-ttu-id="f7f9c-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="f7f9c-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="f7f9c-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="f7f9c-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f7f9c-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="f7f9c-430">Hungría</span><span class="sxs-lookup"><span data-stu-id="f7f9c-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-431">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-431">Format</span></span>

<span data-ttu-id="f7f9c-432">Diez dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-433">Pattern</span></span>

<span data-ttu-id="f7f9c-434">Diez dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-434">Ten digits:</span></span>
  
-  <span data-ttu-id="f7f9c-435">Un dígito que debe ser "8"</span><span class="sxs-lookup"><span data-stu-id="f7f9c-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="f7f9c-436">Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="f7f9c-437">Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día</span><span class="sxs-lookup"><span data-stu-id="f7f9c-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="f7f9c-438">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-439">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-439">Checksum</span></span>

<span data-ttu-id="f7f9c-440">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-441">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-441">Definition</span></span>

<span data-ttu-id="f7f9c-442">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-443">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-444">Se encuentra una `Keywords_hungary_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-445">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-446">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-447">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="f7f9c-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-449">número de identificación fiscal húngara</span><span class="sxs-lookup"><span data-stu-id="f7f9c-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="f7f9c-450">NIF Húngaro</span><span class="sxs-lookup"><span data-stu-id="f7f9c-450">hungarian tin</span></span>
  
<span data-ttu-id="f7f9c-451">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-451">tax id number</span></span>
  
<span data-ttu-id="f7f9c-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="f7f9c-452">vat number</span></span>
  
<span data-ttu-id="f7f9c-453">n.º de autoridad fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-453">tax authority no</span></span>
  
<span data-ttu-id="f7f9c-454">número de identidad fiscal de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-454">tax id tax identity number</span></span>
  
<span data-ttu-id="f7f9c-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-455">taxidnumber#</span></span>
  
<span data-ttu-id="f7f9c-456">/ #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-456">tin#</span></span>
  
<span data-ttu-id="f7f9c-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-457">hungatiantin#</span></span>
  
<span data-ttu-id="f7f9c-458">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-458">tax identification no</span></span>
  
<span data-ttu-id="f7f9c-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-459">taxidno#</span></span>
  
<span data-ttu-id="f7f9c-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="f7f9c-460">adóazonosító szám</span></span>
  
<span data-ttu-id="f7f9c-461">adószám</span><span class="sxs-lookup"><span data-stu-id="f7f9c-461">adószám</span></span>
  
<span data-ttu-id="f7f9c-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="f7f9c-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="f7f9c-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f7f9c-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-464">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-464">Format</span></span>

<span data-ttu-id="f7f9c-465">Siete dígitos seguidos de una letra sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-466">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-466">Pattern</span></span>

<span data-ttu-id="f7f9c-467">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="f7f9c-468">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-468">Seven digits</span></span> 
    
- <span data-ttu-id="f7f9c-469">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-470">Checksum</span></span>

<span data-ttu-id="f7f9c-471">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-472">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-472">Definition</span></span>

<span data-ttu-id="f7f9c-473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-474">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-475">Se encuentra una `Keywords_ireland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-476">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-477">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="f7f9c-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-480">n.º de servicio público</span><span class="sxs-lookup"><span data-stu-id="f7f9c-480">public service no</span></span>
  
<span data-ttu-id="f7f9c-481">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-481">personal public service no</span></span>
  
<span data-ttu-id="f7f9c-482">n.º de PPS</span><span class="sxs-lookup"><span data-stu-id="f7f9c-482">pps no</span></span>
  
<span data-ttu-id="f7f9c-483">n.º de servicio personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-483">personal service no</span></span>
  
<span data-ttu-id="f7f9c-484">n.º de servicio de PPS</span><span class="sxs-lookup"><span data-stu-id="f7f9c-484">pps service no</span></span>
  
<span data-ttu-id="f7f9c-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-485">ppsno#</span></span>
  
<span data-ttu-id="f7f9c-486">n.º de PPS irlandés</span><span class="sxs-lookup"><span data-stu-id="f7f9c-486">irish pps no</span></span>
  
<span data-ttu-id="f7f9c-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-487">publicserviceno#</span></span>
  
<span data-ttu-id="f7f9c-488">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-488">personal public service number</span></span>
  
<span data-ttu-id="f7f9c-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="f7f9c-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="f7f9c-490">pps uimh</span></span>
  
<span data-ttu-id="f7f9c-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="f7f9c-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="f7f9c-492">Italia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-493">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-493">Format</span></span>

<span data-ttu-id="f7f9c-494">16 letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f7f9c-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-495">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-495">Pattern</span></span>

<span data-ttu-id="f7f9c-496">16 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="f7f9c-497">Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="f7f9c-498">Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre</span><span class="sxs-lookup"><span data-stu-id="f7f9c-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="f7f9c-499">Dos dígitos que corresponden a los últimos dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="f7f9c-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="f7f9c-500">Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="f7f9c-501">Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="f7f9c-502">Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).</span><span class="sxs-lookup"><span data-stu-id="f7f9c-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="f7f9c-503">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-504">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-504">Checksum</span></span>

<span data-ttu-id="f7f9c-505">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-506">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-506">Definition</span></span>

<span data-ttu-id="f7f9c-507">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-508">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-509">Se encuentra una `Keywords_italy_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-510">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-511">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-512">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="f7f9c-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-514">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-514">tax number</span></span>
  
<span data-ttu-id="f7f9c-515">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-515">tax no.</span></span>
  
<span data-ttu-id="f7f9c-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-516">taxno#</span></span>
  
<span data-ttu-id="f7f9c-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-517">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-518">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-519">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-519">tax id</span></span>
  
<span data-ttu-id="f7f9c-520">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-520">taxid#</span></span>
  
<span data-ttu-id="f7f9c-521">Código fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-521">fiscal code</span></span>
  
<span data-ttu-id="f7f9c-522">Codice fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="f7f9c-523">Letonia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-524">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-524">Format</span></span>

<span data-ttu-id="f7f9c-525">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-526">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-526">Pattern</span></span>

<span data-ttu-id="f7f9c-527">11 dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f7f9c-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="f7f9c-528">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="f7f9c-529">Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="f7f9c-530">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-531">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-531">Checksum</span></span>

<span data-ttu-id="f7f9c-532">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-533">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-533">Definition</span></span>

<span data-ttu-id="f7f9c-534">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-535">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-536">Se encuentra una `Keywords_latvia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-537">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-538">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-539">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="f7f9c-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-541">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-541">tax number</span></span>
  
<span data-ttu-id="f7f9c-542">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-542">tax no.</span></span>
  
<span data-ttu-id="f7f9c-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-543">taxno#</span></span>
  
<span data-ttu-id="f7f9c-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-544">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-545">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-546">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-546">tax id</span></span>
  
<span data-ttu-id="f7f9c-547">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-547">taxid#</span></span>
  
<span data-ttu-id="f7f9c-548">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-548">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-549">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-549">tax identification no.</span></span>
  
<span data-ttu-id="f7f9c-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="f7f9c-550">nodokļa numurs</span></span>
  
<span data-ttu-id="f7f9c-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="f7f9c-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="f7f9c-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="f7f9c-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="f7f9c-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="f7f9c-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-554">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-554">Format</span></span>

<span data-ttu-id="f7f9c-555">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-556">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-556">Pattern</span></span>

<span data-ttu-id="f7f9c-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-558">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-558">Checksum</span></span>

<span data-ttu-id="f7f9c-559">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-560">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-560">Definition</span></span>

<span data-ttu-id="f7f9c-561">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-562">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-563">Se encuentra una `Keywords_lithuania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-564">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-565">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-566">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="f7f9c-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-568">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-568">tax number</span></span>
  
<span data-ttu-id="f7f9c-569">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-569">tax no.</span></span>
  
<span data-ttu-id="f7f9c-570">Nº de impuestos #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-570">tax no#</span></span>
  
<span data-ttu-id="f7f9c-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-571">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-572">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-573">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-573">tax id</span></span>
  
<span data-ttu-id="f7f9c-574">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-574">taxid#</span></span>
  
<span data-ttu-id="f7f9c-575">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-575">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-576">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-576">tax identification no.</span></span>
  
<span data-ttu-id="f7f9c-577">identificador mokesčių</span><span class="sxs-lookup"><span data-stu-id="f7f9c-577">mokesčių id</span></span>
  
<span data-ttu-id="f7f9c-578">numeración mokesčių</span><span class="sxs-lookup"><span data-stu-id="f7f9c-578">mokesčių numeris</span></span>
  
<span data-ttu-id="f7f9c-579">mokesčių identifikavimas número</span><span class="sxs-lookup"><span data-stu-id="f7f9c-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="f7f9c-580">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="f7f9c-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-581">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-581">Format</span></span>

<span data-ttu-id="f7f9c-582">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-583">Pattern</span></span>

<span data-ttu-id="f7f9c-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-584">13 digits:</span></span>
  
-  <span data-ttu-id="f7f9c-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-585">11 digits</span></span> 
    
- <span data-ttu-id="f7f9c-586">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-587">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-587">Checksum</span></span>

<span data-ttu-id="f7f9c-588">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-589">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-589">Definition</span></span>

<span data-ttu-id="f7f9c-590">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-591">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-592">Se encuentra una `Keywords_luxemburg_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-593">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-594">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-595">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="f7f9c-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-597">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-597">tax number</span></span>
  
<span data-ttu-id="f7f9c-598">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-598">tax no.</span></span>
  
<span data-ttu-id="f7f9c-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-599">taxno#</span></span>
  
<span data-ttu-id="f7f9c-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-600">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-601">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-602">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-602">tax id</span></span>
  
<span data-ttu-id="f7f9c-603">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-603">taxid#</span></span>
  
<span data-ttu-id="f7f9c-604">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-604">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-605">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-605">tax identification no.</span></span>
  
<span data-ttu-id="f7f9c-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-606">steuernummer</span></span>
  
<span data-ttu-id="f7f9c-607">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-607">steuer id</span></span>
  
<span data-ttu-id="f7f9c-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="f7f9c-609">Malta</span><span class="sxs-lookup"><span data-stu-id="f7f9c-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-610">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-610">Format</span></span>

<span data-ttu-id="f7f9c-611">Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f7f9c-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="f7f9c-612">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-613">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-613">Pattern</span></span>

<span data-ttu-id="f7f9c-614">Nacionales de Malta: 7 dígitos y una letra</span><span class="sxs-lookup"><span data-stu-id="f7f9c-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="f7f9c-615">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-615">Seven digits</span></span> 
    
- <span data-ttu-id="f7f9c-616">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="f7f9c-617">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="f7f9c-618">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-619">Checksum</span></span>

<span data-ttu-id="f7f9c-620">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-621">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-621">Definition</span></span>

<span data-ttu-id="f7f9c-622">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-623">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-624">Se encuentra una `Keywords_malta_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-626">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-627">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="f7f9c-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-629">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-629">tax number</span></span>
  
<span data-ttu-id="f7f9c-630">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-630">tax no.</span></span>
  
<span data-ttu-id="f7f9c-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-631">taxno#</span></span>
  
<span data-ttu-id="f7f9c-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-632">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-633">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-634">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-634">tax id</span></span>
  
<span data-ttu-id="f7f9c-635">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-635">taxid#</span></span>
  
<span data-ttu-id="f7f9c-636">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-636">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-637">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-637">tax identification no.</span></span>
  
<span data-ttu-id="f7f9c-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="f7f9c-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="f7f9c-639">identificador TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="f7f9c-639">id tat-taxxa</span></span>
  
<span data-ttu-id="f7f9c-640">numru ta ' identifikazzjoni TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="f7f9c-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="f7f9c-641">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-642">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-642">Format</span></span>

<span data-ttu-id="f7f9c-643">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-644">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-644">Pattern</span></span>

<span data-ttu-id="f7f9c-645">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-646">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-646">Checksum</span></span>

<span data-ttu-id="f7f9c-647">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-648">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-648">Definition</span></span>

<span data-ttu-id="f7f9c-649">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-650">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-651">Se encuentra una `Keywords_netherlands_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-652">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-653">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-654">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="f7f9c-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-656">número de identificación fiscal de países bajos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="f7f9c-657">identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-657">netherlands tax identification</span></span>
  
<span data-ttu-id="f7f9c-658">número de identificación fiscal de Netherland</span><span class="sxs-lookup"><span data-stu-id="f7f9c-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="f7f9c-659">identificación de impuestos de Netherland</span><span class="sxs-lookup"><span data-stu-id="f7f9c-659">netherland's tax identification</span></span>
  
<span data-ttu-id="f7f9c-660">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-660">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-661">identificador fiscal holandés</span><span class="sxs-lookup"><span data-stu-id="f7f9c-661">dutch tax id</span></span>
  
<span data-ttu-id="f7f9c-662">número de identificación fiscal holandes</span><span class="sxs-lookup"><span data-stu-id="f7f9c-662">dutch tax identification number</span></span>
  
<span data-ttu-id="f7f9c-663">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-663">tax id</span></span>
  
<span data-ttu-id="f7f9c-664">identificador de impuesto #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-664">tax id#</span></span>
  
<span data-ttu-id="f7f9c-665">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-665">tax number</span></span>
  
<span data-ttu-id="f7f9c-666">Nº de impuestos #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-666">tax no#</span></span>
  
<span data-ttu-id="f7f9c-667">Tax #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-667">tax#</span></span>
  
<span data-ttu-id="f7f9c-668">/</span><span class="sxs-lookup"><span data-stu-id="f7f9c-668">tin</span></span>
  
<span data-ttu-id="f7f9c-669">/ #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-669">tin#</span></span>
  
<span data-ttu-id="f7f9c-670">NIF-Países Bajos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-670">netherlands tin</span></span>
  
<span data-ttu-id="f7f9c-671">estaño de Netherland</span><span class="sxs-lookup"><span data-stu-id="f7f9c-671">netherland's tin</span></span>
  
<span data-ttu-id="f7f9c-672">último países de la identificatienummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="f7f9c-673">identificatienummerto de furgoneta</span><span class="sxs-lookup"><span data-stu-id="f7f9c-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="f7f9c-674">identificatienummer en último lugar</span><span class="sxs-lookup"><span data-stu-id="f7f9c-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="f7f9c-675">último países de la identificatie</span><span class="sxs-lookup"><span data-stu-id="f7f9c-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="f7f9c-676">último identificador de Nummer de países bajos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="f7f9c-677">Países Bajos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="f7f9c-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-678">btw nummer</span></span>
  
<span data-ttu-id="f7f9c-679">Nederlandse de la última identificatie</span><span class="sxs-lookup"><span data-stu-id="f7f9c-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="f7f9c-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-681">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-681">Format</span></span>

<span data-ttu-id="f7f9c-682">Once dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-683">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-683">Pattern</span></span>

<span data-ttu-id="f7f9c-684">Once dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-685">Checksum</span></span>

<span data-ttu-id="f7f9c-686">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-687">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-687">Definition</span></span>

<span data-ttu-id="f7f9c-688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-689">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-690">Se encuentra una `Keywords_poland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-691">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-692">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-693">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="f7f9c-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-695">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-695">tax number</span></span>
  
<span data-ttu-id="f7f9c-696">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-696">tax no.</span></span>
  
<span data-ttu-id="f7f9c-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-697">taxno#</span></span>
  
<span data-ttu-id="f7f9c-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-698">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-699">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-700">nip</span><span class="sxs-lookup"><span data-stu-id="f7f9c-700">nip</span></span>
  
<span data-ttu-id="f7f9c-701">nip #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-701">nip#</span></span>
  
<span data-ttu-id="f7f9c-702">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-702">tax id</span></span>
  
<span data-ttu-id="f7f9c-703">identificador de impuesto #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-703">tax id#</span></span>
  
<span data-ttu-id="f7f9c-704">identificador NIP</span><span class="sxs-lookup"><span data-stu-id="f7f9c-704">nip id</span></span>
  
<span data-ttu-id="f7f9c-705">identificador NIP #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-705">nip id#</span></span>
  
<span data-ttu-id="f7f9c-706">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-706">tax identification number</span></span>
  
<span data-ttu-id="f7f9c-707">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-707">tax identification no.</span></span>
  
<span data-ttu-id="f7f9c-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="f7f9c-708">vat number</span></span>
  
<span data-ttu-id="f7f9c-709">n.º de IVA</span><span class="sxs-lookup"><span data-stu-id="f7f9c-709">vat no.</span></span>
  
<span data-ttu-id="f7f9c-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-710">vatno#</span></span>
  
<span data-ttu-id="f7f9c-711">NIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-711">vat id</span></span>
  
<span data-ttu-id="f7f9c-712">NIF #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-712">vat id#</span></span>
  
<span data-ttu-id="f7f9c-713">numerar identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="f7f9c-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="f7f9c-714">Polski número de identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="f7f9c-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="f7f9c-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="f7f9c-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-717">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-717">Format</span></span>

<span data-ttu-id="f7f9c-718">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-719">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-719">Pattern</span></span>

<span data-ttu-id="f7f9c-720">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-721">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-721">Checksum</span></span>

<span data-ttu-id="f7f9c-722">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-723">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-723">Definition</span></span>

<span data-ttu-id="f7f9c-724">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-725">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-726">Se encuentra una `Keywords_portugal_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-728">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-729">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="f7f9c-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-731">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-731">tax number</span></span>
  
<span data-ttu-id="f7f9c-732">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-732">tax no.</span></span>
  
<span data-ttu-id="f7f9c-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-733">taxno#</span></span>
  
<span data-ttu-id="f7f9c-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-734">taxnumber#</span></span>
  
<span data-ttu-id="f7f9c-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f7f9c-735">taxnumber</span></span>
  
<span data-ttu-id="f7f9c-736">NIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-736">nif</span></span>
  
<span data-ttu-id="f7f9c-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-737">nif#</span></span>
  
<span data-ttu-id="f7f9c-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-738">numero fiscal</span></span>
  
<span data-ttu-id="f7f9c-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="f7f9c-740">Rumania</span><span class="sxs-lookup"><span data-stu-id="f7f9c-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-741">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-741">Format</span></span>

<span data-ttu-id="f7f9c-742">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-743">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-743">Pattern</span></span>

<span data-ttu-id="f7f9c-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-745">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-745">Checksum</span></span>

<span data-ttu-id="f7f9c-746">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-747">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-747">Definition</span></span>

<span data-ttu-id="f7f9c-748">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-749">La expresión `Regex_romania_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-750">Se encuentra una `Keywords_romania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f7f9c-751">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="f7f9c-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-753">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-753">tax id</span></span>
  
<span data-ttu-id="f7f9c-754">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-754">tax id number</span></span>
  
<span data-ttu-id="f7f9c-755">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-755">tax file no</span></span>
  
<span data-ttu-id="f7f9c-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-756">tax file number</span></span>
  
<span data-ttu-id="f7f9c-757">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-757">tax no</span></span>
  
<span data-ttu-id="f7f9c-758">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-758">tax number</span></span>
  
<span data-ttu-id="f7f9c-759">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-759">taxid#</span></span>
  
<span data-ttu-id="f7f9c-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-760">taxno#</span></span>
  
<span data-ttu-id="f7f9c-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="f7f9c-761">id-ul taxei</span></span>
  
<span data-ttu-id="f7f9c-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="f7f9c-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="f7f9c-763">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-764">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-764">Format</span></span>

<span data-ttu-id="f7f9c-765">10 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-766">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-766">Pattern</span></span>

<span data-ttu-id="f7f9c-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-768">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-768">Checksum</span></span>

<span data-ttu-id="f7f9c-769">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f7f9c-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-770">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-770">Definition</span></span>

<span data-ttu-id="f7f9c-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-772">La expresión `Regex_slovakia_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-773">Se encuentra una `Keywords_slovakia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f7f9c-774">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="f7f9c-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-776">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-776">tax id</span></span>
  
<span data-ttu-id="f7f9c-777">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-777">tax id number</span></span>
  
<span data-ttu-id="f7f9c-778">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="f7f9c-778">tin id</span></span>
  
<span data-ttu-id="f7f9c-779">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="f7f9c-779">tin no</span></span>
  
<span data-ttu-id="f7f9c-780">ID de estaño de eslovaco</span><span class="sxs-lookup"><span data-stu-id="f7f9c-780">slovakian tin id</span></span>
  
<span data-ttu-id="f7f9c-781">/</span><span class="sxs-lookup"><span data-stu-id="f7f9c-781">tin</span></span>
  
<span data-ttu-id="f7f9c-782">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-782">tax file no</span></span>
  
<span data-ttu-id="f7f9c-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-783">tax file number</span></span>
  
<span data-ttu-id="f7f9c-784">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-784">tax no</span></span>
  
<span data-ttu-id="f7f9c-785">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-785">tax number</span></span>
  
<span data-ttu-id="f7f9c-786">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-786">taxid#</span></span>
  
<span data-ttu-id="f7f9c-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-787">taxno#</span></span>
  
<span data-ttu-id="f7f9c-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="f7f9c-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="f7f9c-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="f7f9c-789">daňové číslo</span></span>
  
<span data-ttu-id="f7f9c-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="f7f9c-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="f7f9c-791">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-792">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-792">Format</span></span>

<span data-ttu-id="f7f9c-793">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-794">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-794">Pattern</span></span>

<span data-ttu-id="f7f9c-795">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-796">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-796">Checksum</span></span>

<span data-ttu-id="f7f9c-797">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-798">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-798">Definition</span></span>

<span data-ttu-id="f7f9c-799">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-800">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-801">Se encuentra una `Keywords_slovenia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-802">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-803">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-804">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="f7f9c-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-806">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-806">tax id</span></span>
  
<span data-ttu-id="f7f9c-807">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-807">tax id number</span></span>
  
<span data-ttu-id="f7f9c-808">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="f7f9c-808">tin id</span></span>
  
<span data-ttu-id="f7f9c-809">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="f7f9c-809">tin no</span></span>
  
<span data-ttu-id="f7f9c-810">ID de estaño de esloveno</span><span class="sxs-lookup"><span data-stu-id="f7f9c-810">slovenian tin id</span></span>
  
<span data-ttu-id="f7f9c-811">/</span><span class="sxs-lookup"><span data-stu-id="f7f9c-811">tin</span></span>
  
<span data-ttu-id="f7f9c-812">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-812">tax file no</span></span>
  
<span data-ttu-id="f7f9c-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-813">tax file number</span></span>
  
<span data-ttu-id="f7f9c-814">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-814">tax no</span></span>
  
<span data-ttu-id="f7f9c-815">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-815">tax number</span></span>
  
<span data-ttu-id="f7f9c-816">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-816">taxid#</span></span>
  
<span data-ttu-id="f7f9c-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-817">taxno#</span></span>
  
<span data-ttu-id="f7f9c-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="f7f9c-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="f7f9c-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="f7f9c-819">davčna številka</span></span>
  
<span data-ttu-id="f7f9c-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="f7f9c-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="f7f9c-821">España</span><span class="sxs-lookup"><span data-stu-id="f7f9c-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-822">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-822">Format</span></span>

<span data-ttu-id="f7f9c-823">Siete u ocho dígitos y una o dos letras en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f7f9c-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-824">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-824">Pattern</span></span>

<span data-ttu-id="f7f9c-825">Personas físicas españolas con una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="f7f9c-826">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-826">Eight digits</span></span> 
    
- <span data-ttu-id="f7f9c-827">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f7f9c-828">Spaniards no residente sin una tarjeta de identidad nacional de España</span><span class="sxs-lookup"><span data-stu-id="f7f9c-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="f7f9c-829">Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="f7f9c-830">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-830">Seven digits</span></span>
    
- <span data-ttu-id="f7f9c-831">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f7f9c-832">Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="f7f9c-833">Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="f7f9c-834">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-834">Seven digits</span></span> 
    
- <span data-ttu-id="f7f9c-835">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="f7f9c-836">Foreigners con un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="f7f9c-837">Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="f7f9c-838">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-838">Seven digits</span></span>
    
- <span data-ttu-id="f7f9c-839">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f7f9c-840">Foreigners sin un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="f7f9c-841">Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="f7f9c-842">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="f7f9c-842">Seven digits</span></span>
    
- <span data-ttu-id="f7f9c-843">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-844">Checksum</span></span>

<span data-ttu-id="f7f9c-845">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-846">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-846">Definition</span></span>

<span data-ttu-id="f7f9c-847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-848">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-849">Se encuentra una `Keywords_spain_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-850">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-851">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-852">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="f7f9c-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-854">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-854">tax id</span></span>
  
<span data-ttu-id="f7f9c-855">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-855">tax id number</span></span>
  
<span data-ttu-id="f7f9c-856">identificador CIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-856">cif id</span></span>
  
<span data-ttu-id="f7f9c-857">n.º CIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-857">cif no</span></span>
  
<span data-ttu-id="f7f9c-858">identificador CIF en Español</span><span class="sxs-lookup"><span data-stu-id="f7f9c-858">spanish cif id</span></span>
  
<span data-ttu-id="f7f9c-859">precio</span><span class="sxs-lookup"><span data-stu-id="f7f9c-859">cif</span></span>
  
<span data-ttu-id="f7f9c-860">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-860">tax file no</span></span>
  
<span data-ttu-id="f7f9c-861">Número CIF en Español</span><span class="sxs-lookup"><span data-stu-id="f7f9c-861">spanish cif number</span></span>
  
<span data-ttu-id="f7f9c-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-862">tax file number</span></span>
  
<span data-ttu-id="f7f9c-863">Número CIF de Español</span><span class="sxs-lookup"><span data-stu-id="f7f9c-863">spanish cif no</span></span>
  
<span data-ttu-id="f7f9c-864">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-864">tax no</span></span>
  
<span data-ttu-id="f7f9c-865">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="f7f9c-865">tax number</span></span>
  
<span data-ttu-id="f7f9c-866">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-866">taxid#</span></span>
  
<span data-ttu-id="f7f9c-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-867">taxno#</span></span>
  
<span data-ttu-id="f7f9c-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-868">cifid#</span></span>
  
<span data-ttu-id="f7f9c-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-869">spanishcifid#</span></span>
  
<span data-ttu-id="f7f9c-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-870">spanishcifno#</span></span>
  
<span data-ttu-id="f7f9c-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="f7f9c-871">número de contribuyente</span></span>
  
<span data-ttu-id="f7f9c-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="f7f9c-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="f7f9c-873">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="f7f9c-874">Número CIF</span><span class="sxs-lookup"><span data-stu-id="f7f9c-874">cif número</span></span>
  
<span data-ttu-id="f7f9c-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="f7f9c-876">Suecia</span><span class="sxs-lookup"><span data-stu-id="f7f9c-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-877">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-877">Format</span></span>

<span data-ttu-id="f7f9c-878">Diez dígitos y un símbolo en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f7f9c-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-879">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-879">Pattern</span></span>

<span data-ttu-id="f7f9c-880">Diez dígitos y un símbolo:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="f7f9c-881">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="f7f9c-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="f7f9c-882">Un signo más, un signo menos o una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="f7f9c-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="f7f9c-883">Tres dígitos que hacen que el número de identificación sea único donde:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="f7f9c-884">Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero</span><span class="sxs-lookup"><span data-stu-id="f7f9c-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="f7f9c-885">El dígito en la novena posición indica el género, ya sea impar o incluso para hembras</span><span class="sxs-lookup"><span data-stu-id="f7f9c-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="f7f9c-886">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="f7f9c-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f7f9c-887">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-887">Checksum</span></span>

<span data-ttu-id="f7f9c-888">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-889">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-889">Definition</span></span>

<span data-ttu-id="f7f9c-890">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-891">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-892">Se encuentra una `Keywords_sweden_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f7f9c-893">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-894">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f7f9c-895">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="f7f9c-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-897">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-897">tax id</span></span>
  
<span data-ttu-id="f7f9c-898">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-898">tax id no.</span></span>
  
<span data-ttu-id="f7f9c-899">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-899">tax id number</span></span>
  
<span data-ttu-id="f7f9c-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="f7f9c-900">tax identification</span></span>
  
<span data-ttu-id="f7f9c-901">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-901">tax identification#</span></span>
  
<span data-ttu-id="f7f9c-902">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-902">tax no.</span></span>
  
<span data-ttu-id="f7f9c-903">Tax #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-903">tax#</span></span>
  
<span data-ttu-id="f7f9c-904">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-904">taxid#</span></span>
  
<span data-ttu-id="f7f9c-905">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-905">tax file</span></span>
  
<span data-ttu-id="f7f9c-906">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-906">tax file no.</span></span>
  
<span data-ttu-id="f7f9c-907">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-907">personal id number</span></span>
  
<span data-ttu-id="f7f9c-908">Nummer de identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="f7f9c-908">skatt id nummer</span></span>
  
<span data-ttu-id="f7f9c-909">Identifikation de patinaje</span><span class="sxs-lookup"><span data-stu-id="f7f9c-909">skatt identifikation</span></span>
  
<span data-ttu-id="f7f9c-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="f7f9c-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="f7f9c-911">LIBRA</span><span class="sxs-lookup"><span data-stu-id="f7f9c-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="f7f9c-912">Formato</span><span class="sxs-lookup"><span data-stu-id="f7f9c-912">Format</span></span>

<span data-ttu-id="f7f9c-913">Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f7f9c-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="f7f9c-914">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="f7f9c-915">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f7f9c-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f7f9c-916">Patrón</span><span class="sxs-lookup"><span data-stu-id="f7f9c-916">Pattern</span></span>

<span data-ttu-id="f7f9c-917">Referencia de contribuyente única (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="f7f9c-918">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="f7f9c-919">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f7f9c-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f7f9c-920">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f7f9c-920">Checksum</span></span>

<span data-ttu-id="f7f9c-921">Sí</span><span class="sxs-lookup"><span data-stu-id="f7f9c-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f7f9c-922">Definición</span><span class="sxs-lookup"><span data-stu-id="f7f9c-922">Definition</span></span>

<span data-ttu-id="f7f9c-923">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f7f9c-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f7f9c-924">La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f7f9c-925">Se encuentra una `Keywords_uk_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f7f9c-926">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7f9c-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="f7f9c-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f7f9c-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="f7f9c-928">tax id</span><span class="sxs-lookup"><span data-stu-id="f7f9c-928">tax id</span></span>
  
<span data-ttu-id="f7f9c-929">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-929">tax id no.</span></span>
  
<span data-ttu-id="f7f9c-930">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="f7f9c-930">tax id number</span></span>
  
<span data-ttu-id="f7f9c-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="f7f9c-931">tax identification</span></span>
  
<span data-ttu-id="f7f9c-932">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-932">tax identification#</span></span>
  
<span data-ttu-id="f7f9c-933">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-933">tax no.</span></span>
  
<span data-ttu-id="f7f9c-934">Tax #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-934">tax#</span></span>
  
<span data-ttu-id="f7f9c-935">taxi #</span><span class="sxs-lookup"><span data-stu-id="f7f9c-935">taxid#</span></span>
  
<span data-ttu-id="f7f9c-936">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="f7f9c-936">tax file</span></span>
  
<span data-ttu-id="f7f9c-937">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="f7f9c-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7f9c-938">Ver también</span><span class="sxs-lookup"><span data-stu-id="f7f9c-938">See also</span></span>

[<span data-ttu-id="f7f9c-939">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="f7f9c-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

