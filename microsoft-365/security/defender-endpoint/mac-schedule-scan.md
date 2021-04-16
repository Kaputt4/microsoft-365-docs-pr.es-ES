---
title: Cómo programar exámenes con MDATP para macOS
description: Obtenga información sobre cómo programar un tiempo de examen automático para Microsoft Defender para Endpoint en macOS para proteger mejor los activos de su organización.
keywords: microsoft, defender, atp, mac, exámenes, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 71576c777f58aa193f2a73db7edea832d29a97c6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860936"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Programar exámenes con Microsoft Defender para endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aunque puede iniciar un examen de amenazas en cualquier momento con Microsoft Defender para endpoint, su empresa puede beneficiarse de exámenes programados o programados. Por ejemplo, puede programar un examen para que se ejecute al principio de cada día laborable o semana. 

## <a name="schedule-a-scan-with-launchd"></a>Programar un examen con *inicio*

Puedes crear una programación de análisis mediante el demonio que *se* inicia en un dispositivo macOS.

1. El código siguiente muestra el esquema que debe usar para programar un examen. Abra un editor de texto y use este ejemplo como guía para su propio archivo de examen programado.

    Para obtener más información sobre el formato *de archivo .plist* que se usa aquí, consulta Acerca [de los archivos](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) de lista de propiedades de información en el sitio web oficial para desarrolladores de Apple.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Guarde el archivo *como com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Para ejecutar un examen completo en lugar de un examen rápido, cambie la línea 12, , para usar la opción en lugar de (es decir, ) y guarde el archivo como `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* en lugar de *com.microsoft.wdav.sched **quick** scan.plist*.

3. Abra **terminal**.
4. Escriba los siguientes comandos para cargar el archivo:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. El examen programado se ejecutará en la fecha, hora y frecuencia definidas en la lista p. En el ejemplo, el examen se ejecuta a las 2:00 a.m. todos los viernes. 

    El `Weekday` valor de usa un entero para indicar el quinto día de la `StartCalendarInterval` semana, o viernes.

 > [!IMPORTANT]
 > Los agentes ejecutados *con el inicio* no se ejecutarán en la hora programada mientras el dispositivo está dormido. En su lugar, se ejecutarán una vez que el dispositivo reanude el modo de suspensión.
 >
 > Si el dispositivo está desactivado, el examen se ejecutará en la próxima hora programada del examen.

## <a name="schedule-a-scan-with-intune"></a>Programar un examen con Intune

También puede programar exámenes con Microsoft Intune. El [script runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell disponible en Scripts para Microsoft Defender para [Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) persistirá cuando el dispositivo reanude el modo de suspensión. 

Consulta [Usar scripts de shell en dispositivos macOS en Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) para obtener instrucciones más detalladas sobre cómo usar este script en tu empresa.
