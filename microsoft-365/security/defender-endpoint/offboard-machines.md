---
title: Dispositivos offboard del servicio Microsoft Defender para endpoints
description: Incorporación Windows dispositivos, servidores, dispositivos que no Windows desde el servicio de Microsoft Defender para endpoints
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 19f4b517682fa58bde7253c074dc4402f6f95bf9
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163427"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Dispositivos offboard del servicio Microsoft Defender para endpoints

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Siga las instrucciones correspondientes según el método de implementación preferido.

> [!NOTE]
> El estado de un dispositivo se cambia a [Inactivo](fix-unhealthy-sensors.md#inactive-devices) 7 días después de la salida.
>
> Los datos de los dispositivos no incluidos (como escala de tiempo, alertas, vulnerabilidades, etc.) permanecerán en el portal hasta que expire el período [de](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) retención configurado.
>
> El perfil del dispositivo (sin datos) [](machines-view-overview.md) permanecerá en la lista de dispositivos durante no más de 180 días.
>
> Además, los dispositivos que [no](tvm-exposure-score.md) están activos en los últimos 30 días no se tienen en cuenta en los datos que reflejan la puntuación de exposición Administración de amenazas y vulnerabilidades de la organización y la puntuación segura de Microsoft para dispositivos.
>
> Para ver solo los dispositivos activos, puede filtrar por estado [de](machines-view-overview.md#health-state)mantenimiento, [etiquetas de dispositivo](machine-tags.md) o grupos de [máquinas.](machine-groups.md)

## <a name="offboard-windows-devices"></a>Dispositivos Windows offboard

- [Dispositivos offboard con un script local](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Dispositivos offboard con directiva de grupo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivos offboard con herramientas de administración de dispositivos móviles](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Servidores offboard

- [Servidores offboard](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Dispositivos no Windows offboard

- [Dispositivos no Windows offboard](configure-endpoints-non-windows.md#offboard-non-windows-devices)
