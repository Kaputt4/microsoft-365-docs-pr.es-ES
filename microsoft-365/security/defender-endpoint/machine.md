---
title: Tipo de recurso Máquina
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Machine en Microsoft Defender para endpoint.
keywords: apis, api admitidas, get, machines
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f96cfd56cb8d61bc62c34e2b1ee08d6313c6a8ad
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186646"
---
# <a name="machine-resource-type"></a>Tipo de recurso Máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

Método|Tipo de valor devuelto |Descripción
:---|:---|:---
[Enumerar máquinas](get-machines.md) | [colección machine](machine.md) | Enumerar el conjunto [de entidades](machine.md) de máquina de la organización.
[Obtener máquina](get-machine-by-id.md) | [máquina](machine.md) | Obtener una [máquina por](machine.md) su identidad.
[Iniciar sesión en los usuarios](get-machine-log-on-users.md) | Colección [usario](user.md) | Obtener el conjunto de [usuario](user.md) que inició sesión en el [equipo](machine.md).
[Obtener alertas relacionadas](get-machine-related-alerts.md) | Colección [alert](alerts.md) | Obtener el conjunto de [entidades](alerts.md) de alerta que se generaron en la [máquina](machine.md).
[Obtener software instalado](get-installed-software.md) | [colección de software](software.md) | Recupera una colección de software instalado relacionado con un identificador de máquina determinado.
[Obtener vulnerabilidades detectadas](get-discovered-vulnerabilities.md) | [colección vulnerability](vulnerability.md) | Recupera una colección de vulnerabilidades detectadas relacionadas con un identificador de máquina determinado.
[Obtener recomendaciones de seguridad](get-security-recommendations.md) | [colección de](recommendation.md) recomendaciones | Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de equipo determinado.
[Agregar o quitar etiquetas de máquina](add-or-remove-machine-tags.md) | [máquina](machine.md) | Agregar o quitar etiqueta a un equipo específico.
[Buscar máquinas por IP](find-machines-by-ip.md) | [colección machine](machine.md) | Buscar máquinas vistas con IP.
[Buscar máquinas por etiqueta](find-machines-by-tag.md) | [colección machine](machine.md) | Buscar máquinas por [Etiqueta](machine-tags.md).
[Obtener KBs que faltan](get-missing-kbs-machine.md) | Colección KB | Obtener una lista de KBs que faltan asociados con el id. de máquina
[Establecer valor de dispositivo](set-device-value.md)| [colección machine](machine.md) | Establece el [valor de un dispositivo](tvm-assign-device-value.md).

## <a name="properties"></a>Propiedades

Propiedad |   Tipo   |   Descripción
:---|:---|:---
id | Cadena | [identidad](machine.md) de máquina.
computerDnsName | Cadena | [nombre](machine.md) completo de la máquina.
firstSeen | DateTimeOffset | Primera fecha y hora en la [que](machine.md) Microsoft Defender for Endpoint observó la máquina.
lastSeen | DateTimeOffset |Hora y fecha del último informe completo del dispositivo recibido. Normalmente, un dispositivo envía un informe completo cada 24 horas.
osPlatform | Cadena | Plataforma del sistema operativo.
osProcessor | Cadena | Procesador del sistema operativo.
version | Cadena | Versión del sistema operativo.
osBuild | Long que admite valores NULL | Número de compilación del sistema operativo.
lastIpAddress | Cadena | Last IP on local NIC on the [machine](machine.md).
lastExternalIpAddress | Cadena | Última IP a través de la [cual el equipo](machine.md) ha accedido a Internet.
healthStatus | Enum | [estado](machine.md) de estado de la máquina. Los valores posibles son: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" y "Unknown". 
rbacGroupName | Cadena | Nombre del grupo de máquinas.
riskScore | Enumeración que admite valores null | Puntuación de riesgo evaluada por Microsoft Defender para Endpoint. Los valores posibles son: 'None', 'Informational', 'Low', 'Medium' y 'High'.
exposureScore | Enumeración que admite valores null | [Puntuación de](tvm-exposure-score.md) exposición evaluada por Microsoft Defender para Endpoint. Los valores posibles son: 'None', 'Low', 'Medium' y 'High'.
aadDeviceId | Guid de representación que admite valores NULL | Id. de dispositivo de AAD (cuando [la máquina](machine.md) está unida a AAD).
machineTags | Colección de cadena | Conjunto de [etiquetas de](machine.md) máquina.
exposureLevel | Enumeración que admite valores null | Nivel de exposición evaluado por Microsoft Defender para Endpoint. Los valores posibles son: 'None', 'Low', 'Medium' y 'High'.
deviceValue | Enumeración que admite valores null | El [valor del dispositivo](tvm-assign-device-value.md). Los valores posibles son: 'Normal', 'Low' y 'High'.
ipAddresses | Colección IpAddress | Conjunto de ***objetos IpAddress.*** Consulta [Obtener api de máquinas](get-machines.md).


