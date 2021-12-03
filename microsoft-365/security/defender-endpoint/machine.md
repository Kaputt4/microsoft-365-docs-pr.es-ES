---
title: Tipo de recurso Máquina
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Machine en Microsoft Defender para endpoint.
keywords: apis, api admitidas, get, machines
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 80ac3e9ed43de98d32fd14063261452cfd5b1372
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284054"
---
# <a name="machine-resource-type"></a>Tipo de recurso Máquina

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

<br>

****

|Método|Tipo de valor devuelto|Descripción|
|---|---|---|
|[Enumerar máquinas](get-machines.md)|[colección machine](machine.md)|Enumerar el conjunto [de entidades](machine.md) de máquina de la organización.|
|[Obtener máquina](get-machine-by-id.md)|[máquina](machine.md)|Obtener una [máquina por](machine.md) su identidad.|
|[Iniciar sesión en los usuarios](get-machine-log-on-users.md)|Colección [usario](user.md)|Obtener el conjunto de [usuario](user.md) que inició sesión en el [equipo](machine.md).|
|[Obtener alertas relacionadas](get-machine-related-alerts.md)|Colección [alert](alerts.md)|Obtener el conjunto de [entidades](alerts.md) de alerta que se generaron en la [máquina](machine.md).|
|[Obtener software instalado](get-installed-software.md)|[colección de software](software.md)|Recupera una colección de software instalado relacionado con un identificador de máquina determinado.|
|[Obtener las vulnerabilidades detectadas](get-discovered-vulnerabilities.md)|[colección vulnerability](vulnerability.md)|Recupera una colección de vulnerabilidades detectadas relacionadas con un identificador de máquina determinado.|
|[Obtener recomendaciones de seguridad](get-security-recommendations.md)|[colección de](recommendation.md) recomendaciones|Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de equipo determinado.|
|[Agregar o quitar etiquetas de máquina](add-or-remove-machine-tags.md)|[máquina](machine.md)|Agregar o quitar etiqueta a un equipo específico.|
|[Buscar máquinas por IP](find-machines-by-ip.md)|[colección machine](machine.md)|Buscar máquinas vistas con IP.|
|[Buscar equipos por etiqueta](find-machines-by-tag.md)|[colección machine](machine.md)|Buscar máquinas por [Etiqueta](machine-tags.md).|
|[Obtener los kB que faltan](get-missing-kbs-machine.md)|Colección KB|Obtener una lista de KBs que faltan asociados con el id. de máquina|
|[Establecer valor de dispositivo](set-device-value.md)|[colección machine](machine.md)|Establece el [valor de un dispositivo](tvm-assign-device-value.md).|
|[Actualizar máquina](update-machine-method.md)|[colección machine](machine.md)|Obtener el estado de actualización de una máquina.|
|

## <a name="properties"></a>Propiedades

<br>

****

|Propiedad|Tipo|Descripción|
|---|---|---|
|id|String|[identidad](machine.md) de máquina.|
|computerDnsName|Cadena|[nombre](machine.md) completo de la máquina.|
|firstSeen|DateTimeOffset|Primera fecha y hora en la [que](machine.md) Microsoft Defender for Endpoint observó la máquina.|
|lastSeen|DateTimeOffset|Hora y fecha del último informe completo del dispositivo recibido. Normalmente, un dispositivo envía un informe completo cada 24 horas.|
|osPlatform|Cadena|Plataforma del sistema operativo.|
|onboardingstatus|String|Estado de incorporación de la máquina. Los valores posibles son: "onboarded" y "offboarded".|
|osProcessor|String|Procesador del sistema operativo. Use la propiedad osArchitecture en su lugar.|
|version|Cadena|Versión del sistema operativo.|
|osBuild|Long que admite valores NULL|Número de compilación del sistema operativo.|
|lastIpAddress|String|Last IP on local NIC on the [machine](machine.md).|
|lastExternalIpAddress|String|Última IP a través de la [cual el equipo](machine.md) ha accedido a Internet.|
|healthStatus|Enum|[estado](machine.md) de estado de la máquina. Los valores posibles son: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" y "Unknown".|
|rbacGroupName|String|Nombre del grupo de máquinas.|
|rbacGroupId|String|Id. de grupo de máquinas.|
|riskScore|Enumeración que admite valores null|Puntuación de riesgo evaluada por Microsoft Defender para Endpoint. Los valores posibles son: 'None', 'Informational', 'Low', 'Medium' y 'High'.|
|aadDeviceId|Guid de representación que admite valores NULL|AAD id. de dispositivo (cuando [el](machine.md) equipo AAD unido).|
|machineTags|Colección string|Conjunto de [etiquetas de](machine.md) máquina.|
|exposureLevel|Enumeración que admite valores null|Nivel de exposición evaluado por Microsoft Defender para Endpoint. Los valores posibles son: 'None', 'Low', 'Medium' y 'High'.|
|deviceValue|Enumeración que admite valores null|El [valor del dispositivo](tvm-assign-device-value.md). Los valores posibles son: 'Normal', 'Low' y 'High'.|
|ipAddresses|Colección IpAddress|Conjunto de ***objetos IpAddress.*** Consulta [Obtener api de máquinas](get-machines.md).|
|osArchitecture|String|Arquitectura del sistema operativo. Los valores posibles son: "32 bits", "64 bits". Use esta propiedad en lugar de osProcessor.|
|
