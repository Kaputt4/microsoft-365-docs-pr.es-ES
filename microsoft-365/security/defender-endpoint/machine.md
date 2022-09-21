---
title: Tipo de recurso de máquina
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Machine en Microsoft Defender para punto de conexión.
keywords: apis, api admitidas, get, machines
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: ffa155a0b1d9598d19af5842553f68372f30b076
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851730"
---
# <a name="machine-resource-type"></a>Tipo de recurso de máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

|Método|Tipo de valor devuelto|Descripción|
|---|---|---|
|[Enumerar máquinas](get-machines.md)|[colección de máquinas](machine.md)|Enumera el conjunto de entidades de [máquina](machine.md) de la organización.|
|[Obtener equipo](get-machine-by-id.md)|[Máquina](machine.md)|Obtenga una [máquina](machine.md) por su identidad.|
|[Obtener usuarios que han iniciado sesión](get-machine-log-on-users.md)|Colección [usario](user.md)|Obtenga el conjunto de [usuarios](user.md) que iniciaron sesión en la [máquina](machine.md).|
|[Obtener alertas relacionadas](get-machine-related-alerts.md)|Colección [alert](alerts.md)|Obtenga el conjunto de entidades de [alerta](alerts.md) que se generaron en la [máquina](machine.md).|
|[Obtener software instalado](get-installed-software.md)|colección [de software](software.md)|Recupera una colección de software instalado relacionado con un identificador de equipo determinado.|
|[Obtener las vulnerabilidades detectadas](get-discovered-vulnerabilities.md)|[colección de vulnerabilidades](vulnerability.md)|Recupera una colección de vulnerabilidades detectadas relacionadas con un identificador de equipo determinado.|
|[Obtener recomendaciones de seguridad](get-security-recommendations.md)|[colección de recomendaciones](recommendation.md)|Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de equipo determinado.|
|[Agregar o quitar etiquetas de máquina](add-or-remove-machine-tags.md)|[Máquina](machine.md)|Agregue o quite la etiqueta a una máquina específica.|
|[Buscar máquinas por IP](find-machines-by-ip.md)|[colección de máquinas](machine.md)|Busque máquinas que se ven con IP.|
|[Buscar equipos por etiqueta](find-machines-by-tag.md)|[colección de máquinas](machine.md)|Buscar máquinas por [etiqueta](machine-tags.md).|
|[Obtener los kB que faltan](get-missing-kbs-machine.md)|Colección KB|Obtener una lista de los KB que faltan asociados con el identificador de equipo|
|[Establecer valor de dispositivo](set-device-value.md)|[colección de máquinas](machine.md)|Establezca el [valor de un dispositivo](tvm-assign-device-value.md).|
|[Actualizar máquina](update-machine-method.md)|[colección de máquinas](machine.md)|Obtenga el estado de actualización de una máquina.|

## <a name="properties"></a>Propiedades

|Propiedad|Tipo|Descripción|
|---|---|---|
|id|Cadena|identidad [de la máquina](machine.md).|
|computerDnsName|Cadena|nombre completo de [la máquina](machine.md).|
|firstSeen|DateTimeOffset|Primera fecha y hora en que Microsoft Defender para punto de conexión observó la [máquina](machine.md).|
|lastSeen|DateTimeOffset|Hora y fecha del último informe de dispositivo completo recibido. Normalmente, un dispositivo envía un informe completo cada 24 horas.|
|osPlatform|Cadena|Plataforma del sistema operativo.|
|onboardingstatus|Cadena|Estado de la incorporación de máquinas. Los valores posibles son: "onboarded", "CanBeOnboarded", "Unsupported" y "InsufficientInfo".|
|osProcessor|Cadena|Procesador del sistema operativo. En su lugar, use la propiedad osArchitecture.|
|version|Cadena|Versión del sistema operativo.|
|osBuild|Long que admite valores NULL|Número de compilación del sistema operativo.|
|lastIpAddress|Cadena|Última dirección IP en la NIC local en el [equipo](machine.md).|
|lastExternalIpAddress|Cadena|Última dirección IP a través de la cual la [máquina](machine.md) accedió a Internet.|
|healthStatus|Enum|estado de mantenimiento de [la máquina](machine.md). Los valores posibles son: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" y "Unknown".|
|rbacGroupName|Cadena|Nombre del grupo de máquinas.|
|rbacGroupId|Cadena|Id. de grupo de máquinas.|
|riskScore|Enumeración que acepta valores NULL|Puntuación de riesgo evaluada por Microsoft Defender para punto de conexión. Los valores posibles son: "None", "Informational", "Low", "Medium" y "High".|
|aadDeviceId|Guid de representación que acepta valores NULL|Id. de dispositivo de AAD (cuando [la máquina](machine.md) está unida a AAD).|
|machineTags|Colección string|Conjunto de etiquetas de [máquina](machine.md) .|
|exposureLevel|Enumeración que acepta valores NULL|Nivel de exposición evaluado por Microsoft Defender para punto de conexión. Los valores posibles son: "None", "Low", "Medium" y "High".|
|deviceValue|Enumeración que acepta valores NULL|[Valor del dispositivo](tvm-assign-device-value.md). Los valores posibles son: "Normal", "Low" y "High".|
|ipAddresses|Colección IpAddress|Conjunto de objetos ***IpAddress*** . Consulte [Obtención de la API de máquinas](get-machines.md).|
|osArchitecture|Cadena|Arquitectura del sistema operativo. Los valores posibles son: "32 bits", "64 bits". Use esta propiedad en lugar de osProcessor.|
