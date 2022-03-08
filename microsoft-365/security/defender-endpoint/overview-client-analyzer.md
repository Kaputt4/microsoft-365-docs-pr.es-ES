---
title: Solucionar problemas de estado del sensor con Microsoft Defender para endpoint client Analyzer
description: Solucionar problemas de estado del sensor en dispositivos para identificar posibles problemas de configuración, entorno, conectividad o telemetría que afecten a los datos o la funcionalidad del sensor.
keywords: sensor, estado del sensor, mal configurado, inactivo, sin datos de sensor, datos de sensor, comunicaciones deficientes, comunicación
ms.prod: m365-security
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0de2fbe98527d8fe36f2b8c5d5db0453988501a7
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323505"
---
# <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>Solucionar problemas de estado del sensor con Microsoft Defender para endpoint client Analyzer

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para Endpoint Client Analyzer (MDECA) puede ser útil al diagnosticar problemas de estado o confiabilidad del sensor [](/microsoft-365/security/defender-endpoint/onboard-configure) en dispositivos integrados que ejecutan Windows, Linux o macOS. Por ejemplo, es posible que desee ejecutar el analizador en una máquina que parezca no estar en buen estado según el estado de mantenimiento del sensor mostrado (Inactivo, Sin datos de [sensor](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) o Comunicaciones deficientes) en el portal de seguridad.

Además de los evidentes problemas de mantenimiento del sensor, MDECA puede recopilar otros seguimientos, registros e información de diagnóstico para solucionar escenarios complejos como:

- Compatibilidad de aplicaciones (AppCompat), rendimiento, conectividad de red o
- Comportamiento inesperado relacionado con [la prevención de pérdida de datos de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about).

## <a name="privacy-notice"></a>Aviso de privacidad

- Microsoft Customer Support Services (CSS) usa regularmente la herramienta Analizador de cliente de Microsoft Defender para endpoints para recopilar información que ayude a solucionar problemas que pueda tener con Microsoft Defender para endpoint.

- Los datos recopilados pueden contener información de identificación personal (PII) y/o datos confidenciales, como direcciones IP, nombres de equipo y nombres de usuario (entre otros).

- Una vez completada la recopilación de datos, la herramienta guarda los datos localmente en el equipo dentro de una subcarpeta y un archivo zip comprimido.

- No se envía ningún dato automáticamente a Microsoft. Si usa la herramienta durante la colaboración en un problema de soporte técnico, es posible que se le pida que envíe los datos comprimidos a CSS de Microsoft mediante secure file Exchange para facilitar la investigación del problema.

Para obtener más información acerca de la Exchange de archivos seguros, vea [How to use Secure File Exchange to exchange files with Microsoft Support](/troubleshoot/azure/general/secure-file-exchange-transfer-files)

Para obtener más información acerca de nuestra declaración de privacidad, consulte [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="requirements"></a>Requisitos

- Antes de ejecutar el analizador, se recomienda asegurarse de que la configuración de proxy o firewall permite el acceso a las direcciones URL de [servicio de Microsoft Defender para puntos de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- El analizador puede ejecutarse en ediciones admitidas de [Windows](minimum-requirements.md#supported-windows-versions), [Linux](microsoft-defender-endpoint-linux.md#system-requirements) o [macOS](microsoft-defender-endpoint-mac.md#system-requirements) antes de la incorporación a Microsoft Defender para Endpoint.

- En Windows dispositivos, si ejecuta el analizador directamente en equipos específicos y no de forma remota a través de [Live Response](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log), sysInternals [PsExec.exe](/sysinternals/downloads/psexec) debe poder ejecutarse (al menos temporalmente). El analizador llama a PsExec.exe herramienta para ejecutar comprobaciones de conectividad en la nube como Sistema local y emular el comportamiento del servicio SENSE.

    > [!NOTE]
    > En dispositivos Windows, si usas la regla Reducción de superficie de ataque (ASR) Bloquear creaciones de proceso que se originen a partir de comandos [PSExec y WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands), es posible que quieras deshabilitar temporalmente la regla o configurar una exclusión en la regla [ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para permitir que el analizador ejecute comprobaciones de conectividad en la nube según lo esperado.
