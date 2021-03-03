---
title: Obtener más información acerca de los tipos de información confidencial
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: e125a6dfb35b7018b5f85100184c842da9231327
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407330"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="c1c64-102">Obtener más información acerca de los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-102">Learn about sensitive information types</span></span>

<span data-ttu-id="c1c64-103">Identificar y clasificar elementos confidenciales que están bajo el control de las organizaciones es el primer paso de la disciplina [de Protección de la información.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="c1c64-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="c1c64-104">Microsoft 365 proporciona tres formas de identificar elementos para que se puedan clasificar:</span><span class="sxs-lookup"><span data-stu-id="c1c64-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="c1c64-105">manualmente por los usuarios</span><span class="sxs-lookup"><span data-stu-id="c1c64-105">manually by users</span></span>
- <span data-ttu-id="c1c64-106">reconocimiento automatizado de patrones, como tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="c1c64-107">aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="c1c64-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="c1c64-108">Los tipos de información confidencial son clasificadores basados en patrones.</span><span class="sxs-lookup"><span data-stu-id="c1c64-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="c1c64-109">Detectan información confidencial como seguridad social, tarjeta de crédito o números de cuenta bancaria para identificar elementos confidenciales, consulte [Definiciones](sensitive-information-type-entity-definitions.md) de entidades de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="c1c64-110">Los tipos de información confidencial se usan en</span><span class="sxs-lookup"><span data-stu-id="c1c64-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="c1c64-111">Directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="c1c64-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="c1c64-112">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="c1c64-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="c1c64-113">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="c1c64-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="c1c64-114">Cumplimiento de las comunicaciones</span><span class="sxs-lookup"><span data-stu-id="c1c64-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="c1c64-115">Directivas de etiquetado automático</span><span class="sxs-lookup"><span data-stu-id="c1c64-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="c1c64-116">Partes fundamentales de un tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="c1c64-117">Cada entidad de tipo de información confidencial se define mediante estos campos:</span><span class="sxs-lookup"><span data-stu-id="c1c64-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="c1c64-118">nombre: cómo se hace referencia al tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="c1c64-119">descripción: describe lo que busca el tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="c1c64-120">patrón: un patrón define lo que detecta un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="c1c64-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="c1c64-121">Consta de los siguientes componentes</span><span class="sxs-lookup"><span data-stu-id="c1c64-121">It consists of the following components</span></span>
    - <span data-ttu-id="c1c64-122">Elemento principal: el elemento principal que busca el tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="c1c64-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="c1c64-123">Puede ser una expresión **regular con** o sin una validación de suma de comprobación, una lista de palabras **clave,** un **diccionario** de palabras clave o una **función**.</span><span class="sxs-lookup"><span data-stu-id="c1c64-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="c1c64-124">Elemento de soporte: elementos que actúan como pruebas de soporte que ayudan a aumentar la confianza de la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c1c64-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="c1c64-125">Por ejemplo, la palabra clave "SSN" cerca de un número SSN.</span><span class="sxs-lookup"><span data-stu-id="c1c64-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="c1c64-126">Puede ser una expresión regular con o sin validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="c1c64-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="c1c64-127">Nivel de confianza: los niveles de confianza (altos, medianos, bajos) reflejan la cantidad de evidencia de soporte que se detectó junto con el elemento principal.</span><span class="sxs-lookup"><span data-stu-id="c1c64-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="c1c64-128">Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando.</span><span class="sxs-lookup"><span data-stu-id="c1c64-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="c1c64-129">Proximidad: número de caracteres entre el elemento principal y el elemento de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="c1c64-129">Proximity – Number of characters between primary and supporting element</span></span>

![Diagrama de prueba corroboradora y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="c1c64-131">Obtenga más información sobre los niveles de confianza en este vídeo</span><span class="sxs-lookup"><span data-stu-id="c1c64-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="c1c64-132">Tipo de información confidencial de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1c64-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="c1c64-133">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="c1c64-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="c1c64-134">Formato</span><span class="sxs-lookup"><span data-stu-id="c1c64-134">Format</span></span>

<span data-ttu-id="c1c64-135">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="c1c64-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="c1c64-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="c1c64-136">Pattern</span></span>

<span data-ttu-id="c1c64-137">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="c1c64-137">Eight digits:</span></span>
- <span data-ttu-id="c1c64-138">dos dígitos</span><span class="sxs-lookup"><span data-stu-id="c1c64-138">two digits</span></span>
- <span data-ttu-id="c1c64-139">un punto</span><span class="sxs-lookup"><span data-stu-id="c1c64-139">a period</span></span>
- <span data-ttu-id="c1c64-140">tres dígitos</span><span class="sxs-lookup"><span data-stu-id="c1c64-140">three digits</span></span>
- <span data-ttu-id="c1c64-141">un punto</span><span class="sxs-lookup"><span data-stu-id="c1c64-141">a period</span></span>
- <span data-ttu-id="c1c64-142">tres dígitos</span><span class="sxs-lookup"><span data-stu-id="c1c64-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c1c64-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c1c64-143">Checksum</span></span>

<span data-ttu-id="c1c64-144">No</span><span class="sxs-lookup"><span data-stu-id="c1c64-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="c1c64-145">Definición</span><span class="sxs-lookup"><span data-stu-id="c1c64-145">Definition</span></span>

<span data-ttu-id="c1c64-146">Una directiva DLP tiene confianza mediana en que se ha detectado este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c1c64-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c1c64-147">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c1c64-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c1c64-148">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="c1c64-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1c64-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c1c64-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="c1c64-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="c1c64-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="c1c64-151">Número de identidad nacional de Argentina</span><span class="sxs-lookup"><span data-stu-id="c1c64-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="c1c64-152">Identidad</span><span class="sxs-lookup"><span data-stu-id="c1c64-152">Identity</span></span> 
- <span data-ttu-id="c1c64-153">Identificación tarjeta de identidad nacional</span><span class="sxs-lookup"><span data-stu-id="c1c64-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="c1c64-154">DNI</span><span class="sxs-lookup"><span data-stu-id="c1c64-154">DNI</span></span> 
- <span data-ttu-id="c1c64-155">Registro nacional de personas de NIC</span><span class="sxs-lookup"><span data-stu-id="c1c64-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="c1c64-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="c1c64-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="c1c64-157">Registro nacional de las personas</span><span class="sxs-lookup"><span data-stu-id="c1c64-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="c1c64-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="c1c64-158">Identidad</span></span> 
- <span data-ttu-id="c1c64-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="c1c64-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="c1c64-160">Más información sobre los niveles de confianza</span><span class="sxs-lookup"><span data-stu-id="c1c64-160">More on confidence levels</span></span>

<span data-ttu-id="c1c64-161">En una definición de entidad de tipo de información **confidencial,** el nivel de confianza refleja la cantidad de evidencia compatible que se detecta además del elemento principal.</span><span class="sxs-lookup"><span data-stu-id="c1c64-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="c1c64-162">Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando.</span><span class="sxs-lookup"><span data-stu-id="c1c64-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="c1c64-163">Por ejemplo, las coincidencias con un nivel de confianza alto contendrán evidencias más compatibles cerca del elemento principal, mientras que las coincidencias con un nivel de confianza bajo contendrán poca o ninguna evidencia compatible en proximidad.</span><span class="sxs-lookup"><span data-stu-id="c1c64-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="c1c64-164">Un nivel de confianza alto devuelve el menor número de falsos positivos, pero puede dar como resultado más falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="c1c64-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="c1c64-165">Los niveles de confianza bajos o medianos devuelven más falsos positivos, pero de pocos a cero falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="c1c64-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="c1c64-166">**confianza baja:** valor de 65, los elementos coincidentes contendrán el menor número de falsos negativos, pero los más falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="c1c64-166">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="c1c64-167">La confianza baja devuelve todas las coincidencias de confianza baja, media y alta.</span><span class="sxs-lookup"><span data-stu-id="c1c64-167">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="c1c64-168">**confianza media:** valor de 75, los elementos coincidentes contendrán una cantidad promedio de falsos positivos y falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="c1c64-168">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="c1c64-169">La confianza media devuelve todas las coincidencias de confianza media y alta.</span><span class="sxs-lookup"><span data-stu-id="c1c64-169">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="c1c64-170">**elevada confianza:** valor de 85, los elementos coincidentes contendrán el menor número de falsos positivos, pero los negativos más falsos.</span><span class="sxs-lookup"><span data-stu-id="c1c64-170">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="c1c64-171">La confianza alta solo devuelve coincidencias de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="c1c64-171">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="c1c64-172">Debe usar patrones de alto nivel de confianza con recuentos bajos, por ejemplo, de cinco a diez, y patrones de confianza bajos con recuentos más altos, por ejemplo, 20 o más.</span><span class="sxs-lookup"><span data-stu-id="c1c64-172">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="c1c64-173">Crear tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="c1c64-173">Creating custom sensitive information types</span></span>

<span data-ttu-id="c1c64-174">Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="c1c64-174">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="c1c64-175">**Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="c1c64-175">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="c1c64-176">Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="c1c64-176">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="c1c64-177">Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="c1c64-177">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="c1c64-178">**Usar EDM** Puede establecer los tipos de información confidencial mediante la clasificación basada en la coincidencia exacta de los datos (EDM).</span><span class="sxs-lookup"><span data-stu-id="c1c64-178">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="c1c64-179">Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="c1c64-179">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="c1c64-180">Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="c1c64-180">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="c1c64-181">**Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1c64-181">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="c1c64-182">Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="c1c64-182">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="c1c64-183">Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c1c64-183">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="c1c64-184">Los niveles de confianza mejorados están disponibles para su uso inmediato en Prevención de pérdida de datos para servicios de Microsoft 365, Microsoft Information Protection para servicios de Microsoft 365, Cumplimiento de comunicaciones, Gobierno de la información y Administración de registros.</span><span class="sxs-lookup"><span data-stu-id="c1c64-184">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="c1c64-185">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="c1c64-185">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="c1c64-186">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="c1c64-186">Chinese (simplified)</span></span>
> - <span data-ttu-id="c1c64-187">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="c1c64-187">Chinese (traditional)</span></span>
> - <span data-ttu-id="c1c64-188">Coreano</span><span class="sxs-lookup"><span data-stu-id="c1c64-188">Korean</span></span>
> - <span data-ttu-id="c1c64-189">Japonés</span><span class="sxs-lookup"><span data-stu-id="c1c64-189">Japanese</span></span>

><span data-ttu-id="c1c64-190">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="c1c64-190">This support is available for sensitive information types.</span></span> <span data-ttu-id="c1c64-191">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="c1c64-191">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="c1c64-192">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="c1c64-192">For further information</span></span>
- [<span data-ttu-id="c1c64-193">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-193">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="c1c64-194">Crear un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1c64-194">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="c1c64-195">Crear un tipo de información confidencial personalizada en PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1c64-195">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
