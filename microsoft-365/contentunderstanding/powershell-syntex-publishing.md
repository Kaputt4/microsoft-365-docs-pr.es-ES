---
title: Publicar modelos de descripción de documentos con PowerShell
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
description: Obtenga información sobre cómo publicar un SharePoint Syntex modelos de comprensión de documentos con PowerShell.
ms.openlocfilehash: 4aa5639d50145cabe5b95a11d3d927b7d2e06749
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074865"
---
# <a name="publish-document-understanding-models-with-powershell"></a>Publicar modelos de descripción de documentos con PowerShell

> [!IMPORTANT]
> Los SharePoint Syntex de PowerShell y todos los demás componentes pnP son herramientas de código abierto con el respaldo de una comunidad activa que les proporciona soporte técnico. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

SharePoint Syntex normalmente se implementan en bibliotecas de documentos en todo el espacio empresarial. Esto se puede hacer mediante el sitio del Centro de contenido, pero esto también se puede hacer con [PnP PowerShell,](https://pnp.github.io/powershell/) como se explica en este artículo.

## <a name="listing-the-available-models-in-a-content-center"></a>Enumerar los modelos disponibles en un Centro de contenido

Para obtener información general sobre los modelos agregados al sitio actual del Centro de contenido SharePoint Syntex use el cmdlet [Get-PnPSyntexModel:](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html)

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModel
```

## <a name="apply-a-model-to-a-library"></a>Aplicar un modelo a una biblioteca

Para aplicar un modelo a una biblioteca, puede usar el cmdlet [Publish-PnPSyntexModel:](https://pnp.github.io/powershell/cmdlets/Publish-PnPSyntexModel.html)

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Publish-PnPSyntexModel -Model "Contract Notice" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="understanding-where-a-model-is-used"></a>Descripción de dónde se usa un modelo

Una vez que haya implementado un modelo en muchas bibliotecas, es posible que desee revisar la lista de bibliotecas con el modelo. Esto se puede hacer con el cmdlet [Get-PnPSyntexModelPublication:](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModelPublication.html)

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModelPublication -Identity "Contract Notice"
```

## <a name="removing-a-model-from-a-library"></a>Quitar un modelo de una biblioteca

La eliminación de un modelo de una biblioteca sigue el mismo patrón que la aplicación y se puede realizar con el cmdlet [Unpublish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Unpublish-PnPSyntexModel.html) de forma interactiva o como lote de varias acciones.

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourSite"
Unpublish-PnPSyntexModel -Model "Invoice model" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="apply-models-in-bulk"></a>Aplicar modelos en masa

Si desea publicar varios modelos en varias bibliotecas, 

En primer lugar, cree un archivo CSV de entrada que enumera los modelos y las ubicaciones de destino:

```CSV
ModelName,TargetSiteUrl,TargetWebServerRelativeUrl,TargetLibraryServerRelativeUrl
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/shared%20documents
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/other
Trade Confirmation,https://contoso.sharepoint.com/sites/Site2,/sites/Site2,/sites/site2/shared%20documents
```

A continuación, este archivo CSV se puede usar como entrada en un script que publicará los modelos enumerados en las bibliotecas adecuadas. En el ejemplo siguiente se usa el procesamiento por lotes para aumentar la eficacia de las solicitudes

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
