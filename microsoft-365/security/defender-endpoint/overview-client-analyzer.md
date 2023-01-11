---
title: Solución de problemas de estado del sensor mediante Microsoft Defender para punto de conexión Analizador de cliente
description: Solución de problemas de estado del sensor en los dispositivos para identificar posibles problemas de configuración, entorno, conectividad o telemetría que afectan a los datos o la funcionalidad del sensor.
keywords: sensor, estado del sensor, mal configurado, inactivo, sin datos del sensor, datos del sensor, comunicaciones dañadas, comunicación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: bae0ff46333b447e73e130901545fe1f87d50d91
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227556"
---
# <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>Solución de problemas de estado del sensor mediante Microsoft Defender para punto de conexión Analizador de cliente

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

El analizador de cliente de Microsoft Defender para punto de conexión (MDECA) puede ser útil al diagnosticar problemas de estado o confiabilidad del sensor en [dispositivos incorporados](/microsoft-365/security/defender-endpoint/onboard-configure) que ejecutan Windows, Linux o macOS. Por ejemplo, es posible que desee ejecutar el analizador en una máquina que parezca estar en mal estado según el [estado de mantenimiento del sensor](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) mostrado (Inactivo, Sin datos de sensor o Comunicaciones afectadas) en el portal de seguridad.

Además de problemas obvios de estado del sensor, MDECA puede recopilar otros seguimientos, registros e información de diagnóstico para solucionar escenarios complejos como:

- Compatibilidad de aplicaciones (AppCompat), rendimiento, conectividad de red o
- Comportamiento inesperado relacionado con la [prevención de pérdida de datos del punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about).

## <a name="privacy-notice"></a>Aviso de privacidad

- Los servicios de soporte al cliente (CSS) de Microsoft usan regularmente la herramienta Microsoft Defender para punto de conexión Client Analyzer para recopilar información que le ayudará a solucionar problemas que pueda estar experimentando con Microsoft Defender para punto de conexión.

- Los datos recopilados pueden contener información de identificación personal (PII) o datos confidenciales, como (entre otros) direcciones IP, nombres de PC y nombres de usuario.

- Una vez completada la recopilación de datos, la herramienta guarda los datos localmente en el equipo dentro de una subcarpeta y un archivo zip comprimido.

- No se envía ningún dato automáticamente a Microsoft. Si usa la herramienta durante la colaboración en un problema de soporte técnico, es posible que se le pida que envíe los datos comprimidos a Css de Microsoft mediante Secure File Exchange para facilitar la investigación del problema.

Para obtener más información sobre Secure File Exchange, consulte [Uso de Secure File Exchange para intercambiar archivos con Soporte técnico de Microsoft](/troubleshoot/azure/general/secure-file-exchange-transfer-files)

Para obtener más información sobre nuestra declaración de privacidad, consulte [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="requirements"></a>Requisitos

- Antes de ejecutar el analizador, se recomienda asegurarse de que la configuración de proxy o firewall permite el acceso a [direcciones URL de servicio Microsoft Defender para punto de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- El analizador se puede ejecutar en ediciones compatibles de [Windows](minimum-requirements.md#supported-windows-versions), [Linux](microsoft-defender-endpoint-linux.md#system-requirements) o [macOS](microsoft-defender-endpoint-mac.md#system-requirements) antes de la incorporación a Microsoft Defender para punto de conexión.

- En el caso de los dispositivos Windows, si ejecuta el analizador directamente en máquinas específicas y no de forma remota a través de [Live Response](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log), se debe permitir la ejecución de SysInternals [PsExec.exe](/sysinternals/downloads/psexec) (al menos temporalmente). El analizador llama a PsExec.exe herramienta para ejecutar comprobaciones de conectividad en la nube como sistema local y emular el comportamiento del servicio SENSE.

    > [!NOTE]
    > En dispositivos Windows, si usas la regla Reducción de superficie expuesta a ataques (ASR) [Bloquear las creaciones de procesos que se originan en comandos PSExec y WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands), es posible que quieras deshabilitar temporalmente la regla o [configurar una exclusión de la regla ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para permitir que el analizador ejecute comprobaciones de conectividad en la nube según lo previsto.
