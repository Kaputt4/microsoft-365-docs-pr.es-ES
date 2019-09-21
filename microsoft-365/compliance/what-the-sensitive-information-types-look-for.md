---
title: Qué buscan los tipos de información confidencial
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye 80 tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.
ms.openlocfilehash: 820bab0a128f952cf5d96208f5d561f4994bd859
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37093042"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="a199a-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="a199a-104">What the sensitive information types look for</span></span>

<span data-ttu-id="a199a-105">La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="a199a-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="a199a-106">Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.</span><span class="sxs-lookup"><span data-stu-id="a199a-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="a199a-107">Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función.</span><span class="sxs-lookup"><span data-stu-id="a199a-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="a199a-108">Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="a199a-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="a199a-109">El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="a199a-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="a199a-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="a199a-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-111">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-111">Format</span></span>

<span data-ttu-id="a199a-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="a199a-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-113">Pattern</span></span>

<span data-ttu-id="a199a-114">Con formato</span><span class="sxs-lookup"><span data-stu-id="a199a-114">Formatted:</span></span>
- <span data-ttu-id="a199a-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="a199a-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="a199a-116">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-116">A hyphen</span></span>
- <span data-ttu-id="a199a-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-117">Four digits</span></span>
- <span data-ttu-id="a199a-118">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-118">A hyphen</span></span>
- <span data-ttu-id="a199a-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-119">A digit</span></span>

<span data-ttu-id="a199a-120">Sin formato: 9 dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="a199a-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="a199a-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-121">Checksum</span></span>

<span data-ttu-id="a199a-122">No</span><span class="sxs-lookup"><span data-stu-id="a199a-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-123">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-123">Definition</span></span>

<span data-ttu-id="a199a-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="a199a-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="a199a-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="a199a-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="a199a-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="a199a-129">ABA</span><span class="sxs-lookup"><span data-stu-id="a199a-129">aba</span></span>
- <span data-ttu-id="a199a-130">aba #</span><span class="sxs-lookup"><span data-stu-id="a199a-130">aba #</span></span>
- <span data-ttu-id="a199a-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="a199a-131">aba routing #</span></span>
- <span data-ttu-id="a199a-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="a199a-132">aba routing number</span></span>
- <span data-ttu-id="a199a-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="a199a-133">aba#</span></span>
- <span data-ttu-id="a199a-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="a199a-134">abarouting#</span></span>
- <span data-ttu-id="a199a-135">aba number</span><span class="sxs-lookup"><span data-stu-id="a199a-135">aba number</span></span>
- <span data-ttu-id="a199a-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-136">abaroutingnumber</span></span>
- <span data-ttu-id="a199a-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="a199a-137">american bank association routing #</span></span>
- <span data-ttu-id="a199a-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="a199a-138">american bank association routing number</span></span>
- <span data-ttu-id="a199a-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="a199a-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="a199a-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="a199a-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="a199a-141">bank routing number</span></span>
- <span data-ttu-id="a199a-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="a199a-142">bankrouting#</span></span>
- <span data-ttu-id="a199a-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-143">bankroutingnumber</span></span>
- <span data-ttu-id="a199a-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="a199a-144">routing transit number</span></span>
- <span data-ttu-id="a199a-145">RTN</span><span class="sxs-lookup"><span data-stu-id="a199a-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="a199a-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="a199a-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-147">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-147">Format</span></span>

<span data-ttu-id="a199a-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="a199a-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-149">Pattern</span></span>

<span data-ttu-id="a199a-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-150">Eight digits:</span></span>
- <span data-ttu-id="a199a-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-151">Two digits</span></span>
- <span data-ttu-id="a199a-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-152">A period</span></span>
- <span data-ttu-id="a199a-153">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-153">Three digits</span></span>
- <span data-ttu-id="a199a-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-154">A period</span></span>
- <span data-ttu-id="a199a-155">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-156">Checksum</span></span>

<span data-ttu-id="a199a-157">No</span><span class="sxs-lookup"><span data-stu-id="a199a-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-158">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-158">Definition</span></span>

<span data-ttu-id="a199a-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="a199a-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="a199a-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="a199a-164">Número de identidad nacional de Argentina</span><span class="sxs-lookup"><span data-stu-id="a199a-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="a199a-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-165">Identity</span></span> 
- <span data-ttu-id="a199a-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="a199a-167">DNI</span><span class="sxs-lookup"><span data-stu-id="a199a-167">DNI</span></span> 
- <span data-ttu-id="a199a-168">Registro Nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="a199a-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="a199a-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="a199a-170">Registro nacional de las personas</span><span class="sxs-lookup"><span data-stu-id="a199a-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="a199a-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-171">Identidad</span></span> 
- <span data-ttu-id="a199a-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="a199a-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="a199a-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-174">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-174">Format</span></span>

<span data-ttu-id="a199a-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="a199a-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-176">Pattern</span></span>

<span data-ttu-id="a199a-177">El número de cuenta tiene entre 6 y 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="a199a-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="a199a-178">Número de sucursal bancaria de Australia:</span><span class="sxs-lookup"><span data-stu-id="a199a-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="a199a-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-179">Three digits</span></span> 
- <span data-ttu-id="a199a-180">Un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-180">A hyphen</span></span> 
- <span data-ttu-id="a199a-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-182">Checksum</span></span>

<span data-ttu-id="a199a-183">No</span><span class="sxs-lookup"><span data-stu-id="a199a-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-184">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-184">Definition</span></span>

<span data-ttu-id="a199a-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a199a-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="a199a-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="a199a-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a199a-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="a199a-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a199a-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="a199a-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="a199a-194">swift bank code</span></span>
- <span data-ttu-id="a199a-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="a199a-195">correspondent bank</span></span>
- <span data-ttu-id="a199a-196">base currency</span><span class="sxs-lookup"><span data-stu-id="a199a-196">base currency</span></span>
- <span data-ttu-id="a199a-197">usa account</span><span class="sxs-lookup"><span data-stu-id="a199a-197">usa account</span></span>
- <span data-ttu-id="a199a-198">holder address</span><span class="sxs-lookup"><span data-stu-id="a199a-198">holder address</span></span>
- <span data-ttu-id="a199a-199">bank address</span><span class="sxs-lookup"><span data-stu-id="a199a-199">bank address</span></span>
- <span data-ttu-id="a199a-200">information account</span><span class="sxs-lookup"><span data-stu-id="a199a-200">information account</span></span>
- <span data-ttu-id="a199a-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="a199a-201">fund transfers</span></span>
- <span data-ttu-id="a199a-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="a199a-202">bank charges</span></span>
- <span data-ttu-id="a199a-203">bank details</span><span class="sxs-lookup"><span data-stu-id="a199a-203">bank details</span></span>
- <span data-ttu-id="a199a-204">banking information</span><span class="sxs-lookup"><span data-stu-id="a199a-204">banking information</span></span>
- <span data-ttu-id="a199a-205">full names</span><span class="sxs-lookup"><span data-stu-id="a199a-205">full names</span></span>
- <span data-ttu-id="a199a-206">OIEA</span><span class="sxs-lookup"><span data-stu-id="a199a-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="a199a-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="a199a-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-208">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-208">Format</span></span>

<span data-ttu-id="a199a-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-210">Pattern</span></span>

<span data-ttu-id="a199a-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="a199a-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-213">Two digits</span></span> 
- <span data-ttu-id="a199a-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="a199a-215">O</span><span class="sxs-lookup"><span data-stu-id="a199a-215">OR</span></span>

- <span data-ttu-id="a199a-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-217">4-9 digits</span></span>

<span data-ttu-id="a199a-218">O</span><span class="sxs-lookup"><span data-stu-id="a199a-218">OR</span></span>

- <span data-ttu-id="a199a-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-220">Checksum</span></span>

<span data-ttu-id="a199a-221">No</span><span class="sxs-lookup"><span data-stu-id="a199a-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-222">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-222">Definition</span></span>

<span data-ttu-id="a199a-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="a199a-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="a199a-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="a199a-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a199a-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="a199a-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="a199a-229">international driving permits</span></span>
- <span data-ttu-id="a199a-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="a199a-230">australian automobile association</span></span>
- <span data-ttu-id="a199a-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="a199a-231">international driving permit</span></span>
- <span data-ttu-id="a199a-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a199a-232">DriverLicence</span></span>
- <span data-ttu-id="a199a-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a199a-233">DriverLicences</span></span>
- <span data-ttu-id="a199a-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-234">Driver Lic</span></span>
- <span data-ttu-id="a199a-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-235">Driver Licence</span></span>
- <span data-ttu-id="a199a-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-236">Driver Licences</span></span>
- <span data-ttu-id="a199a-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a199a-237">DriversLic</span></span>
- <span data-ttu-id="a199a-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a199a-238">DriversLicence</span></span>
- <span data-ttu-id="a199a-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a199a-239">DriversLicences</span></span>
- <span data-ttu-id="a199a-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-240">Drivers Lic</span></span>
- <span data-ttu-id="a199a-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-241">Drivers Lics</span></span>
- <span data-ttu-id="a199a-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-242">Drivers Licence</span></span>
- <span data-ttu-id="a199a-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-243">Drivers Licences</span></span>
- <span data-ttu-id="a199a-244">N.º carné</span><span class="sxs-lookup"><span data-stu-id="a199a-244">Driver'Lic</span></span>
- <span data-ttu-id="a199a-245">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="a199a-245">Driver'Lics</span></span>
- <span data-ttu-id="a199a-246">N.º carné</span><span class="sxs-lookup"><span data-stu-id="a199a-246">Driver'Licence</span></span>
- <span data-ttu-id="a199a-247">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="a199a-247">Driver'Licences</span></span>
- <span data-ttu-id="a199a-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-248">Driver' Lic</span></span>
- <span data-ttu-id="a199a-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-249">Driver' Lics</span></span>
- <span data-ttu-id="a199a-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-250">Driver' Licence</span></span>
- <span data-ttu-id="a199a-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-251">Driver' Licences</span></span>
- <span data-ttu-id="a199a-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a199a-252">Driver'sLic</span></span>
- <span data-ttu-id="a199a-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a199a-253">Driver'sLics</span></span>
- <span data-ttu-id="a199a-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a199a-254">Driver'sLicence</span></span>
- <span data-ttu-id="a199a-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a199a-255">Driver'sLicences</span></span>
- <span data-ttu-id="a199a-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-256">Driver's Lic</span></span>
- <span data-ttu-id="a199a-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-257">Driver's Lics</span></span>
- <span data-ttu-id="a199a-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-258">Driver's Licence</span></span>
- <span data-ttu-id="a199a-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-259">Driver's Licences</span></span>
- <span data-ttu-id="a199a-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-260">DriverLic#</span></span>
- <span data-ttu-id="a199a-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-261">DriverLics#</span></span>
- <span data-ttu-id="a199a-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="a199a-262">DriverLicence#</span></span>
- <span data-ttu-id="a199a-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a199a-263">DriverLicences#</span></span>
- <span data-ttu-id="a199a-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-264">Driver Lic#</span></span>
- <span data-ttu-id="a199a-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-265">Driver Lics#</span></span>
- <span data-ttu-id="a199a-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-266">Driver Licence#</span></span>
- <span data-ttu-id="a199a-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-267">Driver Licences#</span></span>
- <span data-ttu-id="a199a-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-268">DriversLic#</span></span>
- <span data-ttu-id="a199a-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-269">DriversLics#</span></span>
- <span data-ttu-id="a199a-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="a199a-270">DriversLicence#</span></span>
- <span data-ttu-id="a199a-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a199a-271">DriversLicences#</span></span>
- <span data-ttu-id="a199a-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-272">Drivers Lic#</span></span>
- <span data-ttu-id="a199a-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-273">Drivers Lics#</span></span>
- <span data-ttu-id="a199a-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-274">Drivers Licence#</span></span>
- <span data-ttu-id="a199a-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-275">Drivers Licences#</span></span>
- <span data-ttu-id="a199a-276">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="a199a-276">Driver'Lic#</span></span>
- <span data-ttu-id="a199a-277">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="a199a-277">Driver'Lics#</span></span>
- <span data-ttu-id="a199a-278">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="a199a-278">Driver'Licence#</span></span>
- <span data-ttu-id="a199a-279">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="a199a-279">Driver'Licences#</span></span>
- <span data-ttu-id="a199a-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-280">Driver' Lic#</span></span>
- <span data-ttu-id="a199a-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-281">Driver' Lics#</span></span>
- <span data-ttu-id="a199a-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-282">Driver' Licence#</span></span>
- <span data-ttu-id="a199a-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-283">Driver' Licences#</span></span>
- <span data-ttu-id="a199a-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-284">Driver'sLic#</span></span>
- <span data-ttu-id="a199a-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-285">Driver'sLics#</span></span>
- <span data-ttu-id="a199a-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="a199a-286">Driver'sLicence#</span></span>
- <span data-ttu-id="a199a-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a199a-287">Driver'sLicences#</span></span>
- <span data-ttu-id="a199a-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-288">Driver's Lic#</span></span>
- <span data-ttu-id="a199a-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-289">Driver's Lics#</span></span>
- <span data-ttu-id="a199a-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-290">Driver's Licence#</span></span>
- <span data-ttu-id="a199a-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="a199a-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a199a-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="a199a-293">aaaa</span><span class="sxs-lookup"><span data-stu-id="a199a-293">aaa</span></span>
- <span data-ttu-id="a199a-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-294">DriverLicense</span></span>
- <span data-ttu-id="a199a-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-295">DriverLicenses</span></span>
- <span data-ttu-id="a199a-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="a199a-296">Driver License</span></span>
- <span data-ttu-id="a199a-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-297">Driver Licenses</span></span>
- <span data-ttu-id="a199a-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-298">DriversLicense</span></span>
- <span data-ttu-id="a199a-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-299">DriversLicenses</span></span>
- <span data-ttu-id="a199a-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a199a-300">Drivers License</span></span>
- <span data-ttu-id="a199a-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-301">Drivers Licenses</span></span>
- <span data-ttu-id="a199a-302">Conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-302">Driver'License</span></span>
- <span data-ttu-id="a199a-303">Conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-303">Driver'Licenses</span></span>
- <span data-ttu-id="a199a-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="a199a-304">Driver' License</span></span>
- <span data-ttu-id="a199a-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-305">Driver' Licenses</span></span>
- <span data-ttu-id="a199a-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-306">Driver'sLicense</span></span>
- <span data-ttu-id="a199a-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-307">Driver'sLicenses</span></span>
- <span data-ttu-id="a199a-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a199a-308">Driver's License</span></span>
- <span data-ttu-id="a199a-309">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-309">Driver's Licenses</span></span>
- <span data-ttu-id="a199a-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-310">DriverLicense#</span></span>
- <span data-ttu-id="a199a-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-311">DriverLicenses#</span></span>
- <span data-ttu-id="a199a-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a199a-312">Driver License#</span></span>
- <span data-ttu-id="a199a-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-313">Driver Licenses#</span></span>
- <span data-ttu-id="a199a-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-314">DriversLicense#</span></span>
- <span data-ttu-id="a199a-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-315">DriversLicenses#</span></span>
- <span data-ttu-id="a199a-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="a199a-316">Drivers License#</span></span>
- <span data-ttu-id="a199a-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-317">Drivers Licenses#</span></span>
- <span data-ttu-id="a199a-318">Conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-318">Driver'License#</span></span>
- <span data-ttu-id="a199a-319">Conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-319">Driver'Licenses#</span></span>
- <span data-ttu-id="a199a-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="a199a-320">Driver' License#</span></span>
- <span data-ttu-id="a199a-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-321">Driver' Licenses#</span></span>
- <span data-ttu-id="a199a-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-322">Driver'sLicense#</span></span>
- <span data-ttu-id="a199a-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="a199a-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="a199a-324">Driver's License#</span></span>
- <span data-ttu-id="a199a-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="a199a-326">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="a199a-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-327">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-327">Format</span></span>

<span data-ttu-id="a199a-328">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-329">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-329">Pattern</span></span>

<span data-ttu-id="a199a-330">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-330">10-11 digits:</span></span>
- <span data-ttu-id="a199a-331">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="a199a-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="a199a-332">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="a199a-333">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="a199a-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="a199a-334">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="a199a-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-335">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-335">Checksum</span></span>

<span data-ttu-id="a199a-336">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-337">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-337">Definition</span></span>

<span data-ttu-id="a199a-338">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-339">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-340">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="a199a-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="a199a-341">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-341">The checksum passes.</span></span>

<span data-ttu-id="a199a-342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-343">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-344">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-345">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="a199a-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="a199a-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="a199a-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="a199a-347">bank account details</span></span>
- <span data-ttu-id="a199a-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="a199a-348">medicare payments</span></span>
- <span data-ttu-id="a199a-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="a199a-349">mortgage account</span></span>
- <span data-ttu-id="a199a-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="a199a-350">bank payments</span></span>
- <span data-ttu-id="a199a-351">information branch</span><span class="sxs-lookup"><span data-stu-id="a199a-351">information branch</span></span>
- <span data-ttu-id="a199a-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="a199a-352">credit card loan</span></span>
- <span data-ttu-id="a199a-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="a199a-353">department of human services</span></span>
- <span data-ttu-id="a199a-354">local service</span><span class="sxs-lookup"><span data-stu-id="a199a-354">local service</span></span>
- <span data-ttu-id="a199a-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="a199a-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="a199a-356">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="a199a-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-357">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-357">Format</span></span>

<span data-ttu-id="a199a-358">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-359">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-359">Pattern</span></span>

<span data-ttu-id="a199a-360">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-361">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-361">Checksum</span></span>

<span data-ttu-id="a199a-362">No</span><span class="sxs-lookup"><span data-stu-id="a199a-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-363">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-363">Definition</span></span>

<span data-ttu-id="a199a-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-365">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-366">Se encuentra una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="a199a-367">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a199a-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-368">Keyword_passport</span></span>

- <span data-ttu-id="a199a-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a199a-369">Passport Number</span></span>
- <span data-ttu-id="a199a-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="a199a-370">Passport No</span></span>
- <span data-ttu-id="a199a-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="a199a-371">Passport #</span></span>
- <span data-ttu-id="a199a-372">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="a199a-372">Passport#</span></span>
- <span data-ttu-id="a199a-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="a199a-373">PassportID</span></span>
- <span data-ttu-id="a199a-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="a199a-374">Passportno</span></span>
- <span data-ttu-id="a199a-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-375">passportnumber</span></span>
- <span data-ttu-id="a199a-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="a199a-376">パスポート</span></span>
- <span data-ttu-id="a199a-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a199a-377">パスポート番号</span></span>
- <span data-ttu-id="a199a-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a199a-378">パスポートのNum</span></span>
- <span data-ttu-id="a199a-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="a199a-379">パスポート ＃</span></span> 
- <span data-ttu-id="a199a-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a199a-380">Numéro de passeport</span></span>
- <span data-ttu-id="a199a-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a199a-381">Passeport n °</span></span>
- <span data-ttu-id="a199a-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a199a-382">Passeport Non</span></span>
- <span data-ttu-id="a199a-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-383">Passeport #</span></span>
- <span data-ttu-id="a199a-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-384">Passeport#</span></span>
- <span data-ttu-id="a199a-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a199a-385">PasseportNon</span></span>
- <span data-ttu-id="a199a-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a199a-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="a199a-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="a199a-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="a199a-388">usuarios</span><span class="sxs-lookup"><span data-stu-id="a199a-388">passport</span></span>
- <span data-ttu-id="a199a-389">passport details</span><span class="sxs-lookup"><span data-stu-id="a199a-389">passport details</span></span>
- <span data-ttu-id="a199a-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a199a-390">immigration and citizenship</span></span>
- <span data-ttu-id="a199a-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="a199a-391">commonwealth of australia</span></span>
- <span data-ttu-id="a199a-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="a199a-392">department of immigration</span></span>
- <span data-ttu-id="a199a-393">residential address</span><span class="sxs-lookup"><span data-stu-id="a199a-393">residential address</span></span>
- <span data-ttu-id="a199a-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a199a-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="a199a-395">régimen</span><span class="sxs-lookup"><span data-stu-id="a199a-395">visa</span></span>
- <span data-ttu-id="a199a-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="a199a-396">national identity card</span></span>
- <span data-ttu-id="a199a-397">passport number</span><span class="sxs-lookup"><span data-stu-id="a199a-397">passport number</span></span>
- <span data-ttu-id="a199a-398">travel document</span><span class="sxs-lookup"><span data-stu-id="a199a-398">travel document</span></span>
- <span data-ttu-id="a199a-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="a199a-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="a199a-400">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="a199a-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-401">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-401">Format</span></span>

<span data-ttu-id="a199a-402">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-403">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-403">Pattern</span></span>

<span data-ttu-id="a199a-404">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="a199a-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="a199a-405">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-405">Three digits</span></span> 
- <span data-ttu-id="a199a-406">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="a199a-406">An optional space</span></span> 
- <span data-ttu-id="a199a-407">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-407">Three digits</span></span> 
- <span data-ttu-id="a199a-408">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="a199a-408">An optional space</span></span> 
- <span data-ttu-id="a199a-409">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-410">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-410">Checksum</span></span>

<span data-ttu-id="a199a-411">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-412">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-412">Definition</span></span>

<span data-ttu-id="a199a-413">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-414">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-415">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="a199a-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="a199a-416">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="a199a-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="a199a-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="a199a-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="a199a-419">australian business number</span></span>
- <span data-ttu-id="a199a-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="a199a-420">marginal tax rate</span></span>
- <span data-ttu-id="a199a-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="a199a-421">medicare levy</span></span>
- <span data-ttu-id="a199a-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="a199a-422">portfolio number</span></span>
- <span data-ttu-id="a199a-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="a199a-423">service veterans</span></span>
- <span data-ttu-id="a199a-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="a199a-424">withholding tax</span></span>
- <span data-ttu-id="a199a-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="a199a-425">individual tax return</span></span>
- <span data-ttu-id="a199a-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="a199a-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="a199a-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a199a-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="a199a-428">00000000</span><span class="sxs-lookup"><span data-stu-id="a199a-428">00000000</span></span>
- <span data-ttu-id="a199a-429">11111111</span><span class="sxs-lookup"><span data-stu-id="a199a-429">11111111</span></span>
- <span data-ttu-id="a199a-430">22222222</span><span class="sxs-lookup"><span data-stu-id="a199a-430">22222222</span></span>
- <span data-ttu-id="a199a-431">33333333</span><span class="sxs-lookup"><span data-stu-id="a199a-431">33333333</span></span>
- <span data-ttu-id="a199a-432">44444444</span><span class="sxs-lookup"><span data-stu-id="a199a-432">44444444</span></span>
- <span data-ttu-id="a199a-433">55555555</span><span class="sxs-lookup"><span data-stu-id="a199a-433">55555555</span></span>
- <span data-ttu-id="a199a-434">66666666</span><span class="sxs-lookup"><span data-stu-id="a199a-434">66666666</span></span>
- <span data-ttu-id="a199a-435">77777777</span><span class="sxs-lookup"><span data-stu-id="a199a-435">77777777</span></span>
- <span data-ttu-id="a199a-436">88888888</span><span class="sxs-lookup"><span data-stu-id="a199a-436">88888888</span></span>
- <span data-ttu-id="a199a-437">99999999</span><span class="sxs-lookup"><span data-stu-id="a199a-437">99999999</span></span>
- <span data-ttu-id="a199a-438">000000000</span><span class="sxs-lookup"><span data-stu-id="a199a-438">000000000</span></span>
- <span data-ttu-id="a199a-439">111111111</span><span class="sxs-lookup"><span data-stu-id="a199a-439">111111111</span></span>
- <span data-ttu-id="a199a-440">222222222</span><span class="sxs-lookup"><span data-stu-id="a199a-440">222222222</span></span>
- <span data-ttu-id="a199a-441">333333333</span><span class="sxs-lookup"><span data-stu-id="a199a-441">333333333</span></span>
- <span data-ttu-id="a199a-442">444444444</span><span class="sxs-lookup"><span data-stu-id="a199a-442">444444444</span></span>
- <span data-ttu-id="a199a-443">555555555</span><span class="sxs-lookup"><span data-stu-id="a199a-443">555555555</span></span>
- <span data-ttu-id="a199a-444">666666666</span><span class="sxs-lookup"><span data-stu-id="a199a-444">666666666</span></span>
- <span data-ttu-id="a199a-445">777777777</span><span class="sxs-lookup"><span data-stu-id="a199a-445">777777777</span></span>
- <span data-ttu-id="a199a-446">888888888</span><span class="sxs-lookup"><span data-stu-id="a199a-446">888888888</span></span>
- <span data-ttu-id="a199a-447">999999999</span><span class="sxs-lookup"><span data-stu-id="a199a-447">999999999</span></span>
- <span data-ttu-id="a199a-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="a199a-448">0000000000</span></span>
- <span data-ttu-id="a199a-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="a199a-449">1111111111</span></span>
- <span data-ttu-id="a199a-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="a199a-450">2222222222</span></span>
- <span data-ttu-id="a199a-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="a199a-451">3333333333</span></span>
- <span data-ttu-id="a199a-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="a199a-452">4444444444</span></span>
- <span data-ttu-id="a199a-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="a199a-453">5555555555</span></span>
- <span data-ttu-id="a199a-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="a199a-454">6666666666</span></span>
- <span data-ttu-id="a199a-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="a199a-455">7777777777</span></span>
- <span data-ttu-id="a199a-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="a199a-456">8888888888</span></span>
- <span data-ttu-id="a199a-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="a199a-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="a199a-458">Clave de autenticación de Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="a199a-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="a199a-459">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-459">Format</span></span>

<span data-ttu-id="a199a-460">La cadena "DocumentDb" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="a199a-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-461">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-461">Pattern</span></span>

- <span data-ttu-id="a199a-462">La cadena "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="a199a-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="a199a-463">Cualquier combinación de entre 3-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-464">Un símbolo mayor que (>), un signo igual (=), una comilla (") o un apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="a199a-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="a199a-465">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="a199a-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a199a-466">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-467">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-467">Checksum</span></span>

<span data-ttu-id="a199a-468">No</span><span class="sxs-lookup"><span data-stu-id="a199a-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-469">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-469">Definition</span></span>

<span data-ttu-id="a199a-470">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-471">La expresión regular CEP_Regex_AzureDocumentDBAuthKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-472">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-473">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-475">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-476">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-476">contoso</span></span>
- <span data-ttu-id="a199a-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-477">fabrikam</span></span>
- <span data-ttu-id="a199a-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-478">northwind</span></span>
- <span data-ttu-id="a199a-479">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-479">sandbox</span></span>
- <span data-ttu-id="a199a-480">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-480">onebox</span></span>
- <span data-ttu-id="a199a-481">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-481">localhost</span></span>
- <span data-ttu-id="a199a-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-482">127.0.0.1</span></span>
- <span data-ttu-id="a199a-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-484">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-484">com</span></span>
- <span data-ttu-id="a199a-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-486">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="a199a-487">Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL de Azure</span><span class="sxs-lookup"><span data-stu-id="a199a-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a199a-488">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-488">Format</span></span>

<span data-ttu-id="a199a-489">La cadena "Server", "Server" o "Data Source" seguida de los caracteres y las cadenas que se describen en el siguiente patrón, incluida la cadena "CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a199a-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-490">com "o" CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a199a-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-491">net "o" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="a199a-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-492">net "y la cadena" Password "o" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="a199a-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-493">Pattern</span></span>

- <span data-ttu-id="a199a-494">La cadena "servidor", "servidor" o "origen de datos"</span><span class="sxs-lookup"><span data-stu-id="a199a-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="a199a-495">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-496">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-496">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-497">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-498">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-499">La cadena "CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a199a-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-500">com "," CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a199a-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-501">net "o" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="a199a-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-502">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-502">net"</span></span>
- <span data-ttu-id="a199a-503">Cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-504">La cadena "Password", "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="a199a-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="a199a-505">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-506">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-506">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-507">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-508">Uno o más caracteres que no son un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="a199a-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="a199a-509">Un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="a199a-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-510">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-510">Checksum</span></span>

<span data-ttu-id="a199a-511">No</span><span class="sxs-lookup"><span data-stu-id="a199a-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-512">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-512">Definition</span></span>

<span data-ttu-id="a199a-513">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-514">La expresión regular CEP_Regex_AzureConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-515">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-516">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-518">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-519">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-519">contoso</span></span>
- <span data-ttu-id="a199a-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-520">fabrikam</span></span>
- <span data-ttu-id="a199a-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-521">northwind</span></span>
- <span data-ttu-id="a199a-522">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-522">sandbox</span></span>
- <span data-ttu-id="a199a-523">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-523">onebox</span></span>
- <span data-ttu-id="a199a-524">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-524">localhost</span></span>
- <span data-ttu-id="a199a-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-525">127.0.0.1</span></span>
- <span data-ttu-id="a199a-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-527">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-527">com</span></span>
- <span data-ttu-id="a199a-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-529">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="a199a-530">Cadena de conexión de Azure IoT</span><span class="sxs-lookup"><span data-stu-id="a199a-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a199a-531">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-531">Format</span></span>

<span data-ttu-id="a199a-532">La cadena "HostName" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="a199a-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-533">net "y" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="a199a-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-534">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-534">Pattern</span></span>

- <span data-ttu-id="a199a-535">La cadena "HostName"</span><span class="sxs-lookup"><span data-stu-id="a199a-535">The string "HostName"</span></span>
- <span data-ttu-id="a199a-536">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-537">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-537">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-538">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-539">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-540">La cadena "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="a199a-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-541">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-541">net"</span></span>
- <span data-ttu-id="a199a-542">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-543">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="a199a-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="a199a-544">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-545">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-545">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-546">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-547">Cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="a199a-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a199a-548">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-549">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-549">Checksum</span></span>

<span data-ttu-id="a199a-550">No</span><span class="sxs-lookup"><span data-stu-id="a199a-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-551">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-551">Definition</span></span>

<span data-ttu-id="a199a-552">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-553">La expresión regular CEP_Regex_AzureIoTConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-554">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-555">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-557">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-558">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-558">contoso</span></span>
- <span data-ttu-id="a199a-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-559">fabrikam</span></span>
- <span data-ttu-id="a199a-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-560">northwind</span></span>
- <span data-ttu-id="a199a-561">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-561">sandbox</span></span>
- <span data-ttu-id="a199a-562">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-562">onebox</span></span>
- <span data-ttu-id="a199a-563">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-563">localhost</span></span>
- <span data-ttu-id="a199a-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-564">127.0.0.1</span></span>
- <span data-ttu-id="a199a-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-566">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-566">com</span></span>
- <span data-ttu-id="a199a-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-568">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="a199a-569">Contraseña de configuración de publicación de Azure</span><span class="sxs-lookup"><span data-stu-id="a199a-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="a199a-570">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-570">Format</span></span>

<span data-ttu-id="a199a-571">La cadena "userpwd =" seguida de una cadena alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="a199a-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-572">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-572">Pattern</span></span>

- <span data-ttu-id="a199a-573">La cadena "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="a199a-573">The string "userpwd="</span></span>
- <span data-ttu-id="a199a-574">Cualquier combinación de 60 letras minúsculas o dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="a199a-575">Un signo de Comillas (")</span><span class="sxs-lookup"><span data-stu-id="a199a-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-576">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-576">Checksum</span></span>

<span data-ttu-id="a199a-577">No</span><span class="sxs-lookup"><span data-stu-id="a199a-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-578">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-578">Definition</span></span>

<span data-ttu-id="a199a-579">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-580">La expresión regular CEP_Regex_AzurePublishSettingPasswords encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-581">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-582">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-584">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-585">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-585">contoso</span></span>
- <span data-ttu-id="a199a-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-586">fabrikam</span></span>
- <span data-ttu-id="a199a-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-587">northwind</span></span>
- <span data-ttu-id="a199a-588">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-588">sandbox</span></span>
- <span data-ttu-id="a199a-589">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-589">onebox</span></span>
- <span data-ttu-id="a199a-590">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-590">localhost</span></span>
- <span data-ttu-id="a199a-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-591">127.0.0.1</span></span>
- <span data-ttu-id="a199a-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-593">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-593">com</span></span>
- <span data-ttu-id="a199a-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-595">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="a199a-596">Cadena de conexión de la caché de Redis de Azure</span><span class="sxs-lookup"><span data-stu-id="a199a-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a199a-597">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-597">Format</span></span>

<span data-ttu-id="a199a-598">La cadena "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="a199a-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-599">net "seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="a199a-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-600">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-600">Pattern</span></span>

- <span data-ttu-id="a199a-601">La cadena "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="a199a-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-602">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-602">net"</span></span>
- <span data-ttu-id="a199a-603">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-604">La cadena "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="a199a-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="a199a-605">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-606">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-606">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-607">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-608">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="a199a-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a199a-609">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-610">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-610">Checksum</span></span>

<span data-ttu-id="a199a-611">No</span><span class="sxs-lookup"><span data-stu-id="a199a-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-612">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-612">Definition</span></span>

<span data-ttu-id="a199a-613">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-614">La expresión regular CEP_Regex_AzureRedisCacheConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="a199a-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="a199a-615">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-616">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-618">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-619">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-619">contoso</span></span>
- <span data-ttu-id="a199a-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-620">fabrikam</span></span>
- <span data-ttu-id="a199a-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-621">northwind</span></span>
- <span data-ttu-id="a199a-622">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-622">sandbox</span></span>
- <span data-ttu-id="a199a-623">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-623">onebox</span></span>
- <span data-ttu-id="a199a-624">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-624">localhost</span></span>
- <span data-ttu-id="a199a-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-625">127.0.0.1</span></span>
- <span data-ttu-id="a199a-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-627">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-627">com</span></span>
- <span data-ttu-id="a199a-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-629">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="a199a-630">ASOCIACIONES de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a199a-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="a199a-631">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-631">Format</span></span>

<span data-ttu-id="a199a-632">La cadena "SIG" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="a199a-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-633">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-633">Pattern</span></span>

- <span data-ttu-id="a199a-634">La cadena "SIG"</span><span class="sxs-lookup"><span data-stu-id="a199a-634">The string "sig"</span></span>
- <span data-ttu-id="a199a-635">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-636">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-636">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-637">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-638">Cualquier combinación de entre 43-53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="a199a-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="a199a-639">La cadena "% 3D"</span><span class="sxs-lookup"><span data-stu-id="a199a-639">The string "%3d"</span></span>
- <span data-ttu-id="a199a-640">Cualquier carácter que no sea una letra minúscula o mayúscula, un dígito o un signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="a199a-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-641">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-641">Checksum</span></span>

<span data-ttu-id="a199a-642">No</span><span class="sxs-lookup"><span data-stu-id="a199a-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-643">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-643">Definition</span></span>

<span data-ttu-id="a199a-644">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-645">La expresión regular CEP_Regex_AzureSAS encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="a199a-646">Cadena de conexión del bus de servicio de Azure</span><span class="sxs-lookup"><span data-stu-id="a199a-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a199a-647">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-647">Format</span></span>

<span data-ttu-id="a199a-648">La cadena "EndPoint" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="a199a-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-649">net "y" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="a199a-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-650">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-650">Pattern</span></span>

- <span data-ttu-id="a199a-651">La cadena "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="a199a-651">The string "EndPoint"</span></span>
- <span data-ttu-id="a199a-652">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-653">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-653">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-654">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-655">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-656">La cadena "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="a199a-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-657">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-657">net"</span></span>
- <span data-ttu-id="a199a-658">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-659">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="a199a-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="a199a-660">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-661">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-661">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-662">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-663">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="a199a-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a199a-664">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-665">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-665">Checksum</span></span>

<span data-ttu-id="a199a-666">No</span><span class="sxs-lookup"><span data-stu-id="a199a-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-667">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-667">Definition</span></span>

<span data-ttu-id="a199a-668">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-669">La expresión regular CEP_Regex_AzureServiceBusConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="a199a-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="a199a-670">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-671">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-673">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-674">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-674">contoso</span></span>
- <span data-ttu-id="a199a-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-675">fabrikam</span></span>
- <span data-ttu-id="a199a-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-676">northwind</span></span>
- <span data-ttu-id="a199a-677">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-677">sandbox</span></span>
- <span data-ttu-id="a199a-678">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-678">onebox</span></span>
- <span data-ttu-id="a199a-679">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-679">localhost</span></span>
- <span data-ttu-id="a199a-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-680">127.0.0.1</span></span>
- <span data-ttu-id="a199a-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-682">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-682">com</span></span>
- <span data-ttu-id="a199a-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-684">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="a199a-685">Clave de cuenta de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="a199a-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="a199a-686">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-686">Format</span></span>

<span data-ttu-id="a199a-687">La cadena "DefaultEndpointsProtocol" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="a199a-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-688">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-688">Pattern</span></span>

- <span data-ttu-id="a199a-689">La cadena "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="a199a-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="a199a-690">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-691">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-691">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-692">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-693">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-694">La cadena "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="a199a-694">The string "AccountKey"</span></span>
- <span data-ttu-id="a199a-695">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-696">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-696">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-697">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="a199a-698">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="a199a-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a199a-699">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-700">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-700">Checksum</span></span>

<span data-ttu-id="a199a-701">No</span><span class="sxs-lookup"><span data-stu-id="a199a-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-702">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-702">Definition</span></span>

<span data-ttu-id="a199a-703">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-704">La expresión regular CEP_Regex_AzureStorageAccountKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-705">La expresión regular CEP_AzureEmulatorStorageAccountFilter no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-706">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-707">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="a199a-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="a199a-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="a199a-709">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="a199a-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-712">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-713">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-713">contoso</span></span>
- <span data-ttu-id="a199a-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-714">fabrikam</span></span>
- <span data-ttu-id="a199a-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-715">northwind</span></span>
- <span data-ttu-id="a199a-716">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-716">sandbox</span></span>
- <span data-ttu-id="a199a-717">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-717">onebox</span></span>
- <span data-ttu-id="a199a-718">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-718">localhost</span></span>
- <span data-ttu-id="a199a-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-719">127.0.0.1</span></span>
- <span data-ttu-id="a199a-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-721">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-721">com</span></span>
- <span data-ttu-id="a199a-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-723">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="a199a-724">Clave de cuenta de almacenamiento de Azure (Genérico)</span><span class="sxs-lookup"><span data-stu-id="a199a-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-725">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-725">Format</span></span>

<span data-ttu-id="a199a-726">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+), precedido o seguido por los caracteres descritos en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="a199a-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-727">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-727">Pattern</span></span>

- <span data-ttu-id="a199a-728">0-1 del símbolo mayor que (>), apóstrofe ('), signo de igual (=), Comillas (") o almohadilla (#)</span><span class="sxs-lookup"><span data-stu-id="a199a-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="a199a-729">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+)</span><span class="sxs-lookup"><span data-stu-id="a199a-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a199a-730">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="a199a-731">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-731">Checksum</span></span>

<span data-ttu-id="a199a-732">No</span><span class="sxs-lookup"><span data-stu-id="a199a-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-733">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-733">Definition</span></span>

<span data-ttu-id="a199a-734">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-735">La expresión regular CEP_Regex_AzureStorageAccountKeyGeneric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="a199a-736">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="a199a-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-737">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-737">Format</span></span>

<span data-ttu-id="a199a-738">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="a199a-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-739">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-739">Pattern</span></span>

<span data-ttu-id="a199a-740">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="a199a-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="a199a-741">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="a199a-742">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-742">A hyphen</span></span> 
- <span data-ttu-id="a199a-743">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="a199a-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="a199a-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="a199a-744">A period</span></span> 
- <span data-ttu-id="a199a-745">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-746">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-746">Checksum</span></span>

<span data-ttu-id="a199a-747">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-748">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-748">Definition</span></span>

<span data-ttu-id="a199a-749">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-750">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-751">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="a199a-752">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-753">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="a199a-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="a199a-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="a199a-755">Identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-755">Identity</span></span>
- <span data-ttu-id="a199a-756">Registro</span><span class="sxs-lookup"><span data-stu-id="a199a-756">Registration</span></span>
- <span data-ttu-id="a199a-757">Determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-757">Identification</span></span> 
- <span data-ttu-id="a199a-758">ID</span><span class="sxs-lookup"><span data-stu-id="a199a-758">ID</span></span> 
- <span data-ttu-id="a199a-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a199a-759">Identiteitskaart</span></span>
- <span data-ttu-id="a199a-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="a199a-760">Registratie nummer</span></span> 
- <span data-ttu-id="a199a-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="a199a-761">Identificatie nummer</span></span> 
- <span data-ttu-id="a199a-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="a199a-762">Identiteit</span></span>
- <span data-ttu-id="a199a-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="a199a-763">Registratie</span></span>
- <span data-ttu-id="a199a-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="a199a-764">Identificatie</span></span> 
- <span data-ttu-id="a199a-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="a199a-765">Carte d’identité</span></span> 
- <span data-ttu-id="a199a-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="a199a-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="a199a-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="a199a-767">numéro d'identification</span></span>
- <span data-ttu-id="a199a-768">identité</span><span class="sxs-lookup"><span data-stu-id="a199a-768">identité</span></span> 
- <span data-ttu-id="a199a-769">indicación</span><span class="sxs-lookup"><span data-stu-id="a199a-769">inscription</span></span> 
- <span data-ttu-id="a199a-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a199a-770">Identifikation</span></span>
- <span data-ttu-id="a199a-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="a199a-771">Identifizierung</span></span>
- <span data-ttu-id="a199a-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-772">Identifikationsnummer</span></span>
- <span data-ttu-id="a199a-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a199a-773">Personalausweis</span></span>
- <span data-ttu-id="a199a-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="a199a-774">Registrierung</span></span>
- <span data-ttu-id="a199a-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="a199a-776">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="a199a-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-777">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-777">Format</span></span>

<span data-ttu-id="a199a-778">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="a199a-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-779">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-779">Pattern</span></span>

<span data-ttu-id="a199a-780">Con formato</span><span class="sxs-lookup"><span data-stu-id="a199a-780">Formatted:</span></span>
- <span data-ttu-id="a199a-781">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-781">Three digits</span></span> 
- <span data-ttu-id="a199a-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-782">A period</span></span> 
- <span data-ttu-id="a199a-783">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-783">Three digits</span></span> 
- <span data-ttu-id="a199a-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-784">A period</span></span> 
- <span data-ttu-id="a199a-785">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-785">Three digits</span></span> 
- <span data-ttu-id="a199a-786">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-786">A hyphen</span></span> 
- <span data-ttu-id="a199a-787">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="a199a-787">Two digits which are check digits</span></span>

<span data-ttu-id="a199a-788">Sin formato</span><span class="sxs-lookup"><span data-stu-id="a199a-788">Unformatted:</span></span>
- <span data-ttu-id="a199a-789">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="a199a-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-790">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-790">Checksum</span></span>

<span data-ttu-id="a199a-791">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-792">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-792">Definition</span></span>

<span data-ttu-id="a199a-793">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-794">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-795">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="a199a-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="a199a-796">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-796">The checksum passes.</span></span>

<span data-ttu-id="a199a-797">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-798">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-799">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-800">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="a199a-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="a199a-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="a199a-802">CPF</span><span class="sxs-lookup"><span data-stu-id="a199a-802">CPF</span></span>
- <span data-ttu-id="a199a-803">Determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-803">Identification</span></span>
- <span data-ttu-id="a199a-804">Registro</span><span class="sxs-lookup"><span data-stu-id="a199a-804">Registration</span></span>
- <span data-ttu-id="a199a-805">Generar</span><span class="sxs-lookup"><span data-stu-id="a199a-805">Revenue</span></span>
- <span data-ttu-id="a199a-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="a199a-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="a199a-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="a199a-807">Imposto</span></span> 
- <span data-ttu-id="a199a-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="a199a-808">Identificação</span></span> 
- <span data-ttu-id="a199a-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="a199a-809">Inscrição</span></span> 
- <span data-ttu-id="a199a-810">Receita</span><span class="sxs-lookup"><span data-stu-id="a199a-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="a199a-811">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a199a-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-812">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-812">Format</span></span>

<span data-ttu-id="a199a-813">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="a199a-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-814">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-814">Pattern</span></span>
<span data-ttu-id="a199a-815">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="a199a-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="a199a-816">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-816">Two digits</span></span> 
- <span data-ttu-id="a199a-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-817">A period</span></span> 
- <span data-ttu-id="a199a-818">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-818">Three digits</span></span> 
- <span data-ttu-id="a199a-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-819">A period</span></span> 
- <span data-ttu-id="a199a-820">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="a199a-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="a199a-821">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="a199a-821">A forward slash</span></span> 
- <span data-ttu-id="a199a-822">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-822">Four-digit branch number</span></span> 
- <span data-ttu-id="a199a-823">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-823">A hyphen</span></span> 
- <span data-ttu-id="a199a-824">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="a199a-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-825">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-825">Checksum</span></span>

<span data-ttu-id="a199a-826">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-827">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-827">Definition</span></span>

<span data-ttu-id="a199a-828">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-829">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-830">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="a199a-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="a199a-831">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-831">The checksum passes.</span></span>

<span data-ttu-id="a199a-832">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-833">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-834">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-835">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="a199a-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="a199a-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="a199a-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="a199a-837">CNPJ</span></span> 
- <span data-ttu-id="a199a-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="a199a-838">CNPJ/MF</span></span> 
- <span data-ttu-id="a199a-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="a199a-839">CNPJ-MF</span></span> 
- <span data-ttu-id="a199a-840">Registro nacional de entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="a199a-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="a199a-841">Registro de contribuyentes</span><span class="sxs-lookup"><span data-stu-id="a199a-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="a199a-842">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="a199a-842">Legal entity</span></span> 
- <span data-ttu-id="a199a-843">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="a199a-843">Legal entities</span></span> 
- <span data-ttu-id="a199a-844">Estado de registro</span><span class="sxs-lookup"><span data-stu-id="a199a-844">Registration Status</span></span> 
- <span data-ttu-id="a199a-845">Empresa</span><span class="sxs-lookup"><span data-stu-id="a199a-845">Business</span></span> 
- <span data-ttu-id="a199a-846">Company</span><span class="sxs-lookup"><span data-stu-id="a199a-846">Company</span></span>
- <span data-ttu-id="a199a-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="a199a-847">CNPJ</span></span> 
- <span data-ttu-id="a199a-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="a199a-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="a199a-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="a199a-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="a199a-850">CGC</span><span class="sxs-lookup"><span data-stu-id="a199a-850">CGC</span></span> 
- <span data-ttu-id="a199a-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="a199a-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="a199a-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="a199a-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="a199a-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="a199a-853">Situação cadastral</span></span> 
- <span data-ttu-id="a199a-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="a199a-854">Inscrição</span></span> 
- <span data-ttu-id="a199a-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="a199a-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="a199a-856">	Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="a199a-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-857">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-857">Format</span></span>

<span data-ttu-id="a199a-858">Registro geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="a199a-859">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-860">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-860">Pattern</span></span>

<span data-ttu-id="a199a-861">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="a199a-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="a199a-862">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-862">Two digits</span></span> 
- <span data-ttu-id="a199a-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-863">A period</span></span> 
- <span data-ttu-id="a199a-864">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-864">Three digits</span></span> 
- <span data-ttu-id="a199a-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-865">A period</span></span> 
- <span data-ttu-id="a199a-866">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-866">Three digits</span></span> 
- <span data-ttu-id="a199a-867">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-867">A hyphen</span></span> 
- <span data-ttu-id="a199a-868">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-868">One digit which is a check digit</span></span>

<span data-ttu-id="a199a-869">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="a199a-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="a199a-870">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-870">10 digits</span></span> 
- <span data-ttu-id="a199a-871">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-871">A hyphen</span></span> 
- <span data-ttu-id="a199a-872">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-873">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-873">Checksum</span></span>

<span data-ttu-id="a199a-874">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-875">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-875">Definition</span></span>

<span data-ttu-id="a199a-876">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-877">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-878">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="a199a-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="a199a-879">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-879">The checksum passes.</span></span>

<span data-ttu-id="a199a-880">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-881">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-882">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-883">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="a199a-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="a199a-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="a199a-885">Cédula de Identidade identidad nacional identificador número de rregistro registro de Iidentidade registro Geral RG (esta palabra clave distingue entre mayúsculas y minúsculas) RIC (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="a199a-886">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="a199a-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-887">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-887">Format</span></span>

<span data-ttu-id="a199a-888">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-889">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-889">Pattern</span></span>

<span data-ttu-id="a199a-890">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="a199a-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="a199a-891">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="a199a-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="a199a-892">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-892">Five digits</span></span> 
- <span data-ttu-id="a199a-893">Un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-893">A hyphen</span></span> 
- <span data-ttu-id="a199a-894">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="a199a-894">Three digits OR</span></span>
- <span data-ttu-id="a199a-895">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="a199a-895">A zero "0"</span></span> 
- <span data-ttu-id="a199a-896">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-897">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-897">Checksum</span></span>

<span data-ttu-id="a199a-898">No</span><span class="sxs-lookup"><span data-stu-id="a199a-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-899">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-899">Definition</span></span>

<span data-ttu-id="a199a-900">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-901">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-902">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="a199a-903">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="a199a-904">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-905">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-906">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-907">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="a199a-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a199a-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="a199a-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="a199a-909">canada savings bonds</span></span>
- <span data-ttu-id="a199a-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="a199a-910">canada revenue agency</span></span>
- <span data-ttu-id="a199a-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="a199a-911">canadian financial institution</span></span>
- <span data-ttu-id="a199a-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="a199a-912">direct deposit form</span></span>
- <span data-ttu-id="a199a-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="a199a-913">canadian citizen</span></span>
- <span data-ttu-id="a199a-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="a199a-914">legal representative</span></span>
- <span data-ttu-id="a199a-915">notary public</span><span class="sxs-lookup"><span data-stu-id="a199a-915">notary public</span></span>
- <span data-ttu-id="a199a-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="a199a-916">commissioner for oaths</span></span>
- <span data-ttu-id="a199a-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="a199a-917">child care benefit</span></span>
- <span data-ttu-id="a199a-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="a199a-918">universal child care</span></span>
- <span data-ttu-id="a199a-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a199a-919">canada child tax benefit</span></span>
- <span data-ttu-id="a199a-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="a199a-920">income tax benefit</span></span>
- <span data-ttu-id="a199a-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="a199a-921">harmonized sales tax</span></span>
- <span data-ttu-id="a199a-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a199a-922">social insurance number</span></span>
- <span data-ttu-id="a199a-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="a199a-923">income tax refund</span></span>
- <span data-ttu-id="a199a-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a199a-924">child tax benefit</span></span>
- <span data-ttu-id="a199a-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="a199a-925">territorial payments</span></span>
- <span data-ttu-id="a199a-926">institution number</span><span class="sxs-lookup"><span data-stu-id="a199a-926">institution number</span></span>
- <span data-ttu-id="a199a-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="a199a-927">deposit request</span></span>
- <span data-ttu-id="a199a-928">banking information</span><span class="sxs-lookup"><span data-stu-id="a199a-928">banking information</span></span>
- <span data-ttu-id="a199a-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="a199a-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="a199a-930">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="a199a-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-931">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-931">Format</span></span>

<span data-ttu-id="a199a-932">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="a199a-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-933">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-933">Pattern</span></span>

<span data-ttu-id="a199a-934">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="a199a-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-935">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-935">Checksum</span></span>

<span data-ttu-id="a199a-936">No</span><span class="sxs-lookup"><span data-stu-id="a199a-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-937">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-937">Definition</span></span>

<span data-ttu-id="a199a-938">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-939">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-940">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="a199a-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a199a-941">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="a199a-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-942">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="a199a-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a199a-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="a199a-944">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="a199a-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="a199a-945">El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="a199a-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="a199a-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a199a-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="a199a-947">LISTAS</span><span class="sxs-lookup"><span data-stu-id="a199a-947">DL</span></span>
- <span data-ttu-id="a199a-948">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="a199a-948">DLS</span></span>
- <span data-ttu-id="a199a-949">CDL</span><span class="sxs-lookup"><span data-stu-id="a199a-949">CDL</span></span>
- <span data-ttu-id="a199a-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="a199a-950">CDLS</span></span>
- <span data-ttu-id="a199a-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a199a-951">DriverLic</span></span>
- <span data-ttu-id="a199a-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a199a-952">DriverLics</span></span>
- <span data-ttu-id="a199a-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-953">DriverLicense</span></span>
- <span data-ttu-id="a199a-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-954">DriverLicenses</span></span>
- <span data-ttu-id="a199a-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a199a-955">DriverLicence</span></span>
- <span data-ttu-id="a199a-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a199a-956">DriverLicences</span></span>
- <span data-ttu-id="a199a-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-957">Driver Lic</span></span>
- <span data-ttu-id="a199a-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-958">Driver Lics</span></span>
- <span data-ttu-id="a199a-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="a199a-959">Driver License</span></span>
- <span data-ttu-id="a199a-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-960">Driver Licenses</span></span>
- <span data-ttu-id="a199a-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-961">Driver Licence</span></span>
- <span data-ttu-id="a199a-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-962">Driver Licences</span></span>
- <span data-ttu-id="a199a-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a199a-963">DriversLic</span></span>
- <span data-ttu-id="a199a-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a199a-964">DriversLics</span></span>
- <span data-ttu-id="a199a-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a199a-965">DriversLicence</span></span>
- <span data-ttu-id="a199a-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a199a-966">DriversLicences</span></span>
- <span data-ttu-id="a199a-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-967">DriversLicense</span></span>
- <span data-ttu-id="a199a-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-968">DriversLicenses</span></span>
- <span data-ttu-id="a199a-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-969">Drivers Lic</span></span>
- <span data-ttu-id="a199a-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-970">Drivers Lics</span></span>
- <span data-ttu-id="a199a-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a199a-971">Drivers License</span></span>
- <span data-ttu-id="a199a-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-972">Drivers Licenses</span></span>
- <span data-ttu-id="a199a-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-973">Drivers Licence</span></span>
- <span data-ttu-id="a199a-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-974">Drivers Licences</span></span>
- <span data-ttu-id="a199a-975">N.º carné</span><span class="sxs-lookup"><span data-stu-id="a199a-975">Driver'Lic</span></span>
- <span data-ttu-id="a199a-976">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="a199a-976">Driver'Lics</span></span>
- <span data-ttu-id="a199a-977">Conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-977">Driver'License</span></span>
- <span data-ttu-id="a199a-978">Conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-978">Driver'Licenses</span></span>
- <span data-ttu-id="a199a-979">N.º carné</span><span class="sxs-lookup"><span data-stu-id="a199a-979">Driver'Licence</span></span>
- <span data-ttu-id="a199a-980">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="a199a-980">Driver'Licences</span></span>
- <span data-ttu-id="a199a-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-981">Driver' Lic</span></span>
- <span data-ttu-id="a199a-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-982">Driver' Lics</span></span>
- <span data-ttu-id="a199a-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="a199a-983">Driver' License</span></span>
- <span data-ttu-id="a199a-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-984">Driver' Licenses</span></span>
- <span data-ttu-id="a199a-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-985">Driver' Licence</span></span>
- <span data-ttu-id="a199a-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-986">Driver' Licences</span></span>
- <span data-ttu-id="a199a-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a199a-987">Driver'sLic</span></span>
- <span data-ttu-id="a199a-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a199a-988">Driver'sLics</span></span>
- <span data-ttu-id="a199a-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-989">Driver'sLicense</span></span>
- <span data-ttu-id="a199a-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-990">Driver'sLicenses</span></span>
- <span data-ttu-id="a199a-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a199a-991">Driver'sLicence</span></span>
- <span data-ttu-id="a199a-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a199a-992">Driver'sLicences</span></span>
- <span data-ttu-id="a199a-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-993">Driver's Lic</span></span>
- <span data-ttu-id="a199a-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-994">Driver's Lics</span></span>
- <span data-ttu-id="a199a-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a199a-995">Driver's License</span></span>
- <span data-ttu-id="a199a-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-996">Driver's Licenses</span></span>
- <span data-ttu-id="a199a-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-997">Driver's Licence</span></span>
- <span data-ttu-id="a199a-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-998">Driver's Licences</span></span>
- <span data-ttu-id="a199a-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="a199a-999">Permis de Conduire</span></span>
- <span data-ttu-id="a199a-1000">id</span><span class="sxs-lookup"><span data-stu-id="a199a-1000">id</span></span>
- <span data-ttu-id="a199a-1001">ids</span><span class="sxs-lookup"><span data-stu-id="a199a-1001">ids</span></span>
- <span data-ttu-id="a199a-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="a199a-1002">idcard number</span></span>
- <span data-ttu-id="a199a-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-1003">idcard numbers</span></span>
- <span data-ttu-id="a199a-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="a199a-1004">idcard #</span></span>
- <span data-ttu-id="a199a-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="a199a-1005">idcard #s</span></span>
- <span data-ttu-id="a199a-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="a199a-1006">idcard card</span></span>
- <span data-ttu-id="a199a-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1007">idcard cards</span></span>
- <span data-ttu-id="a199a-1008">tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1008">idcard</span></span>
- <span data-ttu-id="a199a-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="a199a-1009">identification number</span></span>
- <span data-ttu-id="a199a-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-1010">identification numbers</span></span>
- <span data-ttu-id="a199a-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="a199a-1011">identification #</span></span>
- <span data-ttu-id="a199a-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="a199a-1012">identification #s</span></span>
- <span data-ttu-id="a199a-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="a199a-1013">identification card</span></span>
- <span data-ttu-id="a199a-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1014">identification cards</span></span>
- <span data-ttu-id="a199a-1015">determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-1015">identification</span></span> 
- <span data-ttu-id="a199a-1016">LISTAS #</span><span class="sxs-lookup"><span data-stu-id="a199a-1016">DL#</span></span>
- <span data-ttu-id="a199a-1017">DISTRIBUCIÓN #</span><span class="sxs-lookup"><span data-stu-id="a199a-1017">DLS#</span></span> 
- <span data-ttu-id="a199a-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="a199a-1018">CDL#</span></span> 
- <span data-ttu-id="a199a-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="a199a-1019">CDLS#</span></span> 
- <span data-ttu-id="a199a-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-1020">DriverLic#</span></span> 
- <span data-ttu-id="a199a-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-1021">DriverLics#</span></span> 
- <span data-ttu-id="a199a-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-1022">DriverLicense#</span></span> 
- <span data-ttu-id="a199a-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="a199a-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="a199a-1024">DriverLicence#</span></span> 
- <span data-ttu-id="a199a-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a199a-1025">DriverLicences#</span></span> 
- <span data-ttu-id="a199a-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-1026">Driver Lic#</span></span>
- <span data-ttu-id="a199a-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-1027">Driver Lics#</span></span> 
- <span data-ttu-id="a199a-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a199a-1028">Driver License#</span></span> 
- <span data-ttu-id="a199a-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="a199a-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a199a-1030">Driver License#</span></span> 
- <span data-ttu-id="a199a-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-1031">Driver Licences#</span></span> 
- <span data-ttu-id="a199a-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-1032">DriversLic#</span></span> 
- <span data-ttu-id="a199a-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-1033">DriversLics#</span></span> 
- <span data-ttu-id="a199a-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-1034">DriversLicense#</span></span> 
- <span data-ttu-id="a199a-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="a199a-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="a199a-1036">DriversLicence#</span></span> 
- <span data-ttu-id="a199a-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a199a-1037">DriversLicences#</span></span> 
- <span data-ttu-id="a199a-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="a199a-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="a199a-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="a199a-1040">Drivers License#</span></span> 
- <span data-ttu-id="a199a-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="a199a-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="a199a-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="a199a-1044">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="a199a-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="a199a-1045">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="a199a-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="a199a-1046">Conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-1046">Driver'License#</span></span> 
- <span data-ttu-id="a199a-1047">Conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="a199a-1048">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="a199a-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="a199a-1049">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="a199a-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="a199a-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="a199a-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="a199a-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="a199a-1052">Driver' License#</span></span> 
- <span data-ttu-id="a199a-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="a199a-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="a199a-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="a199a-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="a199a-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="a199a-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="a199a-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a199a-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="a199a-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="a199a-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a199a-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="a199a-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="a199a-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="a199a-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="a199a-1064">Driver's License#</span></span> 
- <span data-ttu-id="a199a-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="a199a-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="a199a-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="a199a-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="a199a-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="a199a-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="a199a-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="a199a-1069">identificador #</span><span class="sxs-lookup"><span data-stu-id="a199a-1069">id#</span></span> 
- <span data-ttu-id="a199a-1070">falta #</span><span class="sxs-lookup"><span data-stu-id="a199a-1070">ids#</span></span> 
- <span data-ttu-id="a199a-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="a199a-1071">idcard card#</span></span> 
- <span data-ttu-id="a199a-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="a199a-1072">idcard cards#</span></span> 
- <span data-ttu-id="a199a-1073">tarjeta #</span><span class="sxs-lookup"><span data-stu-id="a199a-1073">idcard#</span></span> 
- <span data-ttu-id="a199a-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="a199a-1074">identification card#</span></span> 
- <span data-ttu-id="a199a-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="a199a-1075">identification cards#</span></span> 
- <span data-ttu-id="a199a-1076">determinación #</span><span class="sxs-lookup"><span data-stu-id="a199a-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="a199a-1077">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="a199a-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1078">Format</span></span>

<span data-ttu-id="a199a-1079">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1080">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1080">Pattern</span></span>

<span data-ttu-id="a199a-1081">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1082">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1082">Checksum</span></span>

<span data-ttu-id="a199a-1083">No</span><span class="sxs-lookup"><span data-stu-id="a199a-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1084">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1084">Definition</span></span>

<span data-ttu-id="a199a-1085">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1086">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1087">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1088">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="a199a-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="a199a-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="a199a-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="a199a-1090">personal health number</span></span>
- <span data-ttu-id="a199a-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="a199a-1091">patient information</span></span>
- <span data-ttu-id="a199a-1092">health services</span><span class="sxs-lookup"><span data-stu-id="a199a-1092">health services</span></span>
- <span data-ttu-id="a199a-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="a199a-1093">speciality services</span></span>
- <span data-ttu-id="a199a-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="a199a-1094">automobile accident</span></span>
- <span data-ttu-id="a199a-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="a199a-1095">patient hospital</span></span>
- <span data-ttu-id="a199a-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="a199a-1096">psychiatrist</span></span>
- <span data-ttu-id="a199a-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="a199a-1097">workers compensation</span></span>
- <span data-ttu-id="a199a-1098">discapacidad</span><span class="sxs-lookup"><span data-stu-id="a199a-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="a199a-1099">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="a199a-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1100">Format</span></span>

<span data-ttu-id="a199a-1101">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1102">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1102">Pattern</span></span>

<span data-ttu-id="a199a-1103">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1104">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1104">Checksum</span></span>

<span data-ttu-id="a199a-1105">No</span><span class="sxs-lookup"><span data-stu-id="a199a-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1106">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1106">Definition</span></span>

<span data-ttu-id="a199a-1107">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1108">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1109">Se encuentra una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="a199a-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="a199a-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="a199a-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="a199a-1112">canadian citizenship</span></span>
- <span data-ttu-id="a199a-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="a199a-1113">canadian passport</span></span>
- <span data-ttu-id="a199a-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="a199a-1114">passport application</span></span>
- <span data-ttu-id="a199a-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="a199a-1115">passport photos</span></span>
- <span data-ttu-id="a199a-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="a199a-1116">certified translator</span></span>
- <span data-ttu-id="a199a-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="a199a-1117">canadian citizens</span></span>
- <span data-ttu-id="a199a-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="a199a-1118">processing times</span></span>
- <span data-ttu-id="a199a-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="a199a-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a199a-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-1120">Keyword_passport</span></span>

- <span data-ttu-id="a199a-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a199a-1121">Passport Number</span></span>
- <span data-ttu-id="a199a-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="a199a-1122">Passport No</span></span>
- <span data-ttu-id="a199a-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="a199a-1123">Passport #</span></span>
- <span data-ttu-id="a199a-1124">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="a199a-1124">Passport#</span></span>
- <span data-ttu-id="a199a-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="a199a-1125">PassportID</span></span>
- <span data-ttu-id="a199a-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="a199a-1126">Passportno</span></span>
- <span data-ttu-id="a199a-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-1127">passportnumber</span></span>
- <span data-ttu-id="a199a-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="a199a-1128">パスポート</span></span>
- <span data-ttu-id="a199a-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a199a-1129">パスポート番号</span></span>
- <span data-ttu-id="a199a-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a199a-1130">パスポートのNum</span></span>
- <span data-ttu-id="a199a-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a199a-1131">パスポート＃</span></span>
- <span data-ttu-id="a199a-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a199a-1132">Numéro de passeport</span></span>
- <span data-ttu-id="a199a-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a199a-1133">Passeport n °</span></span>
- <span data-ttu-id="a199a-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a199a-1134">Passeport Non</span></span>
- <span data-ttu-id="a199a-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-1135">Passeport #</span></span>
- <span data-ttu-id="a199a-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-1136">Passeport#</span></span>
- <span data-ttu-id="a199a-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a199a-1137">PasseportNon</span></span>
- <span data-ttu-id="a199a-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a199a-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="a199a-1139">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a199a-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1140">Format</span></span>

<span data-ttu-id="a199a-1141">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1142">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1142">Pattern</span></span>

<span data-ttu-id="a199a-1143">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1144">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1144">Checksum</span></span>

<span data-ttu-id="a199a-1145">No</span><span class="sxs-lookup"><span data-stu-id="a199a-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1146">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1146">Definition</span></span>

<span data-ttu-id="a199a-1147">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-1148">Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="a199a-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="a199a-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="a199a-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="a199a-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a199a-1151">social insurance number</span></span>
- <span data-ttu-id="a199a-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="a199a-1152">health information act</span></span>
- <span data-ttu-id="a199a-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="a199a-1153">income tax information</span></span>
- <span data-ttu-id="a199a-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="a199a-1154">manitoba health</span></span>
- <span data-ttu-id="a199a-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="a199a-1155">health registration</span></span>
- <span data-ttu-id="a199a-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="a199a-1156">prescription purchases</span></span>
- <span data-ttu-id="a199a-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="a199a-1157">benefit eligibility</span></span>
- <span data-ttu-id="a199a-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="a199a-1158">personal health</span></span>
- <span data-ttu-id="a199a-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="a199a-1159">power of attorney</span></span>
- <span data-ttu-id="a199a-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="a199a-1160">registration number</span></span>
- <span data-ttu-id="a199a-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="a199a-1161">personal health number</span></span>
- <span data-ttu-id="a199a-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="a199a-1162">practitioner referral</span></span>
- <span data-ttu-id="a199a-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="a199a-1163">wellness professional</span></span>
- <span data-ttu-id="a199a-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="a199a-1164">patient referral</span></span>
- <span data-ttu-id="a199a-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="a199a-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="a199a-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="a199a-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="a199a-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="a199a-1167">Nunavut</span></span>
- <span data-ttu-id="a199a-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="a199a-1168">Quebec</span></span>
- <span data-ttu-id="a199a-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="a199a-1169">Northwest Territories</span></span>
- <span data-ttu-id="a199a-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="a199a-1170">Ontario</span></span>
- <span data-ttu-id="a199a-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="a199a-1171">British Columbia</span></span>
- <span data-ttu-id="a199a-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="a199a-1172">Alberta</span></span>
- <span data-ttu-id="a199a-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="a199a-1173">Saskatchewan</span></span>
- <span data-ttu-id="a199a-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="a199a-1174">Manitoba</span></span>
- <span data-ttu-id="a199a-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="a199a-1175">Yukon</span></span>
- <span data-ttu-id="a199a-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="a199a-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="a199a-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="a199a-1177">New Brunswick</span></span>
- <span data-ttu-id="a199a-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="a199a-1178">Nova Scotia</span></span>
- <span data-ttu-id="a199a-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="a199a-1179">Prince Edward Island</span></span>
- <span data-ttu-id="a199a-1180">Canadá</span><span class="sxs-lookup"><span data-stu-id="a199a-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="a199a-1181">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="a199a-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1182">Format</span></span>

<span data-ttu-id="a199a-1183">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1184">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1184">Pattern</span></span>

<span data-ttu-id="a199a-1185">Con formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1185">Formatted:</span></span>
- <span data-ttu-id="a199a-1186">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1186">Three digits</span></span> 
- <span data-ttu-id="a199a-1187">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="a199a-1187">A hyphen or space</span></span> 
- <span data-ttu-id="a199a-1188">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1188">Three digits</span></span> 
- <span data-ttu-id="a199a-1189">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="a199a-1189">A hyphen or space</span></span> 
- <span data-ttu-id="a199a-1190">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1190">Three digits</span></span>

<span data-ttu-id="a199a-1191">Sin formato: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1192">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1192">Checksum</span></span>

<span data-ttu-id="a199a-1193">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1194">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1194">Definition</span></span>

<span data-ttu-id="a199a-1195">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1196">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1197">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a199a-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="a199a-1198">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="a199a-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="a199a-1199">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="a199a-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="a199a-1200">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-1201">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1201">The checksum passes.</span></span>

<span data-ttu-id="a199a-1202">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1203">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1204">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="a199a-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="a199a-1205">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1206">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="a199a-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="a199a-1207">Keyword_sin</span></span>

- <span data-ttu-id="a199a-1208">sin</span><span class="sxs-lookup"><span data-stu-id="a199a-1208">sin</span></span> 
- <span data-ttu-id="a199a-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="a199a-1209">social insurance</span></span> 
- <span data-ttu-id="a199a-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a199a-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="a199a-1211">pecados</span><span class="sxs-lookup"><span data-stu-id="a199a-1211">sins</span></span> 
- <span data-ttu-id="a199a-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="a199a-1212">ssn</span></span> 
- <span data-ttu-id="a199a-1213">SSN</span><span class="sxs-lookup"><span data-stu-id="a199a-1213">ssns</span></span> 
- <span data-ttu-id="a199a-1214">social security</span><span class="sxs-lookup"><span data-stu-id="a199a-1214">social security</span></span> 
- <span data-ttu-id="a199a-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="a199a-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="a199a-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="a199a-1216">national identification number</span></span> 
- <span data-ttu-id="a199a-1217">national id</span><span class="sxs-lookup"><span data-stu-id="a199a-1217">national id</span></span> 
- <span data-ttu-id="a199a-1218">PIN #</span><span class="sxs-lookup"><span data-stu-id="a199a-1218">sin#</span></span> 
- <span data-ttu-id="a199a-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="a199a-1219">soc ins</span></span> 
- <span data-ttu-id="a199a-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="a199a-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="a199a-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a199a-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="a199a-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="a199a-1222">driver's license</span></span> 
- <span data-ttu-id="a199a-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="a199a-1223">drivers license</span></span> 
- <span data-ttu-id="a199a-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="a199a-1224">driver's licence</span></span> 
- <span data-ttu-id="a199a-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a199a-1225">drivers licence</span></span> 
- <span data-ttu-id="a199a-1226">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="a199a-1226">DOB</span></span> 
- <span data-ttu-id="a199a-1227">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-1227">Birthdate</span></span> 
- <span data-ttu-id="a199a-1228">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="a199a-1228">Birthday</span></span> 
- <span data-ttu-id="a199a-1229">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="a199a-1230">	Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="a199a-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1231">Format</span></span>

<span data-ttu-id="a199a-1232">7-8 dígitos más delimitadores, un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="a199a-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1233">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1233">Pattern</span></span>

<span data-ttu-id="a199a-1234">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="a199a-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="a199a-1235">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-1235">1-2 digits</span></span> 
- <span data-ttu-id="a199a-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-1236">A period</span></span> 
- <span data-ttu-id="a199a-1237">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1237">Three digits</span></span> 
- <span data-ttu-id="a199a-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="a199a-1238">A period</span></span> 
- <span data-ttu-id="a199a-1239">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1239">Three digits</span></span> 
- <span data-ttu-id="a199a-1240">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-1240">A dash</span></span> 
- <span data-ttu-id="a199a-1241">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1242">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1242">Checksum</span></span>

<span data-ttu-id="a199a-1243">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1244">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1244">Definition</span></span>

<span data-ttu-id="a199a-1245">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1246">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1247">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="a199a-1248">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1248">The checksum passes.</span></span>

<span data-ttu-id="a199a-1249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1250">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1251">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="a199a-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="a199a-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="a199a-1254">Número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-1254">National Identification Number</span></span> 
- <span data-ttu-id="a199a-1255">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-1255">Identity card</span></span> 
- <span data-ttu-id="a199a-1256">ID</span><span class="sxs-lookup"><span data-stu-id="a199a-1256">ID</span></span> 
- <span data-ttu-id="a199a-1257">Determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-1257">Identification</span></span> 
- <span data-ttu-id="a199a-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="a199a-1259">REALIZAR</span><span class="sxs-lookup"><span data-stu-id="a199a-1259">RUN</span></span> 
- <span data-ttu-id="a199a-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="a199a-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="a199a-1261">ESTANCARSE</span><span class="sxs-lookup"><span data-stu-id="a199a-1261">RUT</span></span> 
- <span data-ttu-id="a199a-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="a199a-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="a199a-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="a199a-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="a199a-1266">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="a199a-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1267">Format</span></span>

<span data-ttu-id="a199a-1268">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1269">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1269">Pattern</span></span>

<span data-ttu-id="a199a-1270">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-1270">18 digits:</span></span>
- <span data-ttu-id="a199a-1271">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="a199a-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="a199a-1272">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a199a-1273">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="a199a-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="a199a-1274">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1275">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1275">Checksum</span></span>

<span data-ttu-id="a199a-1276">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1277">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1277">Definition</span></span>

<span data-ttu-id="a199a-1278">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1279">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1280">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="a199a-1281">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1281">The checksum passes.</span></span>

<span data-ttu-id="a199a-1282">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1283">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1284">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1285">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="a199a-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="a199a-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="a199a-1287">Tarjeta de identidad de residente</span><span class="sxs-lookup"><span data-stu-id="a199a-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="a199a-1288">China</span><span class="sxs-lookup"><span data-stu-id="a199a-1288">PRC</span></span> 
- <span data-ttu-id="a199a-1289">Tarjeta de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-1289">National Identification Card</span></span> 
- <span data-ttu-id="a199a-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="a199a-1290">身份证</span></span> 
- <span data-ttu-id="a199a-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="a199a-1291">居民 身份证</span></span> 
- <span data-ttu-id="a199a-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="a199a-1292">居民身份证</span></span> 
- <span data-ttu-id="a199a-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="a199a-1293">鉴定</span></span> 
- <span data-ttu-id="a199a-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-1294">身分證</span></span> 
- <span data-ttu-id="a199a-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-1295">居民 身份證</span></span>
- <span data-ttu-id="a199a-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="a199a-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="a199a-1297">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1298">Format</span></span>

<span data-ttu-id="a199a-1299">16 dígitos que pueden ser formateados o sin formato (dddddddddddddddd) y deben pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="a199a-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1300">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1300">Pattern</span></span>

<span data-ttu-id="a199a-1301">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="a199a-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1302">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1302">Checksum</span></span>

<span data-ttu-id="a199a-1303">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="a199a-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1304">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1304">Definition</span></span>

<span data-ttu-id="a199a-1305">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1306">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1307">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-1307">One of the following is true:</span></span>
    - <span data-ttu-id="a199a-1308">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="a199a-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="a199a-1309">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="a199a-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="a199a-1310">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-1311">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1311">The checksum passes.</span></span>

<span data-ttu-id="a199a-1312">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1313">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1314">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="a199a-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="a199a-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="a199a-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="a199a-1317">card verification</span></span>
- <span data-ttu-id="a199a-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="a199a-1318">card identification number</span></span>
- <span data-ttu-id="a199a-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="a199a-1319">cvn</span></span>
- <span data-ttu-id="a199a-1320">cid</span><span class="sxs-lookup"><span data-stu-id="a199a-1320">cid</span></span>
- <span data-ttu-id="a199a-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="a199a-1321">cvc2</span></span>
- <span data-ttu-id="a199a-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="a199a-1322">cvv2</span></span>
- <span data-ttu-id="a199a-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="a199a-1323">pin block</span></span>
- <span data-ttu-id="a199a-1324">security code</span><span class="sxs-lookup"><span data-stu-id="a199a-1324">security code</span></span>
- <span data-ttu-id="a199a-1325">security number</span><span class="sxs-lookup"><span data-stu-id="a199a-1325">security number</span></span>
- <span data-ttu-id="a199a-1326">security no</span><span class="sxs-lookup"><span data-stu-id="a199a-1326">security no</span></span>
- <span data-ttu-id="a199a-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="a199a-1327">issue number</span></span>
- <span data-ttu-id="a199a-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="a199a-1328">issue no</span></span>
- <span data-ttu-id="a199a-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="a199a-1329">cryptogramme</span></span>
- <span data-ttu-id="a199a-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="a199a-1330">numéro de sécurité</span></span>
- <span data-ttu-id="a199a-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="a199a-1331">numero de securite</span></span>
- <span data-ttu-id="a199a-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="a199a-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="a199a-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="a199a-1334">prüfziffer</span></span>
- <span data-ttu-id="a199a-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="a199a-1335">prufziffer</span></span>
- <span data-ttu-id="a199a-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="a199a-1336">sicherheits Kode</span></span>
- <span data-ttu-id="a199a-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="a199a-1337">sicherheitscode</span></span>
- <span data-ttu-id="a199a-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="a199a-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1339">verfalldatum</span></span>
- <span data-ttu-id="a199a-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="a199a-1340">codice di verifica</span></span>
- <span data-ttu-id="a199a-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1341">cod.</span></span> <span data-ttu-id="a199a-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1342">sicurezza</span></span>
- <span data-ttu-id="a199a-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1343">cod sicurezza</span></span>
- <span data-ttu-id="a199a-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a199a-1344">n autorizzazione</span></span>
- <span data-ttu-id="a199a-1345">Código</span><span class="sxs-lookup"><span data-stu-id="a199a-1345">código</span></span>
- <span data-ttu-id="a199a-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="a199a-1346">codigo</span></span>
- <span data-ttu-id="a199a-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1347">cod.</span></span> <span data-ttu-id="a199a-1348">seg</span><span class="sxs-lookup"><span data-stu-id="a199a-1348">seg</span></span>
- <span data-ttu-id="a199a-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="a199a-1349">cod seg</span></span>
- <span data-ttu-id="a199a-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1350">código de segurança</span></span>
- <span data-ttu-id="a199a-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1351">codigo de seguranca</span></span>
- <span data-ttu-id="a199a-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1352">codigo de segurança</span></span>
- <span data-ttu-id="a199a-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1353">código de seguranca</span></span>
- <span data-ttu-id="a199a-1354">campos.</span><span class="sxs-lookup"><span data-stu-id="a199a-1354">cód.</span></span> <span data-ttu-id="a199a-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1355">segurança</span></span>
- <span data-ttu-id="a199a-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1356">cod.</span></span> <span data-ttu-id="a199a-1357">DQO SEGURANCA.</span><span class="sxs-lookup"><span data-stu-id="a199a-1357">seguranca cod.</span></span> <span data-ttu-id="a199a-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1358">segurança</span></span>
- <span data-ttu-id="a199a-1359">campos.</span><span class="sxs-lookup"><span data-stu-id="a199a-1359">cód.</span></span> <span data-ttu-id="a199a-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1360">seguranca</span></span>
- <span data-ttu-id="a199a-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1361">cód segurança</span></span>
- <span data-ttu-id="a199a-1362">Bacalao SEGURANCA contra reembolso de segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="a199a-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1363">cód seguranca</span></span>
- <span data-ttu-id="a199a-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="a199a-1364">número de verificação</span></span>
- <span data-ttu-id="a199a-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="a199a-1365">numero de verificacao</span></span>
- <span data-ttu-id="a199a-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="a199a-1366">ablauf</span></span>
- <span data-ttu-id="a199a-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="a199a-1367">gültig bis</span></span>
- <span data-ttu-id="a199a-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="a199a-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="a199a-1369">gultig bis</span></span>
- <span data-ttu-id="a199a-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="a199a-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="a199a-1371">scadenza</span></span>
- <span data-ttu-id="a199a-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="a199a-1372">data scad</span></span>
- <span data-ttu-id="a199a-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="a199a-1373">fecha de expiracion</span></span>
- <span data-ttu-id="a199a-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="a199a-1374">fecha de venc</span></span>
- <span data-ttu-id="a199a-1375">1er</span><span class="sxs-lookup"><span data-stu-id="a199a-1375">vencimiento</span></span>
- <span data-ttu-id="a199a-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="a199a-1376">válido hasta</span></span>
- <span data-ttu-id="a199a-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="a199a-1377">valido hasta</span></span>
- <span data-ttu-id="a199a-1378">vto</span><span class="sxs-lookup"><span data-stu-id="a199a-1378">vto</span></span>
- <span data-ttu-id="a199a-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="a199a-1379">data de expiração</span></span>
- <span data-ttu-id="a199a-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="a199a-1380">data de expiracao</span></span>
- <span data-ttu-id="a199a-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="a199a-1381">data em que expira</span></span>
- <span data-ttu-id="a199a-1382">validade</span><span class="sxs-lookup"><span data-stu-id="a199a-1382">validade</span></span>
- <span data-ttu-id="a199a-1383">valorar</span><span class="sxs-lookup"><span data-stu-id="a199a-1383">valor</span></span>
- <span data-ttu-id="a199a-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="a199a-1384">vencimento</span></span>
- <span data-ttu-id="a199a-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="a199a-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="a199a-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="a199a-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="a199a-1387">AMEX</span><span class="sxs-lookup"><span data-stu-id="a199a-1387">amex</span></span>
- <span data-ttu-id="a199a-1388">american express</span><span class="sxs-lookup"><span data-stu-id="a199a-1388">american express</span></span>
- <span data-ttu-id="a199a-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="a199a-1389">americanexpress</span></span>
- <span data-ttu-id="a199a-1390">Régimen</span><span class="sxs-lookup"><span data-stu-id="a199a-1390">Visa</span></span>
- <span data-ttu-id="a199a-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="a199a-1391">mastercard</span></span>
- <span data-ttu-id="a199a-1392">master card</span><span class="sxs-lookup"><span data-stu-id="a199a-1392">master card</span></span>
- <span data-ttu-id="a199a-1393">valuación</span><span class="sxs-lookup"><span data-stu-id="a199a-1393">mc</span></span> 
- <span data-ttu-id="a199a-1394">MasterCard</span><span class="sxs-lookup"><span data-stu-id="a199a-1394">mastercards</span></span>
- <span data-ttu-id="a199a-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1395">master cards</span></span>
- <span data-ttu-id="a199a-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="a199a-1396">diner's Club</span></span>
- <span data-ttu-id="a199a-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="a199a-1397">diners club</span></span>
- <span data-ttu-id="a199a-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="a199a-1398">dinersclub</span></span>
- <span data-ttu-id="a199a-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="a199a-1399">discover card</span></span>
- <span data-ttu-id="a199a-1400">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1400">discovercard</span></span>
- <span data-ttu-id="a199a-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1401">discover cards</span></span>
- <span data-ttu-id="a199a-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="a199a-1402">JCB</span></span>
- <span data-ttu-id="a199a-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="a199a-1403">japanese card bureau</span></span>
- <span data-ttu-id="a199a-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="a199a-1404">carte blanche</span></span>
- <span data-ttu-id="a199a-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="a199a-1405">carteblanche</span></span>
- <span data-ttu-id="a199a-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="a199a-1406">credit card</span></span>
- <span data-ttu-id="a199a-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="a199a-1407">cc#</span></span>
- <span data-ttu-id="a199a-1408"># CC:</span><span class="sxs-lookup"><span data-stu-id="a199a-1408">cc#:</span></span>
- <span data-ttu-id="a199a-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="a199a-1409">expiration date</span></span>
- <span data-ttu-id="a199a-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="a199a-1410">exp date</span></span>
- <span data-ttu-id="a199a-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="a199a-1411">expiry date</span></span>
- <span data-ttu-id="a199a-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="a199a-1412">date d’expiration</span></span>
- <span data-ttu-id="a199a-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="a199a-1413">date d'exp</span></span>
- <span data-ttu-id="a199a-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="a199a-1414">date expiration</span></span>
- <span data-ttu-id="a199a-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="a199a-1415">bank card</span></span>
- <span data-ttu-id="a199a-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1416">bankcard</span></span>
- <span data-ttu-id="a199a-1417">card number</span><span class="sxs-lookup"><span data-stu-id="a199a-1417">card number</span></span>
- <span data-ttu-id="a199a-1418">card num</span><span class="sxs-lookup"><span data-stu-id="a199a-1418">card num</span></span>
- <span data-ttu-id="a199a-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-1419">cardnumber</span></span>
- <span data-ttu-id="a199a-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="a199a-1420">cardnumbers</span></span>
- <span data-ttu-id="a199a-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-1421">card numbers</span></span>
- <span data-ttu-id="a199a-1422">crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1422">creditcard</span></span>
- <span data-ttu-id="a199a-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1423">credit cards</span></span>
- <span data-ttu-id="a199a-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1424">creditcards</span></span>
- <span data-ttu-id="a199a-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="a199a-1425">ccn</span></span>
- <span data-ttu-id="a199a-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="a199a-1426">card holder</span></span>
- <span data-ttu-id="a199a-1427">titular</span><span class="sxs-lookup"><span data-stu-id="a199a-1427">cardholder</span></span>
- <span data-ttu-id="a199a-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="a199a-1428">card holders</span></span>
- <span data-ttu-id="a199a-1429">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="a199a-1429">cardholders</span></span>
- <span data-ttu-id="a199a-1430">check card</span><span class="sxs-lookup"><span data-stu-id="a199a-1430">check card</span></span>
- <span data-ttu-id="a199a-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1431">checkcard</span></span>
- <span data-ttu-id="a199a-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1432">check cards</span></span>
- <span data-ttu-id="a199a-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1433">checkcards</span></span>
- <span data-ttu-id="a199a-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="a199a-1434">debit card</span></span>
- <span data-ttu-id="a199a-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1435">debitcard</span></span>
- <span data-ttu-id="a199a-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1436">debit cards</span></span>
- <span data-ttu-id="a199a-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1437">debitcards</span></span>
- <span data-ttu-id="a199a-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="a199a-1438">atm card</span></span>
- <span data-ttu-id="a199a-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1439">atmcard</span></span>
- <span data-ttu-id="a199a-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1440">atm cards</span></span>
- <span data-ttu-id="a199a-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1441">atmcards</span></span>
- <span data-ttu-id="a199a-1442">enrutar</span><span class="sxs-lookup"><span data-stu-id="a199a-1442">enroute</span></span>
- <span data-ttu-id="a199a-1443">en route</span><span class="sxs-lookup"><span data-stu-id="a199a-1443">en route</span></span>
- <span data-ttu-id="a199a-1444">card type</span><span class="sxs-lookup"><span data-stu-id="a199a-1444">card type</span></span>
- <span data-ttu-id="a199a-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="a199a-1445">carte bancaire</span></span>
- <span data-ttu-id="a199a-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="a199a-1446">carte de crédit</span></span>
- <span data-ttu-id="a199a-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="a199a-1447">carte de credit</span></span>
- <span data-ttu-id="a199a-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1448">numéro de carte</span></span>
- <span data-ttu-id="a199a-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1449">numero de carte</span></span>
- <span data-ttu-id="a199a-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1450">nº de la carte</span></span>
- <span data-ttu-id="a199a-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1451">nº de carte</span></span>
- <span data-ttu-id="a199a-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="a199a-1452">kreditkarte</span></span>
- <span data-ttu-id="a199a-1453">karte</span><span class="sxs-lookup"><span data-stu-id="a199a-1453">karte</span></span>
- <span data-ttu-id="a199a-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="a199a-1454">karteninhaber</span></span>
- <span data-ttu-id="a199a-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a199a-1455">karteninhabers</span></span>
- <span data-ttu-id="a199a-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="a199a-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="a199a-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="a199a-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="a199a-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="a199a-1458">kreditkartentyp</span></span>
- <span data-ttu-id="a199a-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="a199a-1459">eigentümername</span></span>
- <span data-ttu-id="a199a-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="a199a-1460">kartennr</span></span> 
- <span data-ttu-id="a199a-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1461">kartennummer</span></span>
- <span data-ttu-id="a199a-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1462">kreditkartennummer</span></span>
- <span data-ttu-id="a199a-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="a199a-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1464">carta di credito</span></span>
- <span data-ttu-id="a199a-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1465">carta credito</span></span>
- <span data-ttu-id="a199a-1466">cobro</span><span class="sxs-lookup"><span data-stu-id="a199a-1466">carta</span></span>
- <span data-ttu-id="a199a-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1467">n carta</span></span>
- <span data-ttu-id="a199a-1468">Nº.</span><span class="sxs-lookup"><span data-stu-id="a199a-1468">nr.</span></span> <span data-ttu-id="a199a-1469">cobro</span><span class="sxs-lookup"><span data-stu-id="a199a-1469">carta</span></span>
- <span data-ttu-id="a199a-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1470">nr carta</span></span>
- <span data-ttu-id="a199a-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1471">numero carta</span></span>
- <span data-ttu-id="a199a-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1472">numero della carta</span></span>
- <span data-ttu-id="a199a-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1473">numero di carta</span></span>
- <span data-ttu-id="a199a-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1474">tarjeta credito</span></span>
- <span data-ttu-id="a199a-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1475">tarjeta de credito</span></span>
- <span data-ttu-id="a199a-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1476">tarjeta crédito</span></span>
- <span data-ttu-id="a199a-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="a199a-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="a199a-1478">tarjeta de atm</span></span>
- <span data-ttu-id="a199a-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="a199a-1479">tarjeta atm</span></span>
- <span data-ttu-id="a199a-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1480">tarjeta debito</span></span>
- <span data-ttu-id="a199a-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1481">tarjeta de debito</span></span>
- <span data-ttu-id="a199a-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="a199a-1482">tarjeta débito</span></span>
- <span data-ttu-id="a199a-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="a199a-1483">tarjeta de débito</span></span>
- <span data-ttu-id="a199a-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1484">nº de tarjeta</span></span>
- <span data-ttu-id="a199a-1485">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1485">no.</span></span> <span data-ttu-id="a199a-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1486">de tarjeta</span></span>
- <span data-ttu-id="a199a-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1487">no de tarjeta</span></span>
- <span data-ttu-id="a199a-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1488">numero de tarjeta</span></span>
- <span data-ttu-id="a199a-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1489">número de tarjeta</span></span>
- <span data-ttu-id="a199a-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="a199a-1490">tarjeta no</span></span>
- <span data-ttu-id="a199a-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="a199a-1491">tarjetahabiente</span></span>
- <span data-ttu-id="a199a-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1492">cartão de crédito</span></span>
- <span data-ttu-id="a199a-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1493">cartão de credito</span></span>
- <span data-ttu-id="a199a-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1494">cartao de crédito</span></span>
- <span data-ttu-id="a199a-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1495">cartao de credito</span></span>
- <span data-ttu-id="a199a-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="a199a-1496">cartão de débito</span></span>
- <span data-ttu-id="a199a-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="a199a-1497">cartao de débito</span></span>
- <span data-ttu-id="a199a-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1498">cartão de debito</span></span>
- <span data-ttu-id="a199a-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1499">cartao de debito</span></span>
- <span data-ttu-id="a199a-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="a199a-1500">débito automático</span></span>
- <span data-ttu-id="a199a-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="a199a-1501">debito automatico</span></span>
- <span data-ttu-id="a199a-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1502">número do cartão</span></span>
- <span data-ttu-id="a199a-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1503">numero do cartão</span></span> 
- <span data-ttu-id="a199a-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1504">número do cartao</span></span>
- <span data-ttu-id="a199a-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1505">numero do cartao</span></span>
- <span data-ttu-id="a199a-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1506">número de cartão</span></span>
- <span data-ttu-id="a199a-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1507">numero de cartão</span></span>
- <span data-ttu-id="a199a-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1508">número de cartao</span></span>
- <span data-ttu-id="a199a-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1509">numero de cartao</span></span>
- <span data-ttu-id="a199a-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1510">nº do cartão</span></span>
- <span data-ttu-id="a199a-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1511">nº do cartao</span></span>
- <span data-ttu-id="a199a-1512">Nº.</span><span class="sxs-lookup"><span data-stu-id="a199a-1512">nº.</span></span> <span data-ttu-id="a199a-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1513">do cartão</span></span>
- <span data-ttu-id="a199a-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1514">no do cartão</span></span>
- <span data-ttu-id="a199a-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1515">no do cartao</span></span>
- <span data-ttu-id="a199a-1516">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1516">no.</span></span> <span data-ttu-id="a199a-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1517">do cartão</span></span>
- <span data-ttu-id="a199a-1518">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1518">no.</span></span> <span data-ttu-id="a199a-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="a199a-1520">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="a199a-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1521">Format</span></span>

<span data-ttu-id="a199a-1522">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1523">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1523">Pattern</span></span>

<span data-ttu-id="a199a-1524">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1525">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1525">Checksum</span></span>

<span data-ttu-id="a199a-1526">No</span><span class="sxs-lookup"><span data-stu-id="a199a-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1527">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1527">Definition</span></span>

<span data-ttu-id="a199a-1528">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1529">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1530">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1531">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="a199a-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="a199a-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="a199a-1533">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="a199a-1533">Croatian identity card</span></span>
- <span data-ttu-id="a199a-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="a199a-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="a199a-1535">Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="a199a-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1536">Format</span></span>

<span data-ttu-id="a199a-1537">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1538">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1538">Pattern</span></span>

<span data-ttu-id="a199a-1539">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-1539">11 digits:</span></span>
- <span data-ttu-id="a199a-1540">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1540">10 digits</span></span> 
- <span data-ttu-id="a199a-1541">El dígito final es un dígito de control para el intercambio internacional de datos, se agregan las letras h antes de los once dígitos.</span><span class="sxs-lookup"><span data-stu-id="a199a-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1542">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1542">Checksum</span></span>

<span data-ttu-id="a199a-1543">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1544">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1544">Definition</span></span>

<span data-ttu-id="a199a-1545">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1546">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1547">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="a199a-1548">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1548">The checksum passes.</span></span>

<span data-ttu-id="a199a-1549">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1550">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1551">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1552">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="a199a-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="a199a-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="a199a-1554">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="a199a-1554">Personal Identification Number</span></span>
- <span data-ttu-id="a199a-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="a199a-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="a199a-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="a199a-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="a199a-1557">Número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="a199a-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1558">Format</span></span>

<span data-ttu-id="a199a-1559">Nueve dígitos con barra diagonal (formato antiguo) 10 dígitos con barra diagonal (nuevo formato) opcional</span><span class="sxs-lookup"><span data-stu-id="a199a-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1560">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1560">Pattern</span></span>

<span data-ttu-id="a199a-1561">Nueve dígitos (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="a199a-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="a199a-1562">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1562">Nine digits</span></span>

<span data-ttu-id="a199a-1563">O</span><span class="sxs-lookup"><span data-stu-id="a199a-1563">OR</span></span>

- <span data-ttu-id="a199a-1564">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a199a-1565">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="a199a-1565">A forward slash</span></span>
- <span data-ttu-id="a199a-1566">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1566">Three digits</span></span>

<span data-ttu-id="a199a-1567">10 dígitos (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="a199a-1567">10 digits (new format):</span></span>
- <span data-ttu-id="a199a-1568">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1568">10 digits</span></span>

<span data-ttu-id="a199a-1569">O</span><span class="sxs-lookup"><span data-stu-id="a199a-1569">OR</span></span>

- <span data-ttu-id="a199a-1570">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a199a-1571">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="a199a-1571">A forward slash</span></span> 
- <span data-ttu-id="a199a-1572">Cuatro dígitos donde el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1573">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1573">Checksum</span></span>

<span data-ttu-id="a199a-1574">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1575">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1575">Definition</span></span>

<span data-ttu-id="a199a-1576">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_czech_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-1577">Se encuentra una palabra clave de Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="a199a-1578">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a199a-1579">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1579">Keywords</span></span>

- <span data-ttu-id="a199a-1580">número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="a199a-1580">czech personal identity number</span></span>
- <span data-ttu-id="a199a-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="a199a-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="a199a-1582">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="a199a-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1583">Format</span></span>

<span data-ttu-id="a199a-1584">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="a199a-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1585">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1585">Pattern</span></span>

<span data-ttu-id="a199a-1586">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-1586">10 digits:</span></span>
- <span data-ttu-id="a199a-1587">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a199a-1588">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-1588">A hyphen</span></span> 
- <span data-ttu-id="a199a-1589">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1590">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1590">Checksum</span></span>

<span data-ttu-id="a199a-1591">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1592">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1592">Definition</span></span>

<span data-ttu-id="a199a-1593">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_denmark_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-1594">Se encuentra una palabra clave de Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="a199a-1595">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1596">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="a199a-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="a199a-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="a199a-1598">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="a199a-1598">Personal Identification Number</span></span>
- <span data-ttu-id="a199a-1599">RCP</span><span class="sxs-lookup"><span data-stu-id="a199a-1599">CPR</span></span>
- <span data-ttu-id="a199a-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="a199a-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="a199a-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="a199a-1602">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="a199a-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1603">Format</span></span>

<span data-ttu-id="a199a-1604">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1605">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1605">Pattern</span></span>

<span data-ttu-id="a199a-1606">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a199a-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a199a-1607">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="a199a-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="a199a-1608">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="a199a-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="a199a-1609">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1610">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1610">Checksum</span></span>

<span data-ttu-id="a199a-1611">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1612">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1612">Definition</span></span>

<span data-ttu-id="a199a-1613">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1614">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1615">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1616">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1616">Keywords</span></span>

<span data-ttu-id="a199a-1617">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a199a-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="a199a-1618">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="a199a-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1619">Format</span></span>

<span data-ttu-id="a199a-1620">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1621">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1621">Pattern</span></span>

<span data-ttu-id="a199a-1622">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="a199a-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1623">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1623">Checksum</span></span>

<span data-ttu-id="a199a-1624">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1625">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1625">Definition</span></span>

<span data-ttu-id="a199a-1626">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1627">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1628">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="a199a-1629">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="a199a-1630">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="a199a-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="a199a-1631">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="a199a-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="a199a-1632">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="a199a-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="a199a-1633">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-1634">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1635">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="a199a-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="a199a-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="a199a-1637">account number</span><span class="sxs-lookup"><span data-stu-id="a199a-1637">account number</span></span> 
- <span data-ttu-id="a199a-1638">card number</span><span class="sxs-lookup"><span data-stu-id="a199a-1638">card number</span></span> 
- <span data-ttu-id="a199a-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="a199a-1639">card no.</span></span> 
- <span data-ttu-id="a199a-1640">security number</span><span class="sxs-lookup"><span data-stu-id="a199a-1640">security number</span></span> 
- <span data-ttu-id="a199a-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="a199a-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="a199a-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a199a-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="a199a-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="a199a-1643">acct nbr</span></span> 
- <span data-ttu-id="a199a-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="a199a-1644">acct num</span></span> 
- <span data-ttu-id="a199a-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="a199a-1645">acct no</span></span> 
- <span data-ttu-id="a199a-1646">american express</span><span class="sxs-lookup"><span data-stu-id="a199a-1646">american express</span></span> 
- <span data-ttu-id="a199a-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="a199a-1647">americanexpress</span></span> 
- <span data-ttu-id="a199a-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="a199a-1648">americano espresso</span></span> 
- <span data-ttu-id="a199a-1649">AMEX</span><span class="sxs-lookup"><span data-stu-id="a199a-1649">amex</span></span> 
- <span data-ttu-id="a199a-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="a199a-1650">atm card</span></span> 
- <span data-ttu-id="a199a-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1651">atm cards</span></span> 
- <span data-ttu-id="a199a-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1652">atm kaart</span></span> 
- <span data-ttu-id="a199a-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1653">atmcard</span></span> 
- <span data-ttu-id="a199a-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1654">atmcards</span></span> 
- <span data-ttu-id="a199a-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1655">atmkaart</span></span> 
- <span data-ttu-id="a199a-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="a199a-1656">atmkaarten</span></span> 
- <span data-ttu-id="a199a-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="a199a-1657">bancontact</span></span> 
- <span data-ttu-id="a199a-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="a199a-1658">bank card</span></span> 
- <span data-ttu-id="a199a-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1659">bankkaart</span></span> 
- <span data-ttu-id="a199a-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="a199a-1660">card holder</span></span> 
- <span data-ttu-id="a199a-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="a199a-1661">card holders</span></span> 
- <span data-ttu-id="a199a-1662">card num</span><span class="sxs-lookup"><span data-stu-id="a199a-1662">card num</span></span> 
- <span data-ttu-id="a199a-1663">card number</span><span class="sxs-lookup"><span data-stu-id="a199a-1663">card number</span></span> 
- <span data-ttu-id="a199a-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-1664">card numbers</span></span> 
- <span data-ttu-id="a199a-1665">card type</span><span class="sxs-lookup"><span data-stu-id="a199a-1665">card type</span></span> 
- <span data-ttu-id="a199a-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="a199a-1666">cardano numerico</span></span> 
- <span data-ttu-id="a199a-1667">titular</span><span class="sxs-lookup"><span data-stu-id="a199a-1667">cardholder</span></span> 
- <span data-ttu-id="a199a-1668">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="a199a-1668">cardholders</span></span> 
- <span data-ttu-id="a199a-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-1669">cardnumber</span></span> 
- <span data-ttu-id="a199a-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="a199a-1670">cardnumbers</span></span> 
- <span data-ttu-id="a199a-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="a199a-1671">carta bianca</span></span> 
- <span data-ttu-id="a199a-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1672">carta credito</span></span> 
- <span data-ttu-id="a199a-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1673">carta di credito</span></span> 
- <span data-ttu-id="a199a-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1674">cartao de credito</span></span> 
- <span data-ttu-id="a199a-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1675">cartao de crédito</span></span> 
- <span data-ttu-id="a199a-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1676">cartao de debito</span></span> 
- <span data-ttu-id="a199a-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="a199a-1677">cartao de débito</span></span> 
- <span data-ttu-id="a199a-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="a199a-1678">carte bancaire</span></span> 
- <span data-ttu-id="a199a-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="a199a-1679">carte blanche</span></span> 
- <span data-ttu-id="a199a-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="a199a-1680">carte bleue</span></span> 
- <span data-ttu-id="a199a-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="a199a-1681">carte de credit</span></span> 
- <span data-ttu-id="a199a-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="a199a-1682">carte de crédit</span></span> 
- <span data-ttu-id="a199a-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1683">carte di credito</span></span> 
- <span data-ttu-id="a199a-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="a199a-1684">carteblanche</span></span> 
- <span data-ttu-id="a199a-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1685">cartão de credito</span></span> 
- <span data-ttu-id="a199a-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1686">cartão de crédito</span></span> 
- <span data-ttu-id="a199a-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1687">cartão de debito</span></span> 
- <span data-ttu-id="a199a-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="a199a-1688">cartão de débito</span></span> 
- <span data-ttu-id="a199a-1689">cb</span><span class="sxs-lookup"><span data-stu-id="a199a-1689">cb</span></span> 
- <span data-ttu-id="a199a-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="a199a-1690">ccn</span></span> 
- <span data-ttu-id="a199a-1691">check card</span><span class="sxs-lookup"><span data-stu-id="a199a-1691">check card</span></span> 
- <span data-ttu-id="a199a-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1692">check cards</span></span> 
- <span data-ttu-id="a199a-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1693">checkcard</span></span>
- <span data-ttu-id="a199a-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1694">checkcards</span></span> 
- <span data-ttu-id="a199a-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1695">chequekaart</span></span> 
- <span data-ttu-id="a199a-1696">Logic</span><span class="sxs-lookup"><span data-stu-id="a199a-1696">cirrus</span></span> 
- <span data-ttu-id="a199a-1697">Cirrus-EDC-maestro</span><span class="sxs-lookup"><span data-stu-id="a199a-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="a199a-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1698">controlekaart</span></span> 
- <span data-ttu-id="a199a-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="a199a-1699">controlekaarten</span></span> 
- <span data-ttu-id="a199a-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="a199a-1700">credit card</span></span> 
- <span data-ttu-id="a199a-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1701">credit cards</span></span> 
- <span data-ttu-id="a199a-1702">crédito</span><span class="sxs-lookup"><span data-stu-id="a199a-1702">creditcard</span></span> 
- <span data-ttu-id="a199a-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1703">creditcards</span></span> 
- <span data-ttu-id="a199a-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1704">debetkaart</span></span> 
- <span data-ttu-id="a199a-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="a199a-1705">debetkaarten</span></span> 
- <span data-ttu-id="a199a-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="a199a-1706">debit card</span></span> 
- <span data-ttu-id="a199a-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1707">debit cards</span></span> 
- <span data-ttu-id="a199a-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="a199a-1708">debitcard</span></span> 
- <span data-ttu-id="a199a-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="a199a-1709">debitcards</span></span> 
- <span data-ttu-id="a199a-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="a199a-1710">debito automatico</span></span> 
- <span data-ttu-id="a199a-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="a199a-1711">diners club</span></span> 
- <span data-ttu-id="a199a-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="a199a-1712">dinersclub</span></span> 
- <span data-ttu-id="a199a-1713">advierte</span><span class="sxs-lookup"><span data-stu-id="a199a-1713">discover</span></span> 
- <span data-ttu-id="a199a-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="a199a-1714">discover card</span></span> 
- <span data-ttu-id="a199a-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1715">discover cards</span></span> 
- <span data-ttu-id="a199a-1716">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1716">discovercard</span></span> 
- <span data-ttu-id="a199a-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="a199a-1717">discovercards</span></span> 
- <span data-ttu-id="a199a-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="a199a-1718">débito automático</span></span>
- <span data-ttu-id="a199a-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="a199a-1719">edc</span></span> 
- <span data-ttu-id="a199a-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="a199a-1720">eigentümername</span></span> 
- <span data-ttu-id="a199a-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="a199a-1721">european debit card</span></span> 
- <span data-ttu-id="a199a-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1722">hoofdkaart</span></span> 
- <span data-ttu-id="a199a-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="a199a-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="a199a-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="a199a-1724">in viaggio</span></span> 
- <span data-ttu-id="a199a-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="a199a-1725">japanese card bureau</span></span> 
- <span data-ttu-id="a199a-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="a199a-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="a199a-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="a199a-1727">jcb</span></span> 
- <span data-ttu-id="a199a-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="a199a-1728">kaart</span></span> 
- <span data-ttu-id="a199a-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="a199a-1729">kaart num</span></span> 
- <span data-ttu-id="a199a-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="a199a-1730">kaartaantal</span></span> 
- <span data-ttu-id="a199a-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="a199a-1731">kaartaantallen</span></span> 
- <span data-ttu-id="a199a-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="a199a-1732">kaarthouder</span></span> 
- <span data-ttu-id="a199a-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="a199a-1733">kaarthouders</span></span> 
- <span data-ttu-id="a199a-1734">karte</span><span class="sxs-lookup"><span data-stu-id="a199a-1734">karte</span></span>  
- <span data-ttu-id="a199a-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="a199a-1735">karteninhaber</span></span> 
- <span data-ttu-id="a199a-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a199a-1736">karteninhabers</span></span>
- <span data-ttu-id="a199a-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="a199a-1737">kartennr</span></span> 
- <span data-ttu-id="a199a-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1738">kartennummer</span></span> 
- <span data-ttu-id="a199a-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="a199a-1739">kreditkarte</span></span> 
- <span data-ttu-id="a199a-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="a199a-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="a199a-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="a199a-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="a199a-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="a199a-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="a199a-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="a199a-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="a199a-1745">dispositivos</span><span class="sxs-lookup"><span data-stu-id="a199a-1745">maestro</span></span> 
- <span data-ttu-id="a199a-1746">master card</span><span class="sxs-lookup"><span data-stu-id="a199a-1746">master card</span></span> 
- <span data-ttu-id="a199a-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="a199a-1747">master cards</span></span> 
- <span data-ttu-id="a199a-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="a199a-1748">mastercard</span></span> 
- <span data-ttu-id="a199a-1749">MasterCard</span><span class="sxs-lookup"><span data-stu-id="a199a-1749">mastercards</span></span> 
- <span data-ttu-id="a199a-1750">valuación</span><span class="sxs-lookup"><span data-stu-id="a199a-1750">mc</span></span> 
- <span data-ttu-id="a199a-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="a199a-1751">mister cash</span></span> 
- <span data-ttu-id="a199a-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1752">n carta</span></span> 
- <span data-ttu-id="a199a-1753">cobro</span><span class="sxs-lookup"><span data-stu-id="a199a-1753">carta</span></span> 
- <span data-ttu-id="a199a-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1754">no de tarjeta</span></span> 
- <span data-ttu-id="a199a-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1755">no do cartao</span></span> 
- <span data-ttu-id="a199a-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1756">no do cartão</span></span> 
- <span data-ttu-id="a199a-1757">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1757">no.</span></span> <span data-ttu-id="a199a-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1758">de tarjeta</span></span> 
- <span data-ttu-id="a199a-1759">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1759">no.</span></span> <span data-ttu-id="a199a-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1760">do cartao</span></span> 
- <span data-ttu-id="a199a-1761">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1761">no.</span></span> <span data-ttu-id="a199a-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1762">do cartão</span></span> 
- <span data-ttu-id="a199a-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1763">nr carta</span></span> 
- <span data-ttu-id="a199a-1764">Nº.</span><span class="sxs-lookup"><span data-stu-id="a199a-1764">nr.</span></span> <span data-ttu-id="a199a-1765">cobro</span><span class="sxs-lookup"><span data-stu-id="a199a-1765">carta</span></span> 
- <span data-ttu-id="a199a-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1766">numeri di scheda</span></span> 
- <span data-ttu-id="a199a-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1767">numero carta</span></span> 
- <span data-ttu-id="a199a-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1768">numero de cartao</span></span> 
- <span data-ttu-id="a199a-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1769">numero de carte</span></span> 
- <span data-ttu-id="a199a-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1770">numero de cartão</span></span> 
- <span data-ttu-id="a199a-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1771">numero de tarjeta</span></span>
- <span data-ttu-id="a199a-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1772">numero della carta</span></span> 
- <span data-ttu-id="a199a-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1773">numero di carta</span></span> 
- <span data-ttu-id="a199a-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1774">numero di scheda</span></span> 
- <span data-ttu-id="a199a-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1775">numero do cartao</span></span> 
- <span data-ttu-id="a199a-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1776">numero do cartão</span></span> 
- <span data-ttu-id="a199a-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1777">numéro de carte</span></span> 
- <span data-ttu-id="a199a-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="a199a-1778">nº carta</span></span> 
- <span data-ttu-id="a199a-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1779">nº de carte</span></span> 
- <span data-ttu-id="a199a-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="a199a-1780">nº de la carte</span></span> 
- <span data-ttu-id="a199a-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="a199a-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1782">nº do cartao</span></span> 
- <span data-ttu-id="a199a-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1783">nº do cartão</span></span> 
- <span data-ttu-id="a199a-1784">Nº.</span><span class="sxs-lookup"><span data-stu-id="a199a-1784">nº.</span></span> <span data-ttu-id="a199a-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1785">do cartão</span></span> 
- <span data-ttu-id="a199a-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1786">número de cartao</span></span> 
- <span data-ttu-id="a199a-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="a199a-1787">número de cartão</span></span> 
- <span data-ttu-id="a199a-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a199a-1788">número de tarjeta</span></span> 
- <span data-ttu-id="a199a-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a199a-1789">número do cartao</span></span> 
- <span data-ttu-id="a199a-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="a199a-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="a199a-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a199a-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a199a-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a199a-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a199a-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="a199a-1793">scheda della banca</span></span> 
- <span data-ttu-id="a199a-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="a199a-1794">scheda di controllo</span></span> 
- <span data-ttu-id="a199a-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1795">scheda di debito</span></span> 
- <span data-ttu-id="a199a-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="a199a-1796">scheda matrice</span></span> 
- <span data-ttu-id="a199a-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a199a-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="a199a-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="a199a-1798">schede di controllo</span></span> 
- <span data-ttu-id="a199a-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1799">schede di debito</span></span> 
- <span data-ttu-id="a199a-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="a199a-1800">schede matrici</span></span> 
- <span data-ttu-id="a199a-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="a199a-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="a199a-1802">scoprono le schede</span></span> 
- <span data-ttu-id="a199a-1803">solo</span><span class="sxs-lookup"><span data-stu-id="a199a-1803">solo</span></span> 
- <span data-ttu-id="a199a-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1804">supporti di scheda</span></span> 
- <span data-ttu-id="a199a-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1805">supporto di scheda</span></span> 
- <span data-ttu-id="a199a-1806">cambia</span><span class="sxs-lookup"><span data-stu-id="a199a-1806">switch</span></span> 
- <span data-ttu-id="a199a-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="a199a-1807">tarjeta atm</span></span> 
- <span data-ttu-id="a199a-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1808">tarjeta credito</span></span> 
- <span data-ttu-id="a199a-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="a199a-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="a199a-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="a199a-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="a199a-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="a199a-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="a199a-1812">tarjeta debito</span></span> 
- <span data-ttu-id="a199a-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="a199a-1813">tarjeta no</span></span>
- <span data-ttu-id="a199a-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="a199a-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="a199a-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1815">tipo della scheda</span></span> 
- <span data-ttu-id="a199a-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="a199a-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="a199a-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1817">scheda</span></span> 
- <span data-ttu-id="a199a-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="a199a-1818">v pay</span></span> 
- <span data-ttu-id="a199a-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="a199a-1819">v-pay</span></span> 
- <span data-ttu-id="a199a-1820">régimen</span><span class="sxs-lookup"><span data-stu-id="a199a-1820">visa</span></span> 
- <span data-ttu-id="a199a-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="a199a-1821">visa plus</span></span> 
- <span data-ttu-id="a199a-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="a199a-1822">visa electron</span></span> 
- <span data-ttu-id="a199a-1823">a</span><span class="sxs-lookup"><span data-stu-id="a199a-1823">visto</span></span> 
- <span data-ttu-id="a199a-1824">visum</span><span class="sxs-lookup"><span data-stu-id="a199a-1824">visum</span></span> 
- <span data-ttu-id="a199a-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="a199a-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="a199a-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a199a-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="a199a-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="a199a-1827">card identification number</span></span>
- <span data-ttu-id="a199a-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="a199a-1828">card verification</span></span> 
- <span data-ttu-id="a199a-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="a199a-1829">cardi la verifica</span></span> 
- <span data-ttu-id="a199a-1830">cid</span><span class="sxs-lookup"><span data-stu-id="a199a-1830">cid</span></span> 
- <span data-ttu-id="a199a-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="a199a-1831">cod seg</span></span> 
- <span data-ttu-id="a199a-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1832">cod seguranca</span></span> 
- <span data-ttu-id="a199a-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1833">cod segurança</span></span> 
- <span data-ttu-id="a199a-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1834">cod sicurezza</span></span> 
- <span data-ttu-id="a199a-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1835">cod.</span></span> <span data-ttu-id="a199a-1836">seg</span><span class="sxs-lookup"><span data-stu-id="a199a-1836">seg</span></span> 
- <span data-ttu-id="a199a-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1837">cod.</span></span> <span data-ttu-id="a199a-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1838">seguranca</span></span> 
- <span data-ttu-id="a199a-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1839">cod.</span></span> <span data-ttu-id="a199a-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1840">segurança</span></span> 
- <span data-ttu-id="a199a-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="a199a-1841">cod.</span></span> <span data-ttu-id="a199a-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1842">sicurezza</span></span> 
- <span data-ttu-id="a199a-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="a199a-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="a199a-1844">codice di verifica</span></span> 
- <span data-ttu-id="a199a-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="a199a-1845">codigo</span></span> 
- <span data-ttu-id="a199a-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="a199a-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1847">codigo de segurança</span></span> 
- <span data-ttu-id="a199a-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="a199a-1848">crittogramma</span></span> 
- <span data-ttu-id="a199a-1849">criptograma</span><span class="sxs-lookup"><span data-stu-id="a199a-1849">cryptogram</span></span> 
- <span data-ttu-id="a199a-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="a199a-1850">cryptogramme</span></span> 
- <span data-ttu-id="a199a-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="a199a-1851">cv2</span></span> 
- <span data-ttu-id="a199a-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="a199a-1852">cvc</span></span> 
- <span data-ttu-id="a199a-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="a199a-1853">cvc2</span></span> 
- <span data-ttu-id="a199a-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="a199a-1854">cvn</span></span> 
- <span data-ttu-id="a199a-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="a199a-1855">cvv</span></span> 
- <span data-ttu-id="a199a-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="a199a-1856">cvv2</span></span> 
- <span data-ttu-id="a199a-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1857">cód seguranca</span></span> 
- <span data-ttu-id="a199a-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1858">cód segurança</span></span> 
- <span data-ttu-id="a199a-1859">campos.</span><span class="sxs-lookup"><span data-stu-id="a199a-1859">cód.</span></span> <span data-ttu-id="a199a-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1860">seguranca</span></span> 
- <span data-ttu-id="a199a-1861">campos.</span><span class="sxs-lookup"><span data-stu-id="a199a-1861">cód.</span></span> <span data-ttu-id="a199a-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1862">segurança</span></span> 
- <span data-ttu-id="a199a-1863">Código</span><span class="sxs-lookup"><span data-stu-id="a199a-1863">código</span></span> 
- <span data-ttu-id="a199a-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="a199a-1864">código de seguranca</span></span> 
- <span data-ttu-id="a199a-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="a199a-1865">código de segurança</span></span> 
- <span data-ttu-id="a199a-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="a199a-1866">de kaart controle</span></span> 
- <span data-ttu-id="a199a-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="a199a-1867">geeft nr uit</span></span> 
- <span data-ttu-id="a199a-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="a199a-1868">issue no</span></span> 
- <span data-ttu-id="a199a-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="a199a-1869">issue number</span></span> 
- <span data-ttu-id="a199a-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="a199a-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="a199a-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="a199a-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="a199a-1873">kwestieaantal</span></span> 
- <span data-ttu-id="a199a-1874">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1874">no.</span></span> <span data-ttu-id="a199a-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="a199a-1875">dell'edizione</span></span> 
- <span data-ttu-id="a199a-1876">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-1876">no.</span></span> <span data-ttu-id="a199a-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1877">di sicurezza</span></span> 
- <span data-ttu-id="a199a-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="a199a-1878">numero de securite</span></span> 
- <span data-ttu-id="a199a-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="a199a-1879">numero de verificacao</span></span> 
- <span data-ttu-id="a199a-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="a199a-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="a199a-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="a199a-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="a199a-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="a199a-1882">scheda</span></span> 
- <span data-ttu-id="a199a-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a199a-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="a199a-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="a199a-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="a199a-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="a199a-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="a199a-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a199a-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="a199a-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="a199a-1887">número de verificação</span></span> 
- <span data-ttu-id="a199a-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="a199a-1888">perno il blocco</span></span> 
- <span data-ttu-id="a199a-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="a199a-1889">pin block</span></span> 
- <span data-ttu-id="a199a-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="a199a-1890">prufziffer</span></span> 
- <span data-ttu-id="a199a-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="a199a-1891">prüfziffer</span></span> 
- <span data-ttu-id="a199a-1892">security code</span><span class="sxs-lookup"><span data-stu-id="a199a-1892">security code</span></span> 
- <span data-ttu-id="a199a-1893">security no</span><span class="sxs-lookup"><span data-stu-id="a199a-1893">security no</span></span> 
- <span data-ttu-id="a199a-1894">security number</span><span class="sxs-lookup"><span data-stu-id="a199a-1894">security number</span></span> 
- <span data-ttu-id="a199a-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="a199a-1895">sicherheits kode</span></span> 
- <span data-ttu-id="a199a-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="a199a-1896">sicherheitscode</span></span> 
- <span data-ttu-id="a199a-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="a199a-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="a199a-1898">speldblok</span></span> 
- <span data-ttu-id="a199a-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="a199a-1899">veiligheid nr</span></span> 
- <span data-ttu-id="a199a-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="a199a-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="a199a-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="a199a-1901">veiligheidscode</span></span> 
- <span data-ttu-id="a199a-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="a199a-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="a199a-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a199a-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="a199a-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="a199a-1905">ablauf</span></span> 
- <span data-ttu-id="a199a-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="a199a-1906">data de expiracao</span></span> 
- <span data-ttu-id="a199a-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="a199a-1907">data de expiração</span></span> 
- <span data-ttu-id="a199a-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="a199a-1908">data del exp</span></span> 
- <span data-ttu-id="a199a-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="a199a-1909">data di exp</span></span> 
- <span data-ttu-id="a199a-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="a199a-1910">data di scadenza</span></span> 
- <span data-ttu-id="a199a-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="a199a-1911">data em que expira</span></span> 
- <span data-ttu-id="a199a-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="a199a-1912">data scad</span></span> 
- <span data-ttu-id="a199a-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="a199a-1913">data scadenza</span></span> 
- <span data-ttu-id="a199a-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="a199a-1914">date de validité</span></span> 
- <span data-ttu-id="a199a-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="a199a-1915">datum afloop</span></span> 
- <span data-ttu-id="a199a-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="a199a-1916">datum van exp</span></span> 
- <span data-ttu-id="a199a-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="a199a-1917">de afloop</span></span> 
- <span data-ttu-id="a199a-1918">espira</span><span class="sxs-lookup"><span data-stu-id="a199a-1918">espira</span></span> 
- <span data-ttu-id="a199a-1919">espira</span><span class="sxs-lookup"><span data-stu-id="a199a-1919">espira</span></span> 
- <span data-ttu-id="a199a-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="a199a-1920">exp date</span></span> 
- <span data-ttu-id="a199a-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="a199a-1921">exp datum</span></span> 
- <span data-ttu-id="a199a-1922">expiración</span><span class="sxs-lookup"><span data-stu-id="a199a-1922">expiration</span></span> 
- <span data-ttu-id="a199a-1923">expiran</span><span class="sxs-lookup"><span data-stu-id="a199a-1923">expire</span></span> 
- <span data-ttu-id="a199a-1924">expira</span><span class="sxs-lookup"><span data-stu-id="a199a-1924">expires</span></span> 
- <span data-ttu-id="a199a-1925">expiración</span><span class="sxs-lookup"><span data-stu-id="a199a-1925">expiry</span></span> 
- <span data-ttu-id="a199a-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="a199a-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="a199a-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="a199a-1927">fecha de venc</span></span> 
- <span data-ttu-id="a199a-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="a199a-1928">gultig bis</span></span> 
- <span data-ttu-id="a199a-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="a199a-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="a199a-1930">gültig bis</span></span> 
- <span data-ttu-id="a199a-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="a199a-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="a199a-1932">la scadenza</span></span> 
- <span data-ttu-id="a199a-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="a199a-1933">scadenza</span></span> 
- <span data-ttu-id="a199a-1934">valable</span><span class="sxs-lookup"><span data-stu-id="a199a-1934">valable</span></span> 
- <span data-ttu-id="a199a-1935">validade</span><span class="sxs-lookup"><span data-stu-id="a199a-1935">validade</span></span> 
- <span data-ttu-id="a199a-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="a199a-1936">valido hasta</span></span> 
- <span data-ttu-id="a199a-1937">valorar</span><span class="sxs-lookup"><span data-stu-id="a199a-1937">valor</span></span> 
- <span data-ttu-id="a199a-1938">venc</span><span class="sxs-lookup"><span data-stu-id="a199a-1938">venc</span></span> 
- <span data-ttu-id="a199a-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="a199a-1939">vencimento</span></span> 
- <span data-ttu-id="a199a-1940">1er</span><span class="sxs-lookup"><span data-stu-id="a199a-1940">vencimiento</span></span> 
- <span data-ttu-id="a199a-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="a199a-1941">verloopt</span></span> 
- <span data-ttu-id="a199a-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="a199a-1942">vervaldag</span></span> 
- <span data-ttu-id="a199a-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="a199a-1943">vervaldatum</span></span> 
- <span data-ttu-id="a199a-1944">vto</span><span class="sxs-lookup"><span data-stu-id="a199a-1944">vto</span></span> 
- <span data-ttu-id="a199a-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="a199a-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="a199a-1946">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="a199a-1946">EU Driver's License Number</span></span>

<span data-ttu-id="a199a-1947">Para obtener más información, vea [tipo de información confidencial del número de licencia del conductor de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="a199a-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="a199a-1948">Número de identificación nacional de la UE</span><span class="sxs-lookup"><span data-stu-id="a199a-1948">EU National Identification Number</span></span>

<span data-ttu-id="a199a-1949">Para obtener más información, consulte el [tipo de información confidencial de número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="a199a-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="a199a-1950">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="a199a-1950">EU Passport Number</span></span>

<span data-ttu-id="a199a-1951">Para obtener más información, consulte [EU Number Sensitive Information Type](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="a199a-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="a199a-1952">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="a199a-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="a199a-1953">Para obtener más información, consulte el [número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="a199a-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="a199a-1954">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="a199a-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="a199a-1955">Para obtener más información, vea [tipo de información confidencial de número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="a199a-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="a199a-1956">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="a199a-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1957">Format</span></span>

<span data-ttu-id="a199a-1958">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1959">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1959">Pattern</span></span>

<span data-ttu-id="a199a-1960">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a199a-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a199a-1961">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="a199a-1962">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="a199a-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="a199a-1963">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="a199a-1964">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1965">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1965">Checksum</span></span>

<span data-ttu-id="a199a-1966">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1967">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1967">Definition</span></span>

<span data-ttu-id="a199a-1968">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1969">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1970">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="a199a-1971">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1972">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1972">Keywords</span></span>

- <span data-ttu-id="a199a-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="a199a-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="a199a-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="a199a-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="a199a-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="a199a-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="a199a-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="a199a-1976">Personbeteckning</span></span>
- <span data-ttu-id="a199a-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="a199a-1978">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="a199a-1978">Finland Passport Number</span></span>

<span data-ttu-id="a199a-1979">Combinación de formato de nueve letras y dígitos de la combinación de los patrones de nueve letras y dígitos: dos letras (no distingue entre mayúsculas y minúsculas) siete dígitos de suma de comprobación no Definition una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-1980">Se encuentra una palabra clave de Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="a199a-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="a199a-1981"></span></span>
<span data-ttu-id="a199a-1982">Palabras clave Keyword_finland_passport_number Passi de Passport</span><span class="sxs-lookup"><span data-stu-id="a199a-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="a199a-1983">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="a199a-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-1984">Format</span></span>

<span data-ttu-id="a199a-1985">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-1986">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-1986">Pattern</span></span>

<span data-ttu-id="a199a-1987">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="a199a-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-1988">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-1988">Checksum</span></span>

<span data-ttu-id="a199a-1989">No</span><span class="sxs-lookup"><span data-stu-id="a199a-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-1990">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-1990">Definition</span></span>

<span data-ttu-id="a199a-1991">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-1992">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-1993">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="a199a-1994">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="a199a-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="a199a-1995">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-1996">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="a199a-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a199a-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="a199a-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a199a-1998">drivers licence</span></span>
- <span data-ttu-id="a199a-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="a199a-1999">drivers license</span></span>
- <span data-ttu-id="a199a-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2000">driving licence</span></span>
- <span data-ttu-id="a199a-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="a199a-2001">driving license</span></span>
- <span data-ttu-id="a199a-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a199a-2002">permis de conduire</span></span>
- <span data-ttu-id="a199a-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="a199a-2003">licence number</span></span>
- <span data-ttu-id="a199a-2004">license number</span><span class="sxs-lookup"><span data-stu-id="a199a-2004">license number</span></span>
- <span data-ttu-id="a199a-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-2005">licence numbers</span></span>
- <span data-ttu-id="a199a-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="a199a-2007">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="a199a-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2008">Format</span></span>

<span data-ttu-id="a199a-2009">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2010">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2010">Pattern</span></span>

<span data-ttu-id="a199a-2011">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2012">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2012">Checksum</span></span>

<span data-ttu-id="a199a-2013">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2014">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2014">Definition</span></span>

<span data-ttu-id="a199a-2015">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2016">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2017">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2017">Keywords</span></span>

<span data-ttu-id="a199a-2018">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a199a-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="a199a-2019">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="a199a-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2020">Format</span></span>

<span data-ttu-id="a199a-2021">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="a199a-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2022">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2022">Pattern</span></span>

<span data-ttu-id="a199a-2023">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="a199a-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="a199a-2024">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2024">Two digits</span></span> 
- <span data-ttu-id="a199a-2025">Dos letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-2026">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2027">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2027">Checksum</span></span>

<span data-ttu-id="a199a-2028">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2029">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2029">Definition</span></span>

<span data-ttu-id="a199a-2030">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2031">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2032">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2033">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a199a-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-2034">Keyword_passport</span></span>

- <span data-ttu-id="a199a-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2035">Passport Number</span></span>
- <span data-ttu-id="a199a-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="a199a-2036">Passport No</span></span>
- <span data-ttu-id="a199a-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="a199a-2037">Passport #</span></span>
- <span data-ttu-id="a199a-2038">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="a199a-2038">Passport#</span></span>
- <span data-ttu-id="a199a-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="a199a-2039">PassportID</span></span>
- <span data-ttu-id="a199a-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="a199a-2040">Passportno</span></span>
- <span data-ttu-id="a199a-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-2041">passportnumber</span></span>
- <span data-ttu-id="a199a-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="a199a-2042">パスポート</span></span>
- <span data-ttu-id="a199a-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2043">パスポート番号</span></span>
- <span data-ttu-id="a199a-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a199a-2044">パスポートのNum</span></span>
- <span data-ttu-id="a199a-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2045">パスポート ＃</span></span> 
- <span data-ttu-id="a199a-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a199a-2046">Numéro de passeport</span></span>
- <span data-ttu-id="a199a-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a199a-2047">Passeport n °</span></span>
- <span data-ttu-id="a199a-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a199a-2048">Passeport Non</span></span>
- <span data-ttu-id="a199a-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-2049">Passeport #</span></span>
- <span data-ttu-id="a199a-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-2050">Passeport#</span></span>
- <span data-ttu-id="a199a-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a199a-2051">PasseportNon</span></span>
- <span data-ttu-id="a199a-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a199a-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="a199a-2053">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a199a-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2054">Format</span></span>

<span data-ttu-id="a199a-2055">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2056">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2056">Pattern</span></span>

<span data-ttu-id="a199a-2057">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="a199a-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="a199a-2058">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="a199a-2059">o</span><span class="sxs-lookup"><span data-stu-id="a199a-2059">or</span></span>
- <span data-ttu-id="a199a-2060">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2061">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2061">Checksum</span></span>

<span data-ttu-id="a199a-2062">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2063">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2063">Definition</span></span>

<span data-ttu-id="a199a-2064">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2065">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2066">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="a199a-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a199a-2067">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2067">The checksum passes.</span></span>

<span data-ttu-id="a199a-2068">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2069">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2070">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="a199a-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a199a-2071">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2071">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2072">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="a199a-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="a199a-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="a199a-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="a199a-2074">insee</span></span>
- <span data-ttu-id="a199a-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="a199a-2075">securité sociale</span></span>
- <span data-ttu-id="a199a-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="a199a-2076">securite sociale</span></span>
- <span data-ttu-id="a199a-2077">national id</span><span class="sxs-lookup"><span data-stu-id="a199a-2077">national id</span></span>
- <span data-ttu-id="a199a-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="a199a-2078">national identification</span></span>
- <span data-ttu-id="a199a-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="a199a-2079">numéro d'identité</span></span>
- <span data-ttu-id="a199a-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="a199a-2080">no d'identité</span></span>
- <span data-ttu-id="a199a-2081">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2081">no.</span></span> <span data-ttu-id="a199a-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="a199a-2082">d'identité</span></span>
- <span data-ttu-id="a199a-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="a199a-2083">numero d'identite</span></span>
- <span data-ttu-id="a199a-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="a199a-2084">no d'identite</span></span>
- <span data-ttu-id="a199a-2085">No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2085">no.</span></span> <span data-ttu-id="a199a-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="a199a-2086">d'identite</span></span>
- <span data-ttu-id="a199a-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="a199a-2087">social security number</span></span>
- <span data-ttu-id="a199a-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="a199a-2088">social security code</span></span>
- <span data-ttu-id="a199a-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a199a-2089">social insurance number</span></span>
- <span data-ttu-id="a199a-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="a199a-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="a199a-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="a199a-2091">d'identité nationale</span></span>
- <span data-ttu-id="a199a-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a199a-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="a199a-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a199a-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="a199a-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a199a-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="a199a-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="a199a-2095">numéro de sécu</span></span>
- <span data-ttu-id="a199a-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="a199a-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="a199a-2097">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="a199a-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2098">Format</span></span>

<span data-ttu-id="a199a-2099">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="a199a-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2100">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2100">Pattern</span></span>

<span data-ttu-id="a199a-2101">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="a199a-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="a199a-2102">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="a199a-2102">A digit or letter</span></span> 
- <span data-ttu-id="a199a-2103">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2103">Two digits</span></span> 
- <span data-ttu-id="a199a-2104">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="a199a-2104">Six digits or letters</span></span> 
- <span data-ttu-id="a199a-2105">Un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-2105">A digit</span></span> 
- <span data-ttu-id="a199a-2106">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="a199a-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2107">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2107">Checksum</span></span>

<span data-ttu-id="a199a-2108">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2109">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2109">Definition</span></span>

<span data-ttu-id="a199a-2110">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2111">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2112">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="a199a-2113">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="a199a-2114">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="a199a-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="a199a-2115">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="a199a-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="a199a-2116">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2116">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2117">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="a199a-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="a199a-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2119">Führerschein</span></span>
- <span data-ttu-id="a199a-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2120">Fuhrerschein</span></span>
- <span data-ttu-id="a199a-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2121">Fuehrerschein</span></span>
- <span data-ttu-id="a199a-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="a199a-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="a199a-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="a199a-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="a199a-2125">Führerschein-</span></span> 
- <span data-ttu-id="a199a-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="a199a-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="a199a-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="a199a-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="a199a-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a199a-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="a199a-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a199a-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="a199a-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a199a-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="a199a-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="a199a-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a199a-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a199a-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a199a-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="a199a-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a199a-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="a199a-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a199a-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a199a-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a199a-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a199a-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="a199a-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a199a-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="a199a-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a199a-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="a199a-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a199a-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="a199a-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a199a-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a199a-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a199a-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a199a-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="a199a-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a199a-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="a199a-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a199a-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a199a-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a199a-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a199a-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="a199a-2152">LISTAS</span><span class="sxs-lookup"><span data-stu-id="a199a-2152">DL</span></span> 
- <span data-ttu-id="a199a-2153">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="a199a-2153">DLS</span></span>
- <span data-ttu-id="a199a-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-2154">Driv Lic</span></span> 
- <span data-ttu-id="a199a-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="a199a-2155">Driv Licen</span></span> 
- <span data-ttu-id="a199a-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="a199a-2156">Driv License</span></span>
- <span data-ttu-id="a199a-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2157">Driv Licenses</span></span> 
- <span data-ttu-id="a199a-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2158">Driv Licence</span></span> 
- <span data-ttu-id="a199a-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-2159">Driv Licences</span></span> 
- <span data-ttu-id="a199a-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-2160">Driv Lic</span></span> 
- <span data-ttu-id="a199a-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="a199a-2161">Driver Licen</span></span> 
- <span data-ttu-id="a199a-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="a199a-2162">Driver License</span></span> 
- <span data-ttu-id="a199a-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2163">Driver Licenses</span></span> 
- <span data-ttu-id="a199a-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2164">Driver Licence</span></span> 
- <span data-ttu-id="a199a-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-2165">Driver Licences</span></span> 
- <span data-ttu-id="a199a-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-2166">Drivers Lic</span></span> 
- <span data-ttu-id="a199a-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="a199a-2167">Drivers Licen</span></span> 
- <span data-ttu-id="a199a-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a199a-2168">Drivers License</span></span> 
- <span data-ttu-id="a199a-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="a199a-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2170">Drivers Licence</span></span> 
- <span data-ttu-id="a199a-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-2171">Drivers Licences</span></span> 
- <span data-ttu-id="a199a-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-2172">Driver's Lic</span></span> 
- <span data-ttu-id="a199a-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="a199a-2173">Driver's Licen</span></span> 
- <span data-ttu-id="a199a-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a199a-2174">Driver's License</span></span> 
- <span data-ttu-id="a199a-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="a199a-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2176">Driver's Licence</span></span> 
- <span data-ttu-id="a199a-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-2177">Driver's Licences</span></span> 
- <span data-ttu-id="a199a-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-2178">Driving Lic</span></span> 
- <span data-ttu-id="a199a-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="a199a-2179">Driving Licen</span></span> 
- <span data-ttu-id="a199a-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="a199a-2180">Driving License</span></span> 
- <span data-ttu-id="a199a-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2181">Driving Licenses</span></span> 
- <span data-ttu-id="a199a-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2182">Driving Licence</span></span> 
- <span data-ttu-id="a199a-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="a199a-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="a199a-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="a199a-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="a199a-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="a199a-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a199a-2187">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a199a-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2188">No-Führerschein</span></span> 
- <span data-ttu-id="a199a-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a199a-2190">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a199a-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2191">N-Führerschein</span></span> 
- <span data-ttu-id="a199a-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a199a-2193">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="a199a-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="a199a-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a199a-2196">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a199a-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2197">No-Führerschein</span></span> 
- <span data-ttu-id="a199a-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a199a-2199">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a199a-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2200">N-Führerschein</span></span> 
- <span data-ttu-id="a199a-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a199a-2202">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a199a-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="a199a-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a199a-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="a199a-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="a199a-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a199a-2205">ausstellungsort</span></span>
- <span data-ttu-id="a199a-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="a199a-2206">ausstellende behöde</span></span>
- <span data-ttu-id="a199a-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="a199a-2207">ausstellende behorde</span></span>
- <span data-ttu-id="a199a-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="a199a-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="a199a-2209">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="a199a-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2210">Format</span></span>

<span data-ttu-id="a199a-2211">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="a199a-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2212">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2212">Pattern</span></span>

<span data-ttu-id="a199a-2213">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a199a-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a199a-2214">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="a199a-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="a199a-2215">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2215">Three digits</span></span> 
- <span data-ttu-id="a199a-2216">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="a199a-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="a199a-2217">Un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2218">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2218">Checksum</span></span>

<span data-ttu-id="a199a-2219">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2220">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2220">Definition</span></span>

<span data-ttu-id="a199a-2221">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2222">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2223">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="a199a-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a199a-2224">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2224">The checksum passes.</span></span>

<span data-ttu-id="a199a-2225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2226">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2227">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="a199a-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a199a-2228">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2228">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2229">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="a199a-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="a199a-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="a199a-2231">reisepass</span></span>
- <span data-ttu-id="a199a-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="a199a-2232">reisepasse</span></span>
- <span data-ttu-id="a199a-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2233">reisepassnummer</span></span>
- <span data-ttu-id="a199a-2234">usuarios</span><span class="sxs-lookup"><span data-stu-id="a199a-2234">passport</span></span>
- <span data-ttu-id="a199a-2235">passports</span><span class="sxs-lookup"><span data-stu-id="a199a-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="a199a-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="a199a-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="a199a-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-2237">geburtsdatum</span></span>
- <span data-ttu-id="a199a-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a199a-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="a199a-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a199a-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="a199a-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="a199a-2241">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="a199a-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="a199a-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="a199a-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="a199a-2243">Reisepass-NR</span><span class="sxs-lookup"><span data-stu-id="a199a-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="a199a-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="a199a-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="a199a-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="a199a-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="a199a-2246">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="a199a-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2247">Format</span></span>

<span data-ttu-id="a199a-2248">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="a199a-2249">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2250">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2250">Pattern</span></span>

<span data-ttu-id="a199a-2251">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="a199a-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="a199a-2252">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-2253">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2253">Eight digits</span></span>

<span data-ttu-id="a199a-2254">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="a199a-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="a199a-2255">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2256">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2256">Checksum</span></span>

<span data-ttu-id="a199a-2257">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2258">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2258">Definition</span></span>

<span data-ttu-id="a199a-2259">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2260">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2261">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2262">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="a199a-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="a199a-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="a199a-2264">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-2264">Identity Card</span></span>
- <span data-ttu-id="a199a-2265">ID</span><span class="sxs-lookup"><span data-stu-id="a199a-2265">ID</span></span>
- <span data-ttu-id="a199a-2266">Determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-2266">Identification</span></span>
- <span data-ttu-id="a199a-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a199a-2267">Personalausweis</span></span>
- <span data-ttu-id="a199a-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="a199a-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="a199a-2269">Ausweis</span></span>
- <span data-ttu-id="a199a-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a199a-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="a199a-2271">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="a199a-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2272">Format</span></span>

<span data-ttu-id="a199a-2273">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="a199a-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2274">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2274">Pattern</span></span>

<span data-ttu-id="a199a-2275">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="a199a-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="a199a-2276">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="a199a-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="a199a-2277">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-2277">A dash</span></span> 
- <span data-ttu-id="a199a-2278">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2278">Six digits</span></span>

<span data-ttu-id="a199a-2279">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="a199a-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="a199a-2280">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="a199a-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="a199a-2281">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-2281">A dash</span></span> 
- <span data-ttu-id="a199a-2282">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2283">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2283">Checksum</span></span>

<span data-ttu-id="a199a-2284">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2285">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2285">Definition</span></span>

<span data-ttu-id="a199a-2286">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2287">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2288">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2289">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="a199a-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="a199a-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="a199a-2291">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="a199a-2291">Greek identity Card</span></span>
- <span data-ttu-id="a199a-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="a199a-2292">Tautotita</span></span>
- <span data-ttu-id="a199a-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="a199a-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="a199a-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="a199a-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="a199a-2295">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="a199a-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2296">Format</span></span>

<span data-ttu-id="a199a-2297">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="a199a-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2298">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2298">Pattern</span></span>

<span data-ttu-id="a199a-2299">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="a199a-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="a199a-2300">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-2301">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2301">Six digits</span></span> 
- <span data-ttu-id="a199a-2302">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="a199a-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2303">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2303">Checksum</span></span>

<span data-ttu-id="a199a-2304">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2305">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2305">Definition</span></span>

<span data-ttu-id="a199a-2306">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2307">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2308">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="a199a-2309">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2309">The checksum passes.</span></span>

<span data-ttu-id="a199a-2310">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2311">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2312">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2312">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2313">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="a199a-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="a199a-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="a199a-2315">tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="a199a-2315">hong kong identity card</span></span>
- <span data-ttu-id="a199a-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="a199a-2316">HKIDC</span></span>
- <span data-ttu-id="a199a-2317">id card</span><span class="sxs-lookup"><span data-stu-id="a199a-2317">id card</span></span>
- <span data-ttu-id="a199a-2318">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-2318">identity card</span></span>
- <span data-ttu-id="a199a-2319">tarjeta de identidad HK</span><span class="sxs-lookup"><span data-stu-id="a199a-2319">hk identity card</span></span>
- <span data-ttu-id="a199a-2320">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="a199a-2320">hong kong id</span></span>
- <span data-ttu-id="a199a-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2321">香港身份證</span></span>
- <span data-ttu-id="a199a-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="a199a-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2323">身份證</span></span>
- <span data-ttu-id="a199a-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2324">身份証</span></span>
- <span data-ttu-id="a199a-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2325">身分證</span></span>
- <span data-ttu-id="a199a-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2326">身分証</span></span>
- <span data-ttu-id="a199a-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2327">香港身份証</span></span>
- <span data-ttu-id="a199a-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2328">香港身分證</span></span>
- <span data-ttu-id="a199a-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2329">香港身分証</span></span>
- <span data-ttu-id="a199a-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2330">香港身份證</span></span>
- <span data-ttu-id="a199a-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2331">香港居民身份證</span></span>
- <span data-ttu-id="a199a-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2332">香港居民身份証</span></span>
- <span data-ttu-id="a199a-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2333">香港居民身分證</span></span>
- <span data-ttu-id="a199a-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2334">香港居民身分証</span></span>
- <span data-ttu-id="a199a-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="a199a-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="a199a-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="a199a-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="a199a-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="a199a-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="a199a-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="a199a-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="a199a-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="a199a-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="a199a-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="a199a-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="a199a-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="a199a-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a199a-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="a199a-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="a199a-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a199a-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="a199a-2351">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="a199a-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2352">Format</span></span>

<span data-ttu-id="a199a-2353">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2354">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2354">Pattern</span></span>

<span data-ttu-id="a199a-2355">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2355">10 letters or digits:</span></span>
- <span data-ttu-id="a199a-2356">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-2357">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2357">Four digits</span></span> 
- <span data-ttu-id="a199a-2358">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="a199a-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2359">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2359">Checksum</span></span>

<span data-ttu-id="a199a-2360">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2361">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2361">Definition</span></span>

<span data-ttu-id="a199a-2362">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2363">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2364">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="a199a-2365">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="a199a-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="a199a-2368">Número de cuenta permanente</span><span class="sxs-lookup"><span data-stu-id="a199a-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="a199a-2369">MANO</span><span class="sxs-lookup"><span data-stu-id="a199a-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="a199a-2370">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="a199a-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2371">Format</span></span>

<span data-ttu-id="a199a-2372">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="a199a-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2373">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2373">Pattern</span></span>

<span data-ttu-id="a199a-2374">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2374">12 digits:</span></span>
- <span data-ttu-id="a199a-2375">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2375">Four digits</span></span> 
- <span data-ttu-id="a199a-2376">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="a199a-2376">An optional space or dash</span></span> 
- <span data-ttu-id="a199a-2377">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2377">Four digits</span></span> 
- <span data-ttu-id="a199a-2378">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="a199a-2378">An optional space or dash</span></span> 
- <span data-ttu-id="a199a-2379">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="a199a-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2380">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2380">Checksum</span></span>

<span data-ttu-id="a199a-2381">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2382">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2382">Definition</span></span>

<span data-ttu-id="a199a-2383">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-2384">Se encuentra una palabra clave de Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="a199a-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="a199a-2385">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2385">The checksum passes.</span></span>
<span data-ttu-id="a199a-2386">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-2387">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a199a-2388">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="a199a-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="a199a-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="a199a-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="a199a-2390">Aadhar</span></span>
- <span data-ttu-id="a199a-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="a199a-2391">Aadhaar</span></span>
- <span data-ttu-id="a199a-2392">UID</span><span class="sxs-lookup"><span data-stu-id="a199a-2392">UID</span></span>
- <span data-ttu-id="a199a-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="a199a-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="a199a-2394">Número de tarjeta de identidad (KTP) de Indonesia</span><span class="sxs-lookup"><span data-stu-id="a199a-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2395">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2395">Format</span></span>

<span data-ttu-id="a199a-2396">16 dígitos que contienen puntos opcionales</span><span class="sxs-lookup"><span data-stu-id="a199a-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2397">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2397">Pattern</span></span>

<span data-ttu-id="a199a-2398">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2398">16 digits:</span></span>
- <span data-ttu-id="a199a-2399">Código de la provincia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2399">Two-digit province code</span></span> 
- <span data-ttu-id="a199a-2400">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2400">A period (optional)</span></span> 
- <span data-ttu-id="a199a-2401">Código de ciudad o regencia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="a199a-2402">Código de subdistrito de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="a199a-2403">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2403">A period (optional)</span></span> 
- <span data-ttu-id="a199a-2404">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a199a-2405">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2405">A period (optional)</span></span> 
- <span data-ttu-id="a199a-2406">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2407">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2407">Checksum</span></span>

<span data-ttu-id="a199a-2408">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2409">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2409">Definition</span></span>

<span data-ttu-id="a199a-2410">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2411">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2412">Se encuentra una palabra clave de Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="a199a-2413">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2414">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2415">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="a199a-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="a199a-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="a199a-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="a199a-2417">KTP</span></span>
- <span data-ttu-id="a199a-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="a199a-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="a199a-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="a199a-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="a199a-2420">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a199a-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2421">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2421">Format</span></span>

<span data-ttu-id="a199a-2422">Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)
</span><span class="sxs-lookup"><span data-stu-id="a199a-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2423">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2423">Pattern</span></span>

<span data-ttu-id="a199a-2424">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a199a-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="a199a-2425">Código de país de dos letras</span><span class="sxs-lookup"><span data-stu-id="a199a-2425">Two-letter country code</span></span>
- <span data-ttu-id="a199a-2426">Dos dígitos de control (seguidos de un espacio opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="a199a-2427">1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)</span><span class="sxs-lookup"><span data-stu-id="a199a-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="a199a-2428">1-3 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2428">1-3 letters or digits</span></span>

<span data-ttu-id="a199a-p135">El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:</span><span class="sxs-lookup"><span data-stu-id="a199a-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="a199a-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="a199a-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2432">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2432">Checksum</span></span>

<span data-ttu-id="a199a-2433">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2434">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2434">Definition</span></span>

<span data-ttu-id="a199a-2435">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2436">La función Func_iban encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2437">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2438">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2438">Keywords</span></span>

<span data-ttu-id="a199a-2439">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a199a-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="a199a-2440">dirección IP</span><span class="sxs-lookup"><span data-stu-id="a199a-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2441">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="a199a-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="a199a-2442">IPv4:</span></span>
<span data-ttu-id="a199a-2443">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="a199a-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="a199a-2444">Protocolo</span><span class="sxs-lookup"><span data-stu-id="a199a-2444">IPv6:</span></span>
<span data-ttu-id="a199a-2445"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="a199a-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2446">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2447">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2447">Checksum</span></span>

<span data-ttu-id="a199a-2448">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2449">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2449">Definition</span></span>

<span data-ttu-id="a199a-2450">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2451">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2452">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="a199a-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a199a-2453">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2454">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2455">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="a199a-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a199a-2456">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2457">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2458">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="a199a-2458">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2459">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="a199a-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="a199a-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="a199a-2461">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="a199a-2462">dirección IP</span><span class="sxs-lookup"><span data-stu-id="a199a-2462">ip address</span></span> 
- <span data-ttu-id="a199a-2463">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="a199a-2463">ip addresses</span></span>
- <span data-ttu-id="a199a-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="a199a-2464">internet protocol</span></span>
- <span data-ttu-id="a199a-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="a199a-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="a199a-2466">Clasificación Internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="a199a-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2467">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2467">Format</span></span>

<span data-ttu-id="a199a-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="a199a-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2469">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2469">Pattern</span></span>

<span data-ttu-id="a199a-2470">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2471">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2471">Checksum</span></span>

<span data-ttu-id="a199a-2472">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2473">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2473">Definition</span></span>

<span data-ttu-id="a199a-2474">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2475">Se encuentra una palabra clave de Dictionary_icd_10_updated.</span><span class="sxs-lookup"><span data-stu-id="a199a-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="a199a-2476">Se encuentra una palabra clave de Dictionary_icd_10_codes.</span><span class="sxs-lookup"><span data-stu-id="a199a-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="a199a-2477">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2478">Se encuentra una palabra clave de Dictionary_icd_10_ actualizada.</span><span class="sxs-lookup"><span data-stu-id="a199a-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="a199a-2479">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2479">Keywords</span></span>

<span data-ttu-id="a199a-2480">Cualquier término del Diccionario de palabras clave de Dictionary_icd_10_updated, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="a199a-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="a199a-2481">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="a199a-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="a199a-2482">Cualquier término del Diccionario de palabras clave de Dictionary_icd_10_codes, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="a199a-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="a199a-2483">Este tipo busca sólo los códigos de seguros, no la descripción.</span><span class="sxs-lookup"><span data-stu-id="a199a-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="a199a-2484">Clasificación Internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="a199a-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2485">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2485">Format</span></span>

<span data-ttu-id="a199a-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="a199a-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2487">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2487">Pattern</span></span>

<span data-ttu-id="a199a-2488">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2489">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2489">Checksum</span></span>

<span data-ttu-id="a199a-2490">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2491">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2491">Definition</span></span>

<span data-ttu-id="a199a-2492">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2493">Se encuentra una palabra clave de Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="a199a-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="a199a-2494">Se encuentra una palabra clave de Dictionary_icd_9_codes.</span><span class="sxs-lookup"><span data-stu-id="a199a-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="a199a-2495">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2496">Se encuentra una palabra clave de Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="a199a-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2497">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2497">Keywords</span></span>

<span data-ttu-id="a199a-2498">Cualquier término del Diccionario de palabras clave de Dictionary_icd_9_updated, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="a199a-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="a199a-2499">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="a199a-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="a199a-2500">Cualquier término del Diccionario de palabras clave de Dictionary_icd_9_codes, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="a199a-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="a199a-2501">Este tipo busca sólo los códigos de seguros, no la descripción.</span><span class="sxs-lookup"><span data-stu-id="a199a-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="a199a-2502">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="a199a-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2503">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2503">Format</span></span>

<span data-ttu-id="a199a-2504">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="a199a-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a199a-2505">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="a199a-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="a199a-2506">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="a199a-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a199a-2507">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="a199a-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2508">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2508">Pattern</span></span>

<span data-ttu-id="a199a-2509">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="a199a-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a199a-2510">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2510">Seven digits</span></span> 
- <span data-ttu-id="a199a-2511">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="a199a-2512">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="a199a-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a199a-2513">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2513">Seven digits</span></span> 
- <span data-ttu-id="a199a-2514">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="a199a-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="a199a-2515">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2516">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2516">Checksum</span></span>

<span data-ttu-id="a199a-2517">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2518">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2518">Definition</span></span>

<span data-ttu-id="a199a-2519">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2520">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2521">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-2521">One of the following is true:</span></span>
    - <span data-ttu-id="a199a-2522">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="a199a-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="a199a-2523">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-2524">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2524">The checksum passes.</span></span>

<span data-ttu-id="a199a-2525">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2526">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2527">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2527">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="a199a-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="a199a-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="a199a-2530">Número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="a199a-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="a199a-2531">Número de PPS</span><span class="sxs-lookup"><span data-stu-id="a199a-2531">PPS Number</span></span> 
- <span data-ttu-id="a199a-2532">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="a199a-2532">PPS Num</span></span> 
- <span data-ttu-id="a199a-2533">N.º PPS</span><span class="sxs-lookup"><span data-stu-id="a199a-2533">PPS No.</span></span> 
- <span data-ttu-id="a199a-2534">N.ro PPS</span><span class="sxs-lookup"><span data-stu-id="a199a-2534">PPS #</span></span> 
- <span data-ttu-id="a199a-2535">PPS #</span><span class="sxs-lookup"><span data-stu-id="a199a-2535">PPS#</span></span> 
- <span data-ttu-id="a199a-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="a199a-2536">PPSN</span></span> 
- <span data-ttu-id="a199a-2537">Tarjeta de servicios públicos</span><span class="sxs-lookup"><span data-stu-id="a199a-2537">Public Services Card</span></span> 
- <span data-ttu-id="a199a-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="a199a-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="a199a-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="a199a-2539">Uimh.</span></span> <span data-ttu-id="a199a-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="a199a-2540">PSP</span></span> 
- <span data-ttu-id="a199a-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="a199a-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="a199a-2542">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="a199a-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2543">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2543">Format</span></span>

<span data-ttu-id="a199a-2544">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2545">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2545">Pattern</span></span>

<span data-ttu-id="a199a-2546">Con formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2546">Formatted:</span></span>
- <span data-ttu-id="a199a-2547">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2547">Two digits</span></span> 
- <span data-ttu-id="a199a-2548">Guion</span><span class="sxs-lookup"><span data-stu-id="a199a-2548">A dash</span></span> 
- <span data-ttu-id="a199a-2549">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2549">Three digits</span></span> 
- <span data-ttu-id="a199a-2550">Guion</span><span class="sxs-lookup"><span data-stu-id="a199a-2550">A dash</span></span> 
- <span data-ttu-id="a199a-2551">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2551">Eight digits</span></span>

<span data-ttu-id="a199a-2552">Sin formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2552">Unformatted:</span></span>
- <span data-ttu-id="a199a-2553">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2554">Checksum</span></span>

<span data-ttu-id="a199a-2555">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2556">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2556">Definition</span></span>

<span data-ttu-id="a199a-2557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2558">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2559">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="a199a-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="a199a-2562">Número de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="a199a-2562">Bank Account Number</span></span> 
- <span data-ttu-id="a199a-2563">Cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="a199a-2563">Bank Account</span></span> 
- <span data-ttu-id="a199a-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2564">Account Number</span></span> 
- <span data-ttu-id="a199a-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="a199a-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="a199a-2566">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="a199a-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2567">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2567">Format</span></span>

<span data-ttu-id="a199a-2568">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2569">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2569">Pattern</span></span>

<span data-ttu-id="a199a-2570">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2571">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2571">Checksum</span></span>

<span data-ttu-id="a199a-2572">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2573">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2573">Definition</span></span>

<span data-ttu-id="a199a-2574">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2575">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2576">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="a199a-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="a199a-2577">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2577">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2578">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="a199a-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="a199a-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="a199a-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="a199a-2580">מספר זהות</span></span> 
- <span data-ttu-id="a199a-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="a199a-2582">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="a199a-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2583">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2583">Format</span></span>

<span data-ttu-id="a199a-2584">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2585">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2585">Pattern</span></span>

- <span data-ttu-id="a199a-2586">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="a199a-2587">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-2588">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-2589">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="a199a-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="a199a-2590">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2591">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2591">Checksum</span></span>

<span data-ttu-id="a199a-2592">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2593">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2593">Definition</span></span>

<span data-ttu-id="a199a-2594">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2595">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2596">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2597">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="a199a-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="a199a-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="a199a-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="a199a-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="a199a-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="a199a-2601">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="a199a-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2602">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2602">Format</span></span>

<span data-ttu-id="a199a-2603">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2604">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2604">Pattern</span></span>

<span data-ttu-id="a199a-2605">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="a199a-2605">Bank account number:</span></span>
- <span data-ttu-id="a199a-2606">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2606">Seven or eight digits</span></span>
- <span data-ttu-id="a199a-2607">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="a199a-2607">Bank account branch code:</span></span>
- <span data-ttu-id="a199a-2608">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2608">Four digits</span></span> 
- <span data-ttu-id="a199a-2609">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="a199a-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="a199a-2610">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2610">Three digits</span></span>

<span data-ttu-id="a199a-2611">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2611">Checksum</span></span>

<span data-ttu-id="a199a-2612">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2613">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2613">Definition</span></span>

<span data-ttu-id="a199a-2614">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2615">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2616">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="a199a-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="a199a-2617">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-2617">One of the following is true:</span></span>
- <span data-ttu-id="a199a-2618">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2619">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="a199a-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="a199a-2620">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2621">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2622">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="a199a-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2623">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="a199a-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="a199a-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="a199a-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2625">Checking Account Number</span></span> 
- <span data-ttu-id="a199a-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="a199a-2626">Checking Account</span></span> 
- <span data-ttu-id="a199a-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-2627">Checking Account #</span></span> 
- <span data-ttu-id="a199a-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="a199a-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-2629">Checking Acct #</span></span> 
- <span data-ttu-id="a199a-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="a199a-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2631">Checking Account No.</span></span> 
- <span data-ttu-id="a199a-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2632">Bank Account Number</span></span> 
- <span data-ttu-id="a199a-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="a199a-2633">Bank Account</span></span> 
- <span data-ttu-id="a199a-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-2634">Bank Account #</span></span> 
- <span data-ttu-id="a199a-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="a199a-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-2636">Bank Acct #</span></span> 
- <span data-ttu-id="a199a-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="a199a-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2638">Bank Account No.</span></span> 
- <span data-ttu-id="a199a-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2639">Savings Account Number</span></span> 
- <span data-ttu-id="a199a-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="a199a-2640">Savings Account</span></span> 
- <span data-ttu-id="a199a-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-2641">Savings Account #</span></span> 
- <span data-ttu-id="a199a-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="a199a-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-2643">Savings Acct #</span></span> 
- <span data-ttu-id="a199a-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="a199a-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2645">Savings Account No.</span></span> 
- <span data-ttu-id="a199a-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2646">Debit Account Number</span></span> 
- <span data-ttu-id="a199a-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="a199a-2647">Debit Account</span></span> 
- <span data-ttu-id="a199a-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-2648">Debit Account #</span></span> 
- <span data-ttu-id="a199a-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="a199a-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-2650">Debit Acct #</span></span> 
- <span data-ttu-id="a199a-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="a199a-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2652">Debit Account No.</span></span> 
- <span data-ttu-id="a199a-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="a199a-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="a199a-2654">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="a199a-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="a199a-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="a199a-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="a199a-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="a199a-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="a199a-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="a199a-2657">口座番号の確認</span></span> 
- <span data-ttu-id="a199a-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2658">銀行口座番号</span></span> 
- <span data-ttu-id="a199a-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="a199a-2659">銀行口座</span></span> 
- <span data-ttu-id="a199a-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2660">銀行口座＃</span></span> 
- <span data-ttu-id="a199a-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="a199a-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="a199a-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="a199a-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="a199a-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2664">銀行口座番号</span></span>
- <span data-ttu-id="a199a-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="a199a-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="a199a-2666">預金口座</span></span> 
- <span data-ttu-id="a199a-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="a199a-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="a199a-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="a199a-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="a199a-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="a199a-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="a199a-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="a199a-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2673">口座番号</span></span> 
- <span data-ttu-id="a199a-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2674">口座番号＃</span></span> 
- <span data-ttu-id="a199a-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="a199a-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="a199a-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="a199a-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="a199a-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="a199a-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="a199a-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="a199a-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="a199a-2681">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="a199a-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2682">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2682">Format</span></span>

<span data-ttu-id="a199a-2683">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2684">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2684">Pattern</span></span>

<span data-ttu-id="a199a-2685">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2686">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2686">Checksum</span></span>

<span data-ttu-id="a199a-2687">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2688">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2688">Definition</span></span>

<span data-ttu-id="a199a-2689">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2690">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2691">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2692">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="a199a-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="a199a-2694">listas #</span><span class="sxs-lookup"><span data-stu-id="a199a-2694">dl#</span></span> 
- <span data-ttu-id="a199a-2695">LISTAS</span><span class="sxs-lookup"><span data-stu-id="a199a-2695">DL＃</span></span> 
- <span data-ttu-id="a199a-2696">distribución #</span><span class="sxs-lookup"><span data-stu-id="a199a-2696">dls#</span></span> 
- <span data-ttu-id="a199a-2697">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="a199a-2697">DLS＃</span></span> 
- <span data-ttu-id="a199a-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="a199a-2698">driver license</span></span> 
- <span data-ttu-id="a199a-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2699">driver licenses</span></span> 
- <span data-ttu-id="a199a-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="a199a-2700">drivers license</span></span> 
- <span data-ttu-id="a199a-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="a199a-2701">driver's license</span></span> 
- <span data-ttu-id="a199a-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2702">drivers licenses</span></span> 
- <span data-ttu-id="a199a-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-2703">driver's licenses</span></span> 
- <span data-ttu-id="a199a-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="a199a-2704">driving licence</span></span> 
- <span data-ttu-id="a199a-2705">Lic #</span><span class="sxs-lookup"><span data-stu-id="a199a-2705">lic#</span></span> 
- <span data-ttu-id="a199a-2706">Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-2706">LIC＃</span></span> 
- <span data-ttu-id="a199a-2707">conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-2707">lics#</span></span> 
- <span data-ttu-id="a199a-2708">state id</span><span class="sxs-lookup"><span data-stu-id="a199a-2708">state id</span></span> 
- <span data-ttu-id="a199a-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="a199a-2709">state identification</span></span> 
- <span data-ttu-id="a199a-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="a199a-2710">state identification number</span></span> 
- <span data-ttu-id="a199a-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2711">低所得国＃</span></span> 
- <span data-ttu-id="a199a-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="a199a-2712">免許証</span></span> 
- <span data-ttu-id="a199a-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="a199a-2713">状態ID</span></span>
- <span data-ttu-id="a199a-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="a199a-2714">状態の識別</span></span> 
- <span data-ttu-id="a199a-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2715">状態の識別番号</span></span> 
- <span data-ttu-id="a199a-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="a199a-2716">運転免許</span></span> 
- <span data-ttu-id="a199a-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a199a-2717">運転免許証</span></span> 
- <span data-ttu-id="a199a-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="a199a-2719">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="a199a-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2720">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2720">Format</span></span>

<span data-ttu-id="a199a-2721">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2722">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2722">Pattern</span></span>

<span data-ttu-id="a199a-2723">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2724">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2724">Checksum</span></span>

<span data-ttu-id="a199a-2725">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2726">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2726">Definition</span></span>

<span data-ttu-id="a199a-2727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2728">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2729">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2730">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="a199a-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="a199a-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="a199a-2732">パスポート</span></span> 
- <span data-ttu-id="a199a-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2733">パスポート番号</span></span> 
- <span data-ttu-id="a199a-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a199a-2734">パスポートのNum</span></span> 
- <span data-ttu-id="a199a-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a199a-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="a199a-2736">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="a199a-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2737">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2737">Format</span></span>

<span data-ttu-id="a199a-2738">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2739">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2739">Pattern</span></span>

<span data-ttu-id="a199a-2740">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2741">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2741">Checksum</span></span>

<span data-ttu-id="a199a-2742">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2743">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2743">Definition</span></span>

<span data-ttu-id="a199a-2744">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2745">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2746">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2747">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="a199a-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="a199a-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2749">Resident Registration Number</span></span>
- <span data-ttu-id="a199a-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2750">Resident Register Number</span></span> 
- <span data-ttu-id="a199a-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="a199a-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="a199a-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2753">Resident Register No.</span></span> 
- <span data-ttu-id="a199a-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="a199a-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="a199a-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="a199a-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="a199a-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="a199a-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="a199a-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="a199a-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="a199a-2760">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="a199a-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2761">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2761">Format</span></span>

<span data-ttu-id="a199a-2762">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2763">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2763">Pattern</span></span>

<span data-ttu-id="a199a-2764">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2764">7-12 digits:</span></span>
- <span data-ttu-id="a199a-2765">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2765">Four digits</span></span> 
- <span data-ttu-id="a199a-2766">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="a199a-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="a199a-2767">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="a199a-2767">Six digits OR</span></span>
- <span data-ttu-id="a199a-2768">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2769">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2769">Checksum</span></span>

<span data-ttu-id="a199a-2770">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2771">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2771">Definition</span></span>

<span data-ttu-id="a199a-2772">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2773">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2774">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="a199a-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="a199a-2775">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2776">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2777">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="a199a-2777">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2778">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="a199a-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="a199a-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="a199a-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="a199a-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="a199a-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="a199a-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="a199a-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="a199a-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="a199a-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="a199a-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="a199a-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="a199a-2785">Número de tarjeta de residencia japonés</span><span class="sxs-lookup"><span data-stu-id="a199a-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2786">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2786">Format</span></span>

<span data-ttu-id="a199a-2787">12 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2788">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2788">Pattern</span></span>

<span data-ttu-id="a199a-2789">12 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2789">12 letters and digits:</span></span>
- <span data-ttu-id="a199a-2790">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="a199a-2791">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2791">Eight digits</span></span> 
- <span data-ttu-id="a199a-2792">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2793">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2793">Checksum</span></span>

<span data-ttu-id="a199a-2794">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2795">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2795">Definition</span></span>

<span data-ttu-id="a199a-2796">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2797">La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2798">Se encuentra una palabra clave de Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2799">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="a199a-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="a199a-2801">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="a199a-2801">Residence card number</span></span>
- <span data-ttu-id="a199a-2802">Nº de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="a199a-2802">Residence card no</span></span>
- <span data-ttu-id="a199a-2803">Tarjeta de residencia #</span><span class="sxs-lookup"><span data-stu-id="a199a-2803">Residence card #</span></span>
- <span data-ttu-id="a199a-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="a199a-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="a199a-2805">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="a199a-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2806">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2806">Format</span></span>

<span data-ttu-id="a199a-2807">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="a199a-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2808">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2808">Pattern</span></span>

<span data-ttu-id="a199a-2809">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2809">12 digits:</span></span>
- <span data-ttu-id="a199a-2810">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a199a-2811">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2811">A dash (optional)</span></span> 
- <span data-ttu-id="a199a-2812">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="a199a-2813">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2813">A dash (optional)</span></span> 
- <span data-ttu-id="a199a-2814">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="a199a-2814">Three random digits</span></span> 
- <span data-ttu-id="a199a-2815">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2816">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2816">Checksum</span></span>

<span data-ttu-id="a199a-2817">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2818">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2818">Definition</span></span>

<span data-ttu-id="a199a-2819">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2820">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2821">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2822">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="a199a-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="a199a-2824">tarjeta de aplicación digital</span><span class="sxs-lookup"><span data-stu-id="a199a-2824">digital application card</span></span>
- <span data-ttu-id="a199a-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="a199a-2825">i/c</span></span>
- <span data-ttu-id="a199a-2826">i/c no</span><span class="sxs-lookup"><span data-stu-id="a199a-2826">i/c no</span></span>
- <span data-ttu-id="a199a-2827">i</span><span class="sxs-lookup"><span data-stu-id="a199a-2827">ic</span></span>
- <span data-ttu-id="a199a-2828">no IC</span><span class="sxs-lookup"><span data-stu-id="a199a-2828">ic no</span></span>
- <span data-ttu-id="a199a-2829">id card</span><span class="sxs-lookup"><span data-stu-id="a199a-2829">id card</span></span>
- <span data-ttu-id="a199a-2830">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-2830">identification Card</span></span>
- <span data-ttu-id="a199a-2831">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-2831">identity card</span></span>
- <span data-ttu-id="a199a-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="a199a-2832">k/p</span></span>
- <span data-ttu-id="a199a-2833">k/p no</span><span class="sxs-lookup"><span data-stu-id="a199a-2833">k/p no</span></span>
- <span data-ttu-id="a199a-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="a199a-2834">kad akuan diri</span></span>
- <span data-ttu-id="a199a-2835">Kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="a199a-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="a199a-2836">Kad pengenalan Malasia</span><span class="sxs-lookup"><span data-stu-id="a199a-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="a199a-2837">PK</span><span class="sxs-lookup"><span data-stu-id="a199a-2837">kp</span></span>
- <span data-ttu-id="a199a-2838">KP no</span><span class="sxs-lookup"><span data-stu-id="a199a-2838">kp no</span></span>
- <span data-ttu-id="a199a-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="a199a-2839">mykad</span></span>
- <span data-ttu-id="a199a-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="a199a-2840">mykas</span></span>
- <span data-ttu-id="a199a-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="a199a-2841">mykid</span></span>
- <span data-ttu-id="a199a-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="a199a-2842">mypr</span></span>
- <span data-ttu-id="a199a-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="a199a-2843">mytentera</span></span>
- <span data-ttu-id="a199a-2844">tarjeta de identidad de Malasia</span><span class="sxs-lookup"><span data-stu-id="a199a-2844">malaysia identity card</span></span>
- <span data-ttu-id="a199a-2845">tarjeta de identidad malasio</span><span class="sxs-lookup"><span data-stu-id="a199a-2845">malaysian identity card</span></span>
- <span data-ttu-id="a199a-2846">nric</span><span class="sxs-lookup"><span data-stu-id="a199a-2846">nric</span></span>
- <span data-ttu-id="a199a-2847">tarjeta de identificación personal</span><span class="sxs-lookup"><span data-stu-id="a199a-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="a199a-2848">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="a199a-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2849">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2849">Format</span></span>

<span data-ttu-id="a199a-2850">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="a199a-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2851">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2851">Pattern</span></span>

<span data-ttu-id="a199a-2852">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2852">8-9 digits:</span></span>
- <span data-ttu-id="a199a-2853">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2853">Three digits</span></span> 
- <span data-ttu-id="a199a-2854">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2854">A space (optional)</span></span> 
- <span data-ttu-id="a199a-2855">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2855">Three digits</span></span> 
- <span data-ttu-id="a199a-2856">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="a199a-2856">A space (optional)</span></span> 
- <span data-ttu-id="a199a-2857">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2858">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2858">Checksum</span></span>

<span data-ttu-id="a199a-2859">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2860">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2860">Definition</span></span>

<span data-ttu-id="a199a-2861">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2862">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2863">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="a199a-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="a199a-2864">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-2865">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2865">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2866">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="a199a-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="a199a-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="a199a-2868">Número de servicio de ciudadanía</span><span class="sxs-lookup"><span data-stu-id="a199a-2868">Citizen service number</span></span> 
- <span data-ttu-id="a199a-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="a199a-2869">BSN</span></span> 
- <span data-ttu-id="a199a-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="a199a-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2871">Sofinummer</span></span> 
- <span data-ttu-id="a199a-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="a199a-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="a199a-2874">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="a199a-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2875">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2875">Format</span></span>

<span data-ttu-id="a199a-2876">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2877">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2877">Pattern</span></span>

<span data-ttu-id="a199a-2878">Tres letras (no distingue entre mayúsculas y minúsculas), un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2879">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2879">Checksum</span></span>

<span data-ttu-id="a199a-2880">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2881">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2881">Definition</span></span>

<span data-ttu-id="a199a-2882">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2883">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2884">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="a199a-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="a199a-2885">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2885">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="a199a-2886">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2886">Keywords</span></span>

<span data-ttu-id="a199a-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="a199a-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="a199a-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="a199a-2888">NHI</span></span> 
- <span data-ttu-id="a199a-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="a199a-2889">New Zealand</span></span> 
- <span data-ttu-id="a199a-2890">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-2890">Health</span></span> 
- <span data-ttu-id="a199a-2891">régimen</span><span class="sxs-lookup"><span data-stu-id="a199a-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="a199a-2892">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="a199a-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2893">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2893">Format</span></span>

<span data-ttu-id="a199a-2894">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2895">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2895">Pattern</span></span>

<span data-ttu-id="a199a-2896">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2896">11 digits:</span></span>
- <span data-ttu-id="a199a-2897">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a199a-2898">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="a199a-2899">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="a199a-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2900">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2900">Checksum</span></span>

<span data-ttu-id="a199a-2901">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2902">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2902">Definition</span></span>

<span data-ttu-id="a199a-2903">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2904">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2905">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="a199a-2906">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2906">The checksum passes.</span></span>
- <span data-ttu-id="a199a-2907">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2908">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2909">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2909">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2910">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="a199a-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="a199a-2912">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="a199a-2912">Personal identification number</span></span>
- <span data-ttu-id="a199a-2913">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="a199a-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="a199a-2914">Número de id.</span><span class="sxs-lookup"><span data-stu-id="a199a-2914">ID Number</span></span>
- <span data-ttu-id="a199a-2915">Determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-2915">Identification</span></span>
- <span data-ttu-id="a199a-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2916">Personnummer</span></span>
- <span data-ttu-id="a199a-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="a199a-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="a199a-2918">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="a199a-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2919">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2919">Format</span></span>

<span data-ttu-id="a199a-2920">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="a199a-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2921">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2921">Pattern</span></span>

<span data-ttu-id="a199a-2922">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-2922">12 digits:</span></span>
- <span data-ttu-id="a199a-2923">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2923">Four digits</span></span> 
- <span data-ttu-id="a199a-2924">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-2924">A hyphen</span></span> 
- <span data-ttu-id="a199a-2925">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-2925">Seven digits</span></span> 
- <span data-ttu-id="a199a-2926">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-2926">A hyphen</span></span> 
- <span data-ttu-id="a199a-2927">Un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2928">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2928">Checksum</span></span>

<span data-ttu-id="a199a-2929">No</span><span class="sxs-lookup"><span data-stu-id="a199a-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2930">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2930">Definition</span></span>

<span data-ttu-id="a199a-2931">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2932">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2933">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2934">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="a199a-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="a199a-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="a199a-2936">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="a199a-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="a199a-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="a199a-2937">UMID</span></span> 
- <span data-ttu-id="a199a-2938">Tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-2938">Identity Card</span></span> 
- <span data-ttu-id="a199a-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="a199a-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="a199a-2940">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="a199a-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2941">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2941">Format</span></span>

<span data-ttu-id="a199a-2942">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2943">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2943">Pattern</span></span>

<span data-ttu-id="a199a-2944">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2945">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2945">Checksum</span></span>

<span data-ttu-id="a199a-2946">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2947">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2947">Definition</span></span>

<span data-ttu-id="a199a-2948">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_polish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="a199a-2949">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="a199a-2950">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2951">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="a199a-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a199a-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="a199a-2953">Dowód osobisty</span></span>
- <span data-ttu-id="a199a-2954">Numerar dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a199a-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="a199a-2955">Nazwa i número dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a199a-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="a199a-2956">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a199a-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="a199a-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="a199a-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="a199a-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="a199a-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="a199a-2959">Dow.</span><span class="sxs-lookup"><span data-stu-id="a199a-2959">dow.</span></span> <span data-ttu-id="a199a-2960">MacOS.</span><span class="sxs-lookup"><span data-stu-id="a199a-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="a199a-2961">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a199a-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2962">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2962">Format</span></span>

<span data-ttu-id="a199a-2963">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2964">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2964">Pattern</span></span>

<span data-ttu-id="a199a-2965">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2966">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2966">Checksum</span></span>

<span data-ttu-id="a199a-2967">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2968">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2968">Definition</span></span>

<span data-ttu-id="a199a-2969">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2970">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2971">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="a199a-2972">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2973">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="a199a-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="a199a-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="a199a-2975">Nr PESEL</span></span>
- <span data-ttu-id="a199a-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="a199a-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="a199a-2977">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="a199a-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2978">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2978">Format</span></span>

<span data-ttu-id="a199a-2979">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2980">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2980">Pattern</span></span>

<span data-ttu-id="a199a-2981">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-2982">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-2982">Checksum</span></span>

<span data-ttu-id="a199a-2983">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-2984">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-2984">Definition</span></span>

<span data-ttu-id="a199a-2985">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-2986">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-2987">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="a199a-2988">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-2988">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="a199a-2989">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="a199a-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a199a-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a199a-2991">Números paszportu</span><span class="sxs-lookup"><span data-stu-id="a199a-2991">Numer paszportu</span></span>
- <span data-ttu-id="a199a-2992">Nº.</span><span class="sxs-lookup"><span data-stu-id="a199a-2992">Nr.</span></span> <span data-ttu-id="a199a-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="a199a-2993">Paszportu</span></span>
- <span data-ttu-id="a199a-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="a199a-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="a199a-2995">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="a199a-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-2996">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-2996">Format</span></span>

<span data-ttu-id="a199a-2997">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-2998">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-2998">Pattern</span></span>

<span data-ttu-id="a199a-2999">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3000">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3000">Checksum</span></span>

<span data-ttu-id="a199a-3001">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3002">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3002">Definition</span></span>

<span data-ttu-id="a199a-3003">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3004">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3005">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="a199a-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3006">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="a199a-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="a199a-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="a199a-3008">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="a199a-3008">Citizen Card</span></span>
- <span data-ttu-id="a199a-3009">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-3009">National ID Card</span></span>
- <span data-ttu-id="a199a-3010">CC</span><span class="sxs-lookup"><span data-stu-id="a199a-3010">CC</span></span>
- <span data-ttu-id="a199a-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="a199a-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="a199a-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="a199a-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="a199a-3013">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="a199a-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3014">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3014">Format</span></span>

<span data-ttu-id="a199a-3015">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3016">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3016">Pattern</span></span>

<span data-ttu-id="a199a-3017">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3018">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3018">Checksum</span></span>

<span data-ttu-id="a199a-3019">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3020">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3020">Definition</span></span>

<span data-ttu-id="a199a-3021">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3022">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3023">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3024">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="a199a-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="a199a-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="a199a-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="a199a-3026">Identification Card</span></span> 
- <span data-ttu-id="a199a-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="a199a-3027">I card number</span></span> 
- <span data-ttu-id="a199a-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="a199a-3028">ID number</span></span> 
- <span data-ttu-id="a199a-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="a199a-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="a199a-3030">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="a199a-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3031">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3031">Format</span></span>

<span data-ttu-id="a199a-3032">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3033">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3033">Pattern</span></span>

- <span data-ttu-id="a199a-3034">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="a199a-3035">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-3036">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-3036">Seven digits</span></span> 
- <span data-ttu-id="a199a-3037">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="a199a-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3038">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3038">Checksum</span></span>

<span data-ttu-id="a199a-3039">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3040">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3040">Definition</span></span>

<span data-ttu-id="a199a-3041">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3042">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3043">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="a199a-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="a199a-3044">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3044">The checksum passes.</span></span>

<span data-ttu-id="a199a-3045">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3046">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3047">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3047">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3048">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="a199a-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="a199a-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="a199a-3050">Tarjeta de identidad de registro nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="a199a-3051">Número de tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-3051">Identity Card Number</span></span> 
- <span data-ttu-id="a199a-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="a199a-3052">NRIC</span></span> 
- <span data-ttu-id="a199a-3053">I</span><span class="sxs-lookup"><span data-stu-id="a199a-3053">IC</span></span> 
- <span data-ttu-id="a199a-3054">Número de identificación de extranjeros</span><span class="sxs-lookup"><span data-stu-id="a199a-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="a199a-3055">AC</span><span class="sxs-lookup"><span data-stu-id="a199a-3055">FIN</span></span> 
- <span data-ttu-id="a199a-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="a199a-3056">身份证</span></span> 
- <span data-ttu-id="a199a-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="a199a-3058">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="a199a-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3059">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3059">Format</span></span>

<span data-ttu-id="a199a-3060">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3061">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3061">Pattern</span></span>

<span data-ttu-id="a199a-3062">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3062">13 digits:</span></span>
- <span data-ttu-id="a199a-3063">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a199a-3064">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3064">Four digits</span></span> 
- <span data-ttu-id="a199a-3065">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="a199a-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="a199a-3066">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="a199a-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="a199a-3067">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3068">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3068">Checksum</span></span>

<span data-ttu-id="a199a-3069">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3070">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3070">Definition</span></span>

<span data-ttu-id="a199a-3071">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3072">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3073">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="a199a-3074">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3075">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="a199a-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="a199a-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="a199a-3077">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="a199a-3077">Identity card</span></span>
- <span data-ttu-id="a199a-3078">ID</span><span class="sxs-lookup"><span data-stu-id="a199a-3078">ID</span></span>
- <span data-ttu-id="a199a-3079">Determinación</span><span class="sxs-lookup"><span data-stu-id="a199a-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="a199a-3080">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="a199a-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3081">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3081">Format</span></span>

<span data-ttu-id="a199a-3082">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="a199a-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3083">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3083">Pattern</span></span>

<span data-ttu-id="a199a-3084">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3084">13 digits:</span></span>
- <span data-ttu-id="a199a-3085">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="a199a-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a199a-3086">Un guión </span><span class="sxs-lookup"><span data-stu-id="a199a-3086">A hyphen</span></span> 
- <span data-ttu-id="a199a-3087">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="a199a-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="a199a-3088">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="a199a-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="a199a-3089">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="a199a-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="a199a-3090">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="a199a-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3091">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3091">Checksum</span></span>

<span data-ttu-id="a199a-3092">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3093">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3093">Definition</span></span>

<span data-ttu-id="a199a-3094">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3095">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3096">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="a199a-3097">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3097">The checksum passes.</span></span>

<span data-ttu-id="a199a-3098">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3099">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3100">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3100">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3101">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="a199a-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="a199a-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="a199a-3103">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="a199a-3103">National ID card</span></span> 
- <span data-ttu-id="a199a-3104">Número de registro de ciudadano</span><span class="sxs-lookup"><span data-stu-id="a199a-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="a199a-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="a199a-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="a199a-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="a199a-3106">RRN</span></span> 
- <span data-ttu-id="a199a-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="a199a-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="a199a-3108">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="a199a-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3109">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3109">Format</span></span>

<span data-ttu-id="a199a-3110">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3111">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3111">Pattern</span></span>

<span data-ttu-id="a199a-3112">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3112">11-12 digits:</span></span>
- <span data-ttu-id="a199a-3113">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3113">Two digits</span></span> 
- <span data-ttu-id="a199a-3114">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="a199a-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="a199a-3115">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3115">7-8 digits</span></span> 
- <span data-ttu-id="a199a-3116">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="a199a-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="a199a-3117">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3118">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3118">Checksum</span></span>

<span data-ttu-id="a199a-3119">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3120">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3120">Definition</span></span>

<span data-ttu-id="a199a-3121">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3122">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3123">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3124">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3124">Keywords</span></span>

<span data-ttu-id="a199a-3125">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a199a-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="a199a-3126">Cadena de conexión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a199a-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3127">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3127">Format</span></span>

<span data-ttu-id="a199a-3128">La cadena "User ID", "User ID", "UID" o "UserId" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="a199a-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3129">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3129">Pattern</span></span>

- <span data-ttu-id="a199a-3130">La cadena "User ID", "User ID", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="a199a-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="a199a-3131">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a199a-3132">La cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula.</span><span class="sxs-lookup"><span data-stu-id="a199a-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="a199a-3133">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-3133">An equal sign (=)</span></span>
- <span data-ttu-id="a199a-3134">Cualquier carácter que no sea un signo de dólar ($), un símbolo de porcentaje (%), un símbolo mayor que (>), un símbolo de arroba (@), Comillas ("), punto y coma (;), llave izquierda ([) o corchete de apertura ({)</span><span class="sxs-lookup"><span data-stu-id="a199a-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="a199a-3135">Cualquier combinación de 7-128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="a199a-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="a199a-3136">Un punto y coma (;) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="a199a-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3137">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3137">Checksum</span></span>

<span data-ttu-id="a199a-3138">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3139">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3139">Definition</span></span>

<span data-ttu-id="a199a-3140">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3141">La expresión regular CEP_Regex_SQLServerConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3142">**No** se encuentra una palabra clave de CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="a199a-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="a199a-3143">La expresión regular CEP_PasswordPlaceHolder no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3144">La expresión regular CEP_CommonExampleKeywords no **encuentra contenido** que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3145">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="a199a-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="a199a-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="a199a-3147">Some-Password</span><span class="sxs-lookup"><span data-stu-id="a199a-3147">some-password</span></span>
- <span data-ttu-id="a199a-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="a199a-3148">somepassword</span></span>
- <span data-ttu-id="a199a-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="a199a-3149">secretPassword</span></span>
- <span data-ttu-id="a199a-3150">AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="a199a-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="a199a-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="a199a-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="a199a-3152">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-3153">Password o pwd seguida de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (\*)--o--</span><span class="sxs-lookup"><span data-stu-id="a199a-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="a199a-3154">Password o pwd seguida de:</span><span class="sxs-lookup"><span data-stu-id="a199a-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="a199a-3155">Signo de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a199a-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="a199a-3156">Símbolo menor que (<)</span><span class="sxs-lookup"><span data-stu-id="a199a-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="a199a-3157">Cualquier combinación de 1-200 caracteres que estén en mayúsculas o minúsculas, dígitos, un asterisco (\*), un guión (-), un subrayado (_) o un carácter de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="a199a-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="a199a-3158">Símbolo mayor que (>)</span><span class="sxs-lookup"><span data-stu-id="a199a-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a199a-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a199a-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a199a-3160">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="a199a-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a199a-3161">contoso</span><span class="sxs-lookup"><span data-stu-id="a199a-3161">contoso</span></span>
- <span data-ttu-id="a199a-3162">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a199a-3162">fabrikam</span></span>
- <span data-ttu-id="a199a-3163">Northwind</span><span class="sxs-lookup"><span data-stu-id="a199a-3163">northwind</span></span>
- <span data-ttu-id="a199a-3164">entorno</span><span class="sxs-lookup"><span data-stu-id="a199a-3164">sandbox</span></span>
- <span data-ttu-id="a199a-3165">onebox</span><span class="sxs-lookup"><span data-stu-id="a199a-3165">onebox</span></span>
- <span data-ttu-id="a199a-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="a199a-3166">localhost</span></span>
- <span data-ttu-id="a199a-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a199a-3167">127.0.0.1</span></span>
- <span data-ttu-id="a199a-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="a199a-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-3169">Puerto</span><span class="sxs-lookup"><span data-stu-id="a199a-3169">com</span></span>
- <span data-ttu-id="a199a-3170">s-int.</span><span class="sxs-lookup"><span data-stu-id="a199a-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a199a-3171">ADO.net</span><span class="sxs-lookup"><span data-stu-id="a199a-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="a199a-3172">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="a199a-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3173">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3173">Format</span></span>

<span data-ttu-id="a199a-3174">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="a199a-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3175">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3175">Pattern</span></span>

<span data-ttu-id="a199a-3176">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="a199a-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="a199a-3177">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="a199a-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="a199a-3178">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="a199a-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="a199a-3179">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="a199a-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="a199a-3180">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3181">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3181">Checksum</span></span>

<span data-ttu-id="a199a-3182">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3183">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3183">Definition</span></span>

<span data-ttu-id="a199a-3184">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3185">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3186">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3187">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3187">Keywords</span></span>

<span data-ttu-id="a199a-3188">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="a199a-3189">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="a199a-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3190">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3190">Format</span></span>

<span data-ttu-id="a199a-3191">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3192">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3192">Pattern</span></span>

<span data-ttu-id="a199a-3193">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3194">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3194">Checksum</span></span>

<span data-ttu-id="a199a-3195">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3196">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3196">Definition</span></span>

<span data-ttu-id="a199a-3197">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3198">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3199">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-3199">One of the following is true:</span></span>
    - <span data-ttu-id="a199a-3200">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="a199a-3201">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-3201">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3202">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="a199a-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="a199a-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="a199a-3204">visa requirements</span></span> 
- <span data-ttu-id="a199a-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="a199a-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="a199a-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="a199a-3206">Schengen visas</span></span> 
- <span data-ttu-id="a199a-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="a199a-3207">Schengen visa</span></span> 
- <span data-ttu-id="a199a-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="a199a-3208">Visa Processing</span></span> 
- <span data-ttu-id="a199a-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="a199a-3209">Visa Type</span></span> 
- <span data-ttu-id="a199a-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="a199a-3210">Single Entry</span></span> 
- <span data-ttu-id="a199a-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="a199a-3211">Multiple Entry</span></span> 
- <span data-ttu-id="a199a-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="a199a-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="a199a-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-3213">Keyword_passport</span></span>

- <span data-ttu-id="a199a-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3214">Passport Number</span></span> 
- <span data-ttu-id="a199a-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="a199a-3215">Passport No</span></span> 
- <span data-ttu-id="a199a-3216">Passport #</span><span class="sxs-lookup"><span data-stu-id="a199a-3216">Passport #</span></span> 
- <span data-ttu-id="a199a-3217">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="a199a-3217">Passport#</span></span> 
- <span data-ttu-id="a199a-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="a199a-3218">PassportID</span></span> 
- <span data-ttu-id="a199a-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="a199a-3219">Passportno</span></span> 
- <span data-ttu-id="a199a-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-3220">passportnumber</span></span> 
- <span data-ttu-id="a199a-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="a199a-3221">パスポート</span></span> 
- <span data-ttu-id="a199a-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a199a-3222">パスポート番号</span></span> 
- <span data-ttu-id="a199a-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a199a-3223">パスポートのNum</span></span> 
- <span data-ttu-id="a199a-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a199a-3224">パスポート＃</span></span> 
- <span data-ttu-id="a199a-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a199a-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="a199a-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a199a-3226">Passeport n °</span></span> 
- <span data-ttu-id="a199a-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a199a-3227">Passeport Non</span></span> 
- <span data-ttu-id="a199a-3228">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-3228">Passeport #</span></span> 
- <span data-ttu-id="a199a-3229">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-3229">Passeport#</span></span> 
- <span data-ttu-id="a199a-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a199a-3230">PasseportNon</span></span> 
- <span data-ttu-id="a199a-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a199a-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="a199a-3232">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="a199a-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3233">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3233">Format</span></span>

<span data-ttu-id="a199a-3234">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3235">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3235">Pattern</span></span>

<span data-ttu-id="a199a-3236">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="a199a-3237">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-3238">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="a199a-3238">An optional space</span></span> 
- <span data-ttu-id="a199a-3239">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="a199a-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="a199a-3240">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="a199a-3240">An optional space</span></span> 
- <span data-ttu-id="a199a-3241">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="a199a-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3242">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3242">Checksum</span></span>

<span data-ttu-id="a199a-3243">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3244">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3244">Definition</span></span>

<span data-ttu-id="a199a-3245">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3246">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3247">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="a199a-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3248">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="a199a-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="a199a-3249">Keyword_swift</span></span>

- <span data-ttu-id="a199a-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="a199a-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="a199a-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="a199a-3251">iso 9362</span></span> 
- <span data-ttu-id="a199a-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="a199a-3252">iso9362</span></span> 
- <span data-ttu-id="a199a-3253">rápido\#</span><span class="sxs-lookup"><span data-stu-id="a199a-3253">swift\#</span></span> 
- <span data-ttu-id="a199a-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="a199a-3254">swiftcode</span></span> 
- <span data-ttu-id="a199a-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-3255">swiftnumber</span></span> 
- <span data-ttu-id="a199a-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="a199a-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="a199a-3257">swift code</span></span> 
- <span data-ttu-id="a199a-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="a199a-3258">swift number #</span></span> 
- <span data-ttu-id="a199a-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="a199a-3259">swift routing number</span></span> 
- <span data-ttu-id="a199a-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="a199a-3260">bic number</span></span> 
- <span data-ttu-id="a199a-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="a199a-3261">bic code</span></span> 
- <span data-ttu-id="a199a-3262">BIC\#</span><span class="sxs-lookup"><span data-stu-id="a199a-3262">bic \#</span></span> 
- <span data-ttu-id="a199a-3263">BIC\#</span><span class="sxs-lookup"><span data-stu-id="a199a-3263">bic\#</span></span> 
- <span data-ttu-id="a199a-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="a199a-3264">bank identifier code</span></span> 
- <span data-ttu-id="a199a-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="a199a-3265">標準化9362</span></span> 
- <span data-ttu-id="a199a-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="a199a-3266">迅速＃</span></span> 
- <span data-ttu-id="a199a-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="a199a-3267">SWIFTコード</span></span> 
- <span data-ttu-id="a199a-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="a199a-3268">SWIFT番号</span></span> 
- <span data-ttu-id="a199a-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="a199a-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="a199a-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="a199a-3270">BIC番号</span></span> 
- <span data-ttu-id="a199a-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="a199a-3271">BICコード</span></span> 
- <span data-ttu-id="a199a-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="a199a-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="a199a-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="a199a-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="a199a-3274">rápido\#</span><span class="sxs-lookup"><span data-stu-id="a199a-3274">rapide \#</span></span> 
- <span data-ttu-id="a199a-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="a199a-3275">code SWIFT</span></span> 
- <span data-ttu-id="a199a-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="a199a-3276">le numéro de swift</span></span> 
- <span data-ttu-id="a199a-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="a199a-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="a199a-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="a199a-3278">le numéro BIC</span></span> 
- <span data-ttu-id="a199a-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="a199a-3279">\# BIC</span></span> 
- <span data-ttu-id="a199a-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="a199a-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="a199a-3281">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="a199a-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3282">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3282">Format</span></span>

<span data-ttu-id="a199a-3283">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3284">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3284">Pattern</span></span>

<span data-ttu-id="a199a-3285">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="a199a-3286">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="a199a-3287">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="a199a-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="a199a-3288">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3289">Checksum</span></span>

<span data-ttu-id="a199a-3290">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3291">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3291">Definition</span></span>

<span data-ttu-id="a199a-3292">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3293">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3294">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="a199a-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="a199a-3295">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3296">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="a199a-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="a199a-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="a199a-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="a199a-3298">身份證字號</span></span> 
- <span data-ttu-id="a199a-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="a199a-3299">身份證</span></span> 
- <span data-ttu-id="a199a-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="a199a-3300">身份證號碼</span></span> 
- <span data-ttu-id="a199a-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="a199a-3301">身份證號</span></span> 
- <span data-ttu-id="a199a-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="a199a-3302">身分證字號</span></span> 
- <span data-ttu-id="a199a-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="a199a-3303">身分證</span></span> 
- <span data-ttu-id="a199a-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="a199a-3304">身分證號碼</span></span> 
- <span data-ttu-id="a199a-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="a199a-3305">身份證號</span></span> 
- <span data-ttu-id="a199a-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="a199a-3306">身分證統一編號</span></span> 
- <span data-ttu-id="a199a-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="a199a-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="a199a-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="a199a-3308">簽名</span></span> 
- <span data-ttu-id="a199a-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="a199a-3309">蓋章</span></span> 
- <span data-ttu-id="a199a-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="a199a-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="a199a-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="a199a-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="a199a-3312">	Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="a199a-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3313">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3313">Format</span></span>

- <span data-ttu-id="a199a-3314">Número de pasaporte biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="a199a-3315">Número de pasaporte no biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3316">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3316">Pattern</span></span>
<span data-ttu-id="a199a-3317">Número de pasaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="a199a-3317">Biometric passport number:</span></span>
- <span data-ttu-id="a199a-3318">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="a199a-3318">The digit "3"</span></span> 
- <span data-ttu-id="a199a-3319">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3319">Eight digits</span></span>

<span data-ttu-id="a199a-3320">Número de pasaporte no biométrico:</span><span class="sxs-lookup"><span data-stu-id="a199a-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="a199a-3321">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3322">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3322">Checksum</span></span>

<span data-ttu-id="a199a-3323">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3324">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3324">Definition</span></span>

<span data-ttu-id="a199a-3325">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3326">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3327">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3328">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="a199a-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="a199a-3330">Número de pasaporte ROC</span><span class="sxs-lookup"><span data-stu-id="a199a-3330">ROC passport number</span></span> 
- <span data-ttu-id="a199a-3331">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="a199a-3331">Passport number</span></span> 
- <span data-ttu-id="a199a-3332">Núm. pasaporte
</span><span class="sxs-lookup"><span data-stu-id="a199a-3332">Passport no</span></span> 
- <span data-ttu-id="a199a-3333">N.ro pasaporte</span><span class="sxs-lookup"><span data-stu-id="a199a-3333">Passport Num</span></span> 
- <span data-ttu-id="a199a-3334">N.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="a199a-3334">Passport #</span></span> 
- <span data-ttu-id="a199a-3335">护照</span><span class="sxs-lookup"><span data-stu-id="a199a-3335">护照</span></span> 
- <span data-ttu-id="a199a-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="a199a-3336">中華民國護照</span></span> 
- <span data-ttu-id="a199a-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="a199a-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="a199a-3338">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="a199a-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3339">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3339">Format</span></span>

<span data-ttu-id="a199a-3340">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3341">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3341">Pattern</span></span>

<span data-ttu-id="a199a-3342">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3342">10 letters and digits:</span></span>
- <span data-ttu-id="a199a-3343">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a199a-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a199a-3344">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3345">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3345">Checksum</span></span>

<span data-ttu-id="a199a-3346">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3347">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3347">Definition</span></span>

<span data-ttu-id="a199a-3348">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3349">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3350">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="a199a-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3351">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="a199a-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="a199a-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="a199a-3353">Certificado de residente</span><span class="sxs-lookup"><span data-stu-id="a199a-3353">Resident Certificate</span></span> 
- <span data-ttu-id="a199a-3354">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="a199a-3354">Resident Cert</span></span> 
- <span data-ttu-id="a199a-3355">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="a199a-3355">Resident Cert.</span></span> 
- <span data-ttu-id="a199a-3356">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-3356">Identification card</span></span> 
- <span data-ttu-id="a199a-3357">Certificado de residente extranjero</span><span class="sxs-lookup"><span data-stu-id="a199a-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="a199a-3358">ARCOS</span><span class="sxs-lookup"><span data-stu-id="a199a-3358">ARC</span></span> 
- <span data-ttu-id="a199a-3359">Certificado de residente en el área de Taiwán</span><span class="sxs-lookup"><span data-stu-id="a199a-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="a199a-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="a199a-3360">TARC</span></span> 
- <span data-ttu-id="a199a-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="a199a-3361">居留證</span></span> 
- <span data-ttu-id="a199a-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="a199a-3362">外僑居留證</span></span> 
- <span data-ttu-id="a199a-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="a199a-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="a199a-3364">Código de identificación de población tailandesa</span><span class="sxs-lookup"><span data-stu-id="a199a-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3365">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3365">Format</span></span>

<span data-ttu-id="a199a-3366">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3367">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3367">Pattern</span></span>

<span data-ttu-id="a199a-3368">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3368">13 digits:</span></span>
- <span data-ttu-id="a199a-3369">El primer dígito no es 0 ni 9</span><span class="sxs-lookup"><span data-stu-id="a199a-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="a199a-3370">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3371">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3371">Checksum</span></span>

<span data-ttu-id="a199a-3372">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3373">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3373">Definition</span></span>

<span data-ttu-id="a199a-3374">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3375">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3376">Se encuentra una palabra clave de Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="a199a-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="a199a-3377">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3378">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3379">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="a199a-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="a199a-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="a199a-3381">Número de id.</span><span class="sxs-lookup"><span data-stu-id="a199a-3381">ID Number</span></span>
- <span data-ttu-id="a199a-3382">Número de identificación</span><span class="sxs-lookup"><span data-stu-id="a199a-3382">Identification Number</span></span>
- <span data-ttu-id="a199a-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a199a-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="a199a-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a199a-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="a199a-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a199a-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="a199a-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a199a-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="a199a-3387">Número de identificación nacional de Turco</span><span class="sxs-lookup"><span data-stu-id="a199a-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3388">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3388">Format</span></span>

<span data-ttu-id="a199a-3389">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3390">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3390">Pattern</span></span>

<span data-ttu-id="a199a-3391">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3392">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3392">Checksum</span></span>

<span data-ttu-id="a199a-3393">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3394">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3394">Definition</span></span>

<span data-ttu-id="a199a-3395">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3396">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3397">Se encuentra una palabra clave de Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="a199a-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="a199a-3398">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3399">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3400">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="a199a-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="a199a-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="a199a-3402">TC Kimlik no</span><span class="sxs-lookup"><span data-stu-id="a199a-3402">TC Kimlik No</span></span>
- <span data-ttu-id="a199a-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="a199a-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="a199a-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="a199a-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="a199a-3405">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="a199a-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="a199a-p144">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a199a-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3408">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3408">Format</span></span>

<span data-ttu-id="a199a-3409">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="a199a-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3410">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3410">Pattern</span></span>

<span data-ttu-id="a199a-3411">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3411">18 letters and digits:</span></span>
- <span data-ttu-id="a199a-3412">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="a199a-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a199a-3413">Un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-3413">One digit</span></span> 
- <span data-ttu-id="a199a-3414">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-3414">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="a199a-3415">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="a199a-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a199a-3416">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3417">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3417">Checksum</span></span>

<span data-ttu-id="a199a-3418">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3419">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3419">Definition</span></span>

<span data-ttu-id="a199a-3420">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3421">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3422">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="a199a-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="a199a-3423">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3424">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="a199a-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a199a-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="a199a-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="a199a-3426">DVLA</span></span> 
- <span data-ttu-id="a199a-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="a199a-3427">light vans</span></span> 
- <span data-ttu-id="a199a-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="a199a-3428">quadbikes</span></span> 
- <span data-ttu-id="a199a-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="a199a-3429">motor cars</span></span> 
- <span data-ttu-id="a199a-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="a199a-3430">125cc</span></span> 
- <span data-ttu-id="a199a-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="a199a-3431">sidecar</span></span> 
- <span data-ttu-id="a199a-3432">Tricycles</span><span class="sxs-lookup"><span data-stu-id="a199a-3432">tricycles</span></span> 
- <span data-ttu-id="a199a-3433">sidecar</span><span class="sxs-lookup"><span data-stu-id="a199a-3433">motorcycles</span></span> 
- <span data-ttu-id="a199a-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="a199a-3434">photocard licence</span></span> 
- <span data-ttu-id="a199a-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="a199a-3435">learner drivers</span></span> 
- <span data-ttu-id="a199a-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="a199a-3436">licence holder</span></span> 
- <span data-ttu-id="a199a-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="a199a-3437">licence holders</span></span> 
- <span data-ttu-id="a199a-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="a199a-3438">driving licences</span></span> 
- <span data-ttu-id="a199a-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="a199a-3439">driving licence</span></span> 
- <span data-ttu-id="a199a-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="a199a-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="a199a-p145">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a199a-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3443">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3443">Format</span></span>

<span data-ttu-id="a199a-3444">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3445">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3445">Pattern</span></span>

<span data-ttu-id="a199a-3446">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="a199a-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3447">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3447">Checksum</span></span>

<span data-ttu-id="a199a-3448">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3449">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3449">Definition</span></span>

<span data-ttu-id="a199a-3450">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3451">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3452">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="a199a-3452">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3453">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="a199a-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="a199a-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="a199a-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="a199a-3455">council nomination</span></span> 
- <span data-ttu-id="a199a-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="a199a-3456">nomination form</span></span> 
- <span data-ttu-id="a199a-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="a199a-3457">electoral register</span></span> 
- <span data-ttu-id="a199a-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="a199a-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="a199a-p146">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a199a-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3461">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3461">Format</span></span>

<span data-ttu-id="a199a-3462">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="a199a-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3463">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3463">Pattern</span></span>

<span data-ttu-id="a199a-3464">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a199a-3464">10-17 digits:</span></span>
- <span data-ttu-id="a199a-3465">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="a199a-3466">Un espacio</span><span class="sxs-lookup"><span data-stu-id="a199a-3466">A space</span></span> 
- <span data-ttu-id="a199a-3467">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3467">Three digits</span></span> 
- <span data-ttu-id="a199a-3468">Un espacio</span><span class="sxs-lookup"><span data-stu-id="a199a-3468">A space</span></span> 
- <span data-ttu-id="a199a-3469">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3470">Checksum</span></span>

<span data-ttu-id="a199a-3471">Sí</span><span class="sxs-lookup"><span data-stu-id="a199a-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3472">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3472">Definition</span></span>

<span data-ttu-id="a199a-3473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3474">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3475">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-3475">One of the following is true:</span></span>
    - <span data-ttu-id="a199a-3476">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="a199a-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="a199a-3477">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="a199a-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="a199a-3478">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="a199a-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="a199a-3479">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a199a-3479">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3480">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="a199a-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="a199a-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="a199a-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="a199a-3482">national health service</span></span> 
- <span data-ttu-id="a199a-3483">del NHS del</span><span class="sxs-lookup"><span data-stu-id="a199a-3483">nhs</span></span> 
- <span data-ttu-id="a199a-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="a199a-3484">health services authority</span></span> 
- <span data-ttu-id="a199a-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="a199a-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="a199a-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="a199a-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="a199a-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="a199a-3487">patient id</span></span> 
- <span data-ttu-id="a199a-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="a199a-3488">patient identification</span></span> 
- <span data-ttu-id="a199a-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="a199a-3489">patient no</span></span> 
- <span data-ttu-id="a199a-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="a199a-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="a199a-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="a199a-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="a199a-3492">EON</span><span class="sxs-lookup"><span data-stu-id="a199a-3492">GP</span></span> 
- <span data-ttu-id="a199a-3493">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="a199a-3493">DOB</span></span> 
- <span data-ttu-id="a199a-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="a199a-3494">D.O.B</span></span> 
- <span data-ttu-id="a199a-3495">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-3495">Date of Birth</span></span> 
- <span data-ttu-id="a199a-3496">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="a199a-p147">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="a199a-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3499">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3499">Format</span></span>

<span data-ttu-id="a199a-3500">7 caracteres o 9 caracteres separados por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="a199a-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3501">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3501">Pattern</span></span>

<span data-ttu-id="a199a-3502">Dos patrones posibles:</span><span class="sxs-lookup"><span data-stu-id="a199a-3502">Two possible patterns:</span></span>

- <span data-ttu-id="a199a-3503">Dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="a199a-3504">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3504">Six digits</span></span>
- <span data-ttu-id="a199a-3505">' A ', ' B ', ' C ' o ' t ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a199a-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="a199a-3506">O</span><span class="sxs-lookup"><span data-stu-id="a199a-3506">OR</span></span>

- <span data-ttu-id="a199a-3507">Dos letras</span><span class="sxs-lookup"><span data-stu-id="a199a-3507">Two letters</span></span>
- <span data-ttu-id="a199a-3508">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-3508">A space or dash</span></span>
- <span data-ttu-id="a199a-3509">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3509">Two digits</span></span>
- <span data-ttu-id="a199a-3510">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-3510">A space or dash</span></span>
- <span data-ttu-id="a199a-3511">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3511">Two digits</span></span>
- <span data-ttu-id="a199a-3512">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-3512">A space or dash</span></span>
- <span data-ttu-id="a199a-3513">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3513">Two digits</span></span>
- <span data-ttu-id="a199a-3514">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-3514">A space or dash</span></span>
- <span data-ttu-id="a199a-3515">' A ', ' B ', ' C ' o ' t '</span><span class="sxs-lookup"><span data-stu-id="a199a-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3516">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3516">Checksum</span></span>

<span data-ttu-id="a199a-3517">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3518">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3518">Definition</span></span>

<span data-ttu-id="a199a-3519">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3520">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3521">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="a199a-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="a199a-3522">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3523">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3524">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="a199a-3524">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3525">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="a199a-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="a199a-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="a199a-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="a199a-3527">national insurance number</span></span> 
- <span data-ttu-id="a199a-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="a199a-3528">national insurance contributions</span></span> 
- <span data-ttu-id="a199a-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="a199a-3529">protection act</span></span> 
- <span data-ttu-id="a199a-3530">Pensión</span><span class="sxs-lookup"><span data-stu-id="a199a-3530">insurance</span></span> 
- <span data-ttu-id="a199a-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="a199a-3531">social security number</span></span> 
- <span data-ttu-id="a199a-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="a199a-3532">insurance application</span></span> 
- <span data-ttu-id="a199a-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="a199a-3533">medical application</span></span> 
- <span data-ttu-id="a199a-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="a199a-3534">social insurance</span></span> 
- <span data-ttu-id="a199a-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="a199a-3535">medical attention</span></span> 
- <span data-ttu-id="a199a-3536">social security</span><span class="sxs-lookup"><span data-stu-id="a199a-3536">social security</span></span> 
- <span data-ttu-id="a199a-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="a199a-3537">great britain</span></span> 
- <span data-ttu-id="a199a-3538">Pensión</span><span class="sxs-lookup"><span data-stu-id="a199a-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="a199a-p148">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a199a-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3541">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3541">Format</span></span>

<span data-ttu-id="a199a-3542">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3543">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3543">Pattern</span></span>

<span data-ttu-id="a199a-3544">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3545">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3545">Checksum</span></span>

<span data-ttu-id="a199a-3546">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3547">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3547">Definition</span></span>

<span data-ttu-id="a199a-3548">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3549">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3550">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="a199a-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3551">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a199a-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a199a-3552">Keyword_passport</span></span>

- <span data-ttu-id="a199a-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3553">Passport Number</span></span> 
- <span data-ttu-id="a199a-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="a199a-3554">Passport No</span></span> 
- <span data-ttu-id="a199a-3555">Passport #</span><span class="sxs-lookup"><span data-stu-id="a199a-3555">Passport #</span></span> 
- <span data-ttu-id="a199a-3556">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="a199a-3556">Passport#</span></span> 
- <span data-ttu-id="a199a-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="a199a-3557">PassportID</span></span> 
- <span data-ttu-id="a199a-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="a199a-3558">Passportno</span></span> 
- <span data-ttu-id="a199a-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a199a-3559">passportnumber</span></span> 
- <span data-ttu-id="a199a-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="a199a-3560">パスポート</span></span> 
- <span data-ttu-id="a199a-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a199a-3561">パスポート番号</span></span> 
- <span data-ttu-id="a199a-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a199a-3562">パスポートのNum</span></span> 
- <span data-ttu-id="a199a-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a199a-3563">パスポート＃</span></span> 
- <span data-ttu-id="a199a-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a199a-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="a199a-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a199a-3565">Passeport n °</span></span> 
- <span data-ttu-id="a199a-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a199a-3566">Passeport Non</span></span> 
- <span data-ttu-id="a199a-3567">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-3567">Passeport #</span></span> 
- <span data-ttu-id="a199a-3568">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a199a-3568">Passeport#</span></span> 
- <span data-ttu-id="a199a-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a199a-3569">PasseportNon</span></span> 
- <span data-ttu-id="a199a-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a199a-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="a199a-3571">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a199a-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3572">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3572">Format</span></span>

<span data-ttu-id="a199a-3573">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3574">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3574">Pattern</span></span>

<span data-ttu-id="a199a-3575">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a199a-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3576">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3576">Checksum</span></span>

<span data-ttu-id="a199a-3577">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3578">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3578">Definition</span></span>

<span data-ttu-id="a199a-3579">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3580">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3581">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="a199a-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3582">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="a199a-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="a199a-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="a199a-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3584">Checking Account Number</span></span> 
- <span data-ttu-id="a199a-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="a199a-3585">Checking Account</span></span> 
- <span data-ttu-id="a199a-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-3586">Checking Account #</span></span> 
- <span data-ttu-id="a199a-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="a199a-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-3588">Checking Acct #</span></span> 
- <span data-ttu-id="a199a-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="a199a-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3590">Checking Account No.</span></span> 
- <span data-ttu-id="a199a-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3591">Bank Account Number</span></span> 
- <span data-ttu-id="a199a-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-3592">Bank Account #</span></span> 
- <span data-ttu-id="a199a-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="a199a-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-3594">Bank Acct #</span></span> 
- <span data-ttu-id="a199a-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="a199a-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3596">Bank Account No.</span></span> 
- <span data-ttu-id="a199a-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3597">Savings Account Number</span></span> 
- <span data-ttu-id="a199a-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="a199a-3598">Savings Account.</span></span> 
- <span data-ttu-id="a199a-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-3599">Savings Account #</span></span> 
- <span data-ttu-id="a199a-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="a199a-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-3601">Savings Acct #</span></span> 
- <span data-ttu-id="a199a-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="a199a-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3603">Savings Account No.</span></span> 
- <span data-ttu-id="a199a-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3604">Debit Account Number</span></span> 
- <span data-ttu-id="a199a-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="a199a-3605">Debit Account</span></span> 
- <span data-ttu-id="a199a-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="a199a-3606">Debit Account #</span></span> 
- <span data-ttu-id="a199a-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="a199a-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="a199a-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="a199a-3608">Debit Acct #</span></span> 
- <span data-ttu-id="a199a-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="a199a-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="a199a-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="a199a-3611">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a199a-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3612">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3612">Format</span></span>

<span data-ttu-id="a199a-3613">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="a199a-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3614">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3614">Pattern</span></span>

<span data-ttu-id="a199a-3615">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="a199a-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="a199a-3616">Nueve dígitos con formato como DDD DDD DDD coincidirán.</span><span class="sxs-lookup"><span data-stu-id="a199a-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="a199a-3617">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="a199a-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3618">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3618">Checksum</span></span>

<span data-ttu-id="a199a-3619">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3620">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3620">Definition</span></span>

<span data-ttu-id="a199a-3621">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3622">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3623">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="a199a-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a199a-3624">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="a199a-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="a199a-3625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3626">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3627">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="a199a-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a199a-3628">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="a199a-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="a199a-3629">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="a199a-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3630">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="a199a-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="a199a-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="a199a-3632">LISTAS</span><span class="sxs-lookup"><span data-stu-id="a199a-3632">DL</span></span> 
- <span data-ttu-id="a199a-3633">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="a199a-3633">DLS</span></span> 
- <span data-ttu-id="a199a-3634">CDL</span><span class="sxs-lookup"><span data-stu-id="a199a-3634">CDL</span></span> 
- <span data-ttu-id="a199a-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="a199a-3635">CDLS</span></span> 
- <span data-ttu-id="a199a-3636">ID</span><span class="sxs-lookup"><span data-stu-id="a199a-3636">ID</span></span> 
- <span data-ttu-id="a199a-3637">Falta</span><span class="sxs-lookup"><span data-stu-id="a199a-3637">IDs</span></span> 
- <span data-ttu-id="a199a-3638">LISTAS #</span><span class="sxs-lookup"><span data-stu-id="a199a-3638">DL#</span></span> 
- <span data-ttu-id="a199a-3639">DISTRIBUCIÓN #</span><span class="sxs-lookup"><span data-stu-id="a199a-3639">DLS#</span></span> 
- <span data-ttu-id="a199a-3640">CDL #</span><span class="sxs-lookup"><span data-stu-id="a199a-3640">CDL#</span></span> 
- <span data-ttu-id="a199a-3641">CDLS #</span><span class="sxs-lookup"><span data-stu-id="a199a-3641">CDLS#</span></span> 
- <span data-ttu-id="a199a-3642">IDENTIFICADOR #</span><span class="sxs-lookup"><span data-stu-id="a199a-3642">ID#</span></span>
- <span data-ttu-id="a199a-3643">Falta #</span><span class="sxs-lookup"><span data-stu-id="a199a-3643">IDs#</span></span> 
- <span data-ttu-id="a199a-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="a199a-3644">ID number</span></span> 
- <span data-ttu-id="a199a-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-3645">ID numbers</span></span> 
- <span data-ttu-id="a199a-3646">LIC</span><span class="sxs-lookup"><span data-stu-id="a199a-3646">LIC</span></span> 
- <span data-ttu-id="a199a-3647">LIC #</span><span class="sxs-lookup"><span data-stu-id="a199a-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="a199a-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a199a-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="a199a-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a199a-3649">DriverLic</span></span> 
- <span data-ttu-id="a199a-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a199a-3650">DriverLics</span></span> 
- <span data-ttu-id="a199a-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-3651">DriverLicense</span></span> 
- <span data-ttu-id="a199a-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-3652">DriverLicenses</span></span> 
- <span data-ttu-id="a199a-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-3653">Driver Lic</span></span> 
- <span data-ttu-id="a199a-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-3654">Driver Lics</span></span> 
- <span data-ttu-id="a199a-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="a199a-3655">Driver License</span></span> 
- <span data-ttu-id="a199a-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-3656">Driver Licenses</span></span> 
- <span data-ttu-id="a199a-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a199a-3657">DriversLic</span></span> 
- <span data-ttu-id="a199a-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a199a-3658">DriversLics</span></span> 
- <span data-ttu-id="a199a-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-3659">DriversLicense</span></span> 
- <span data-ttu-id="a199a-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-3660">DriversLicenses</span></span> 
- <span data-ttu-id="a199a-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-3661">Drivers Lic</span></span> 
- <span data-ttu-id="a199a-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-3662">Drivers Lics</span></span> 
- <span data-ttu-id="a199a-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a199a-3663">Drivers License</span></span> 
- <span data-ttu-id="a199a-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="a199a-3665">N.º carné</span><span class="sxs-lookup"><span data-stu-id="a199a-3665">Driver'Lic</span></span> 
- <span data-ttu-id="a199a-3666">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="a199a-3666">Driver'Lics</span></span> 
- <span data-ttu-id="a199a-3667">Conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-3667">Driver'License</span></span> 
- <span data-ttu-id="a199a-3668">Conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="a199a-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-3669">Driver' Lic</span></span> 
- <span data-ttu-id="a199a-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-3670">Driver' Lics</span></span> 
- <span data-ttu-id="a199a-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="a199a-3671">Driver' License</span></span> 
- <span data-ttu-id="a199a-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="a199a-3672">Driver' Licenses</span></span>
- <span data-ttu-id="a199a-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a199a-3673">Driver'sLic</span></span> 
- <span data-ttu-id="a199a-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a199a-3674">Driver'sLics</span></span> 
- <span data-ttu-id="a199a-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a199a-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="a199a-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a199a-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="a199a-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a199a-3677">Driver's Lic</span></span> 
- <span data-ttu-id="a199a-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="a199a-3678">Driver's Lics</span></span> 
- <span data-ttu-id="a199a-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a199a-3679">Driver's License</span></span> 
- <span data-ttu-id="a199a-3680">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="a199a-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="a199a-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="a199a-3681">identification number</span></span> 
- <span data-ttu-id="a199a-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="a199a-3682">identification numbers</span></span> 
- <span data-ttu-id="a199a-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="a199a-3683">identification #</span></span> 
- <span data-ttu-id="a199a-3684">id card</span><span class="sxs-lookup"><span data-stu-id="a199a-3684">id card</span></span> 
- <span data-ttu-id="a199a-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="a199a-3685">id cards</span></span> 
- <span data-ttu-id="a199a-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="a199a-3686">identification card</span></span> 
- <span data-ttu-id="a199a-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="a199a-3687">identification cards</span></span> 
- <span data-ttu-id="a199a-3688">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-3688">DriverLic#</span></span> 
- <span data-ttu-id="a199a-3689">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-3689">DriverLics#</span></span> 
- <span data-ttu-id="a199a-3690">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-3690">DriverLicense#</span></span> 
- <span data-ttu-id="a199a-3691">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="a199a-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-3692">Driver Lic#</span></span> 
- <span data-ttu-id="a199a-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-3693">Driver Lics#</span></span> 
- <span data-ttu-id="a199a-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a199a-3694">Driver License#</span></span> 
- <span data-ttu-id="a199a-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="a199a-3696">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-3696">DriversLic#</span></span> 
- <span data-ttu-id="a199a-3697">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-3697">DriversLics#</span></span> 
- <span data-ttu-id="a199a-3698">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-3698">DriversLicense#</span></span> 
- <span data-ttu-id="a199a-3699">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="a199a-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="a199a-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="a199a-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="a199a-3702">Drivers License#</span></span> 
- <span data-ttu-id="a199a-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="a199a-3704">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="a199a-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="a199a-3705">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="a199a-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="a199a-3706">Conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-3706">Driver'License#</span></span> 
- <span data-ttu-id="a199a-3707">Conducción #</span><span class="sxs-lookup"><span data-stu-id="a199a-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="a199a-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="a199a-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="a199a-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="a199a-3710">Driver' License#</span></span> 
- <span data-ttu-id="a199a-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="a199a-3712">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a199a-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="a199a-3713">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a199a-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="a199a-3714">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a199a-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="a199a-3715">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a199a-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a199a-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="a199a-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="a199a-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="a199a-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="a199a-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="a199a-3718">Driver's License#</span></span> 
- <span data-ttu-id="a199a-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a199a-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="a199a-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="a199a-3720">id card#</span></span> 
- <span data-ttu-id="a199a-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="a199a-3721">id cards#</span></span> 
- <span data-ttu-id="a199a-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="a199a-3722">identification card#</span></span> 
- <span data-ttu-id="a199a-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="a199a-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="a199a-3724">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a199a-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="a199a-3725">Abreviatura del estado (por ejemplo, "NY")</span><span class="sxs-lookup"><span data-stu-id="a199a-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="a199a-3726">Nombre del estado (por ejemplo, "New York")</span><span class="sxs-lookup"><span data-stu-id="a199a-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="a199a-3727">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a199a-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3728">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3728">Format</span></span>

<span data-ttu-id="a199a-3729">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="a199a-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3730">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3730">Pattern</span></span>

<span data-ttu-id="a199a-3731">Con formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3731">Formatted:</span></span>
- <span data-ttu-id="a199a-3732">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="a199a-3732">The digit "9"</span></span> 
- <span data-ttu-id="a199a-3733">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3733">Two digits</span></span> 
- <span data-ttu-id="a199a-3734">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-3734">A space or dash</span></span> 
- <span data-ttu-id="a199a-3735">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="a199a-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="a199a-3736">Un dígito</span><span class="sxs-lookup"><span data-stu-id="a199a-3736">A digit</span></span> 
- <span data-ttu-id="a199a-3737">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="a199a-3737">A space, or dash</span></span> 
- <span data-ttu-id="a199a-3738">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3738">Four digits</span></span>

<span data-ttu-id="a199a-3739">Sin formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3739">Unformatted:</span></span>
- <span data-ttu-id="a199a-3740">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="a199a-3740">The digit "9"</span></span> 
- <span data-ttu-id="a199a-3741">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3741">Two digits</span></span> 
- <span data-ttu-id="a199a-3742">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="a199a-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="a199a-3743">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a199a-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3744">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3744">Checksum</span></span>

<span data-ttu-id="a199a-3745">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="a199a-3746">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3746">Definition</span></span>

<span data-ttu-id="a199a-3747">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3748">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3749">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="a199a-3750">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="a199a-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="a199a-3751">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a199a-3752">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="a199a-3753">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="a199a-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="a199a-3754">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3755">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3756">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="a199a-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="a199a-3757">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="a199a-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="a199a-3758">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a199a-3759">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3759">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3760">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="a199a-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="a199a-3761">Keyword_itin</span></span>

- <span data-ttu-id="a199a-3762">contribuyente</span><span class="sxs-lookup"><span data-stu-id="a199a-3762">taxpayer</span></span> 
- <span data-ttu-id="a199a-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="a199a-3763">tax id</span></span> 
- <span data-ttu-id="a199a-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="a199a-3764">tax identification</span></span> 
- <span data-ttu-id="a199a-3765">élen</span><span class="sxs-lookup"><span data-stu-id="a199a-3765">itin</span></span> 
- <span data-ttu-id="a199a-3766">SSN</span><span class="sxs-lookup"><span data-stu-id="a199a-3766">ssn</span></span> 
- <span data-ttu-id="a199a-3767">/</span><span class="sxs-lookup"><span data-stu-id="a199a-3767">tin</span></span> 
- <span data-ttu-id="a199a-3768">social security</span><span class="sxs-lookup"><span data-stu-id="a199a-3768">social security</span></span> 
- <span data-ttu-id="a199a-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="a199a-3769">tax payer</span></span> 
- <span data-ttu-id="a199a-3770">itins</span><span class="sxs-lookup"><span data-stu-id="a199a-3770">itins</span></span> 
- <span data-ttu-id="a199a-3771">taxi</span><span class="sxs-lookup"><span data-stu-id="a199a-3771">taxid</span></span> 
- <span data-ttu-id="a199a-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="a199a-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="a199a-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a199a-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="a199a-3774">Licencia</span><span class="sxs-lookup"><span data-stu-id="a199a-3774">License</span></span> 
- <span data-ttu-id="a199a-3775">LISTAS</span><span class="sxs-lookup"><span data-stu-id="a199a-3775">DL</span></span> 
- <span data-ttu-id="a199a-3776">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="a199a-3776">DOB</span></span> 
- <span data-ttu-id="a199a-3777">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-3777">Birthdate</span></span> 
- <span data-ttu-id="a199a-3778">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="a199a-3778">Birthday</span></span> 
- <span data-ttu-id="a199a-3779">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="a199a-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="a199a-3780">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a199a-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a199a-3781">Formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3781">Format</span></span>

<span data-ttu-id="a199a-3782">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="a199a-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="a199a-3783">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="a199a-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="a199a-3784">Patrón</span><span class="sxs-lookup"><span data-stu-id="a199a-3784">Pattern</span></span>

<span data-ttu-id="a199a-3785">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="a199a-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="a199a-3786">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="a199a-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a199a-3787">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="a199a-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="a199a-3788">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="a199a-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a199a-3789">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="a199a-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="a199a-3790">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="a199a-3790">Checksum</span></span>

<span data-ttu-id="a199a-3791">No</span><span class="sxs-lookup"><span data-stu-id="a199a-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="a199a-3792">Definición</span><span class="sxs-lookup"><span data-stu-id="a199a-3792">Definition</span></span>

<span data-ttu-id="a199a-3793">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3794">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3795">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="a199a-3795">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a199a-3796">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3796">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-3797">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3797">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="a199a-3798">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3798">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3799">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3799">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3800">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="a199a-3800">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a199a-3801">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3801">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-3802">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3802">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="a199a-3803">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3803">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3804">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3804">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3805">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="a199a-3805">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a199a-3806">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3806">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-3807">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3807">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="a199a-3808">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3808">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3809">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3809">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3810">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="a199a-3810">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a199a-3811">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3811">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a199a-3812">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="a199a-3812">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="a199a-3813">Una directiva DLP está 40% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a199a-3813">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a199a-3814">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3814">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3815">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3815">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3816">La función Func_randomized_unformatted_ssn no encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3816">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3817">No se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="a199a-3817">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="a199a-3818">O bien</span><span class="sxs-lookup"><span data-stu-id="a199a-3818">Or</span></span>

- <span data-ttu-id="a199a-3819">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3819">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3820">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3820">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3821">La función Func_randomized_unformatted_ssn no encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a199a-3821">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="a199a-3822">No se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="a199a-3822">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a199a-3823">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a199a-3823">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="a199a-3824">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="a199a-3824">Keyword_ssn</span></span>

- <span data-ttu-id="a199a-3825">Social Security</span><span class="sxs-lookup"><span data-stu-id="a199a-3825">Social Security</span></span> 
- <span data-ttu-id="a199a-3826">Social Security#</span><span class="sxs-lookup"><span data-stu-id="a199a-3826">Social Security#</span></span> 
- <span data-ttu-id="a199a-3827">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="a199a-3827">Soc Sec</span></span> 
- <span data-ttu-id="a199a-3828">SSN</span><span class="sxs-lookup"><span data-stu-id="a199a-3828">SSN</span></span> 
- <span data-ttu-id="a199a-3829">SSN</span><span class="sxs-lookup"><span data-stu-id="a199a-3829">SSNS</span></span> 
- <span data-ttu-id="a199a-3830">SSN #</span><span class="sxs-lookup"><span data-stu-id="a199a-3830">SSN#</span></span> 
- <span data-ttu-id="a199a-3831">SS #</span><span class="sxs-lookup"><span data-stu-id="a199a-3831">SS#</span></span> 
- <span data-ttu-id="a199a-3832">SSID</span><span class="sxs-lookup"><span data-stu-id="a199a-3832">SSID</span></span> 
   

