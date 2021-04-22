---
title: Dispositivos offboard del servicio Microsoft Defender para endpoints
description: Incorporación de dispositivos Windows 10, servidores y dispositivos que no son de Windows desde el servicio de Microsoft Defender para endpoints
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934158"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Dispositivos offboard del servicio Microsoft Defender para endpoints

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Siga las instrucciones correspondientes según el método de implementación preferido.

>[!NOTE]
> El estado de un dispositivo se cambia a [Inactivo](fix-unhealthy-sensors.md#inactive-devices) 7 días después de la salida. <br> Los datos de los dispositivos no incluidos (como escala de tiempo, alertas, vulnerabilidades, etc.) permanecerán en el portal hasta que expire el período [de](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) retención configurado. <br>
> El perfil del dispositivo (sin datos) [](machines-view-overview.md) permanecerá en la lista de dispositivos durante no más de 180 días.
> Además, los dispositivos que no están activos en los últimos 30 días no se tienen [](tvm-exposure-score.md) en cuenta en los datos que reflejan la puntuación de exposición a la administración de amenazas y vulnerabilidades de la organización y la puntuación de Microsoft Secure Score para dispositivos. <br>
> Para ver solo los dispositivos activos, puede filtrar por estado [de](machines-view-overview.md#health-state)mantenimiento, [etiquetas de dispositivo](machine-tags.md) o grupos de [máquinas.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Dispositivos con Windows 10 fuera de la pantalla
- [Dispositivos offboard con un script local](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Dispositivos offboard con directiva de grupo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivos offboard con herramientas de administración de dispositivos móviles](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Servidores offboard
- [Servidores offboard](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Dispositivos offboard que no son Windows
- [Dispositivos offboard que no son Windows](configure-endpoints-non-windows.md#offboard-non-windows-devices)

