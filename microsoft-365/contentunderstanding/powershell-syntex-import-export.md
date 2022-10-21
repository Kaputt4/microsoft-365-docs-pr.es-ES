---
title: Exportación e importación de modelos de procesamiento de documentos no estructurados con PowerShell
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
description: Obtenga información sobre cómo exportar e importar modelos con PowerShell en Microsoft Syntex.
ms.openlocfilehash: 975a4f463d80c273f31912c30c70c5e7c07fd6c9
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662103"
---
# <a name="export-and-import-unstructured-document-processing-models-with-powershell"></a>Exportación e importación de modelos de procesamiento de documentos no estructurados con PowerShell

<sup>**Se aplica a:**  &ensp; &#10003; procesamiento de documentos no estructurados</sup>

> [!IMPORTANT]
> Los cmdlets de PowerShell de Microsoft Syntex y todos los demás componentes de PnP son herramientas de código abierto respaldadas por una comunidad activa que proporciona soporte técnico para ellos. Los canales oficiales de soporte técnico de Microsoft no ofrecen ningún contrato de nivel de servicio para herramientas de código abierto.

Los modelos de Syntex se pueden exportar como plantillas PnP, lo que permite reutilizarlos entre centros de contenido o inquilinos.

## <a name="export-all-models-in-a-content-center"></a>Exportación de todos los modelos en un centro de contenido

Para exportar todos los modelos de procesamiento de documentos no estructurados de un centro de contenido a una sola plantilla PnP, use los siguientes cmdlets de [PowerShell de PnP](https://pnp.github.io/powershell/) :

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>Exportación de modelos específicos

Para exportar modelos de procesamiento de documentos no estructurados específicos desde un centro de contenido a una plantilla PnP, use los siguientes cmdlets de [PowerShell de PnP](https://pnp.github.io/powershell/) :

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

Los modelos de procesamiento de documentos no estructurados que se han exportado a plantillas PnP se pueden importar a un centro de contenido en cualquier inquilino. Si la exportación incluía datos de entrenamiento, el modelo se modificará una vez importado.

Para importar un modelo, use los siguientes comandos:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
