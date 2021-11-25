---
title: Corregir sensores incorrectos en Microsoft Defender para endpoint
description: Corrige los sensores de dispositivo que se informan como mal configurados o inactivos para que el servicio reciba datos del dispositivo.
keywords: mal configurado, inactivo, sensor de corrección, estado del sensor, sin datos del sensor, datos del sensor, comunicaciones deficientes, comunicación
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
ms.date: 11/23/2020
ms.technology: mde
ms.openlocfilehash: 71b0ca22a7a040aaa49fc160038a89292c20019c
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167351"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Corregir sensores incorrectos en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-fixsensor-abovefoldlink)

Los dispositivos que se clasifican como mal configurados o inactivos se pueden marcar debido a distintas causas. En esta sección se proporcionan algunas explicaciones sobre lo que podría haber provocado que un dispositivo se clasificara como inactivo o mal configurado.

## <a name="inactive-devices"></a>Dispositivos inactivos

Un dispositivo inactivo no está marcado necesariamente debido a un problema. Las siguientes acciones realizadas en un dispositivo pueden hacer que un dispositivo se clasifice como inactivo:

### <a name="device-is-not-in-use"></a>El dispositivo no está en uso

Si el dispositivo no se ha utilizado durante más de siete días por cualquier motivo, permanecerá en estado "Inactivo" en el portal.

### <a name="device-was-reinstalled-or-renamed"></a>El dispositivo se reinstaló o cambió el nombre
Un dispositivo reinstalado o cambiado de nombre generará una nueva entidad de dispositivo en el Centro de seguridad de Microsoft Defender. La entidad de dispositivo anterior permanecerá con el estado "Inactivo" en el portal. Si reinstalaste un dispositivo e implementaste el paquete Defender for Endpoint, busca el nuevo nombre del dispositivo para comprobar que el dispositivo está informando normalmente.

### <a name="device-was-offboarded"></a>El dispositivo se ha desactivado
Si el dispositivo se ha desactivado, seguirá apareciendo en la lista de dispositivos. Después de siete días, el estado de mantenimiento del dispositivo debe cambiar a inactivo.

### <a name="device-is-not-sending-signals"></a>El dispositivo no envía señales
Si el dispositivo no envía ninguna señal durante más de siete días a cualquiera de los canales de Microsoft Defender para endpoint por cualquier motivo, incluidas las condiciones que se incluyen en la clasificación de dispositivos mal configurados, un dispositivo puede considerarse inactivo. 

¿Esperas que un dispositivo esté en estado "Activo"? [Abra un vale de soporte](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)técnico .

## <a name="misconfigured-devices"></a>Dispositivos mal configurados
Los dispositivos mal configurados se pueden clasificar en:
- Comunicaciones deficientes
- Sin datos del sensor

### <a name="impaired-communications"></a>Comunicaciones deficientes
Este estado indica que hay una comunicación limitada entre el dispositivo y el servicio.

Las siguientes acciones sugeridas pueden ayudar a solucionar problemas relacionados con un dispositivo mal configurado con comunicaciones deficientes:

- [Asegurarse de que el dispositivo tiene conexión a Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.

- [Comprobar la conectividad del cliente a Microsoft Defender para las direcciones URL del servicio endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Compruebe que la configuración de proxy se haya completado correctamente, que WinHTTP pueda detectar y comunicarse a través del servidor proxy de su entorno y que el servidor proxy permita el tráfico a las direcciones URL del servicio de Microsoft Defender para puntos de conexión.

Si has tomado medidas correctivas y el estado del dispositivo sigue mal configurado, [abre un vale de soporte técnico.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

### <a name="no-sensor-data"></a>Sin datos del sensor
Un dispositivo mal configurado con el estado "Sin datos de sensor" tiene comunicación con el servicio, pero solo puede informar de datos parciales del sensor.

Siga estas acciones para corregir problemas conocidos relacionados con un dispositivo mal configurado con el estado "Sin datos de sensor":

- [Asegurarse de que el dispositivo tiene conexión a Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.

- [Comprobar la conectividad del cliente a Microsoft Defender para las direcciones URL del servicio endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Compruebe que la configuración de proxy se haya completado correctamente, que WinHTTP pueda detectar y comunicarse a través del servidor proxy de su entorno y que el servidor proxy permita el tráfico a las direcciones URL del servicio de Microsoft Defender para puntos de conexión.

- [Asegurarse de que el servicio de datos de diagnóstico está habilitado](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Si los dispositivos no están informando correctamente, es posible que deba comprobar que el servicio de datos de diagnóstico de Windows está configurado para iniciarse automáticamente y se está ejecutando en el punto de conexión.

- [Asegúrese de que Antivirus de Microsoft Defender no está deshabilitada por la directiva](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Si los dispositivos ejecutan un cliente antimalware de terceros, el agente de Defender for Endpoint necesita que el controlador antimalware de inicio anticipado (ELAM) de Antivirus de Microsoft Defender esté habilitado.

Si has tomado medidas correctivas y el estado del dispositivo sigue mal configurado, [abre un vale de soporte técnico.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

## <a name="see-also"></a>Recursos adicionales
- [Comprobar el estado del sensor en Microsoft Defender para endpoint](check-sensor-status.md)
- [Información general del Analizador de clientes](overview-client-analyzer.md)
- [Descargar y ejecutar el Analizador de clientes](download-client-analyzer.md)
- [Ejecutar el Analizador de clientes en Windows](run-analyzer-windows.md)
- [Ejecutar el Analizador de clientes en macOS o Linux](run-analyzer-macos-linux.md)
- [ Recopilación de datos para solucionar problemas avanzados en Windows](data-collection-analyzer.md)

