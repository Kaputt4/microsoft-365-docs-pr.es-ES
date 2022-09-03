---
title: Dispositivos fuera del panel del servicio Microsoft Defender para punto de conexión
description: Incorporación de dispositivos Windows, servidores y dispositivos que no sean de Windows desde el servicio Microsoft Defender para punto de conexión
keywords: offboarding, Microsoft Defender para punto de conexión offboarding, offboarding
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
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 2b43d818f1cc871c843ec6f1d29f770d96d06d45
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67580649"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Dispositivos fuera del panel del servicio Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Siga las instrucciones correspondientes en función del método de implementación que prefiera.

> [!NOTE]
> El estado de un dispositivo se cambiará a [Inactivo](fix-unhealthy-sensors.md#inactive-devices) 7 días después de la retirada.
>
> Los datos de los dispositivos no conectados (como escala de tiempo, alertas, vulnerabilidades, etc.) permanecerán en el portal hasta que expire el [período de retención](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) configurado.
>
> El perfil del dispositivo (sin datos) permanecerá en la lista de [dispositivos](machines-view-overview.md) durante no más de 180 días.
>
> Además, los dispositivos que no están activos en los últimos 30 días no se tienen en cuenta en los datos que reflejan la [puntuación de exposición](tvm-exposure-score.md) de Defender Vulnerability Management de su organización y la Puntuación de seguridad de Microsoft para dispositivos.
>
> Para ver solo los dispositivos activos, puede filtrar por [estado de mantenimiento del sensor](machines-view-overview.md#use-filters-to-customize-the-device-inventory-views), [etiquetas de dispositivo](machine-tags.md) o [grupos de máquinas](machine-groups.md).

## <a name="offboard-windows-devices"></a>Dispositivos Windows fuera del panel

- [Dispositivos fuera del panel con un script local](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Dispositivos fuera del panel que usan directiva de grupo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivos fuera del panel con herramientas de mobile Administración de dispositivos](configure-endpoints-mdm.md#offboard-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Servidores fuera del panel

- [Servidores fuera del panel](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Dispositivos fuera del panel que no son de Windows

- [Dispositivos fuera del panel que no son de Windows](configure-endpoints-non-windows.md#offboard-non-windows-devices)
