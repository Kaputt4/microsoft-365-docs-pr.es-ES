---
title: Publicación de modelos personalizados con PowerShell
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: medium
description: Obtenga información sobre cómo publicar modelos personalizados de Microsoft Syntex mediante PowerShell.
ms.openlocfilehash: 46724246d1a4c85676f1722c643968a09f843c79
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68661314"
---
# <a name="publish-custom-models-with-powershell"></a>Publicación de modelos personalizados con PowerShell

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos personalizados</sup>

> [!IMPORTANT]
> Los cmdlets de PowerShell de Microsoft Syntex y todos los demás componentes de PnP son herramientas de código abierto respaldadas por una comunidad activa que proporciona soporte técnico para ellos. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

Normalmente, los modelos de Syntex se implementan en bibliotecas de documentos en todo el inquilino. Esto se puede hacer mediante el sitio del centro de contenido, pero también se puede hacer con [PowerShell PnP](https://pnp.github.io/powershell/) , como se explica en este artículo.

## <a name="listing-the-available-models-in-a-content-center"></a>Enumeración de los modelos disponibles en un centro de contenido

Para obtener información general de los modelos agregados al sitio actual del centro de contenido de Syntex, use el cmdlet [Get-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html) :

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModel
```

## <a name="apply-a-model-to-a-library"></a>Aplicación de un modelo a una biblioteca

Para aplicar un modelo a una biblioteca, use el cmdlet [Publish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Publish-PnPSyntexModel.html) :

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Publish-PnPSyntexModel -Model "Contract Notice" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="understanding-where-a-model-is-used"></a>Descripción de dónde se usa un modelo

Una vez que haya implementado un modelo en muchas bibliotecas, es posible que desee revisar la lista de bibliotecas mediante el modelo. Esto se puede hacer con el cmdlet [Get-PnPSyntexModelPublication](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModelPublication.html) :

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModelPublication -Identity "Contract Notice"
```

## <a name="removing-a-model-from-a-library"></a>Eliminación de un modelo de una biblioteca

La eliminación de un modelo de una biblioteca sigue el mismo patrón que la aplicación y se puede realizar mediante el cmdlet [Unpublish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Unpublish-PnPSyntexModel.html) de forma interactiva o como lote de varias acciones.

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourSite"
Unpublish-PnPSyntexModel -Model "Invoice model" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="apply-models-in-bulk"></a>Aplicación masiva de modelos

Si desea publicar varios modelos en varias bibliotecas, cree un archivo CSV de entrada que muestre los modelos y las ubicaciones de destino:

```CSV
ModelName,TargetSiteUrl,TargetWebServerRelativeUrl,TargetLibraryServerRelativeUrl
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/shared%20documents
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/other
Trade Confirmation,https://contoso.sharepoint.com/sites/Site2,/sites/Site2,/sites/site2/shared%20documents
```

A continuación, este archivo CSV se puede usar como entrada en un script que publicará los modelos enumerados en las bibliotecas adecuadas. En el ejemplo siguiente, se usa el procesamiento por lotes para aumentar la eficacia de las solicitudes.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourSite"
$targetsCSV = "./Publish-SyntexModelBulk.csv"

Connect-PnPOnline -url $contentCenterURL

$targetLibraries = Import-Csv -Path $targetsCSV

$batch = New-PnPBatch

foreach ($target in $targetLibraries) {
    Publish-PnPSyntexModel -Model $target.ModelName -TargetSiteUrl $target.TargetSiteUrl -TargetWebServerRelativeUrl $target.TargetWebServerRelativeUrl -TargetLibraryServerRelativeUrl $target.TargetLibraryServerRelativeUrl -Batch $batch
}

Invoke-PnPBatch -Batch $batch
```
