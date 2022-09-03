---
title: Publicación de modelos de comprensión de documentos con PowerShell
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: medium
description: Obtenga información sobre cómo publicar un SharePoint Syntex modelos de comprensión de documentos con PowerShell.
ms.openlocfilehash: 20c100473207d246f7f1d3b8d9a1f52063c418e0
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585804"
---
# <a name="publish-document-understanding-models-with-powershell"></a>Publicación de modelos de comprensión de documentos con PowerShell

> [!IMPORTANT]
> Los cmdlets de PowerShell SharePoint Syntex y todos los demás componentes de PnP son herramientas de código abierto respaldadas por una comunidad activa que proporciona soporte técnico para ellos. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

SharePoint Syntex modelos normalmente se implementan en bibliotecas de documentos en el inquilino. Esto se puede hacer mediante el sitio del centro de contenido, pero también se puede hacer con [PowerShell PnP](https://pnp.github.io/powershell/) , como se explica en este artículo.

## <a name="listing-the-available-models-in-a-content-center"></a>Enumeración de los modelos disponibles en un centro de contenido

Para obtener información general de los modelos agregados al sitio actual del centro de contenido SharePoint Syntex, use el cmdlet [Get-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html):

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
