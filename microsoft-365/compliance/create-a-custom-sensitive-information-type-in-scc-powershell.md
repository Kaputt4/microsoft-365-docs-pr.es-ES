---
title: Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda a crear e importar un tipo de información confidencial personalizada para DLP en el Centro de seguridad y cumplimiento.
ms.openlocfilehash: 25b2d972214410df96d3dedbe204b75b6cd0b1d9
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039394"
---
# <a name="create-a-custom-sensitive-information-type-in-security--compliance-center-powershell"></a><span data-ttu-id="57299-103">Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="57299-103">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="57299-104">Data loss prevention (DLP) in Microsoft 365 includes many built-in [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that are ready for you to use in your DLP policies.</span><span class="sxs-lookup"><span data-stu-id="57299-104">Data loss prevention (DLP) in Microsoft 365 includes many built-in [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="57299-105">These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span><span class="sxs-lookup"><span data-stu-id="57299-105">These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span>
  
<span data-ttu-id="57299-106">But what if you need to identify and protect a different type of sensitive information (for example, an employee ID that uses a format specific to your organization)?</span><span class="sxs-lookup"><span data-stu-id="57299-106">But what if you need to identify and protect a different type of sensitive information (for example, an employee ID that uses a format specific to your organization)?</span></span> <span data-ttu-id="57299-107">To do this, you can create a custom sensitive information type that is defined in an XML file called a *rule package*.</span><span class="sxs-lookup"><span data-stu-id="57299-107">To do this, you can create a custom sensitive information type that is defined in an XML file called a *rule package*.</span></span>
  
<span data-ttu-id="57299-108">This topic shows you how to create an XML file that defines your own custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="57299-108">This topic shows you how to create an XML file that defines your own custom sensitive information type.</span></span> <span data-ttu-id="57299-109">You need to know how to create a regular expression.</span><span class="sxs-lookup"><span data-stu-id="57299-109">You need to know how to create a regular expression.</span></span> <span data-ttu-id="57299-110">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span><span class="sxs-lookup"><span data-stu-id="57299-110">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="57299-111">You can use this example XML as a starting point for your own XML file.</span><span class="sxs-lookup"><span data-stu-id="57299-111">You can use this example XML as a starting point for your own XML file.</span></span>
  
<span data-ttu-id="57299-112">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57299-112">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell.</span></span> <span data-ttu-id="57299-113">Then you're ready to use your custom sensitive information type in your DLP policies and test that it's detecting the sensitive information as you intended.</span><span class="sxs-lookup"><span data-stu-id="57299-113">Then you're ready to use your custom sensitive information type in your DLP policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="57299-114">You can also create less complex custom sensitive information types in the Security & Compliance Center UI.</span><span class="sxs-lookup"><span data-stu-id="57299-114">You can also create less complex custom sensitive information types in the Security & Compliance Center UI.</span></span> <span data-ttu-id="57299-115">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="57299-115">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="57299-116">Declinación de responsabilidades importante</span><span class="sxs-lookup"><span data-stu-id="57299-116">Important disclaimer</span></span>
<!-- this is worded much better than the previous one is -->
<span data-ttu-id="57299-117">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns.</span><span class="sxs-lookup"><span data-stu-id="57299-117">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns.</span></span> <span data-ttu-id="57299-118">For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS).</span><span class="sxs-lookup"><span data-stu-id="57299-118">For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS).</span></span> <span data-ttu-id="57299-119">Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.</span><span class="sxs-lookup"><span data-stu-id="57299-119">Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.</span></span>  <span data-ttu-id="57299-120">As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes.</span><span class="sxs-lookup"><span data-stu-id="57299-120">As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes.</span></span> <span data-ttu-id="57299-121">Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span><span class="sxs-lookup"><span data-stu-id="57299-121">Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="57299-122">Consulte [Posibles problemas de validación a tener en cuenta](#potential-validation-issues-to-be-aware-of) en este tema.</span><span class="sxs-lookup"><span data-stu-id="57299-122">See, [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="57299-123">Para obtener más información sobre el motor Boost.RegEx (anteriormente conocido como RegEx++) que se usa para el procesamiento de texto, vea [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="57299-123">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="57299-124">XML de ejemplo de un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="57299-124">Sample XML of a rule package</span></span>

<span data-ttu-id="57299-125">Here's the sample XML of the rule package that we'll create in this topic.</span><span class="sxs-lookup"><span data-stu-id="57299-125">Here's the sample XML of the rule package that we'll create in this topic.</span></span> <span data-ttu-id="57299-126">Elements and attributes are explained in the sections below.</span><span class="sxs-lookup"><span data-stu-id="57299-126">Elements and attributes are explained in the sections below.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
    <Version build="0" major="1" minor="0" revision="0"/>
    <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
    <Details defaultLangCode="en-us">
        <LocalizedDetails langcode="en-us">
            <PublisherName>Contoso</PublisherName>
            <Name>Employee ID Custom Rule Pack</Name>
            <Description>
            This rule package contains the custom Employee ID entity.
            </Description>
        </LocalizedDetails>
    </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
            <Any minMatches="1">
                <Match idRef="Keyword_badge" minCount="2"/>
                <Match idRef="Keyword_employee"/>
            </Any>
            <Any minMatches="0" maxMatches="0">
                <Match idRef="Keyword_false_positives_local"/>
                <Match idRef="Keyword_false_positives_intl"/>
            </Any>
        </Pattern>
    </Entity>
    <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
    <Keyword id="Keyword_employee">
        <Group matchStyle="word">
            <Term>Identification</Term>
            <Term>Contoso Employee</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_badge">
        <Group matchStyle="string">
            <Term>card</Term>
            <Term>badge</Term>
            <Term caseSensitive="true">ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_local">
        <Group matchStyle="word">
            <Term>credit card</Term>
            <Term>national ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_intl">
        <Group matchStyle="word">
            <Term>identity card</Term>
            <Term>national ID</Term>
            <Term>EU debit card</Term>
        </Group>
    </Keyword>
    <LocalizedStrings>
        <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
            <Name default="true" langcode="en-us">Employee ID</Name>
            <Description default="true" langcode="en-us">
            A custom classification for detecting Employee IDs.
            </Description>
            <Description default="false" langcode="de-de">
            Description for German locale.
            </Description>
        </Resource>
    </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="57299-127">What are your key requirements?</span><span class="sxs-lookup"><span data-stu-id="57299-127">What are your key requirements?</span></span> <span data-ttu-id="57299-128">[Rule, Entity, Pattern elements]</span><span class="sxs-lookup"><span data-stu-id="57299-128">[Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="57299-129">Antes de empezar, resulta útil comprender la estructura básica del esquema XML de una regla y cómo puede usar esta estructura para definir su tipo personalizado de información confidencial de forma que identifique el contenido adecuado.</span><span class="sxs-lookup"><span data-stu-id="57299-129">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="57299-130">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns.</span><span class="sxs-lookup"><span data-stu-id="57299-130">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns.</span></span> <span data-ttu-id="57299-131">A pattern is what DLP looks for when it evaluates content such as email and documents.</span><span class="sxs-lookup"><span data-stu-id="57299-131">A pattern is what DLP looks for when it evaluates content such as email and documents.</span></span>
  <!-- ok then this is going to be really confusing since the terminology changes.... -->
<span data-ttu-id="57299-132">(A quick note on terminology - if you're familiar with DLP policies, you know that a policy contains one or more rules comprised of conditions and actions.</span><span class="sxs-lookup"><span data-stu-id="57299-132">(A quick note on terminology - if you're familiar with DLP policies, you know that a policy contains one or more rules comprised of conditions and actions.</span></span> <span data-ttu-id="57299-133">However, in this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="57299-133">However, in this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type.</span></span> <span data-ttu-id="57299-134">So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.)</span><span class="sxs-lookup"><span data-stu-id="57299-134">So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.)</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="57299-135">Escenario más sencillo: entidad con un patrón</span><span class="sxs-lookup"><span data-stu-id="57299-135">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="57299-136">Here's the simplest scenario.</span><span class="sxs-lookup"><span data-stu-id="57299-136">Here's the simplest scenario.</span></span> <span data-ttu-id="57299-137">You want your DLP policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number.</span><span class="sxs-lookup"><span data-stu-id="57299-137">You want your DLP policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number.</span></span> <span data-ttu-id="57299-138">So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers.</span><span class="sxs-lookup"><span data-stu-id="57299-138">So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers.</span></span> <span data-ttu-id="57299-139">Any content containing a nine-digit number satisfies the pattern.</span><span class="sxs-lookup"><span data-stu-id="57299-139">Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![Diagrama de una entidad con un patrón](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="57299-141">Pero, aunque es sencillo, este patrón puede identificar un gran número de falsos positivos si coincide con contenido donde aparezcan números de nueve dígitos que no sean necesariamente id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="57299-141">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="57299-142">Escenario más común: entidad con varios patrones</span><span class="sxs-lookup"><span data-stu-id="57299-142">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="57299-143">Por este motivo, es más común definir una entidad con más de un patrón, donde los patrones identifican pruebas complementarias (como una palabra clave o una fecha), además de la entidad (como un número de nueve dígitos).</span><span class="sxs-lookup"><span data-stu-id="57299-143">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="57299-144">Por ejemplo, para incrementar la probabilidad de identificar contenido donde haya un id. de empleado, puede definir un patrón que también identifique una fecha de contratación y, además, definir otro patrón que identifique una fecha de contratación y una palabra clave (como "Id. de empleado"), además del número de nueve dígitos.</span><span class="sxs-lookup"><span data-stu-id="57299-144">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![Diagrama de una entidad con varios patrones](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="57299-146">Debe tener en cuenta un par de aspectos importantes de esta estructura:</span><span class="sxs-lookup"><span data-stu-id="57299-146">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="57299-147">Patterns that require more evidence have a higher confidence level.</span><span class="sxs-lookup"><span data-stu-id="57299-147">Patterns that require more evidence have a higher confidence level.</span></span> <span data-ttu-id="57299-148">This is useful because when you later use this sensitive information type in a DLP policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span><span class="sxs-lookup"><span data-stu-id="57299-148">This is useful because when you later use this sensitive information type in a DLP policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="57299-149">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern.</span><span class="sxs-lookup"><span data-stu-id="57299-149">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern.</span></span> <span data-ttu-id="57299-150">These supporting elements are referenced by the Pattern but included in the Rule.</span><span class="sxs-lookup"><span data-stu-id="57299-150">These supporting elements are referenced by the Pattern but included in the Rule.</span></span> <span data-ttu-id="57299-151">This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span><span class="sxs-lookup"><span data-stu-id="57299-151">This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="57299-152">What entity do you need to identify?</span><span class="sxs-lookup"><span data-stu-id="57299-152">What entity do you need to identify?</span></span> <span data-ttu-id="57299-153">[Entity element, id attribute]</span><span class="sxs-lookup"><span data-stu-id="57299-153">[Entity element, id attribute]</span></span>

<span data-ttu-id="57299-154">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern.</span><span class="sxs-lookup"><span data-stu-id="57299-154">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern.</span></span> <span data-ttu-id="57299-155">Each entity has a unique GUID as its ID.</span><span class="sxs-lookup"><span data-stu-id="57299-155">Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="57299-156">Asignar un nombre a la entidad y generar su GUID</span><span class="sxs-lookup"><span data-stu-id="57299-156">Name the entity and generate its GUID</span></span>
<!-- why isn't the following in procedure format? -->
<span data-ttu-id="57299-157">Add the Rules and Entity elements.</span><span class="sxs-lookup"><span data-stu-id="57299-157">Add the Rules and Entity elements.</span></span> <span data-ttu-id="57299-158">Then add a comment that contains the name of your custom entity - in this example, Employee ID.</span><span class="sxs-lookup"><span data-stu-id="57299-158">Then add a comment that contains the name of your custom entity - in this example, Employee ID.</span></span> <span data-ttu-id="57299-159">Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a DLP policy.</span><span class="sxs-lookup"><span data-stu-id="57299-159">Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a DLP policy.</span></span>
  
<span data-ttu-id="57299-160">Next, generate a GUID for your entity.</span><span class="sxs-lookup"><span data-stu-id="57299-160">Next, generate a GUID for your entity.</span></span> <span data-ttu-id="57299-161">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span><span class="sxs-lookup"><span data-stu-id="57299-161">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span> <span data-ttu-id="57299-162">Later, you'll also add the entity GUID to the localized strings section.</span><span class="sxs-lookup"><span data-stu-id="57299-162">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![Marcado XML donde se muestran los elementos Rules y Entity](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="57299-164">What pattern do you want to match?</span><span class="sxs-lookup"><span data-stu-id="57299-164">What pattern do you want to match?</span></span> <span data-ttu-id="57299-165">[Pattern element, IdMatch element, Regex element]</span><span class="sxs-lookup"><span data-stu-id="57299-165">[Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="57299-166">The pattern contains the list of what the sensitive information type is looking for.</span><span class="sxs-lookup"><span data-stu-id="57299-166">The pattern contains the list of what the sensitive information type is looking for.</span></span> <span data-ttu-id="57299-167">This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses).</span><span class="sxs-lookup"><span data-stu-id="57299-167">This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses).</span></span> <span data-ttu-id="57299-168">Sensitive information types can have multiple patterns with unique confidences.</span><span class="sxs-lookup"><span data-stu-id="57299-168">Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="57299-169">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) …</span><span class="sxs-lookup"><span data-stu-id="57299-169">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) …</span></span> <span data-ttu-id="57299-170">(\s).</span><span class="sxs-lookup"><span data-stu-id="57299-170">(\s).</span></span> <span data-ttu-id="57299-171">This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity.</span><span class="sxs-lookup"><span data-stu-id="57299-171">This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity.</span></span> <span data-ttu-id="57299-172">IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number.</span><span class="sxs-lookup"><span data-stu-id="57299-172">IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number.</span></span> <span data-ttu-id="57299-173">A Pattern element must have exactly one IdMatch element.</span><span class="sxs-lookup"><span data-stu-id="57299-173">A Pattern element must have exactly one IdMatch element.</span></span>
  
![Marcado XML donde se muestran varios elementos Pattern que hacen referencia a un único elemento Regex](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="57299-175">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy.</span><span class="sxs-lookup"><span data-stu-id="57299-175">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy.</span></span> <span data-ttu-id="57299-176">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here.</span><span class="sxs-lookup"><span data-stu-id="57299-176">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here.</span></span> <span data-ttu-id="57299-177">Confidence level (also called match accuracy) is explained later in this topic.</span><span class="sxs-lookup"><span data-stu-id="57299-177">Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![Opciones de precisión de coincidencia y recuento de instancias](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="57299-179">When you create your regular expression, keep in mind that there are potential issues to be aware of.</span><span class="sxs-lookup"><span data-stu-id="57299-179">When you create your regular expression, keep in mind that there are potential issues to be aware of.</span></span> <span data-ttu-id="57299-180">For example, if you write and upload a regex that identifies too much content, this can impact performance.</span><span class="sxs-lookup"><span data-stu-id="57299-180">For example, if you write and upload a regex that identifies too much content, this can impact performance.</span></span> <span data-ttu-id="57299-181">To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span><span class="sxs-lookup"><span data-stu-id="57299-181">To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="57299-182">Do you want to require additional evidence?</span><span class="sxs-lookup"><span data-stu-id="57299-182">Do you want to require additional evidence?</span></span> <span data-ttu-id="57299-183">[Match element, minCount attribute]</span><span class="sxs-lookup"><span data-stu-id="57299-183">[Match element, minCount attribute]</span></span>

<span data-ttu-id="57299-184">Además del elemento IdMatch, un patrón puede usar el elemento Match para exigir pruebas complementarias adicionales, como una palabra clave, una expresión regular, una fecha o una dirección.</span><span class="sxs-lookup"><span data-stu-id="57299-184">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="57299-185">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element.</span><span class="sxs-lookup"><span data-stu-id="57299-185">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element.</span></span> <span data-ttu-id="57299-186">Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched.</span><span class="sxs-lookup"><span data-stu-id="57299-186">Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched.</span></span> <span data-ttu-id="57299-187">You can use the Any element to introduce AND or OR operators (more on that in a later section).</span><span class="sxs-lookup"><span data-stu-id="57299-187">You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="57299-188">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements.</span><span class="sxs-lookup"><span data-stu-id="57299-188">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements.</span></span> <span data-ttu-id="57299-189">For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span><span class="sxs-lookup"><span data-stu-id="57299-189">For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![Marcado XML donde se muestra el elemento Match con el atributo minOccurs](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="57299-191">Palabras clave [elementos Keyword, Group y Term, atributos matchStyle y caseSensitive]</span><span class="sxs-lookup"><span data-stu-id="57299-191">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="57299-192">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence.</span><span class="sxs-lookup"><span data-stu-id="57299-192">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence.</span></span> <span data-ttu-id="57299-193">For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID".</span><span class="sxs-lookup"><span data-stu-id="57299-193">For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID".</span></span> <span data-ttu-id="57299-194">To do this, you use the Keyword element.</span><span class="sxs-lookup"><span data-stu-id="57299-194">To do this, you use the Keyword element.</span></span> <span data-ttu-id="57299-195">The Keyword element has an id attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span><span class="sxs-lookup"><span data-stu-id="57299-195">The Keyword element has an id attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="57299-196">Keywords are included as a list of Term elements in a Group element.</span><span class="sxs-lookup"><span data-stu-id="57299-196">Keywords are included as a list of Term elements in a Group element.</span></span> <span data-ttu-id="57299-197">The Group element has a matchStyle attribute with two possible values:</span><span class="sxs-lookup"><span data-stu-id="57299-197">The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="57299-198">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters.</span><span class="sxs-lookup"><span data-stu-id="57299-198">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters.</span></span> <span data-ttu-id="57299-199">You should always use word unless you need to match parts of words or match words in Asian languages.</span><span class="sxs-lookup"><span data-stu-id="57299-199">You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="57299-200">**matchStyle="string"** String match identifies strings no matter what they're surrounded by.</span><span class="sxs-lookup"><span data-stu-id="57299-200">**matchStyle="string"** String match identifies strings no matter what they're surrounded by.</span></span> <span data-ttu-id="57299-201">For example, "id" will match "bid" and "idea".</span><span class="sxs-lookup"><span data-stu-id="57299-201">For example, "id" will match "bid" and "idea".</span></span> <span data-ttu-id="57299-202">Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span><span class="sxs-lookup"><span data-stu-id="57299-202">Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="57299-203">Por último, puede usar el atributo caseSensitive del elemento Term para especificar que el contenido tiene que coincidir exactamente con la palabra clave, incluidas las letras en minúscula y mayúscula.</span><span class="sxs-lookup"><span data-stu-id="57299-203">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![Marcado XML donde se muestran elementos Match que hacen referencia palabras clave](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="57299-205">Expresiones regulares [elemento Regex]</span><span class="sxs-lookup"><span data-stu-id="57299-205">Regular expressions [Regex element]</span></span>

<span data-ttu-id="57299-206">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern - a nine-digit number surrounded by whitespace.</span><span class="sxs-lookup"><span data-stu-id="57299-206">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern - a nine-digit number surrounded by whitespace.</span></span> <span data-ttu-id="57299-207">In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span><span class="sxs-lookup"><span data-stu-id="57299-207">In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="57299-208">Patrones adicionales, como fechas o direcciones [funciones integradas]</span><span class="sxs-lookup"><span data-stu-id="57299-208">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="57299-209">In addition to the built-in sensitive information types, DLP also includes built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address.</span><span class="sxs-lookup"><span data-stu-id="57299-209">In addition to the built-in sensitive information types, DLP also includes built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address.</span></span> <span data-ttu-id="57299-210">DLP does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span><span class="sxs-lookup"><span data-stu-id="57299-210">DLP does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="57299-211">Por ejemplo, una tarjeta de identificación de empleado contiene una fecha de contratación, por lo que esta entidad personalizada puede usar la función integrada `Func_us_date` para identificar una fecha en el formato usado normalmente en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="57299-211">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="57299-212">Para obtener más información, vea [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="57299-212">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![Marcado XML donde se muestra el elemento Match que hace referencia a una función integrada](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="57299-214">Diferentes combinaciones de pruebas [elemento Any, atributos minMatches y maxMatches]</span><span class="sxs-lookup"><span data-stu-id="57299-214">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="57299-215">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator - all of the matches must be satisfied before the pattern can be satisfied.</span><span class="sxs-lookup"><span data-stu-id="57299-215">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator - all of the matches must be satisfied before the pattern can be satisfied.</span></span> <span data-ttu-id="57299-216">However, you can create more flexible matching logic by using the Any element to group Match elements.</span><span class="sxs-lookup"><span data-stu-id="57299-216">However, you can create more flexible matching logic by using the Any element to group Match elements.</span></span> <span data-ttu-id="57299-217">For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span><span class="sxs-lookup"><span data-stu-id="57299-217">For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="57299-218">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched.</span><span class="sxs-lookup"><span data-stu-id="57299-218">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched.</span></span> <span data-ttu-id="57299-219">Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches.</span><span class="sxs-lookup"><span data-stu-id="57299-219">Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches.</span></span> <span data-ttu-id="57299-220">To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span><span class="sxs-lookup"><span data-stu-id="57299-220">To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="57299-221">Coincidir como mínimo con un elemento Match secundario</span><span class="sxs-lookup"><span data-stu-id="57299-221">Match at least one child Match element</span></span>

<span data-ttu-id="57299-222">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute.</span><span class="sxs-lookup"><span data-stu-id="57299-222">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute.</span></span> <span data-ttu-id="57299-223">In effect, these Match elements are joined by an implicit OR operator.</span><span class="sxs-lookup"><span data-stu-id="57299-223">In effect, these Match elements are joined by an implicit OR operator.</span></span> <span data-ttu-id="57299-224">This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span><span class="sxs-lookup"><span data-stu-id="57299-224">This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="57299-225">Coincidir un subconjunto exacto de elementos Match secundarios</span><span class="sxs-lookup"><span data-stu-id="57299-225">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="57299-226">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value.</span><span class="sxs-lookup"><span data-stu-id="57299-226">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value.</span></span> <span data-ttu-id="57299-227">This Any element is satisfied only if exactly one date or keyword is found - any more than that, and the pattern won't be matched.</span><span class="sxs-lookup"><span data-stu-id="57299-227">This Any element is satisfied only if exactly one date or keyword is found - any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="57299-228">Ninguna coincidencia de elementos Match secundarios</span><span class="sxs-lookup"><span data-stu-id="57299-228">Match none of children Match elements</span></span>

<span data-ttu-id="57299-229">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0.</span><span class="sxs-lookup"><span data-stu-id="57299-229">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0.</span></span> <span data-ttu-id="57299-230">This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span><span class="sxs-lookup"><span data-stu-id="57299-230">This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="57299-231">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card".</span><span class="sxs-lookup"><span data-stu-id="57299-231">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card".</span></span> <span data-ttu-id="57299-232">However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card".</span><span class="sxs-lookup"><span data-stu-id="57299-232">However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card".</span></span> <span data-ttu-id="57299-233">So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span><span class="sxs-lookup"><span data-stu-id="57299-233">So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="57299-234">Coincidencia de varios términos únicos</span><span class="sxs-lookup"><span data-stu-id="57299-234">Match a number of unique terms</span></span>

<span data-ttu-id="57299-235">Si quiere hacer coincidir una serie de condiciones únicas, utilice el parámetro *uniqueResults*, establecido en *true*, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57299-235">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="57299-236">En este ejemplo, se define un patrón para la revisión del salario con al menos tres coincidencias únicas.</span><span class="sxs-lookup"><span data-stu-id="57299-236">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="57299-237">How close to the entity must the other evidence be?</span><span class="sxs-lookup"><span data-stu-id="57299-237">How close to the entity must the other evidence be?</span></span> <span data-ttu-id="57299-238">[patternsProximity attribute]</span><span class="sxs-lookup"><span data-stu-id="57299-238">[patternsProximity attribute]</span></span>

<span data-ttu-id="57299-239">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID".</span><span class="sxs-lookup"><span data-stu-id="57299-239">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID".</span></span> <span data-ttu-id="57299-240">It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID.</span><span class="sxs-lookup"><span data-stu-id="57299-240">It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID.</span></span> <span data-ttu-id="57299-241">You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span><span class="sxs-lookup"><span data-stu-id="57299-241">You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![Marcado XML donde se muestra el atributo patternsProximity](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="57299-243">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern.</span><span class="sxs-lookup"><span data-stu-id="57299-243">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern.</span></span> <span data-ttu-id="57299-244">The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span><span class="sxs-lookup"><span data-stu-id="57299-244">The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![Diagrama de la ventana de proximidad](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="57299-246">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date.</span><span class="sxs-lookup"><span data-stu-id="57299-246">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date.</span></span> <span data-ttu-id="57299-247">Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span><span class="sxs-lookup"><span data-stu-id="57299-247">Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![Diagrama de prueba corroboradora y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="57299-249">Note that for email, the message body and each attachment are treated as separate items.</span><span class="sxs-lookup"><span data-stu-id="57299-249">Note that for email, the message body and each attachment are treated as separate items.</span></span> <span data-ttu-id="57299-250">This means that the proximity window does not extend beyond the end of each of these items.</span><span class="sxs-lookup"><span data-stu-id="57299-250">This means that the proximity window does not extend beyond the end of each of these items.</span></span> <span data-ttu-id="57299-251">For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span><span class="sxs-lookup"><span data-stu-id="57299-251">For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="57299-252">What are the right confidence levels for different patterns?</span><span class="sxs-lookup"><span data-stu-id="57299-252">What are the right confidence levels for different patterns?</span></span> <span data-ttu-id="57299-253">[confidenceLevel attribute, recommendedConfidence attribute]</span><span class="sxs-lookup"><span data-stu-id="57299-253">[confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="57299-254">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched.</span><span class="sxs-lookup"><span data-stu-id="57299-254">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched.</span></span> <span data-ttu-id="57299-255">For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span><span class="sxs-lookup"><span data-stu-id="57299-255">For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="57299-256">The Pattern element has a required confidenceLevel attribute.</span><span class="sxs-lookup"><span data-stu-id="57299-256">The Pattern element has a required confidenceLevel attribute.</span></span> <span data-ttu-id="57299-257">You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity - the patterns in an entity must have different confidence levels that you assign.</span><span class="sxs-lookup"><span data-stu-id="57299-257">You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity - the patterns in an entity must have different confidence levels that you assign.</span></span> <span data-ttu-id="57299-258">The precise value of the integer doesn't matter - simply pick numbers that make sense to your compliance team.</span><span class="sxs-lookup"><span data-stu-id="57299-258">The precise value of the integer doesn't matter - simply pick numbers that make sense to your compliance team.</span></span> <span data-ttu-id="57299-259">After you upload your custom sensitive information type and then create a DLP policy, you can reference these confidence levels in the conditions of the rules that you create.</span><span class="sxs-lookup"><span data-stu-id="57299-259">After you upload your custom sensitive information type and then create a DLP policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![Marcado XML donde se muestran los elementos Pattern con distintos valores para el atributo confidenceLevel](../media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
<span data-ttu-id="57299-261">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span><span class="sxs-lookup"><span data-stu-id="57299-261">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="57299-262">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span><span class="sxs-lookup"><span data-stu-id="57299-262">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="57299-263">When you create a rule in a DLP policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span><span class="sxs-lookup"><span data-stu-id="57299-263">When you create a rule in a DLP policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span>
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-security-amp-compliance-center-localizedstrings-element"></a><span data-ttu-id="57299-264">Do you want to support other languages in the UI of the Security &amp; Compliance Center?</span><span class="sxs-lookup"><span data-stu-id="57299-264">Do you want to support other languages in the UI of the Security &amp; Compliance Center?</span></span> <span data-ttu-id="57299-265">[LocalizedStrings element]</span><span class="sxs-lookup"><span data-stu-id="57299-265">[LocalizedStrings element]</span></span>

<span data-ttu-id="57299-266">If your compliance team uses the Microsoft 365 Security &amp; Compliance Center to create DLP policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="57299-266">If your compliance team uses the Microsoft 365 Security &amp; Compliance Center to create DLP policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type.</span></span> <span data-ttu-id="57299-267">When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span><span class="sxs-lookup"><span data-stu-id="57299-267">When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![Opciones de precisión de coincidencia y recuento de instancias](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="57299-269">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity.</span><span class="sxs-lookup"><span data-stu-id="57299-269">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity.</span></span> <span data-ttu-id="57299-270">In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span><span class="sxs-lookup"><span data-stu-id="57299-270">In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![Marcado XML donde se muestra el contenido del elemento LocalizedStrings](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="57299-272">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="57299-272">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Security &amp; Compliance Center.</span></span> <span data-ttu-id="57299-273">You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span><span class="sxs-lookup"><span data-stu-id="57299-273">You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="57299-274">Otro marcado de paquete de reglas [GUID de RulePack]</span><span class="sxs-lookup"><span data-stu-id="57299-274">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="57299-275">Finally, the beginning of each RulePackage contains some general information that you need to fill in.</span><span class="sxs-lookup"><span data-stu-id="57299-275">Finally, the beginning of each RulePackage contains some general information that you need to fill in.</span></span> <span data-ttu-id="57299-276">You can use the following markup as a template and replace the ".</span><span class="sxs-lookup"><span data-stu-id="57299-276">You can use the following markup as a template and replace the ".</span></span> <span data-ttu-id="57299-277">.</span><span class="sxs-lookup"><span data-stu-id="57299-277">.</span></span> <span data-ttu-id="57299-278">."</span><span class="sxs-lookup"><span data-stu-id="57299-278">."</span></span> <span data-ttu-id="57299-279">placeholders with your own info.</span><span class="sxs-lookup"><span data-stu-id="57299-279">placeholders with your own info.</span></span>
  
<span data-ttu-id="57299-280">Most importantly, you'll need to generate a GUID for the RulePack.</span><span class="sxs-lookup"><span data-stu-id="57299-280">Most importantly, you'll need to generate a GUID for the RulePack.</span></span> <span data-ttu-id="57299-281">Above, you generated a GUID for the entity; this is a second GUID for the RulePack.</span><span class="sxs-lookup"><span data-stu-id="57299-281">Above, you generated a GUID for the entity; this is a second GUID for the RulePack.</span></span> <span data-ttu-id="57299-282">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span><span class="sxs-lookup"><span data-stu-id="57299-282">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="57299-283">The Version element is also important.</span><span class="sxs-lookup"><span data-stu-id="57299-283">The Version element is also important.</span></span> <span data-ttu-id="57299-284">When you upload your rule package for the first time, Microsoft 365 notes the version number.</span><span class="sxs-lookup"><span data-stu-id="57299-284">When you upload your rule package for the first time, Microsoft 365 notes the version number.</span></span> <span data-ttu-id="57299-285">Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span><span class="sxs-lookup"><span data-stu-id="57299-285">Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    . . .
 </Rules>
</RulePackage>

```

<span data-ttu-id="57299-286">Una vez completado, el elemento RulePack será parecido a este.</span><span class="sxs-lookup"><span data-stu-id="57299-286">When complete, your RulePack element should look like this.</span></span>
  
![Marcado XML donde se muestra el elemento RulePack](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="57299-288">Cambios para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57299-288">Changes for Exchange Online</span></span>

<span data-ttu-id="57299-289">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP.</span><span class="sxs-lookup"><span data-stu-id="57299-289">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP.</span></span> <span data-ttu-id="57299-290">Now your custom sensitive information types can be used in both the Exchange admin center and the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="57299-290">Now your custom sensitive information types can be used in both the Exchange admin center and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="57299-291">As part of this improvement, you should use Security &amp; Compliance Center PowerShell to import your custom sensitive information types - you can't import them from the Exchange PowerShell anymore.</span><span class="sxs-lookup"><span data-stu-id="57299-291">As part of this improvement, you should use Security &amp; Compliance Center PowerShell to import your custom sensitive information types - you can't import them from the Exchange PowerShell anymore.</span></span> <span data-ttu-id="57299-292">Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Security &amp; Compliance Center to appear in the Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="57299-292">Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Security &amp; Compliance Center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="57299-293">Note that in the Security &amp; Compliance Center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** cmdlet to upload a rule package.</span><span class="sxs-lookup"><span data-stu-id="57299-293">Note that in the Security &amp; Compliance Center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="57299-294">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="57299-294">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="57299-295">Cargar un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="57299-295">Upload your rule package</span></span>



<span data-ttu-id="57299-296">Para cargar un paquete de reglas, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="57299-296">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="57299-297">Guárdelo como un archivo .xml con codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="57299-297">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="57299-298">Conectarse a PowerShell del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="57299-298">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. <span data-ttu-id="57299-299">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="57299-299">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="57299-300">En este ejemplo se carga el archivo XML de Unicode denominado MyNewRulePack.xml desde C:\Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="57299-300">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="57299-301">Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="57299-301">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="57299-302">El límite para las colecciones de tipo de información confidencial personalizado es de 10.</span><span class="sxs-lookup"><span data-stu-id="57299-302">The limit for custom sensitive information type collections is 10.</span></span>

4. <span data-ttu-id="57299-303">Para comprobar si un tipo de información confidencial se creó correctamente, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="57299-303">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="57299-304">Ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) para comprobar que se muestra el nuevo paquete de reglas en la lista:</span><span class="sxs-lookup"><span data-stu-id="57299-304">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="57299-305">Ejecute el cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) para comprobar que se muestra el tipo de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="57299-305">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="57299-306">Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.</span><span class="sxs-lookup"><span data-stu-id="57299-306">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="57299-307">Reemplace \<Name\> con el valor de Nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="57299-307">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="57299-308">Posibles problemas de validación</span><span class="sxs-lookup"><span data-stu-id="57299-308">Potential validation issues to be aware of</span></span>

<span data-ttu-id="57299-309">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues.</span><span class="sxs-lookup"><span data-stu-id="57299-309">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues.</span></span> <span data-ttu-id="57299-310">Here are some known issues that the validation checks for — a regular expression:</span><span class="sxs-lookup"><span data-stu-id="57299-310">Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="57299-311">No puede empezar ni terminar con el alternador "|", que coincide con todo, ya que se considera una coincidencia vacía.</span><span class="sxs-lookup"><span data-stu-id="57299-311">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="57299-312">Por ejemplo, "|a" o "b|" no superarán la validación.</span><span class="sxs-lookup"><span data-stu-id="57299-312">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="57299-313">No puede empezar ni terminar con un patrón ".{0,m}", ya que no tiene ninguna finalidad funcional y solo perjudica al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="57299-313">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="57299-314">Por ejemplo, ".{0,50}ASDF" o "ASDF.{0,50}" no superarán la validación.</span><span class="sxs-lookup"><span data-stu-id="57299-314">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="57299-315">No puede tener ".{0,m}" o "{1,m}" en grupos, ni tampoco ".\*" o ".+" en grupos.</span><span class="sxs-lookup"><span data-stu-id="57299-315">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="57299-316">Por ejemplo, "(.{0,50000})" no superará la validación.</span><span class="sxs-lookup"><span data-stu-id="57299-316">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="57299-317">No puede tener ningún carácter con los repetidores "{0,m}" o "{1,m}" en grupos.</span><span class="sxs-lookup"><span data-stu-id="57299-317">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="57299-318">Por ejemplo, "(a\*)" no superará la validación.</span><span class="sxs-lookup"><span data-stu-id="57299-318">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="57299-319">No puede empezar ni terminar con ".{1,m}" (en su lugar, use simplemente ".").</span><span class="sxs-lookup"><span data-stu-id="57299-319">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="57299-320">Por ejemplo, ".{1,m}asdf" no superará la validación; en su lugar, use ".asdf".</span><span class="sxs-lookup"><span data-stu-id="57299-320">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="57299-321">No puede tener un repetidor no enlazado (como "\*" o "+") en un grupo.</span><span class="sxs-lookup"><span data-stu-id="57299-321">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="57299-322">Por ejemplo, "(xx)\*" y "(xx)+" no superarán la validación.</span><span class="sxs-lookup"><span data-stu-id="57299-322">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
    
<span data-ttu-id="57299-323">Si un tipo personalizado de información confidencial contiene un problema que puede afectar al rendimiento, no se cargará y es posible que se muestre uno de estos mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="57299-323">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="57299-324">**Cuantificadores genéricos que coinciden con más de un contenido de lo esperado (por ejemplo, "+", "\*")**</span><span class="sxs-lookup"><span data-stu-id="57299-324">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="57299-325">**Aserciones de búsqueda anticipada y posterior**</span><span class="sxs-lookup"><span data-stu-id="57299-325">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="57299-326">**Agrupación compleja en conjunto con cuantificadores generales**</span><span class="sxs-lookup"><span data-stu-id="57299-326">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="57299-327">Volver a rastrear el contenido para identificar la información confidencial</span><span class="sxs-lookup"><span data-stu-id="57299-327">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="57299-328">DLP uses the search crawler to identify and classify sensitive information in site content.</span><span class="sxs-lookup"><span data-stu-id="57299-328">DLP uses the search crawler to identify and classify sensitive information in site content.</span></span> <span data-ttu-id="57299-329">Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated.</span><span class="sxs-lookup"><span data-stu-id="57299-329">Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated.</span></span> <span data-ttu-id="57299-330">But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span><span class="sxs-lookup"><span data-stu-id="57299-330">But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="57299-331">En Microsoft 365, no se puede solicitar de forma manual un nuevo rastreo de todo un espacio empresarial, pero puede hacerlo para una colección de sitios, una lista o una biblioteca (vea [Solicitar de forma manual un rastreo y volver a indexar un sitio, una biblioteca o una lista](https://docs.microsoft.com/sharepoint/crawl-site-content)).</span><span class="sxs-lookup"><span data-stu-id="57299-331">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library - see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="57299-332">Eliminación de un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="57299-332">Remove a custom sensitive information type</span></span>

> [!NOTE]
> <span data-ttu-id="57299-333">Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="57299-333">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="57299-334">En PowerShell del Centro de seguridad y cumplimiento, hay dos métodos para quitar los tipos personalizados de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="57299-334">In Security & Compliance Center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="57299-335">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type).</span><span class="sxs-lookup"><span data-stu-id="57299-335">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type).</span></span> <span data-ttu-id="57299-336">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span><span class="sxs-lookup"><span data-stu-id="57299-336">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="57299-337">**Quitar un paquete de reglas personalizado y todos los tipos de información confidencial que contiene**: este método se documenta en esta sección.</span><span class="sxs-lookup"><span data-stu-id="57299-337">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="57299-338">Conectarse a PowerShell del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="57299-338">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)

2. <span data-ttu-id="57299-339">Para quitar un paquete de reglas personalizado, use el cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="57299-339">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="57299-340">Puede usar el valor de nombre (en cualquier idioma) o el valor (GUID) `RulePack id` para identificar el paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="57299-340">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="57299-341">En este ejemplo se quita el paquete de reglas denominado "Paquete de reglas personalizado de Id. de empleado".</span><span class="sxs-lookup"><span data-stu-id="57299-341">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="57299-342">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="57299-342">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="57299-343">Para comprobar que ha quitado correctamente un nuevo tipo personalizado de información confidencial, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="57299-343">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="57299-344">Ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) y compruebe que ya no se muestra el paquete de reglas en la lista:</span><span class="sxs-lookup"><span data-stu-id="57299-344">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="57299-345">Ejecute el cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) para comprobar que ya no aparecen los tipos de información confidencial en el paquete de reglas que ha quitado:</span><span class="sxs-lookup"><span data-stu-id="57299-345">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="57299-346">Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.</span><span class="sxs-lookup"><span data-stu-id="57299-346">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="57299-347">Reemplace \<Name\> con el valor de Nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) para comprobar que el tipo de información confidencial ya no aparece:</span><span class="sxs-lookup"><span data-stu-id="57299-347">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="57299-348">Modificación de un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="57299-348">Modify a custom sensitive information type</span></span>

<span data-ttu-id="57299-349">Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57299-349">In Security & Compliance Center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="57299-350">Exporte el paquete de reglas existente que contiene el tipo de información confidencial a un archivo XML (o, si lo tiene, use el archivo XML existente).</span><span class="sxs-lookup"><span data-stu-id="57299-350">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="57299-351">Modifique el tipo personalizado de información confidencial en el archivo XML exportado.</span><span class="sxs-lookup"><span data-stu-id="57299-351">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="57299-352">Importe el archivo XML actualizado en el paquete de reglas existentes.</span><span class="sxs-lookup"><span data-stu-id="57299-352">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="57299-353">Para conectarse a PowerShell del Centro de seguridad y cumplimiento, vea [Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span><span class="sxs-lookup"><span data-stu-id="57299-353">To connect to Security & Compliance Center PowerShell, see [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="57299-354">Paso 1: exportar el paquete de reglas existentes a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="57299-354">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="57299-355">Si tiene una copia del archivo XML (si, por ejemplo, lo acaba de crear y de importar), puede saltar al paso siguiente para modificar el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="57299-355">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="57299-356">Si aún no lo sabe, ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) para buscar el nombre del paquete de reglas personalizado:</span><span class="sxs-lookup"><span data-stu-id="57299-356">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="57299-357">El paquete de reglas integrado que contiene los tipos de información confidencial integrados se denomina Paquete de reglas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="57299-357">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="57299-358">El paquete de reglas que contiene los tipos de información confidencial personalizados que creó en la interfaz de usuario del Centro de seguridad y cumplimiento se denomina Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="57299-358">The rule package that contains the custom sensitive information types that you created in the Security & Compliance Center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="57299-359">Use el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) para almacenar el paquete de reglas personalizadas en una variable:</span><span class="sxs-lookup"><span data-stu-id="57299-359">Use the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="57299-360">Por ejemplo, si el paquete de reglas se llama "Paquete de reglas personalizado de Id. de empleado", ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="57299-360">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="57299-361">Use el cmdlet [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) para exportar el paquete de reglas personalizado a un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="57299-361">Use the [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="57299-362">En este ejemplo se exporta el paquete de reglas para el archivo denominado ExportedRulePackage.xml en la carpeta C:\Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="57299-362">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="57299-363">Paso 2: modificar el tipo de información confidencial en el archivo XML exportado</span><span class="sxs-lookup"><span data-stu-id="57299-363">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="57299-364">Anteriormente en este tema se describen los tipos de información confidencial en el archivo XML y otros elementos del archivo.</span><span class="sxs-lookup"><span data-stu-id="57299-364">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="57299-365">Paso 3: importar el archivo XML actualizado en el paquete de reglas existentes</span><span class="sxs-lookup"><span data-stu-id="57299-365">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="57299-366">Para importar el archivo XML actualizado en el paquete de reglas existentes, use el cmdlet [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="57299-366">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="57299-367">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="57299-367">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="57299-368">Referencia: Definición de esquema XML de paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="57299-368">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="57299-369">Puede copiar este marcado, guardarlo como un archivo XSD y usarlo para validar el archivo XML del paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="57299-369">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="https://schemas.microsoft.com/office/2011/mce"
           targetNamespace="https://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a><span data-ttu-id="57299-370">Más información</span><span class="sxs-lookup"><span data-stu-id="57299-370">More information</span></span>

- [<span data-ttu-id="57299-371">Información general sobre las directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="57299-371">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="57299-372">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="57299-372">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="57299-373">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="57299-373">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
