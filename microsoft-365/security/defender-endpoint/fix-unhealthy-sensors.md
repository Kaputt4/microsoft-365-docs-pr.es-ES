---
title: Corrección de sensores incorrectos en Microsoft Defender para punto de conexión
description: Corrija los sensores de dispositivo que notifican como mal configurados o inactivos para que el servicio reciba datos del dispositivo.
keywords: mal configurado, inactivo, corregir sensor, estado del sensor, sin datos del sensor, datos del sensor, comunicaciones afectadas, comunicación
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
ms.date: 11/23/2020
ms.subservice: mde
ms.openlocfilehash: e53e453bb60a203dfaf32669ad7995ec6e96a839
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67516420"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Corrección de sensores incorrectos en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-fixsensor-abovefoldlink)

Los dispositivos se pueden clasificar como mal configurados o inactivos se marcan por diferentes causas. En esta sección se proporcionan algunas explicaciones sobre lo que podría haber provocado que un dispositivo se clasificara como inactivo o mal configurado.

## <a name="inactive-devices"></a>Dispositivos inactivos

Un dispositivo inactivo no se marca necesariamente debido a un problema. Las siguientes acciones realizadas en un dispositivo pueden hacer que un dispositivo se clasifique como inactivo:

- El dispositivo no está en uso
- Se reinstaló o se cambió el nombre del dispositivo
- El dispositivo se desbordó
- El dispositivo no envía señales


### <a name="device-isnt-in-use"></a>El dispositivo no está en uso

Cualquier dispositivo que no esté en uso durante más de siete días conservará el estado "Inactivo" en el portal.

### <a name="device-was-reinstalled-or-renamed"></a>Se reinstaló o se cambió el nombre del dispositivo
Se genera una nueva entidad de dispositivo en Microsoft 365 Defender para dispositivos reinstalados o cuyo nombre se ha cambiado. La entidad de dispositivo anterior permanece, con un estado "Inactivo" en el portal. Si reinstaló un dispositivo e implementó el paquete de Defender para punto de conexión, busque el nuevo nombre del dispositivo para comprobar que el dispositivo notifica con normalidad.

### <a name="device-was-offboarded"></a>El dispositivo se desbordó
Si el dispositivo se ha desconectado, seguirá apareciendo en la lista de dispositivos. Después de siete días, el estado de mantenimiento del dispositivo debe cambiar a inactivo.

### <a name="device-isnt-sending-signals"></a>El dispositivo no envía señales
Si el dispositivo no envía señales a ningún canal de Microsoft Defender para punto de conexión durante más de siete días por cualquier motivo, un dispositivo se puede considerar inactivo; esto incluye condiciones que se encuentran en la clasificación de dispositivos mal configurados.

¿Espera que un dispositivo esté en estado "Activo"? [Abra una incidencia de soporte técnico](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).

## <a name="misconfigured-devices"></a>Dispositivos mal configurados
Los dispositivos mal configurados se pueden clasificar aún más en:
- Comunicaciones deterioradas
- Sin datos del sensor

### <a name="impaired-communications"></a>Comunicaciones deterioradas
Este estado indica que hay una comunicación limitada entre el dispositivo y el servicio.

Las siguientes acciones sugeridas pueden ayudar a corregir problemas relacionados con un dispositivo mal configurado con comunicaciones afectadas:

- [Asegurarse de que el dispositivo tiene conexión a Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.

- [Comprobación de la conectividad de cliente con direcciones URL de servicio de Microsoft Defender para punto de conexión](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Compruebe que la configuración del proxy se completó correctamente, que WinHTTP puede detectar y comunicarse a través del servidor proxy del entorno y que el servidor proxy permite el tráfico a las direcciones URL del servicio Microsoft Defender para punto de conexión.

Si ha realizado acciones correctivas y el estado del dispositivo sigue mal configurado, [abra una incidencia de soporte](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409) técnico.

### <a name="no-sensor-data"></a>Sin datos del sensor
Un dispositivo mal configurado con el estado "Sin datos de sensor" tiene comunicación con el servicio, pero solo puede notificar datos parciales del sensor.

Siga estas acciones para corregir problemas conocidos relacionados con un dispositivo mal configurado con el estado "Sin datos del sensor":

- [Asegurarse de que el dispositivo tiene conexión a Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.

- [Comprobación de la conectividad de cliente con direcciones URL de servicio de Microsoft Defender para punto de conexión](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Compruebe que la configuración del proxy se completó correctamente, que WinHTTP puede detectar y comunicarse a través del servidor proxy del entorno y que el servidor proxy permite el tráfico a las direcciones URL del servicio Microsoft Defender para punto de conexión.

- [Asegúrese de que el servicio de datos de diagnóstico está habilitado](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Si los dispositivos no informan correctamente, debe comprobar que el servicio de datos de diagnóstico de Windows está establecido para iniciarse automáticamente. Compruebe también que el servicio de datos de diagnóstico de Windows se ejecuta en el punto de conexión.

- [Asegúrese de que la directiva no deshabilita el Antivirus de Microsoft Defender](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Si los dispositivos ejecutan un cliente antimalware de terceros, el agente de Defender para punto de conexión requiere que el controlador Antimalware de inicio anticipado (ELAM) del Antivirus de Microsoft Defender esté habilitado.

Si ha realizado acciones correctivas y el estado del dispositivo sigue mal configurado, [abra una incidencia de soporte](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409) técnico.

## <a name="see-also"></a>Vea también
- [Comprobación del estado del sensor en Microsoft Defender para punto de conexión](check-sensor-status.md)
- [Información general del Analizador de clientes](overview-client-analyzer.md)
- [Descargar y ejecutar el Analizador de clientes](download-client-analyzer.md)
- [Ejecutar el Analizador de clientes en Windows](run-analyzer-windows.md)
- [Ejecutar el Analizador de clientes en macOS o Linux](run-analyzer-macos-linux.md)
- [ Recopilación de datos para solucionar problemas avanzados en Windows](data-collection-analyzer.md)

