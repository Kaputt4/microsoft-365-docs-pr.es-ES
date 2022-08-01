---
title: Propiedades y métodos estáticos
description: Recupera las alertas más recientes.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: cc935bd3d05c3a4f0e42b1382a94a5d744e27959
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168443"
---
# <a name="recommendation-resource-type"></a>Tipo de recurso Recomendación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

<br>

****

|Método|Tipo de valor devuelto|Description|
|---|---|---|
|[Enumerar todas las recomendaciones](get-all-recommendations.md)|Colección de recomendaciones|Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización|
|[Obtener recomendación por identificación](get-recommendation-by-id.md)|Recomendación|Recupera una recomendación de seguridad por su identificador|
|[Obtener software de recomendación](list-recommendation-software.md)|[Software](software.md)|Recupera una recomendación de seguridad relacionada con un software específico|
|[Obtener dispositivos de recomendación](get-recommendation-machines.md)|Colección MachineRef|Recupera una lista de dispositivos asociados con la recomendación de seguridad|
|[Obtener vulnerabilidades de recomendación](get-recommendation-vulnerabilities.md)|[Colección Vulnerability](vulnerability.md)|Recupera una lista de vulnerabilidades asociadas con la recomendación de seguridad|
|

## <a name="properties"></a>Propiedades

<br>

****

|Propiedad|Tipo|Descripción|
|---|---|---|
|id|Cadena|Id. de recomendación|
|productName|cadena|Nombre de software relacionado|
|recommendationName|Cadena|Nombre de recomendación|
|Debilidades|Long|Número de vulnerabilidades detectadas|
|Proveedor|Cadena|Nombre de proveedor relacionado|
|recommendedVersion|Cadena|Versión recomendada|
|recommendedProgram|Cadena|Programa recomendado|
|recommendedVendor|Cadena|Proveedor recomendado|
|recommendationCategory|Cadena|Categoría de recomendación. Los valores posibles son: "Accounts", "Application", "Network", "OS", "SecurityControls"|
|subCategory|Cadena|Subcategoría recomendación|
|severityScore|Doble|Posible impacto de la configuración en la puntuación segura de Microsoft para dispositivos de la organización (1-10)|
|publicExploit|Boolean|La vulnerabilidad pública está disponible|
|activeAlert|Boolean|La alerta activa está asociada con esta recomendación|
|associatedThreats|Colección string|El informe de análisis de amenazas está asociado a esta recomendación|
|remediationType|Cadena|Tipo de corrección. Los valores posibles son: "ConfigurationChange", "Update", "Upgrade","Uninstall"|
|Estado|Enum|Estado de excepción de recomendación. Los valores posibles son: "Active" y "Exception"|
|configScoreImpact|Doble|Impacto de puntuación segura de Microsoft para dispositivos|
|exposureImpact|Doble|Impacto de la puntuación de exposición|
|totalMachineCount|Long|Número de dispositivos instalados|
|exposedMachinesCount|Long|Número de dispositivos instalados expuestos a vulnerabilidades|
|nonProductivityImpactedAssets|Long|Número de dispositivos que no se ven afectados|
|relatedComponent|Cadena|Componente de software relacionado|
|
