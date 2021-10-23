---
title: " Recopilación de datos para solucionar problemas avanzados en Windows"
description: Obtenga información sobre cómo usar el analizador de cliente para recopilar datos para escenarios complejos de solución de problemas
keywords: analzyer, recopilar datos, solucionar problemas de mdeclientanalyzer, solución de problemas avanzada
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 469e1cd227e83facb678c85bd123f4ea250cd08c
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555913"
---
# <a name="data-collection-for-advanced-troubleshooting-on-windows"></a> Recopilación de datos para solucionar problemas avanzados en Windows

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Al colaborar con profesionales de soporte técnico de Microsoft, es posible que se le pida que use el analizador de cliente para recopilar datos para solucionar problemas de escenarios más complejos. El script del analizador admite otros parámetros para ese fin y puede recopilar un conjunto de registros específico en función de los síntomas observados que deben investigarse.

Ejecute '**MDEClientAnalyzer.cmd /?** para ver la lista de parámetros disponibles y su descripción:

![Imagen de los parámetros del analizador de cliente en la línea de comandos.](images/d89a1c04cf8441e4df72005879871bd0.png)

> [!NOTE]
> Cuando se usa cualquier parámetro de solución de problemas avanzado, el analizador también llama a [MpCmdRun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/collect-diagnostic-data-update-compliance) para recopilar Antivirus de Microsoft Defender registros de soporte técnico relacionados.

**-h:** llama a [Windows grabadora de](/windows-hardware/test/wpt/wpr-command-line-options) rendimiento para recopilar un seguimiento detallado del rendimiento general además del conjunto de registros estándar.

**-l:** llama al monitor de rendimiento Windows [integrado](/windows-server/remote/remote-desktop-services/rds-rdsh-performance-counters) para recopilar un seguimiento ligero de perfmon. Esto puede ser útil al diagnosticar problemas de degradación de rendimiento lento que se producen con el tiempo pero difíciles de reproducir a petición.

**-c:** llamadas al [monitor de procesos](/sysinternals/downloads/procmon) para la supervisión avanzada del sistema de archivos en tiempo real, el Registro y la actividad de procesos/subprocesos. Esto es especialmente útil cuando se solucionan varios escenarios de compatibilidad de aplicaciones.

**-i:** llama al comando integradonetsh.exe [ para](/windows/win32/winsock/netsh-exe) iniciar un seguimiento de firewall de windows y de red que resulta útil para solucionar diversos problemas relacionados con la red.

**-b:** igual que '-c', pero el seguimiento del monitor de proceso se iniciará durante el siguiente arranque y se detendrán solo cuando se vuelva a usar -b.

**-a:** llama a [Windows Registrador](/windows-hardware/test/wpt/wpr-command-line-options) de rendimiento para recopilar un seguimiento detallado del rendimiento específico del análisis de problemas altos de CPU relacionados con el proceso antivirus (MsMpEng.exe).

**-v:** usa antivirus [MpCmdRun.exe argumento de línea de comandos](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus) con las marcas -trace más detalladas.

**-t:** inicia un seguimiento detallado de todos los componentes del lado cliente relevantes para DLP de extremo. Esto es útil para escenarios en los que las [acciones DLP](/microsoft-365/compliance/endpoint-dlp-learn-about#endpoint-activities-you-can-monitor-and-take-action-on) no se están produciendo como se esperaba para los archivos.

**-q:** llama DLPDiagnose.ps1 script desde el directorio de herramientas del analizador que valida la configuración básica y los requisitos para DLP de extremo.

**-d:** recopila un volcado de memoria de MsSense **S**.exe (el proceso de sensor en el sistema operativo Windows Server 2016 o antiguo) y procesos relacionados.

- \* Esta marca se puede usar junto con las marcas mencionadas anteriormente.
- \*\* La captura de un volcado de memoria de procesos protegidos por [PPL](/windows-hardware/drivers/install/early-launch-antimalware) como MsSense.exe o MsMpEng.exe no es compatible con el analizador en este momento.

**-z:** configura las claves del Registro en la máquina para prepararla para la colección de volcados de memoria completa de la máquina a través [de CrashOnCtrlScroll](/windows-hardware/drivers/debugger/forcing-a-system-crash-from-the-keyboard). Esto sería útil para el análisis de problemas de inmovilización del equipo.

\* Mantenga presionada la tecla CTRL situada más a la derecha y, a continuación, presione dos veces la tecla DE BLOQUEO DE DESPLAZAMIENTO.

**-k:** usa [la herramienta NotMyFault](/sysinternals/downloads/notmyfault) para forzar al sistema a bloquearse y generar un volcado de memoria de la máquina. Esto sería útil para analizar varios problemas de estabilidad del sistema operativo.

El analizador y todas las marcas de escenario anteriores se pueden iniciar de forma remota ejecutando 'RemoteMDEClientAnalyzer.cmd', que también se incluye en el conjunto de herramientas del analizador:

![Imagen de la línea de comandos con información del analizador.](images/57cab9d82d08f672a92bf9e748ac9572.png)

> [!NOTE]
>
> - Al usar RemoteMDEClientAnalyzer.cmd, llama a psexec para descargar la herramienta desde el recurso compartido de archivos configurado y, a continuación, ejecutarla localmente a través de PsExec.exe.
    El script CMD usa la marca "-r" para especificar que se ejecuta de forma remota en el contexto SYSTEM y, por lo tanto, no se mostrará ningún mensaje al usuario.
> - Esa misma marca se puede usar con MDEClientAnalyzer.cmd para evitar un mensaje al usuario que solicite especificar el número de minutos para la recopilación de datos. Por ejemplo:
>
>    **MDEClientAnalyzer.cmd -r -i -m 5**
>
>   - **-r:** indica que la herramienta se ejecuta desde un contexto remoto (o no interactivo)
>   - **-i:** marca de escenario para la recopilación de seguimiento de red junto con otros registros relacionados
>   - **-m** \# - El número de minutos que se ejecutarán (5 minutos en el ejemplo anterior)
