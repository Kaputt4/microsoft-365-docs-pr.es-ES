---
title: Programación de exámenes con Microsoft Defender para punto de conexión en macOS
description: Obtenga información sobre cómo programar un tiempo de examen automático para Microsoft Defender para punto de conexión en macOS con el fin de proteger mejor los recursos de su organización.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, scans, antivirus
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
ms.openlocfilehash: 64d1657c2e078c6e1a649e597d6ab0a37f262850
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223576"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Programación de exámenes con Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aunque puede iniciar un examen de amenazas en cualquier momento con Microsoft Defender para punto de conexión, su empresa podría beneficiarse de exámenes programados o programados. Por ejemplo, puede programar un examen para que se ejecute al principio de cada día laborable o semana. 

## <a name="schedule-a-scan-with-launchd"></a>Programación de un examen con *el inicio*

Puede crear una programación de examen mediante el demonio *lanzado* en un dispositivo macOS.

Para obtener más información sobre el formato de archivo *.plist* que se usa aquí, consulte [Acerca de los archivos de lista de propiedades de información](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) en el sitio web oficial para desarrolladores de Apple.

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

2. Guarde el archivo como *com.microsoft.wdav.schedquickscan.plist*.

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
            <integer>50</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Guarde el archivo como *com.microsoft.wdav.schedfullscan.plist*.
 
### <a name="load-your-file"></a>Carga del archivo

1. Abra **terminal**.
2. Escriba los siguientes comandos para cargar el archivo:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

3. El examen programado se ejecutará en la fecha, hora y frecuencia definidas en la lista P. En los ejemplos anteriores, el examen se ejecuta a las 2:50 a.m. todos los viernes. 

    - El `Weekday` valor de `StartCalendarInterval` usa un entero para indicar el quinto día de la semana o viernes. El intervalo está comprendido entre 0 y 7, con 7 representando el domingo.
    - El `Day` valor de `StartCalendarInterval` usa un entero para indicar el tercer día del mes. El intervalo está comprendido entre 1 y 31.
    - El `Hour` valor de `StartCalendarInterval` usa un entero para indicar la segunda hora del día. El intervalo está comprendido entre 0 y 24.
    El `Minute` valor de `StartCalendarInterval` usa un entero para indicar cincuenta minutos de la hora. El intervalo está comprendido entre 0 y 59.
    
    
 > [!IMPORTANT]
 > Los agentes ejecutados con *el inicio* no se ejecutarán a la hora programada mientras el dispositivo esté inactivo. En su lugar, se ejecutarán una vez que el dispositivo se reanude del modo de suspensión.
 >
 > Si el dispositivo está desactivado, el examen se ejecutará en la siguiente hora de examen programada.

## <a name="schedule-a-scan-with-intune"></a>Programar un examen con Intune

También puede programar exámenes con Microsoft Intune. El [script de shell de runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) disponible en [Scripts para Microsoft Defender para punto de conexión](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) se conservará cuando el dispositivo se reanude del modo de suspensión. 

Consulte [Uso de scripts de shell en dispositivos macOS en Intune](/mem/intune/apps/macos-shell-scripts) para obtener instrucciones más detalladas sobre cómo usar este script en la empresa.
