---
title: Exportación e importación de modelos de comprensión de documentos con PowerShell
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
description: Obtenga información sobre cómo exportar e importar modelos de comprensión de documentos con PowerShell en SharePoint Syntex.
ms.openlocfilehash: a022ee3be11470892cc62dda06173e83ee50f865
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585232"
---
# <a name="export-and-import-document-understanding-models-with-powershell"></a>Exportación e importación de modelos de comprensión de documentos con PowerShell

> [!IMPORTANT]
> Los cmdlets de PowerShell SharePoint Syntex y todos los demás componentes de PnP son herramientas de código abierto respaldadas por una comunidad activa que proporciona soporte técnico para ellos. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

SharePoint Syntex modelos se pueden exportar como plantillas PnP, lo que permite reutilizarlos entre centros de contenido o inquilinos.

## <a name="export-all-models-in-a-content-center"></a>Exportación de todos los modelos en un centro de contenido

Para exportar todos los modelos de un centro de contenido a una sola plantilla PnP, use los siguientes cmdlets de [PowerShell de PnP](https://pnp.github.io/powershell/) :

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>Exportación de modelos específicos

Para exportar modelos específicos de un centro de contenido a una plantilla PnP, use los siguientes cmdlets de [PowerShell de PnP](https://pnp.github.io/powershell/) :

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Configuration .\extract.json
```

Extract.json define qué modelos desea exportar, lo que permite especificar el modelo por nombre o identificador y, opcionalmente, configurar para no extraer datos de entrenamiento.

### <a name="example---specify-model-by-name"></a>Ejemplo: especificar el modelo por nombre

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "name": "Sample - benefits change notice.classifier"
            }
        ]
    }
}
```

### <a name="example---specify-model-by-id"></a>Ejemplo: Especificación del modelo por identificador

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "id": 3,
                "excludeTrainingData": true
            }
        ]
    }
}
```

Si no incluye la propiedad "includeTrainingData", el comportamiento predeterminado es incluir.

> [!NOTE]
> Los datos de entrenamiento son necesarios para que un modelo se pueda editar cuando se importe a un centro de contenido de destino.

## <a name="import-models-to-a-content-center"></a>Importación de modelos a un centro de contenido
Los modelos de comprensión de documentos que se han exportado a plantillas PnP se pueden importar a un centro de contenido en cualquier inquilino. Si la exportación incluía datos de entrenamiento, el modelo se modificará una vez importado.

Para importar un modelo, use los siguientes comandos:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
