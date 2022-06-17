---
title: Comenzar con el modo de solución de problemas en Microsoft Defender para punto de conexión
description: Active el modo de solución de problemas de Microsoft Defender para punto de conexión para solucionar varios problemas antivirus.
keywords: antivirus, solución de problemas, modo de solución de problemas, protección contra alteraciones, compatibilidad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4525ab2e979a16381ba75d2bdb229fb73d394156
ms.sourcegitcommit: 7ac54e1952383d5cd5f084c6a9d247eb747d4904
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2022
ms.locfileid: "66139394"
---
# <a name="get-started-with-troubleshooting-mode-in-microsoft-defender-for-endpoint"></a>Comenzar con el modo de solución de problemas en Microsoft Defender para punto de conexión 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Microsoft Defender para punto de conexión modo de solución de problemas le permite solucionar problemas de varias características antivirus de Microsoft Defender al habilitarlas desde el dispositivo y probar diferentes escenarios, incluso si están controladas por la directiva de la organización. El modo de solución de problemas está deshabilitado de forma predeterminada y requiere que lo active para un dispositivo (o grupo de dispositivos) durante un tiempo limitado. Tenga en cuenta que se trata exclusivamente de una característica de solo Enterprise y requiere acceso Microsoft 365 Defender.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Use el modo de solución de problemas para deshabilitar o cambiar la configuración de protección contra alteraciones para realizar lo siguiente:

  - Antivirus de Microsoft Defender solución de problemas funcional /compatibilidad de aplicaciones (bloques de aplicación falsos positivos).

  - Antivirus de Microsoft Defender solución de problemas de rendimiento mediante el modo de solución de problemas y la manipulación de la protección contra alteraciones y otras configuraciones de antivirus.

- Si se produce un evento de manipulación (por ejemplo, la `MpPreference` instantánea se modifica o elimina), el modo de solución de problemas finalizará y se habilitará la protección contra alteraciones en el dispositivo.

- Los administradores locales, con los permisos adecuados, pueden cambiar las configuraciones en puntos de conexión individuales que normalmente están bloqueados por la directiva. Tener un dispositivo en modo de solución de problemas puede ser útil al diagnosticar Antivirus de Microsoft Defender escenarios de rendimiento y compatibilidad.

  - Los administradores locales no podrán desactivar Antivirus de Microsoft Defender ni desinstalarla.

  - Los administradores locales podrán configurar todas las demás opciones de seguridad del conjunto de Antivirus de Microsoft Defender (por ejemplo, protección en la nube, protección contra alteraciones).

- Los administradores con permisos de "Administrar configuración de seguridad" tendrán acceso para activar el modo de solución de problemas.

- Microsoft Defender para punto de conexión recopila registros y datos de investigación a lo largo del proceso de solución de problemas.

  - La instantánea de se tomará antes de `MpPreference` que comience el modo de solución de problemas.

  - La segunda instantánea se tomará justo antes de que expire el modo de solución de problemas.

  - También se recopilarán los registros operativos de durante el modo de solución de problemas.

  - Todos los registros e instantáneas anteriores se recopilarán y estarán disponibles para que un administrador lo recopile mediante la característica [Recopilar paquete de investigación](respond-machine-alerts.md#collect-investigation-package-from-devices) en la página del dispositivo. Tenga en cuenta que Microsoft no quitará estos datos del dispositivo hasta que un administrador los recopile.

- Los administradores también pueden revisar los cambios en la configuración que tienen lugar durante el modo de solución de problemas en **Visor de eventos** en la página del dispositivo.

- El modo de solución de problemas se desactiva automáticamente después de alcanzar el tiempo de expiración (dura 3 horas). Después de la expiración, todas las configuraciones administradas por directivas volverán a ser de solo lectura y volverán a su estado antes de establecer el modo de solución de problemas.

- Puede tardar hasta 15 minutos desde el momento en que se envía el comando de Microsoft 365 Defender a cuando se activa en el dispositivo.

- La notificación se enviará al usuario final cuando comience el modo de solución de problemas y cuando finalice el modo de solución de problemas. También se enviará una advertencia notificando que finalizará pronto.

- El principio y el final del modo de solución de problemas se identificarán en la **escala de tiempo del** dispositivo en la página del dispositivo.

- Puede consultar todos los eventos de modo de solución de problemas en la búsqueda avanzada.

> [!NOTE]
> Los cambios de administración de directivas se aplicarán a la máquina cuando esté activo en el modo de solución de problemas. Sin embargo, los cambios no surtirán efecto hasta que expire el modo de solución de problemas. Además, las actualizaciones de Antivirus de Microsoft Defender Plataforma no se aplicarán durante el modo de solución de problemas. Las actualizaciones de la plataforma se aplicarán una vez que el modo de solución de problemas finalice con una actualización Windows.

## <a name="prerequisites"></a>Requisitos previos

- Dispositivo que ejecuta Windows 10 (versión 19044.1618 o posterior), Windows 11, Windows Server 2019 o Windows Server 2022.

  Semestre/Redstone|Versión del sistema operativo|Release
  :---|:---|:---
  21H2/SV1|>=22000.593|[KB5011563: Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011563)
  20H1/20H2/21H1|>=19042.1620<br/> >=19041.1620<br/> >=19043.1620|[KB5011543: Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011543)
  Windows Server 2022|>=20348.617|[KB5011558: Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011558)
  Windows Server 2019 (RS5)|>=17763.2746|[KB5011551: Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011551)

- Para aplicar el modo de solución de problemas, Microsoft Defender para punto de conexión deben estar inscritos en el inquilino y estar activos en el dispositivo.

- El dispositivo debe ejecutarse activamente Antivirus de Microsoft Defender, versión 4.18.2203 o posterior.

## <a name="enable-the-troubleshooting-mode"></a>Habilitación del modo de solución de problemas

1. Vaya al portal de Microsoft 365 Defender (<https://security.microsoft.com>) e inicie sesión.

2. Vaya a la página del dispositivo o la página del equipo del dispositivo que desea activar en el modo de solución de problemas. Seleccione **Activar el modo de solución de problemas**. Tenga en cuenta que esto requiere permisos de "Administrar la configuración de seguridad en Security Center" para Microsoft Defender para punto de conexión.

   :::image type="content" source="../../media/ts-mode-menu.png" alt-text="Activar el modo de solución de problemas" lightbox="../../media/ts-mode-menu.png":::

3. Confirme que desea activar el modo de solución de problemas para el dispositivo.

   :::image type="content" source="../../media/ts-mode-conf-flyout.png" alt-text="Control flotante de configuración" lightbox="../../media/ts-mode-conf-flyout.png":::

4. La página del dispositivo muestra que el dispositivo está ahora en modo de solución de problemas.

   :::image type="content" source="../../media/ts-mode-option-greyed-out.png" alt-text="El dispositivo está ahora en modo de solución de problemas" lightbox="../../media/ts-mode-option-greyed-out.png":::

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

Estas son algunas consultas de búsqueda avanzadas pregeneradas para proporcionarle visibilidad sobre los eventos de solución de problemas que se producen en su entorno. También puede usar estas consultas para [crear reglas de detección](/defender/custom-detection-rules.md#create-a-custom-detection-rule) que le avisan cuando los dispositivos están en modo de solución de problemas.

### <a name="get-troubleshooting-events-for-a-particular-device"></a>Obtención de eventos de solución de problemas para un dispositivo determinado

```kusto
let deviceName = "<device name>";   // update with device name
let deviceId = "<device id>";   // update with device id
search in (DeviceEvents)
(DeviceName == deviceName
) and ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| project $table, Timestamp,DeviceId, DeviceName, _tsmodeproperties,
 _tsmodeproperties.TroubleshootingState, _tsmodeproperties.TroubleshootingPreviousState, _tsmodeproperties.TroubleshootingStartTime,
 _tsmodeproperties.TroubleshootingStateExpiry, _tsmodeproperties.TroubleshootingStateRemainingMinutes,
 _tsmodeproperties.TroubleshootingStateChangeReason, _tsmodeproperties.TroubleshootingStateChangeSource
```

### <a name="devices-currently-in-troubleshooting-mode"></a>Dispositivos actualmente en modo de solución de problemas

```kusto
search in (DeviceEvents)
ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(3h)
| where _tsmodeproperties.TroubleshootingStateChangeReason contains "started"
|summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
```

### <a name="count-of-troubleshooting-mode-instances-by-device"></a>Recuento de instancias de modo de solución de problemas por dispositivo

```kusto
search in (DeviceEvents)
ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(30d)  // choose the date range you want
| where _tsmodeproperties.TroubleshootingStateChangeReason contains "started"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| sort by count_
```

### <a name="total-count"></a>Recuento total

```kusto
search in (DeviceEvents)
ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(2d) //beginning of time range
| where Timestamp < ago(1d) //end of time range
| where _tsmodeproperties.TroubleshootingStateChangeReason contains "started"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count()
| where count_ > 5          // choose your max # of TS mode instances for your time range
```

## <a name="related-topic"></a>Tema relacionado

- [Escenarios del modo de resolución de problemas](troubleshooting-mode-scenarios.md)
- [Configuración de seguridad de la protección con protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
