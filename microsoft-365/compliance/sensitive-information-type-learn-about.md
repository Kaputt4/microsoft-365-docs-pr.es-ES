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
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166455"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="0ceff-102">Obtener más información acerca de los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-102">Learn about sensitive information types</span></span>

<span data-ttu-id="0ceff-103">Identificar y clasificar elementos confidenciales que están bajo el control de su organización es el primer paso de la disciplina [de Protección de la información.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="0ceff-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="0ceff-104">Microsoft 365 ofrece tres formas de identificar elementos para que se puedan clasificar:</span><span class="sxs-lookup"><span data-stu-id="0ceff-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="0ceff-105">manualmente por los usuarios</span><span class="sxs-lookup"><span data-stu-id="0ceff-105">manually by users</span></span>
- <span data-ttu-id="0ceff-106">reconocimiento de patrones automatizado, como los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="0ceff-107">aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="0ceff-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="0ceff-108">Los tipos de información confidencial son clasificadores basados en patrones.</span><span class="sxs-lookup"><span data-stu-id="0ceff-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="0ceff-109">Detectan información confidencial, como números de cuentas bancarias, tarjetas de crédito o seguridad social, para identificar elementos confidenciales, ver definiciones de entidad de [tipos de información confidencial](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="0ceff-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="0ceff-110">Los tipos de información confidencial se usan en</span><span class="sxs-lookup"><span data-stu-id="0ceff-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="0ceff-111">Directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="0ceff-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="0ceff-112">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="0ceff-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="0ceff-113">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="0ceff-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="0ceff-114">Cumplimiento de las comunicaciones</span><span class="sxs-lookup"><span data-stu-id="0ceff-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="0ceff-115">Directivas de etiquetado automático</span><span class="sxs-lookup"><span data-stu-id="0ceff-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="0ceff-116">Partes fundamentales de un tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="0ceff-117">Cada entidad de tipo de información confidencial se define mediante estos campos:</span><span class="sxs-lookup"><span data-stu-id="0ceff-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="0ceff-118">nombre: cómo se hace referencia al tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="0ceff-119">description: describe lo que busca el tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="0ceff-120">patrón: un patrón define lo que detecta un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="0ceff-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="0ceff-121">Consta de los siguientes componentes</span><span class="sxs-lookup"><span data-stu-id="0ceff-121">It consists of the following components</span></span>
    - <span data-ttu-id="0ceff-122">Elemento principal: el elemento principal que busca el tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="0ceff-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="0ceff-123">Puede ser una expresión **regular con o** sin una validación de suma de comprobación, una lista de palabras clave, un diccionario de palabras clave o una **función**.  </span><span class="sxs-lookup"><span data-stu-id="0ceff-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="0ceff-124">Elemento de apoyo: elementos que actúan como evidencia de apoyo que ayudan a aumentar la confianza de la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="0ceff-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="0ceff-125">Por ejemplo, la palabra clave "SSN" cerca de un número de SSN.</span><span class="sxs-lookup"><span data-stu-id="0ceff-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="0ceff-126">Puede ser una expresión regular con o sin una validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="0ceff-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="0ceff-127">Nivel de confianza: los niveles de confianza (alto, medio, bajo) reflejan cuánta evidencia de apoyo se detectó junto con el elemento principal.</span><span class="sxs-lookup"><span data-stu-id="0ceff-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="0ceff-128">Cuanto más evidencia de apoyo contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que buscas.</span><span class="sxs-lookup"><span data-stu-id="0ceff-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="0ceff-129">Proximidad: número de caracteres entre el elemento principal y el elemento de apoyo</span><span class="sxs-lookup"><span data-stu-id="0ceff-129">Proximity – Number of characters between primary and supporting element</span></span>

![Diagrama de prueba corroboradora y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="0ceff-131">Obtenga más información sobre los niveles de confianza en este vídeo</span><span class="sxs-lookup"><span data-stu-id="0ceff-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="0ceff-132">Ejemplo de tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="0ceff-133">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="0ceff-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="0ceff-134">Formato</span><span class="sxs-lookup"><span data-stu-id="0ceff-134">Format</span></span>

<span data-ttu-id="0ceff-135">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="0ceff-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="0ceff-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="0ceff-136">Pattern</span></span>

<span data-ttu-id="0ceff-137">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="0ceff-137">Eight digits:</span></span>
- <span data-ttu-id="0ceff-138">dos dígitos</span><span class="sxs-lookup"><span data-stu-id="0ceff-138">two digits</span></span>
- <span data-ttu-id="0ceff-139">un punto</span><span class="sxs-lookup"><span data-stu-id="0ceff-139">a period</span></span>
- <span data-ttu-id="0ceff-140">tres dígitos</span><span class="sxs-lookup"><span data-stu-id="0ceff-140">three digits</span></span>
- <span data-ttu-id="0ceff-141">un punto</span><span class="sxs-lookup"><span data-stu-id="0ceff-141">a period</span></span>
- <span data-ttu-id="0ceff-142">tres dígitos</span><span class="sxs-lookup"><span data-stu-id="0ceff-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0ceff-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0ceff-143">Checksum</span></span>

<span data-ttu-id="0ceff-144">No</span><span class="sxs-lookup"><span data-stu-id="0ceff-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="0ceff-145">Definición</span><span class="sxs-lookup"><span data-stu-id="0ceff-145">Definition</span></span>

<span data-ttu-id="0ceff-146">Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0ceff-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0ceff-147">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0ceff-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0ceff-148">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="0ceff-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ceff-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0ceff-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="0ceff-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="0ceff-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="0ceff-151">Número de identidad nacional de Argentina</span><span class="sxs-lookup"><span data-stu-id="0ceff-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="0ceff-152">Identidad</span><span class="sxs-lookup"><span data-stu-id="0ceff-152">Identity</span></span> 
- <span data-ttu-id="0ceff-153">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="0ceff-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="0ceff-154">DNI</span><span class="sxs-lookup"><span data-stu-id="0ceff-154">DNI</span></span> 
- <span data-ttu-id="0ceff-155">Registro nacional de personas nic</span><span class="sxs-lookup"><span data-stu-id="0ceff-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="0ceff-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="0ceff-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="0ceff-157">Registro nacional de las personas</span><span class="sxs-lookup"><span data-stu-id="0ceff-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="0ceff-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="0ceff-158">Identidad</span></span> 
- <span data-ttu-id="0ceff-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="0ceff-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="0ceff-160">Más información sobre los niveles de confianza</span><span class="sxs-lookup"><span data-stu-id="0ceff-160">More on confidence levels</span></span>

<span data-ttu-id="0ceff-161">En una definición de entidad de tipo de información **confidencial,** el nivel de confianza refleja cuánta evidencia de apoyo se detecta además del elemento principal.</span><span class="sxs-lookup"><span data-stu-id="0ceff-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="0ceff-162">Cuanto más evidencia de apoyo contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que buscas.</span><span class="sxs-lookup"><span data-stu-id="0ceff-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="0ceff-163">Por ejemplo, las coincidencias con un nivel de confianza alto contendrán más evidencias de apoyo cerca del elemento principal, mientras que las coincidencias con un nivel de confianza bajo contendrán poca o ninguna evidencia de apoyo en proximidad.</span><span class="sxs-lookup"><span data-stu-id="0ceff-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="0ceff-164">Un nivel de confianza alto devuelve el menor número de falsos positivos, pero puede dar como resultado más falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="0ceff-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="0ceff-165">Los niveles de confianza bajos o medianos devuelven más falsos positivos, pero algunos a cero falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="0ceff-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="0ceff-166">**confianza baja:** valor de 65, los elementos coincidentes contendrán el menor número de falsos negativos, pero los más falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="0ceff-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="0ceff-167">**confianza media:** valor de 75, los elementos coincidentes contendrán una cantidad media de falsos positivos y falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="0ceff-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="0ceff-168">**confianza alta:** valor de 85, los elementos coincidentes contendrán el menor número de falsos positivos, pero los más falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="0ceff-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="0ceff-169">Debes usar patrones de nivel de confianza alto con recuentos bajos, por ejemplo, de cinco a diez, y patrones de confianza baja con recuentos más altos, por ejemplo, 20 o más.</span><span class="sxs-lookup"><span data-stu-id="0ceff-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="0ceff-170">Crear tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="0ceff-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="0ceff-171">Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="0ceff-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="0ceff-172">**Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="0ceff-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="0ceff-173">Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="0ceff-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="0ceff-174">Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="0ceff-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="0ceff-175">**Usar EDM** Puede establecer los tipos de información confidencial mediante la clasificación basada en la coincidencia exacta de los datos (EDM).</span><span class="sxs-lookup"><span data-stu-id="0ceff-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="0ceff-176">Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="0ceff-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="0ceff-177">Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="0ceff-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="0ceff-178">**Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ceff-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="0ceff-179">Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="0ceff-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="0ceff-180">Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0ceff-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="0ceff-181">Los niveles de confianza mejorados están disponibles para su uso inmediato en prevención de pérdida de datos para los servicios de Microsoft 365, Microsoft Information Protection para servicios de Microsoft 365, cumplimiento de comunicaciones, gobierno de información y administración de registros.</span><span class="sxs-lookup"><span data-stu-id="0ceff-181">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="0ceff-182">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="0ceff-182">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="0ceff-183">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="0ceff-183">Chinese (simplified)</span></span>
> - <span data-ttu-id="0ceff-184">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="0ceff-184">Chinese (traditional)</span></span>
> - <span data-ttu-id="0ceff-185">Coreano</span><span class="sxs-lookup"><span data-stu-id="0ceff-185">Korean</span></span>
> - <span data-ttu-id="0ceff-186">Japonés</span><span class="sxs-lookup"><span data-stu-id="0ceff-186">Japanese</span></span>

><span data-ttu-id="0ceff-187">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="0ceff-187">This support is available for sensitive information types.</span></span> <span data-ttu-id="0ceff-188">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="0ceff-188">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="0ceff-189">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="0ceff-189">For further information</span></span>
- [<span data-ttu-id="0ceff-190">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-190">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="0ceff-191">Crear un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0ceff-191">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="0ceff-192">Crear un tipo personalizado de información confidencial en PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ceff-192">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
