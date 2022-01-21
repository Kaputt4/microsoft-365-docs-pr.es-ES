---
title: Usar PowerShell para solicitar el procesamiento por un modelo de comprensión de documentos
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
description: Obtenga información sobre cómo usar PowerShell para solicitar el procesamiento por un SharePoint Syntex de comprensión de documentos.
ms.openlocfilehash: f6e013bddbec3c0f12bb8665de538967adfff116
ms.sourcegitcommit: d37fce3b708ea5232b4102fd0e693f4bf17a8948
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2022
ms.locfileid: "62159678"
---
# <a name="use-powershell-to-request-processing-by-a-document-understanding-model"></a>Usar PowerShell para solicitar el procesamiento por un modelo de comprensión de documentos

> [!IMPORTANT]
> Los SharePoint Syntex de PowerShell y todos los demás componentes pnP son herramientas de código abierto con el respaldo de una comunidad activa que les proporciona soporte técnico. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

Los modelos de comprensión de documentos procesarán los archivos recién cargados en una biblioteca. También es posible solicitar manualmente el procesamiento en la interfaz de usuario. Sin embargo, puede haber escenarios en los que sea más eficaz desencadenar el procesamiento a través de PowerShell.

## <a name="request-processing-of-all-items-that-have-not-been-previously-classified"></a>Solicitar el procesamiento de todos los elementos que no se han clasificado previamente

Puede solicitar el procesamiento de todos los elementos de la biblioteca que no se hayan clasificado previamente mediante este comando:

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents"
```

Para un procesamiento de menor prioridad, también puede considerar el uso del parámetro -OffPeak, que pondrá en cola los archivos para su procesamiento fuera del horario comercial en el que se encuentra el espacio empresarial. Consulta [Request-PnPSyntexClassifyAndExtract](https://pnp.github.io/powershell/cmdlets/Request-PnPSyntexClassifyAndExtract.html) para obtener más información.

## <a name="request-processing-of-all-items-in-a-library"></a>Solicitar el procesamiento de todos los elementos de una biblioteca

Puede solicitar el procesamiento de todos los archivos de la biblioteca, incluso si se han clasificado previamente. Esto puede ser útil si ha actualizado un modelo o ha agregado otro modelo a la biblioteca.

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents" -Force
```

> [!NOTE]
> El uso de la opción -Force con más de 5000 elementos habilitará automáticamente el procesamiento máximo.

## <a name="request-processing-of-all-items-based-on-a-property"></a>Solicitar el procesamiento de todos los elementos basados en una propiedad

Si desea limitar el procesamiento a un subconjunto específico de elementos de una biblioteca, puede usar un script para seleccionar un grupo específico de archivos. En el ejemplo siguiente, el script permite seleccionar un campo y un valor de campo por el que filtrar. Las consultas más complejas se pueden completar [con Get-PnPListItem](https://pnp.github.io/powershell/cmdlets/Get-PnPListItem.html).

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"
$list = Get-PnPList -Identity "Documents"
# Set the field name to filter items by
$fieldName = "Vendor"
# Set the field value to filter by
$fieldFilter = "Fabrikam"

$listItems = (Get-PnPListItem -List $list -fields $fieldName).fieldValues
$targetItems = $listItems | Where-Object -Property Provider -EQ -Value $fieldFilter

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
foreach ($listItem in $targetItems) {
    Request-PnPSyntexClassifyAndExtract -FileUrl $listItem.FileRef -Batch $classifyBatch
}

# Execute batch
Invoke-PnPBatch -Batch $batch
```

## <a name="request-processing-of-specific-files"></a>Procesamiento de solicitudes de archivos específicos

El procesamiento también se puede solicitar para archivos específicos.

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx"
```

El archivo por modelo de archivos también admite el procesamiento por lotes:

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx" -Batch $batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/relecloud contract.docx" -Batch $batch

# Execute batch
Invoke-PnPBatch -Batch $batch
```
