---
title: " Recopilación de datos para solucionar problemas avanzados en Windows"
description: Aprenda a usar el analizador de cliente para recopilar datos para escenarios complejos de solución de problemas.
keywords: analzyer, recopilar datos, solucionar problemas de mdeclientanalyzer, solución de problemas avanzada
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.subservice: m365d
search.appverid: met150
ms.openlocfilehash: 1f76cd92a20444447844b8d7daac170f87b4f0c8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67683459"
---
# <a name="data-collection-for-advanced-troubleshooting-on-windows"></a> Recopilación de datos para solucionar problemas avanzados en Windows

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Al colaborar con profesionales de soporte técnico de Microsoft, es posible que se le pida que use el analizador de cliente para recopilar datos para solucionar problemas de escenarios más complejos. El script del analizador admite otros parámetros para ese propósito y puede recopilar un conjunto de registros específico en función de los síntomas observados que deben investigarse.

Ejecute '**MDEClientAnalyzer.cmd /?**' para ver la lista de parámetros disponibles y su descripción:

:::image type="content" source="images/d89a1c04cf8441e4df72005879871bd0.png" alt-text="Parámetros de MDEClientAnalyzer.cmd" lightbox="images/d89a1c04cf8441e4df72005879871bd0.png":::

> [!NOTE]
> Cuando se usa cualquier parámetro de solución de problemas avanzado, el analizador también llama a [MpCmdRun.exe](/microsoft-365/security/defender-endpoint/command-line-arguments-microsoft-defender-antivirus) para recopilar registros de soporte técnico relacionados con el Antivirus de Microsoft Defender.

**-h** : llama a [Windows Performance Recorder](/windows-hardware/test/wpt/wpr-command-line-options) para recopilar un seguimiento detallado del rendimiento general además del conjunto de registros estándar.

**-l**: llama a [la Monitor de rendimiento](/windows-server/remote/remote-desktop-services/rds-rdsh-performance-counters) integrada de Windows para recopilar un seguimiento ligero del perfmon. Esto puede ser útil al diagnosticar problemas de degradación del rendimiento lentos que se producen con el tiempo, pero difíciles de reproducir a petición.

**-c** : llama al [monitor de procesos](/sysinternals/downloads/procmon) para la supervisión avanzada del sistema de archivos en tiempo real, el registro y la actividad de proceso/subproceso. Esto resulta especialmente útil al solucionar problemas de varios escenarios de compatibilidad de aplicaciones.

**-i** : llama a [ un comando integrado denetsh.exe](/windows/win32/winsock/netsh-exe) para iniciar un seguimiento de firewall de red y windows que resulta útil al solucionar diversos problemas relacionados con la red.

**-b** : igual que '-c', pero el seguimiento del monitor de procesos se iniciará durante el siguiente arranque y se detendrá solo cuando se vuelva a usar -b.

**-a** - Llama a [Windows Performance Recorder](/windows-hardware/test/wpt/wpr-command-line-options) para recopilar un seguimiento detallado del rendimiento específico para el análisis de problemas de CPU elevados relacionados con el proceso antivirus (MsMpEng.exe).

**-v** : usa antivirus [MpCmdRun.exe argumento de línea de comandos](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus) con marcas -trace más detalladas.

**-t** : inicia un seguimiento detallado de todos los componentes del lado cliente relevantes para DLP de punto de conexión. Esto resulta útil en escenarios en los que [las acciones DLP](/microsoft-365/compliance/endpoint-dlp-learn-about#endpoint-activities-you-can-monitor-and-take-action-on) no se producen según lo esperado para los archivos.

**-q** : llama a DLPDiagnose.ps1 script desde el directorio "Tools" del analizador que valida la configuración básica y los requisitos de DLP de punto de conexión.

**-d**: recopila un volcado de memoria de MsSense **S**.exe (el proceso del sensor en Windows Server 2016 o sistema operativo anterior) y procesos relacionados.

- \* Esta marca se puede usar junto con las marcas mencionadas anteriormente.
- \*\* En este momento, el analizador no admite la captura de un volcado de memoria de [procesos protegidos por PPL](/windows-hardware/drivers/install/early-launch-antimalware) , como MsSense.exe o MsMpEng.exe.

**-z** : configura las claves del Registro en la máquina para prepararla para la recopilación completa de volcados de memoria de la máquina a través [de CrashOnCtrlScroll](/windows-hardware/drivers/debugger/forcing-a-system-crash-from-the-keyboard). Esto sería útil para el análisis de problemas de inmovilización de equipos.

\* Mantenga presionada la tecla CTRL situada más a la derecha y presione dos veces la tecla SCROLL LOCK.

**-k** : usa la herramienta [NotMyFault](/sysinternals/downloads/notmyfault) para forzar que el sistema se bloquee y genere un volcado de memoria de la máquina. Esto sería útil para analizar diversos problemas de estabilidad del sistema operativo.

El analizador y todas las marcas de escenario anteriores se pueden iniciar de forma remota mediante la ejecución de "RemoteMDEClientAnalyzer.cmd", que también se incluye en el conjunto de herramientas del analizador:

:::image type="content" source="images/57cab9d82d08f672a92bf9e748ac9572.png" alt-text="Parámetros de RemoteMDEClientAnalyzer.cmd" lightbox="images/57cab9d82d08f672a92bf9e748ac9572.png":::

> [!NOTE]
>
> - Al usar RemoteMDEClientAnalyzer.cmd, llama a psexec para descargar la herramienta del recurso compartido de archivos configurado y, a continuación, ejecutarla localmente a través de PsExec.exe.
    El script CMD usa la marca "-r" para especificar que se ejecuta de forma remota dentro del contexto SYSTEM, por lo que no se presentará ningún mensaje al usuario.
> - Esa misma marca se puede usar con MDEClientAnalyzer.cmd para evitar un mensaje al usuario que solicita especificar el número de minutos para la recopilación de datos. Por ejemplo:
>
>    **MDEClientAnalyzer.cmd -r -i -m 5**
>
>   - **-r** : indica que la herramienta se está ejecutando desde un contexto remoto (o no interactivo)
>   - **-i** : marca de escenario para la recopilación de seguimiento de red junto con otros registros relacionados
>   - **-m** \# - El número de minutos que se van a ejecutar (5 minutos en el ejemplo anterior)
