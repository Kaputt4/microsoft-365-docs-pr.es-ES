---
title: Propiedades y métodos estáticos.
description: Recupera las alertas más recientes.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771602"
---
# <a name="recommendation-resource-type"></a>Tipo de recurso Recomendación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos
Método |Tipo de valor devuelto |Descripción
:---|:---|:---
[Enumerar todas las recomendaciones](get-all-recommendations.md) | Colección de recomendaciones | Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización
[Obtener recomendación por identificador](get-recommendation-by-id.md) | Recomendación | Recupera una recomendación de seguridad por su identificador
[Obtener software de recomendación](get-recommendation-software.md)| [Software](software.md) | Recupera una recomendación de seguridad relacionada con un software específico
[Obtener dispositivos de recomendación](get-recommendation-machines.md)|Colección MachineRef | Recupera una lista de dispositivos asociados con la recomendación de seguridad
[Obtener vulnerabilidades de recomendación](get-recommendation-vulnerabilities.md) | [Colección Vulnerability](vulnerability.md) | Recupera una lista de vulnerabilidades asociadas con la recomendación de seguridad


## <a name="properties"></a>Propiedades
Propiedad |   Tipo   |   Descripción
:---|:---|:---
id | Cadena | Id. de recomendación
productName | cadena | Nombre de software relacionado  
recommendationName | Cadena | Nombre de recomendación
Debilidades | Long | Número de vulnerabilidades detectadas
Proveedor | Cadena | Nombre de proveedor relacionado
recommendedVersion | Cadena | Versión recomendada
recommendationCategory | Cadena | Categoría de recomendación. Los valores posibles son: "Accounts", "Application", "Network", "OS", "SecurityStack
subCategory | Cadena | Subcategoría recomendación
severityScore | Doble | Posible impacto de la configuración en la puntuación segura de Microsoft para dispositivos de la organización (1-10)
publicExploit | Boolean | La vulnerabilidad pública está disponible 
activeAlert | Boolean | La alerta activa está asociada con esta recomendación
associatedThreats | Colección string | El informe de análisis de amenazas está asociado a esta recomendación
remediationType | Cadena | Tipo de corrección. Los valores posibles son: "ConfigurationChange", "Update", "Upgrade","Uninstall"
Estado | Enum | Estado de excepción de recomendación. Los valores posibles son: "Active" y "Exception"
configScoreImpact | Doble | Impacto de puntuación segura de Microsoft para dispositivos
exposureImpacte | Doble | Impacto de la puntuación de exposición
totalMachineCount | Long | Número de dispositivos instalados
exposedMachinesCount | Long | Número de dispositivos instalados expuestos a vulnerabilidades
nonProductivityImpactedAssets | Long | Número de dispositivos que no se ven afectados  
relatedComponent | Cadena |  Componente de software relacionado
