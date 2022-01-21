---
title: Trabajar con las explicaciones del modelo de descripción de documentos en PowerShell
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: normal
description: Obtenga información sobre el trabajo con SharePoint Syntex explicación del modelo de documentos en PowerShell.
ms.openlocfilehash: 06f0eb7314b85f9463689fea32667666e5e167fd
ms.sourcegitcommit: d37fce3b708ea5232b4102fd0e693f4bf17a8948
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2022
ms.locfileid: "62159714"
---
# <a name="work-with-document-understanding-model-explanations-in-powershell"></a>Trabajar con las explicaciones del modelo de descripción de documentos en PowerShell

> [!IMPORTANT]
> Los SharePoint Syntex de PowerShell y todos los demás componentes pnP son herramientas de código abierto con el respaldo de una comunidad activa que les proporciona soporte técnico. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

Las plantillas de explicación personalizadas se almacenan en una lista dentro de un centro de contenido. Dado que estas explicaciones se almacenan como elementos de lista, PowerShell puede usarse para interactuar con ellos.

## <a name="list-saved-explanations"></a>Enumerar las explicaciones guardadas

En este ejemplo se muestra cómo ver todas las plantillas de explicación personalizadas que se han guardado en un centro de contenido específico.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list and items
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"
$explanations = Get-PnPListItem -List $explanationTemplatesList -Fields "Id", "Title", "ExplanationName", "ExplanationType", "ExplanationDescription","ExplanationContent"

# Extract explanation components
$explanationValues = $explanations.fieldvalues 
$explanationOutput = @()

foreach ($explanation in $explanationValues) {
    $content = $explanation.ExplanationContent
    $content = $content.replace('false','"false"')
    $content = $content.replace('true','"true"')
    $contentArray = $content | ConvertFrom-Json

    $output = New-Object -TypeName PSObject
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Explanation Name" -Value $explanation.ExplanationName
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Explanation Description" -Value $explanation.ExplanationDescription
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Explanation Type" -Value $contentArray.kind
    Add-Member -InputObject $output -MemberType NoteProperty -Name "RegEx Pattern" -Value $contentArray.pattern
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Phrase List" -Value $contentArray.ngrams
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Case Sensitive" -Value $contentArray.caseSensitive
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Ignore Digit Identity" -Value $contentArray.ignoreDigitIdentity
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Ignore Letter Identity" -Value $contentArray.ignoreLetterIdentity

    $explanationOutput += $output
}

$explanationOutput
```

## <a name="create-a-phrase-list-explanation"></a>Crear una explicación de lista de frases

En este ejemplo se muestra cómo crear una plantilla de explicación de lista de frases personalizada.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"
$explanationName = "Phrase Explanation A"
$explanationDescription = "This is my explanation"
$phrases = "Phrase 1", "Phrase 2"
$caseSensitive = $false
$ignoreDigitIdentity= $false
$ignoreLetterIdentity = $false

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"

#Generate GUID for explanation
$guid = New-Guid

#Format phrase list
$phrases = $phrases -join "`",`""

#Convert booleans to lower case strings
$caseSensitive = ($caseSensitive.ToString()).ToLower()
$ignoreDigitIdentity= ($ignoreDigitIdentity.ToString()).ToLower()
$ignoreLetterIdentity = ($ignoreLetterIdentity.ToString()).ToLower()

# Build explanation content
$explanationContent = "{`"id`":`"$guid`",`"kind`":`"dictionaryFeature`",`"name`":`"$explanationName`",`"active`":true,`"nGrams`":[`"$phrases`"],`"caseSensitive`":$caseSensitive,`"ignoreDigitIdentity`":$ignoreDigitIdentity,`"ignoreLetterIdentity`":$ignoreLetterIdentity}"

# Create item in explanation list
Add-PnPListItem -List $explanationTemplatesList -Values @{"Title"= $explanationName; "ExplanationName" = $explanationName; "ExplanationDescription" = $explanationDescription; "ExplanationContent" = $explanationContent}
```

## <a name="create-a-regular-expression-explanation"></a>Crear una explicación de expresión regular

En este ejemplo se muestra cómo crear una plantilla de explicación de expresión regular personalizada.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"
$explanationName = "RegEx Explanation A"
$explanationDescription = "This is my explanation"
$pattern = "\b(https?):\/\/\S+"

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"

#Generate GUID for explanation
$guid = New-Guid

# Build explanation content
$pattern = $pattern.Replace('\','\\')
$explanationContent = "{`"id`":`"$guid`",`"kind`":`"regexFeature`",`"name`":`"$explanationName`",`"active`":true,`"pattern`":`"$pattern`"}"

# Create item in explanation list
Add-PnPListItem -List $explanationTemplatesList -Values @{"Title"= $explanationName; "ExplanationName" = $explanationName; "ExplanationDescription" = $explanationDescription; "ExplanationContent" = $explanationContent}
```

## <a name="create-a-phrase-list-explanation-based-on-a-term-set"></a>Crear una explicación de lista de frases basada en un conjunto de términos

En este ejemplo se muestra cómo crear una plantilla de explicación de lista de frases personalizada tomando los valores de un conjunto de términos. Esto incluye los nombres de término preferidos y los sinónimos.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"
$termSetName = "Terms"
$termGroupName = "GroupA"
$explanationName = "MMS Explanation A"
$explanationDescription = "This is my explanation"
$caseSensitive = $false
$ignoreDigitIdentity= $false
$ignoreLetterIdentity = $false

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"

#Generate GUID for explanation
$guid = New-Guid

#Get term set, including preferred labels and synonyms
$terms = Get-PnPTerm -TermGroup $termGroupName -TermSet $termSetName -Includes Labels
$phrases = $terms.labels.value

#Format phrase list
$phrases = $phrases -join "`",`""

#Convert booleans to lower case strings
$caseSensitive = ($caseSensitive.ToString()).ToLower()
$ignoreDigitIdentity= ($ignoreDigitIdentity.ToString()).ToLower()
$ignoreLetterIdentity = ($ignoreLetterIdentity.ToString()).ToLower()

# Build explanation content
$explanationContent = "{`"id`":`"$guid`",`"kind`":`"dictionaryFeature`",`"name`":`"$explanationName`",`"active`":true,`"nGrams`":[`"$phrases`"],`"caseSensitive`":$caseSensitive,`"ignoreDigitIdentity`":$ignoreDigitIdentity,`"ignoreLetterIdentity`":$ignoreLetterIdentity}"

# Create item in explanation list
Add-PnPListItem -List $explanationTemplatesList -Values @{"Title"= $explanationName; "ExplanationName" = $explanationName; "ExplanationDescription" = $explanationDescription; "ExplanationContent" = $explanationContent}
```
