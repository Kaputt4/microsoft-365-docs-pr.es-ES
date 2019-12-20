---
title: Número de la seguridad social de la UE o identificador equivalente
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 0666818dc892070f5c2f0c34abd8ca33d1253e33
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805933"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="44808-104">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="44808-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="44808-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de la seguridad social (SSN) o del identificador equivalente de la UE.</span><span class="sxs-lookup"><span data-stu-id="44808-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="44808-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="44808-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="44808-107">Austria</span><span class="sxs-lookup"><span data-stu-id="44808-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="44808-108">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-108">Format</span></span>

<span data-ttu-id="44808-109">10 dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="44808-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-110">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-110">Pattern</span></span>

<span data-ttu-id="44808-111">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44808-111">10 digits:</span></span>
  
-  <span data-ttu-id="44808-112">Tres dígitos que corresponden a un número de serie</span><span class="sxs-lookup"><span data-stu-id="44808-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="44808-113">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="44808-113">One check digit</span></span>
    
- <span data-ttu-id="44808-114">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="44808-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44808-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-115">Checksum</span></span>

<span data-ttu-id="44808-116">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-117">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-117">Definition</span></span>

<span data-ttu-id="44808-118">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-119">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-120">Se encuentra una `Keywords_austria_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-121">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-122">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-123">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-125">n.º de seguridad social</span><span class="sxs-lookup"><span data-stu-id="44808-125">social security no</span></span>
  
<span data-ttu-id="44808-126">social security number</span><span class="sxs-lookup"><span data-stu-id="44808-126">social security number</span></span>
  
<span data-ttu-id="44808-127">social security code</span><span class="sxs-lookup"><span data-stu-id="44808-127">social security code</span></span>
  
<span data-ttu-id="44808-128">número de seguro</span><span class="sxs-lookup"><span data-stu-id="44808-128">insurance number</span></span>
  
<span data-ttu-id="44808-129">SSN austriaco</span><span class="sxs-lookup"><span data-stu-id="44808-129">austrian ssn</span></span>
  
<span data-ttu-id="44808-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="44808-130">ssn#</span></span>
  
<span data-ttu-id="44808-131">SSN</span><span class="sxs-lookup"><span data-stu-id="44808-131">ssn</span></span>
  
<span data-ttu-id="44808-132">código de seguro</span><span class="sxs-lookup"><span data-stu-id="44808-132">insurance code</span></span>
  
<span data-ttu-id="44808-133">código de seguro #</span><span class="sxs-lookup"><span data-stu-id="44808-133">insurance code#</span></span>
  
<span data-ttu-id="44808-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="44808-134">socialsecurityno#</span></span>
  
<span data-ttu-id="44808-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="44808-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="44808-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="44808-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="44808-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="44808-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="44808-138">Bélgica</span><span class="sxs-lookup"><span data-stu-id="44808-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="44808-139">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-139">Format</span></span>

<span data-ttu-id="44808-140">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="44808-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-141">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-141">Pattern</span></span>

<span data-ttu-id="44808-142">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="44808-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44808-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-143">Checksum</span></span>

<span data-ttu-id="44808-144">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-145">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-145">Definition</span></span>

<span data-ttu-id="44808-146">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-147">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-148">Se encuentra una `Keywords_belgium_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-149">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-150">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-151">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-153">número nacional belga</span><span class="sxs-lookup"><span data-stu-id="44808-153">belgian national number</span></span>
  
<span data-ttu-id="44808-154">número nacional</span><span class="sxs-lookup"><span data-stu-id="44808-154">national number</span></span>
  
<span data-ttu-id="44808-155">social security number</span><span class="sxs-lookup"><span data-stu-id="44808-155">social security number</span></span>
  
<span data-ttu-id="44808-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-156">nationalnumber#</span></span>
  
<span data-ttu-id="44808-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="44808-157">ssn#</span></span>
  
<span data-ttu-id="44808-158">SSN</span><span class="sxs-lookup"><span data-stu-id="44808-158">ssn</span></span>
  
<span data-ttu-id="44808-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="44808-159">nationalnumber</span></span>
  
<span data-ttu-id="44808-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="44808-160">bnn#</span></span>
  
<span data-ttu-id="44808-161">bnn</span><span class="sxs-lookup"><span data-stu-id="44808-161">bnn</span></span>
  
<span data-ttu-id="44808-162">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-162">personal id number</span></span>
  
<span data-ttu-id="44808-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-163">personalidnumber#</span></span>
  
<span data-ttu-id="44808-164">numéro nacional</span><span class="sxs-lookup"><span data-stu-id="44808-164">numéro national</span></span>
  
<span data-ttu-id="44808-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="44808-165">numéro de sécurité</span></span>
  
<span data-ttu-id="44808-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="44808-166">numéro d'assuré</span></span>
  
<span data-ttu-id="44808-167">Nacional del identificador</span><span class="sxs-lookup"><span data-stu-id="44808-167">identifiant national</span></span>
  
<span data-ttu-id="44808-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="44808-168">identifiantnational#</span></span>
  
<span data-ttu-id="44808-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="44808-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="44808-170">Croacia</span><span class="sxs-lookup"><span data-stu-id="44808-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="44808-171">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-171">Format</span></span>

<span data-ttu-id="44808-172">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="44808-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-173">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-173">Pattern</span></span>

 <span data-ttu-id="44808-174">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44808-174">11 digits:</span></span> 
  
-  <span data-ttu-id="44808-175">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="44808-175">Ten digits</span></span> 
    
- <span data-ttu-id="44808-176">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="44808-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44808-177">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-177">Checksum</span></span>

<span data-ttu-id="44808-178">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-179">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-179">Definition</span></span>

<span data-ttu-id="44808-180">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-181">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-182">Se encuentra una `Keywords_croatia_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-183">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-184">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-185">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-187">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-187">personal identification number</span></span>
  
<span data-ttu-id="44808-188">número de ciudadano principal</span><span class="sxs-lookup"><span data-stu-id="44808-188">master citizen number</span></span>
  
<span data-ttu-id="44808-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="44808-189">national identification number</span></span>
  
<span data-ttu-id="44808-190">social security number</span><span class="sxs-lookup"><span data-stu-id="44808-190">social security number</span></span>
  
<span data-ttu-id="44808-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-191">nationalnumber#</span></span>
  
<span data-ttu-id="44808-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="44808-192">ssn#</span></span>
  
<span data-ttu-id="44808-193">SSN</span><span class="sxs-lookup"><span data-stu-id="44808-193">ssn</span></span>
  
<span data-ttu-id="44808-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="44808-194">nationalnumber</span></span>
  
<span data-ttu-id="44808-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="44808-195">bnn#</span></span>
  
<span data-ttu-id="44808-196">bnn</span><span class="sxs-lookup"><span data-stu-id="44808-196">bnn</span></span>
  
<span data-ttu-id="44808-197">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-197">personal id number</span></span>
  
<span data-ttu-id="44808-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-198">personalidnumber#</span></span>
  
<span data-ttu-id="44808-199">OIB</span><span class="sxs-lookup"><span data-stu-id="44808-199">oib</span></span>
  
<span data-ttu-id="44808-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="44808-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="44808-201">Chequia</span><span class="sxs-lookup"><span data-stu-id="44808-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="44808-202">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-202">Format</span></span>

<span data-ttu-id="44808-203">Diez dígitos y una barra diagonal inversa en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="44808-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-204">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-204">Pattern</span></span>

<span data-ttu-id="44808-205">Diez dígitos y una barra diagonal inversa:</span><span class="sxs-lookup"><span data-stu-id="44808-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="44808-206">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD):</span><span class="sxs-lookup"><span data-stu-id="44808-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="44808-207">Una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="44808-207">A backslash</span></span>
    
- <span data-ttu-id="44808-208">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha.</span><span class="sxs-lookup"><span data-stu-id="44808-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="44808-209">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="44808-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44808-210">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-210">Checksum</span></span>

<span data-ttu-id="44808-211">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-212">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-212">Definition</span></span>

<span data-ttu-id="44808-213">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-214">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-215">Se encuentra una `Keywords_czech_republic_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-216">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-217">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-218">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-220">número de nacimiento</span><span class="sxs-lookup"><span data-stu-id="44808-220">birth number</span></span>
  
<span data-ttu-id="44808-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="44808-221">national identification number</span></span>
  
<span data-ttu-id="44808-222">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-222">personal identification number</span></span>
  
<span data-ttu-id="44808-223">social security number</span><span class="sxs-lookup"><span data-stu-id="44808-223">social security number</span></span>
  
<span data-ttu-id="44808-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-224">nationalnumber#</span></span>
  
<span data-ttu-id="44808-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="44808-225">ssn#</span></span>
  
<span data-ttu-id="44808-226">SSN</span><span class="sxs-lookup"><span data-stu-id="44808-226">ssn</span></span>
  
<span data-ttu-id="44808-227">número nacional</span><span class="sxs-lookup"><span data-stu-id="44808-227">national number</span></span>
  
<span data-ttu-id="44808-228">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-228">personal id number</span></span>
  
<span data-ttu-id="44808-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-229">personalidnumber#</span></span>
  
<span data-ttu-id="44808-230">rč</span><span class="sxs-lookup"><span data-stu-id="44808-230">rč</span></span>
  
<span data-ttu-id="44808-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="44808-231">rodné číslo</span></span>
  
<span data-ttu-id="44808-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="44808-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="44808-233">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="44808-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="44808-234">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-234">Format</span></span>

<span data-ttu-id="44808-235">Diez dígitos y un guión en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="44808-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-236">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-236">Pattern</span></span>

<span data-ttu-id="44808-237">Diez dígitos y un guión:</span><span class="sxs-lookup"><span data-stu-id="44808-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="44808-238">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="44808-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="44808-239">Un guión </span><span class="sxs-lookup"><span data-stu-id="44808-239">A hyphen</span></span>
    
- <span data-ttu-id="44808-240">Cuatro dígitos que corresponden a un número de secuencia</span><span class="sxs-lookup"><span data-stu-id="44808-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44808-241">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-241">Checksum</span></span>

<span data-ttu-id="44808-242">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-243">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-243">Definition</span></span>

<span data-ttu-id="44808-244">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-245">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-246">Se encuentra una `Keywords_denmark_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-247">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-248">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-249">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-251">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-251">personal identification number</span></span>
  
<span data-ttu-id="44808-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="44808-252">national identification number</span></span>
  
<span data-ttu-id="44808-253">social security number</span><span class="sxs-lookup"><span data-stu-id="44808-253">social security number</span></span>
  
<span data-ttu-id="44808-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-254">nationalnumber#</span></span>
  
<span data-ttu-id="44808-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="44808-255">ssn#</span></span>
  
<span data-ttu-id="44808-256">SSN</span><span class="sxs-lookup"><span data-stu-id="44808-256">ssn</span></span>
  
<span data-ttu-id="44808-257">número nacional</span><span class="sxs-lookup"><span data-stu-id="44808-257">national number</span></span>
  
<span data-ttu-id="44808-258">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-258">personal id number</span></span>
  
<span data-ttu-id="44808-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-259">personalidnumber#</span></span>
  
<span data-ttu-id="44808-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="44808-260">cpr-nummer</span></span>
  
<span data-ttu-id="44808-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="44808-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="44808-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="44808-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="44808-263">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-263">Format</span></span>

<span data-ttu-id="44808-264">Una combinación de 11 caracteres en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="44808-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-265">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-265">Pattern</span></span>

<span data-ttu-id="44808-266">Una combinación de 11 caracteres en el formato especificado:</span><span class="sxs-lookup"><span data-stu-id="44808-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="44808-267">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="44808-267">Six digits</span></span> 
    
- <span data-ttu-id="44808-268">Una instancia de una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="44808-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="44808-269">Símbolo más</span><span class="sxs-lookup"><span data-stu-id="44808-269">Plus symbol</span></span>
    
  - <span data-ttu-id="44808-270">Símbolo menos</span><span class="sxs-lookup"><span data-stu-id="44808-270">Minus symbol</span></span>
    
  - <span data-ttu-id="44808-271">La letra "A" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44808-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="44808-272">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="44808-272">Three digits</span></span>
    
- <span data-ttu-id="44808-273">Una letra o un dígito</span><span class="sxs-lookup"><span data-stu-id="44808-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44808-274">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-274">Checksum</span></span>

<span data-ttu-id="44808-275">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-276">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-276">Definition</span></span>

<span data-ttu-id="44808-277">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-278">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-279">Se encuentra una `Keywords_finland_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-280">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-281">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-282">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-284">identification number</span><span class="sxs-lookup"><span data-stu-id="44808-284">identification number</span></span>
  
<span data-ttu-id="44808-285">identificador personal</span><span class="sxs-lookup"><span data-stu-id="44808-285">personal id</span></span>
  
<span data-ttu-id="44808-286">número de identidad</span><span class="sxs-lookup"><span data-stu-id="44808-286">identity number</span></span>
  
<span data-ttu-id="44808-287">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="44808-287">finnish national id number</span></span>
  
<span data-ttu-id="44808-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44808-288">personalidnumber#</span></span>
  
<span data-ttu-id="44808-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="44808-289">national identification number</span></span>
  
<span data-ttu-id="44808-290">número de identificador</span><span class="sxs-lookup"><span data-stu-id="44808-290">id number</span></span>
  
<span data-ttu-id="44808-291">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="44808-291">national id no.</span></span>
  
<span data-ttu-id="44808-292">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="44808-292">national id number</span></span>
  
<span data-ttu-id="44808-293">identificador no</span><span class="sxs-lookup"><span data-stu-id="44808-293">id no</span></span>
  
<span data-ttu-id="44808-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="44808-294">tunnistenumero</span></span>
  
<span data-ttu-id="44808-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="44808-295">henkilötunnus</span></span>
  
<span data-ttu-id="44808-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="44808-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="44808-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="44808-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="44808-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="44808-298">identiteetti numero</span></span>
  
<span data-ttu-id="44808-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="44808-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="44808-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="44808-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="44808-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="44808-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="44808-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="44808-302">tunnusnumero</span></span>
  
<span data-ttu-id="44808-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="44808-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="44808-304">hetu</span><span class="sxs-lookup"><span data-stu-id="44808-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="44808-305">Francia</span><span class="sxs-lookup"><span data-stu-id="44808-305">France</span></span>

<span data-ttu-id="44808-306">Para obtener más información, consulte la sección "número de la seguridad social de Francia (INSEE)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44808-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="44808-307">Alemania</span><span class="sxs-lookup"><span data-stu-id="44808-307">Germany</span></span>

<span data-ttu-id="44808-308">Para obtener más información, consulte la sección "número de tarjeta de identidades Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44808-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="44808-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="44808-309">Greece</span></span>

<span data-ttu-id="44808-310">Para obtener más información, consulte la sección "tarjeta de identificación nacional de Grecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44808-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="44808-311">Hungría</span><span class="sxs-lookup"><span data-stu-id="44808-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="44808-312">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-312">Format</span></span>

<span data-ttu-id="44808-313">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="44808-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-314">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-314">Pattern</span></span>

<span data-ttu-id="44808-315">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="44808-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44808-316">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-316">Checksum</span></span>

<span data-ttu-id="44808-317">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-318">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-318">Definition</span></span>

<span data-ttu-id="44808-319">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-320">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-321">Se encuentra una `Keywords_hungary_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-322">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-323">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-324">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-326">número de la seguridad social húngara</span><span class="sxs-lookup"><span data-stu-id="44808-326">hungarian social security number</span></span>
  
<span data-ttu-id="44808-327">social security number</span><span class="sxs-lookup"><span data-stu-id="44808-327">social security number</span></span>
  
<span data-ttu-id="44808-328">NúmeroSeguridadSocial #</span><span class="sxs-lookup"><span data-stu-id="44808-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="44808-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="44808-329">hssn#</span></span>
  
<span data-ttu-id="44808-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="44808-330">socialsecuritynno</span></span>
  
<span data-ttu-id="44808-331">hssn</span><span class="sxs-lookup"><span data-stu-id="44808-331">hssn</span></span>
  
<span data-ttu-id="44808-332">taj</span><span class="sxs-lookup"><span data-stu-id="44808-332">taj</span></span>
  
<span data-ttu-id="44808-333">taj #</span><span class="sxs-lookup"><span data-stu-id="44808-333">taj#</span></span>
  
<span data-ttu-id="44808-334">SSN</span><span class="sxs-lookup"><span data-stu-id="44808-334">ssn</span></span>
  
<span data-ttu-id="44808-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="44808-335">ssn#</span></span>
  
<span data-ttu-id="44808-336">n.º de seguridad social</span><span class="sxs-lookup"><span data-stu-id="44808-336">social security no</span></span>
  
<span data-ttu-id="44808-337">áfa</span><span class="sxs-lookup"><span data-stu-id="44808-337">áfa</span></span>
  
<span data-ttu-id="44808-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="44808-338">közösségi adószám</span></span>
  
<span data-ttu-id="44808-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="44808-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="44808-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="44808-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="44808-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="44808-341">áfa szám</span></span>
  
<span data-ttu-id="44808-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="44808-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="44808-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="44808-343">Portugal</span></span>

<span data-ttu-id="44808-344">Para obtener más información, consulte la sección "número de tarjeta de ciudadano de Portugal" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44808-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="44808-345">España</span><span class="sxs-lookup"><span data-stu-id="44808-345">Spain</span></span>

<span data-ttu-id="44808-346">Para obtener más información, consulte la sección "número de la seguridad social de España (SSN)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44808-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="44808-347">Suecia</span><span class="sxs-lookup"><span data-stu-id="44808-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="44808-348">Formato</span><span class="sxs-lookup"><span data-stu-id="44808-348">Format</span></span>

<span data-ttu-id="44808-349">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="44808-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44808-350">Pattern</span><span class="sxs-lookup"><span data-stu-id="44808-350">Pattern</span></span>

<span data-ttu-id="44808-351">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44808-351">12 digits:</span></span>
  
-  <span data-ttu-id="44808-352">Ocho dígitos que corresponden a la fecha de nacimiento (AAAAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44808-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="44808-353">Tres dígitos que corresponden a un número de serie en el que:</span><span class="sxs-lookup"><span data-stu-id="44808-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="44808-354">El último dígito del número de serie indica el sexo por la asignación de un número impar para macho y un número par para hembras</span><span class="sxs-lookup"><span data-stu-id="44808-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="44808-355">Hasta 1990, la asignación de número de serie que se corresponde con el condado en el que nació el portador del número o (si nació antes de 1947) donde estuvo viviendo, de acuerdo con los registros fiscales, el 1 de enero de 1947, con un código especial (por lo general, 9 como el séptimo dígito) para Immigrants</span><span class="sxs-lookup"><span data-stu-id="44808-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="44808-356">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="44808-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44808-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="44808-357">Checksum</span></span>

<span data-ttu-id="44808-358">Sí</span><span class="sxs-lookup"><span data-stu-id="44808-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44808-359">Definición</span><span class="sxs-lookup"><span data-stu-id="44808-359">Definition</span></span>

<span data-ttu-id="44808-360">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-361">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44808-362">Se encuentra una `Keywords_sweden_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="44808-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="44808-363">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44808-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44808-364">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="44808-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44808-365">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44808-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="44808-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="44808-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="44808-367">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-367">personal id number</span></span>
  
<span data-ttu-id="44808-368">identification number</span><span class="sxs-lookup"><span data-stu-id="44808-368">identification number</span></span>
  
<span data-ttu-id="44808-369">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-369">personal id no</span></span>
  
<span data-ttu-id="44808-370">n.º de identidad</span><span class="sxs-lookup"><span data-stu-id="44808-370">identity no</span></span>
  
<span data-ttu-id="44808-371">n.º de identificación</span><span class="sxs-lookup"><span data-stu-id="44808-371">identification no</span></span>
  
<span data-ttu-id="44808-372">n.º de identificación personal</span><span class="sxs-lookup"><span data-stu-id="44808-372">personal identification no</span></span>
  
<span data-ttu-id="44808-373">identificador personnummer</span><span class="sxs-lookup"><span data-stu-id="44808-373">personnummer id</span></span>
  
<span data-ttu-id="44808-374">personligt ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="44808-374">personligt id-nummer</span></span>
  
<span data-ttu-id="44808-375">unikt ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="44808-375">unikt id-nummer</span></span>
  
<span data-ttu-id="44808-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="44808-376">personnummer</span></span>
  
<span data-ttu-id="44808-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="44808-377">identifikationsnumret</span></span>
  
<span data-ttu-id="44808-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="44808-378">personnummer#</span></span>
  
<span data-ttu-id="44808-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="44808-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44808-380">Vea también</span><span class="sxs-lookup"><span data-stu-id="44808-380">See also</span></span>

[<span data-ttu-id="44808-381">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="44808-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

