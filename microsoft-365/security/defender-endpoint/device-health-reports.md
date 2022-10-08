---
title: Informes de estado del dispositivo en Microsoft Defender para punto de conexión
description: Use el informe de estado del dispositivo para realizar un seguimiento del estado del dispositivo, el estado y las versiones del antivirus, las plataformas del sistema operativo y las versiones de Windows 10.
keywords: estado de mantenimiento, antivirus, plataforma del sistema operativo, versión de Windows 10, versión, estado, cumplimiento, estado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/06/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: 7bd1848793b72740a988b83661aa42bd66963749
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193023"
---
# <a name="device-health-reports-in-microsoft-defender-for-endpoint"></a>Informes de estado del dispositivo en Microsoft Defender para punto de conexión

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

El informe Estado del dispositivo proporciona información sobre los dispositivos de la organización. El informe incluye información de tendencias que muestra el estado de mantenimiento del sensor, el estado del antivirus, las plataformas del sistema operativo, las versiones de Windows 10 y Microsoft Defender versiones de actualización del antivirus.

> [!IMPORTANT]
> Para que Windows&nbsp;Server 2012 R2&nbsp;y Windows&nbsp;Server&nbsp;2016 aparezcan en los informes de estado del dispositivo, estos dispositivos deben incorporarse mediante el paquete de solución unificado&nbsp;moderno. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

En el panel de navegación del panel de seguridad de Microsoft 365, seleccione **Informes** y, a continuación, abra **Estado y cumplimiento del dispositivo**.
El panel Estado y cumplimiento del dispositivo se estructura en dos pestañas:

- La [pestaña **Estado del sensor & sistema operativo**](device-health-sensor-health-os.md#sensor-health--os-tab) proporciona información general del sistema operativo, dividida en tres tarjetas que muestran los siguientes atributos de dispositivo:
  - [Tarjeta de estado del sensor](device-health-sensor-health-os.md#sensor-health-card)
  - [Tarjeta de sistemas operativos y plataformas](device-health-sensor-health-os.md#operating-systems-and-platforms-card)
  - [Tarjeta de versiones de Windows](device-health-sensor-health-os.md#windows-versions-card)

- La [pestaña **estado Microsoft Defender Antivirus**](device-health-microsoft-defender-antivirus-health.md#microsoft-defender-antivirus-health-tab) tiene ocho tarjetas que informan sobre los aspectos de Microsoft Defender Antivirus:
  - [Tarjeta de modo antivirus](device-health-microsoft-defender-antivirus-health.md#antivirus-mode-card)
  - [Tarjeta de versión del motor antivirus](device-health-microsoft-defender-antivirus-health.md#antivirus-engine-version-card)
  - [Tarjeta de versión de inteligencia de seguridad antivirus](device-health-microsoft-defender-antivirus-health.md#antivirus-security-intelligence-version-card)
  - [Tarjeta de versión de la plataforma antivirus](device-health-microsoft-defender-antivirus-health.md#antivirus-platform-version-card)
  - [Tarjeta de resultados del examen antivirus reciente](device-health-microsoft-defender-antivirus-health.md#recent-antivirus-scan-results-card)
  - [Tarjeta de actualizaciones del motor antivirus](device-health-microsoft-defender-antivirus-health.md#antivirus-engine-updates-card)
  - [Tarjeta de actualizaciones de inteligencia de seguridad](device-health-microsoft-defender-antivirus-health.md#security-intelligence-updates-card)
  - [Tarjeta de actualizaciones de la plataforma antivirus](device-health-microsoft-defender-antivirus-health.md#antivirus-platform-updates-card)

## <a name="report-access-permissions"></a>Permisos de acceso de informes

Para acceder al informe de cumplimiento de antivirus y estado del dispositivo en el panel seguridad de Microsoft 365, se requieren los siguientes permisos:

| Nombre del permiso | Tipo de permiso |
|:---|:---|
| Ver datos | Administración de amenazas y vulnerabilidades (TVM) |

Para asignar estos permisos:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta con el administrador de seguridad o Administrador global rol asignado.
1. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).
1. Seleccione el rol que desea editar.
1. Seleccione **Editar**.
1. En **Editar rol**, en la pestaña **General** , en **Nombre del** rol, escriba un nombre para el rol.
1. En **Descripción** , escriba un breve resumen del rol.
1. En **Permisos**, seleccione **Ver datos** y, en **Ver datos** , seleccione **Administración de amenazas y vulnerabilidades** (TVM).

## <a name="see-also"></a>Vea también

- [Cree y administre roles para el control de acceso basado en rol](user-roles.md).
- [Exportación de propiedades y métodos de API de detalles de estado del antivirus de dispositivo](device-health-api-methods-properties.md)
