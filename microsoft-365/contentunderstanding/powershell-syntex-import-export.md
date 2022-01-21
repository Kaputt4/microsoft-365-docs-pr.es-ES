---
title: Exportar e importar modelos de comprensión de documentos con PowerShell
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
description: Obtenga información sobre cómo exportar e importar modelos de comprensión de documentos con PowerShell en SharePoint Syntex.
ms.openlocfilehash: 6751a66d713ada8c06445d8bfd0efdb5c3ac2fad
ms.sourcegitcommit: d37fce3b708ea5232b4102fd0e693f4bf17a8948
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2022
ms.locfileid: "62159510"
---
# <a name="export-and-import-document-understanding-models-with-powershell"></a>Exportar e importar modelos de comprensión de documentos con PowerShell

> [!IMPORTANT]
> Los SharePoint Syntex de PowerShell y todos los demás componentes pnP son herramientas de código abierto con el respaldo de una comunidad activa que les proporciona soporte técnico. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

SharePoint Syntex pueden exportarse como plantillas PnP, lo que permite la reutilización entre los centros de contenido o los inquilinos.

## <a name="export-all-models-in-a-content-center"></a>Exportar todos los modelos en un centro de contenido

Para exportar todos los modelos de un centro de contenido a una sola plantilla PnP, use los siguientes cmdlets [de PowerShell pnP:](https://pnp.github.io/powershell/)

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>Exportar modelos específicos

Para exportar modelos específicos de un centro de contenido a una plantilla PnP, use los siguientes cmdlets [de PowerShell pnP:](https://pnp.github.io/powershell/)

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Configuration .\extract.json
```

El archivo extract.json define los modelos que desea exportar, lo que permite especificar el modelo por nombre o id. y, opcionalmente, configurar para no extraer datos de aprendizaje.

### <a name="example---specify-model-by-name"></a>Ejemplo: especificar el modelo por su nombre

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

### <a name="example---specify-model-by-id"></a>Ejemplo: especificar el modelo por identificador

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
> Los datos de aprendizaje son necesarios para que un modelo se pueda editar cuando se importe a un centro de contenido de destino.

## <a name="import-models-to-a-content-center"></a>Importar modelos a un centro de contenido
Los modelos de descripción de documentos que se han exportado a plantillas PnP se pueden importar a un centro de contenido de cualquier inquilino. Si la exportación incluye datos de aprendizaje, el modelo se podrá editar una vez importado.

Para importar un modelo, use los siguientes comandos:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
