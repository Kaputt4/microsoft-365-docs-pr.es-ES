---
title: Personalizar un tipo de información confidencial integrado
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información acerca de cómo crear un tipo de información confidencial personalizado que le permita usar reglas que cumplan con las necesidades de su organización.
ms.openlocfilehash: 7c9be91de796ed06ca2bdd71e9e4de0462a92358
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817939"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="35781-103">Personalizar un tipo de información confidencial integrado</span><span class="sxs-lookup"><span data-stu-id="35781-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="35781-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span><span class="sxs-lookup"><span data-stu-id="35781-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span></span> <span data-ttu-id="35781-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span><span class="sxs-lookup"><span data-stu-id="35781-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span></span> <span data-ttu-id="35781-106">To use these rules, you have to include them in a policy.</span><span class="sxs-lookup"><span data-stu-id="35781-106">To use these rules, you have to include them in a policy.</span></span> <span data-ttu-id="35781-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="35781-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span></span> <span data-ttu-id="35781-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span><span class="sxs-lookup"><span data-stu-id="35781-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="35781-109">You can take this example and apply it to other built-in sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="35781-109">You can take this example and apply it to other built-in sensitive information types.</span></span> <span data-ttu-id="35781-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="35781-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="35781-111">Exportar el archivo XML de las reglas actuales</span><span class="sxs-lookup"><span data-stu-id="35781-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="35781-112">Para exportar el archivo XML, necesita [conectarse al Centro de seguridad y cumplimiento mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="35781-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="35781-113">In the PowerShell, type the following to display your organization's rules on screen.</span><span class="sxs-lookup"><span data-stu-id="35781-113">In the PowerShell, type the following to display your organization's rules on screen.</span></span> <span data-ttu-id="35781-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span><span class="sxs-lookup"><span data-stu-id="35781-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. <span data-ttu-id="35781-115">Store your organization's rules in a variable by typing the following.</span><span class="sxs-lookup"><span data-stu-id="35781-115">Store your organization's rules in a variable by typing the following.</span></span> <span data-ttu-id="35781-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span><span class="sxs-lookup"><span data-stu-id="35781-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. <span data-ttu-id="35781-117">Make a formatted XML file with all that data by typing the following.</span><span class="sxs-lookup"><span data-stu-id="35781-117">Make a formatted XML file with all that data by typing the following.</span></span> <span data-ttu-id="35781-118">( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span><span class="sxs-lookup"><span data-stu-id="35781-118">( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> <span data-ttu-id="35781-119">Make sure that you use the file location where your rule pack is actually stored.</span><span class="sxs-lookup"><span data-stu-id="35781-119">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="35781-120">`C:\custompath\` is a placeholder.</span><span class="sxs-lookup"><span data-stu-id="35781-120">`C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="35781-121">Encontrar en el archivo XML la regla que quiera modificar</span><span class="sxs-lookup"><span data-stu-id="35781-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="35781-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span><span class="sxs-lookup"><span data-stu-id="35781-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span></span> <span data-ttu-id="35781-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span><span class="sxs-lookup"><span data-stu-id="35781-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="35781-124">Use un editor de texto para abrir el archivo XML exportado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="35781-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="35781-125">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules.</span><span class="sxs-lookup"><span data-stu-id="35781-125">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules.</span></span> <span data-ttu-id="35781-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span><span class="sxs-lookup"><span data-stu-id="35781-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>
    
3. <span data-ttu-id="35781-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span><span class="sxs-lookup"><span data-stu-id="35781-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span></span> <span data-ttu-id="35781-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span><span class="sxs-lookup"><span data-stu-id="35781-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span></span> <span data-ttu-id="35781-129">An example of this is the U.S. Social Security number rule, which is abbreviated "SSN."</span><span class="sxs-lookup"><span data-stu-id="35781-129">An example of this is the U.S. Social Security number rule, which is abbreviated "SSN."</span></span> <span data-ttu-id="35781-130">The Credit Card Number rule XML should look like the following code sample.</span><span class="sxs-lookup"><span data-stu-id="35781-130">The Credit Card Number rule XML should look like the following code sample.</span></span>
    
  ```xml
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

<span data-ttu-id="35781-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span><span class="sxs-lookup"><span data-stu-id="35781-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span></span> <span data-ttu-id="35781-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span><span class="sxs-lookup"><span data-stu-id="35781-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="35781-133">Modificar el código XML y crear un tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="35781-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="35781-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span><span class="sxs-lookup"><span data-stu-id="35781-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span></span> <span data-ttu-id="35781-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="35781-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="35781-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span><span class="sxs-lookup"><span data-stu-id="35781-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="35781-137">All XML rule definitions are built on the following general template.</span><span class="sxs-lookup"><span data-stu-id="35781-137">All XML rule definitions are built on the following general template.</span></span> <span data-ttu-id="35781-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span><span class="sxs-lookup"><span data-stu-id="35781-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span></span> <span data-ttu-id="35781-139">.</span><span class="sxs-lookup"><span data-stu-id="35781-139">.</span></span> <span data-ttu-id="35781-140">."</span><span class="sxs-lookup"><span data-stu-id="35781-140">."</span></span> <span data-ttu-id="35781-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span><span class="sxs-lookup"><span data-stu-id="35781-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="35781-142">Now, you have something that looks similar to the following XML.</span><span class="sxs-lookup"><span data-stu-id="35781-142">Now, you have something that looks similar to the following XML.</span></span> <span data-ttu-id="35781-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span><span class="sxs-lookup"><span data-stu-id="35781-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span></span> <span data-ttu-id="35781-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span><span class="sxs-lookup"><span data-stu-id="35781-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span></span> <span data-ttu-id="35781-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="35781-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="35781-146">Quitar el requisito de evidencias corroborativas de un tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="35781-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="35781-147">Ahora que tiene un tipo de información confidencial que puede cargar al Centro de seguridad &amp; cumplimiento, el siguiente paso es hacer que la regla sea más específica.</span><span class="sxs-lookup"><span data-stu-id="35781-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="35781-148">Modifique la regla para que solo busque un número de 16 dígitos que pasa la suma de comprobación pero no requiere evidencia corroborativa adicional (como las palabras clave).</span><span class="sxs-lookup"><span data-stu-id="35781-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="35781-149">Para ello, tiene que quitar la parte del código XML que busca la evidencia corroborativa.</span><span class="sxs-lookup"><span data-stu-id="35781-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="35781-150">La evidencia corroborativa es muy útil para reducir los falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="35781-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="35781-151">En este caso, suelen haber determinadas palabras clave o una fecha de expiración cerca del número de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="35781-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="35781-152">Si quita esa evidencia, debe ajustar también la seguridad que tiene de haber encontrado un número de tarjeta de crédito. Para ello, reduzca `confidenceLevel`, que es 85 en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="35781-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="35781-153">Buscar palabras clave específicas de la organización</span><span class="sxs-lookup"><span data-stu-id="35781-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="35781-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span><span class="sxs-lookup"><span data-stu-id="35781-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span></span> <span data-ttu-id="35781-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span><span class="sxs-lookup"><span data-stu-id="35781-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span></span> <span data-ttu-id="35781-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span><span class="sxs-lookup"><span data-stu-id="35781-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span></span> <span data-ttu-id="35781-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span><span class="sxs-lookup"><span data-stu-id="35781-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="35781-158">Cargar la regla</span><span class="sxs-lookup"><span data-stu-id="35781-158">Upload your rule</span></span>

<span data-ttu-id="35781-159">Para cargar la regla, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="35781-159">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="35781-160">Save it as an .xml file with Unicode encoding.</span><span class="sxs-lookup"><span data-stu-id="35781-160">Save it as an .xml file with Unicode encoding.</span></span> <span data-ttu-id="35781-161">This is important because the rule won't work if the file is saved with a different encoding.</span><span class="sxs-lookup"><span data-stu-id="35781-161">This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="35781-162">Conectarse al Centro de seguridad y cumplimiento con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="35781-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="35781-163">En el símbolo del sistema de PowerShell, escriba lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="35781-163">In the PowerShell, type the following.</span></span>

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> <span data-ttu-id="35781-164">Make sure that you use the file location where your rule pack is actually stored.</span><span class="sxs-lookup"><span data-stu-id="35781-164">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="35781-165">`C:\custompath\` is a placeholder.</span><span class="sxs-lookup"><span data-stu-id="35781-165">`C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="35781-166">Para confirmar, escriba “Y” y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="35781-166">To confirm, type Y, and then press **Enter**.</span></span>
5. <span data-ttu-id="35781-167">Compruebe que la nueva regla se haya cargado y que se muestre el nombre escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="35781-167">Verify that your new rule was uploaded and it's display name by typing:</span></span>

```powershell
Get-DlpSensitiveInformationType
```

<span data-ttu-id="35781-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span><span class="sxs-lookup"><span data-stu-id="35781-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span></span> <span data-ttu-id="35781-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="35781-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="35781-170">Glosario de términos</span><span class="sxs-lookup"><span data-stu-id="35781-170">Term glossary</span></span>

<span data-ttu-id="35781-171">Estas son las definiciones de los términos que encontró en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35781-171">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="35781-172">**Término**</span><span class="sxs-lookup"><span data-stu-id="35781-172">**Term**</span></span>|<span data-ttu-id="35781-173">**Definición**</span><span class="sxs-lookup"><span data-stu-id="35781-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="35781-174">Entidad</span><span class="sxs-lookup"><span data-stu-id="35781-174">Entity</span></span>|<span data-ttu-id="35781-175">Entities are what we call sensitive information types, such as credit card numbers.</span><span class="sxs-lookup"><span data-stu-id="35781-175">Entities are what we call sensitive information types, such as credit card numbers.</span></span> <span data-ttu-id="35781-176">Each entity has a unique GUID as its ID.</span><span class="sxs-lookup"><span data-stu-id="35781-176">Each entity has a unique GUID as its ID.</span></span> <span data-ttu-id="35781-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span><span class="sxs-lookup"><span data-stu-id="35781-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span></span> <span data-ttu-id="35781-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span><span class="sxs-lookup"><span data-stu-id="35781-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="35781-179">Funciones</span><span class="sxs-lookup"><span data-stu-id="35781-179">Functions</span></span>|<span data-ttu-id="35781-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span><span class="sxs-lookup"><span data-stu-id="35781-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span></span> <span data-ttu-id="35781-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span><span class="sxs-lookup"><span data-stu-id="35781-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="35781-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="35781-182">IdMatch</span></span>|<span data-ttu-id="35781-183">Este es el identificador para el que el patrón está intentando encontrar coincidencias, por ejemplo, un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="35781-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="35781-184">Listas de palabras clave</span><span class="sxs-lookup"><span data-stu-id="35781-184">Keyword lists</span></span>|<span data-ttu-id="35781-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span><span class="sxs-lookup"><span data-stu-id="35781-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span></span> <span data-ttu-id="35781-186">These aren't currently displayed in the XML.</span><span class="sxs-lookup"><span data-stu-id="35781-186">These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="35781-187">Pattern</span><span class="sxs-lookup"><span data-stu-id="35781-187">Pattern</span></span>|<span data-ttu-id="35781-188">El patrón contiene la lista de lo que el tipo confidencial está buscando.</span><span class="sxs-lookup"><span data-stu-id="35781-188">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="35781-189">Incluye palabras clave, regex y funciones internas que realizan tareas como verificar sumas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="35781-189">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="35781-190">Los tipos de información confidencial pueden tener varios patrones con confianzas únicas.</span><span class="sxs-lookup"><span data-stu-id="35781-190">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="35781-191">Esto resulta útil para crear un tipo de información confidencial que devuelve una confianza alta si se encuentra evidencia confirmativa y una confianza menor si se encuentra poca o ninguna evidencia confirmativa.</span><span class="sxs-lookup"><span data-stu-id="35781-191">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="35781-192">Patrón confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="35781-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="35781-193">This is the level of confidence that the DLP engine found a match.</span><span class="sxs-lookup"><span data-stu-id="35781-193">This is the level of confidence that the DLP engine found a match.</span></span> <span data-ttu-id="35781-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span><span class="sxs-lookup"><span data-stu-id="35781-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span></span> <span data-ttu-id="35781-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span><span class="sxs-lookup"><span data-stu-id="35781-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="35781-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="35781-196">patternsProximity</span></span>|<span data-ttu-id="35781-197">Cuando encontramos lo que parece un patrón de número de tarjeta de crédito, `patternsProximity` es la proximidad alrededor de la cual buscaremos una evidencia corroborativa.</span><span class="sxs-lookup"><span data-stu-id="35781-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="35781-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="35781-198">recommendedConfidence</span></span>|<span data-ttu-id="35781-199">This is the confidence level we recommend for this rule.</span><span class="sxs-lookup"><span data-stu-id="35781-199">This is the confidence level we recommend for this rule.</span></span> <span data-ttu-id="35781-200">The recommended confidence applies to entities and affinities.</span><span class="sxs-lookup"><span data-stu-id="35781-200">The recommended confidence applies to entities and affinities.</span></span> <span data-ttu-id="35781-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span><span class="sxs-lookup"><span data-stu-id="35781-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span></span> <span data-ttu-id="35781-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span><span class="sxs-lookup"><span data-stu-id="35781-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span></span> <span data-ttu-id="35781-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span><span class="sxs-lookup"><span data-stu-id="35781-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span></span> <span data-ttu-id="35781-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span><span class="sxs-lookup"><span data-stu-id="35781-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span></span> <span data-ttu-id="35781-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span><span class="sxs-lookup"><span data-stu-id="35781-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="35781-206">Más información</span><span class="sxs-lookup"><span data-stu-id="35781-206">For more information</span></span>

- [<span data-ttu-id="35781-207">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="35781-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="35781-208">Crear un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="35781-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="35781-209">Información general sobre las directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="35781-209">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
