---
title: Programación de un examen antivirus mediante Anacron en Microsoft Defender para punto de conexión en Linux
description: Obtenga información sobre cómo programar un examen antivirus en Microsoft Defender para punto de conexión en Linux para una mejor protección de los recursos de su organización.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, scan, antivirus, microsoft defender para punto de conexión en Linux
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ad13d3e403f3fad81bec275506017f2da4066737
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223928"
---
# <a name="schedule-an-antivirus-scan-using-anacron-in-microsoft-defender-for-endpoint-on-linux"></a>Programación de un examen antivirus mediante Anacron en Microsoft Defender para punto de conexión en Linux

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Para ejecutar un examen de Microsoft Defender Antivirus para Linux, consulte [Comandos admitidos](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).

> [!NOTE]
> Este artículo admite Microsoft Defender para punto de conexión en Linux para distribuciones de Red Hat Enterprise Linux (RHEL).

## <a name="system-requirements"></a>Requisitos del sistema

Consulte los siguientes requisitos del sistema necesarios para programar Microsoft Defender examen antivirus en Microsoft Defender punto de conexión en Linux.

- Distribuciones y versiones de servidores Linux: Red Hat Enterprise Linux 7.2 o posterior.
- La opción **FANOTIFY** del kernel debe estar habilitada.

## <a name="scheduling-microsoft-defender-antivirus-scan-in-red-hat-linux"></a>Programación del examen Microsoft Defender Antivirus en Red Hat Linux

Puede programar trabajos cron para iniciar Microsoft Defender exámenes antivirus según una programación. Para obtener más información, consulte [Programación de exámenes con Microsoft Defender para punto de conexión en Linux](linux-schedule-scan-mde.md). Este proceso funciona bien si el dispositivo siempre está en funcionamiento. 

Pero si los dispositivos Linux están apagados o sin conexión durante la programación de cron, el examen no se ejecutará. En estas situaciones, puede usar **anacron** para leer la marca de tiempo y buscar el último trabajo ejecutado. Si el dispositivo se cerró durante el trabajo cron programado, debe esperar hasta la próxima hora programada. Mediante **anacron**, el sistema detectará la última vez que se ejecutó el examen. Si el dispositivo no ejecutó el trabajo cron, lo iniciará automáticamente. 

### <a name="schedule-microsoft-defender-antivirus-scans-in-red-hat-linux"></a>Programación de exámenes Microsoft Defender Antivirus en Red Hat Linux

Siga estos pasos para programar exámenes:

1. Conéctese al servidor RedHat mediante Putty.
1. Edite el archivo anacron: 

    ```vi /etc/anacron```

    :::image type="content" source="images/vi_etc_anacron.png" alt-text="archivo anacron":::

    ```
    # /etc/anacrontab: configuration file for anacron
    # See anacron (8) and anacrontab (5) for details.
    SHELL=/bin/sh
    PATH=/sbin:/bin:/usr/sbin:/usr/bin
    RANDOM_DELAY=45
    # Anacron jobs will start between 8pm and 11pm.
    START_HOURS_RANGE=20-23
    # delay will be 5 minutes + RANDOM_DELAY for cron.daily
    ```

1. Tenga en cuenta los siguientes elementos del archivo.
    1. **Cáscara:** El shell se conoce como ```/bin/sh```y no como ```/bin/bash```. Recuerde al escribir los trabajos.
    1. **RANDOM_DELAY:** Describe el tiempo máximo en minutos para el trabajo. Este valor se usa para desplazar los trabajos para que no se ejecuten demasiados trabajos al mismo tiempo. El uso de este retraso es ideal para las soluciones de VDI.
    1. **START_HOURS_RANGE:** Describe el intervalo de tiempo para ejecutar el trabajo.
    1. **cron.daily:** Describe 1 como el período de días necesario para la frecuencia de ejecuciones de trabajos. 5 es el retraso en minutos que anacron espera después de reiniciar el dispositivo.

1. Revise los trabajos de anacron:

    ```ls -lh /etc/cron*```

    :::image type="content" source="images/ls_lh_etc_cron.png" alt-text="trabajos de anacron":::

    ```
    [root@enaredhat7 /] # 1s -1h /etc/cron*
    - rw - - - - - - -. 1   root    root    0   Nov 30  2021    /etc/cron.deny
    - rw - r - - r - -. 1   root    root    451 Dec 27  2013    /etc/crontab

    /etc/cron.d:
    total 28k
    - rw - r - - r - -. 1   root    root    128 Nov 30  2021    0hourly
    - rw - r - - r - -. 1   root    root    121 Feb 25  18:11   omilogotate
    - rw - r - - r - -. 1   root    root    118 Feb 25  18:14   omsagent
    - rw - r - - r - -. 1   root    root    79  Feb 25  18:15   OMSConsistencyInvoker
    - rw - r - - r - -. 1   root    root    108 Nov 9   2021    raid-check
    - rw - r - - r - -. 1   root    root    135 Jun 1   22:35   scxagent
    - rw - - - - - - -. 1   root    root    235 Jan 20  2020    sysstat

    /etc/cron.daily:
    total 24k
    - rwxr - xr - x.    1   root    root    127 Jun 14  16:49   avscandaily
    - rwx - - - - - -.  1   root    root    219 Aug 7   2019    logrotate
    - rwxr - xr - x.    1   root    root    618 Jul 10  2018    man-db.cron
    - rwx - - - - - -.  1   root    root    208 Nov 9   2017    mlocate
    - rwx - - - - - -.  1   root    root    558 Apr 18  19:03   rhsmd
    - rwxr - xr - x.    1   root    root    114 Apr 8   2021    rhui-update-client

    /etc/cron.hourly:
    total 8.0k
    - rwxr - xr - x.    1   root    root    392 Nov 30  2021    0anacron
    - rwxr - xr - x.    1   root    root    131 Jun 14  17:05   update

    /etc/cron.monthly:
    total 0
    - rwxr - xr - x.    1   root    root    0   Jun 14  17:47   mdatpupdate
    
    /etc/cron.weekly:
    total 0
    ```

1. Omita el ```/etc/cron.d``` directorio, verá ```/etc/corn.daily, hourly, monthly, and weekly```. 

1. Para programar un examen antivirus semanal, puede crear un archivo (trabajo) en el ```/etc/cron.weekly``` directorio.

    ```cd /etc/cron.weekly```

   ``` vi mdavfullscan```

    ```Press Insert```
    
    :::image type="content" source="images/vi_mdavfullscan.png" alt-text="exámenes de antivirus semanales":::

   ```
    #!/bin/sh
    set -e
    echo    $(date)     “Time Scan Begins”  >>/logs/mdav_avacron_full_scan.log
    /bin/mdatp scan full >> /logs/mdav_avacron_full_scan.log
    echo    $(date) “Time Scan Finished”        >>/logs/mdav_avacron_full_scan.log
    exit    0
    ~
    ```

    ```Press Esc```

    ```Type: wq!```

1. Cambie los permisos de archivo para permitir que se ejecute el archivo.

    ```Chmod 755 mdavfullscan```

    ```ls -la```

    :::image type="content" source="images/chmod-755-mdavfullscan.png" alt-text="7. Cambiar los permisos de archivo":::

    ```
    [root@enaredhat7    cron.weekly]# 1s -1a
    total   16
    drwxr - xr – x. 2   root    root    26  Jun 14  19:19   .
    drwxr - xr – x. 85  root    root    8192    Jun 14  19:01   ..
    - rw - r - - r - -. 1   root    root    128 Jun 14  19:19   mdavfullscan
    [root@enaredhat7 cron.weekly] # chmod 755 mdavfullscan
    [root@enaredhat7 cron.weekly] # 1s  -1h
    total 4. 0k
    - rwxr - xr – x.    1   root    root    128 Jun 14  19:19   mdavfullscan
    [root@enaredhat7 cron.weekly] #
    ```

1. Use el comando para probar el trabajo de anacron semanal.
    
    ```./mdavfullscan```

1. Use el comando para comprobar que el trabajo se ejecutó correctamente.

    ```cat /logs/mdav_avacron_full_scan.log```

    :::image type="content" source="images/mdav_avacron_full_scan_log.png" alt-text="comprobar que se ejecutó el trabajo":::

    ```
    [root@enaredhat7    cron.weekly] # cat  / logs / mdav_avacron_full_scan.log
    Tue Jun 14  20:20:44    UTC 2022 Time Scan Begins
    Scan has finished
        66547   file(s) scanned
    0   threat(s) detected
    Tue Jun 14  20:20:50    UTC 2022 Time Scan Finished
    [root@enaredhat7 cron.weekly] #
    ```
