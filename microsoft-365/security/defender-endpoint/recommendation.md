---
title: Propiedades y métodos estáticos
description: Recupera las alertas recientes principales.
keywords: apis, graph api, api admitidas, get, alerts, recent
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: ad1864850b8953be424836b270349821d6fe3783
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68632610"
---
# <a name="recommendation-resource-type"></a>Tipo de recurso de recomendación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

<br>

****

|Método|Tipo de valor devuelto|Descripción|
|---|---|---|
|[Enumerar todas las recomendaciones](get-all-recommendations.md)|Colección recommendation|Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.|
|[Obtener recomendación por identificación](get-recommendation-by-id.md)|Recomendación|Recupera una recomendación de seguridad por su identificador|
|[Obtener software de recomendación](list-recommendation-software.md)|[Software](software.md)|Recupera una recomendación de seguridad relacionada con un software específico|
|[Obtener dispositivos de recomendación](get-recommendation-machines.md)|Colección MachineRef|Recupera una lista de dispositivos asociados a la recomendación de seguridad.|
|[Obtención de vulnerabilidades de recomendación](get-recommendation-vulnerabilities.md)|[Colección de vulnerabilidades](vulnerability.md)|Recupera una lista de vulnerabilidades asociadas a la recomendación de seguridad.|
|

## <a name="properties"></a>Propiedades

<br>

****

|Propiedad|Tipo|Descripción|
|---|---|---|
|id|Cadena|Identificador de recomendación|
|productName|Cadena|Nombre de software relacionado|
|recommendationName|Cadena|Nombre de la recomendación|
|Debilidades|Long|Número de vulnerabilidades detectadas|
|Proveedor|Cadena|Nombre del proveedor relacionado|
|recommendedVersion|Cadena|Versión recomendada|
|recommendedProgram|Cadena|Programa recomendado|
|recommendedVendor|Cadena|Proveedor recomendado|
|recommendationCategory|Cadena|Categoría de recomendación. Los valores posibles son: "Accounts", "Application", "Network", "OS", "SecurityControls"|
|Subcategoría|Cadena|Subcategoría de recomendación|
|severityScore|Doble|Posible impacto de la configuración en la Puntuación de seguridad de Microsoft para dispositivos de la organización (1-10)|
|publicExploit|Boolean|La vulnerabilidad de seguridad pública está disponible|
|activeAlert|Boolean|La alerta activa está asociada a esta recomendación|
|associatedThreats|Colección string|El informe de análisis de amenazas está asociado a esta recomendación|
|remediationType|Cadena|Tipo de corrección. Los valores posibles son: "ConfigurationChange","Update","Upgrade","Uninstall"|
|Estado|Enum|Estado de excepción de recomendación. Los valores posibles son: "Active" y "Exception"|
|configScoreImpact|Doble|Impacto en la puntuación de seguridad de Microsoft para dispositivos|
|exposureImpact|Doble|Impacto de la puntuación de exposición|
|totalMachineCount|Long|Número de dispositivos instalados|
|exposedMachinesCount|Long|Número de dispositivos instalados que se exponen a vulnerabilidades|
|nonProductivityImpactedAssets|Long|Número de dispositivos que no se ven afectados|
|relatedComponent|Cadena|Componente de software relacionado|
|
