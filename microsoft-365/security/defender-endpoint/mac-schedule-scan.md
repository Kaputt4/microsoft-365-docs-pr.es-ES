---
title: Cómo programar exámenes con Microsoft Defender para endpoint en macOS
description: Obtenga información sobre cómo programar un tiempo de examen automático para Microsoft Defender para Endpoint en macOS para proteger mejor los activos de su organización.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, exámenes, antivirus
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c1d785f88160a7e0ffd17285b384f54ba4f2f74a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156237"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Programar exámenes con Microsoft Defender para endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aunque puede iniciar un examen de amenazas en cualquier momento con Microsoft Defender para endpoint, su empresa puede beneficiarse de exámenes programados o programados. Por ejemplo, puede programar un examen para que se ejecute al principio de cada día laborable o semana. 

## <a name="schedule-a-scan-with-launchd"></a>Programar un examen con *inicio*

Puedes crear una programación de análisis mediante el demonio que *se* inicia en un dispositivo macOS.

Para obtener más información sobre el formato *de archivo .plist* que se usa aquí, consulta Acerca [de los archivos](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) de lista de propiedades de información en el sitio web oficial para desarrolladores de Apple.

### <a name="schedule-a-quick-scan"></a>Programar un examen rápido

El código siguiente muestra el esquema que debe usar para programar un examen rápido. 

1. Abra un editor de texto y use este ejemplo como guía para su propio archivo de examen programado.

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

### <a name="schedule-a-full-scan"></a>Programar un examen completo

1. Abra un editor de texto y use este ejemplo para un examen completo.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedfullscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan full</string>
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

2. Guarde el archivo *como com.microsoft.wdav.schedfullscan.plist*.
 
### <a name="load-your-file"></a>Cargar el archivo

1. Abra **terminal**.
2. Escriba los siguientes comandos para cargar el archivo:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

3. El examen programado se ejecutará en la fecha, hora y frecuencia definidas en la lista p. En los ejemplos anteriores, el examen se ejecuta a las 2:00 a.m. todos los viernes. 

    El `Weekday` valor de usa un entero para indicar el quinto día de la `StartCalendarInterval` semana, o viernes.

 > [!IMPORTANT]
 > Los agentes ejecutados *con el inicio* no se ejecutarán en la hora programada mientras el dispositivo está dormido. En su lugar, se ejecutarán una vez que el dispositivo reanude el modo de suspensión.
 >
 > Si el dispositivo está desactivado, el examen se ejecutará en la próxima hora programada del examen.

## <a name="schedule-a-scan-with-intune"></a>Programar un examen con Intune

También puede programar exámenes con Microsoft Intune. El [script runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell disponible en Scripts para Microsoft Defender para [Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) persistirá cuando el dispositivo reanude el modo de suspensión. 

Consulta [Usar scripts de shell en dispositivos macOS en Intune](/mem/intune/apps/macos-shell-scripts) para obtener instrucciones más detalladas sobre cómo usar este script en tu empresa.
