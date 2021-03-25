---
title: Recursos para ATP de Microsoft Defender para Mac
description: Recursos para ATP de Microsoft Defender para Mac, como cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos de CLI y problemas conocidos con el producto.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 37d31fe93a849871e7da92fff521b6a75beac531
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187642"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a>Recursos para Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Recopilación de información de diagnóstico

Si puede reproducir un problema, aumente el nivel de registro, ejecute el sistema durante algún tiempo y restaure el nivel de registro en el valor predeterminado.

1. Aumentar el nivel de registro:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproducir el problema

3. Ejecute `sudo mdatp diagnostic create` para realizar una copia de seguridad de los registros de Microsoft Defender para puntos de conexión. Los archivos se almacenarán dentro de un archivo .zip. Este comando también imprimirá la ruta de acceso del archivo a la copia de seguridad después de que la operación se realice correctamente.

   > [!TIP]
   > De forma predeterminada, los registros de diagnóstico se guardan en `/Library/Application Support/Microsoft/Defender/wdavdiag/` . Para cambiar el directorio donde se guardan los registros de diagnóstico, pase al `--path [directory]` comando siguiente, reemplazando `[directory]` por el directorio deseado.

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Restaurar nivel de registro:

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Problemas de instalación de registro

Si se produce un error durante la instalación, el instalador solo informará de un error general.

El registro detallado se guardará en `/Library/Logs/Microsoft/mdatp/install.log` . Si tiene problemas durante la instalación, envíenos este archivo para que podamos diagnosticar la causa.

## <a name="uninstalling"></a>Desinstalación

Hay varias maneras de desinstalar Microsoft Defender para Endpoint para Mac. Tenga en cuenta que aunque la desinstalación administrada centralmente está disponible en JAMF, todavía no está disponible para Microsoft Intune.

### <a name="interactive-uninstallation"></a>Desinstalación interactiva

- Abre **Finder > aplicaciones**. Haga clic con el botón **secundario en Microsoft Defender ATP > Mover a la papelera**.

### <a name="from-the-command-line"></a>Desde la línea de comandos

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a>Configuración desde la línea de comandos

Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos:

|Grupo        |Escenario                                   |Comando                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Configuración|Activar/desactivar la protección en tiempo real           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Configuración|Activar/desactivar la protección en la nube               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Configuración|Activar/desactivar diagnósticos de productos            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Configuración|Activar/desactivar el envío automático de muestra    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Configuración|Agregar un nombre de amenaza a la lista permitida      |`mdatp threat allowed add --name [threat-name]`                                   |
|Configuración|Quitar un nombre de amenaza de la lista permitida |`mdatp threat allowed remove --name [threat-name]`                                |
|Configuración|Enumerar todos los nombres de amenazas permitidos              |`mdatp threat allowed list`                                                       |
|Configuración|Activar la protección de LA PUA                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Configuración|Desactivar la protección de LA PUA                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Configuración|Activar el modo de auditoría para la protección de PUA      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Configuración|Activar/desactivar passiveMode                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnostics  |Cambiar el nivel de registro                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnostics  |Generar registros de diagnóstico                   |`mdatp diagnostic create --path [directory]`                                      |
|Salud       |Comprobar el estado del producto                 |`mdatp health`                                                                    |
|Salud       |Buscar un atributo de producto spefic       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Protection   |Examinar una ruta de acceso                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Protection   |Realizar un examen rápido                            |`mdatp scan quick`                                                                |
|Protection   |Realizar un examen completo                             |`mdatp scan full`                                                                 |
|Protection   |Cancelar un examen a petición en curso           |`mdatp scan cancel`                                                               |
|Protection   |Solicitar una actualización de inteligencia de seguridad     |`mdatp definitions update`                                                        |
|EDR          |Agregar etiqueta de grupo al dispositivo. Las etiquetas EDR se usan para administrar grupos de dispositivos. Para obtener más información, visite https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Quitar etiqueta de grupo del dispositivo               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Agregar id. de grupo                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Cómo habilitar la autocompleción

Para habilitar la autocompleción en bash, ejecute el siguiente comando y reinicie la sesión de Terminal:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Para habilitar la autocompleción en zsh:

- Comprueba si la autocompleción está habilitada en el dispositivo:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Si el comando anterior no produce ningún resultado, puede habilitar la autocompleción con el siguiente comando:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Ejecute los siguientes comandos para habilitar la autocompleción para Microsoft Defender para Endpoint para Mac y reiniciar la sesión de Terminal:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Directorio de cuarentena cliente de Microsoft Defender para extremo

`/Library/Application Support/Microsoft/Defender/quarantine/` contiene los archivos en cuarentena por `mdatp` . Los archivos se denominan después del trackingId de amenazas. El trackingIds actual se muestra con `mdatp threat list` .

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Información del portal de Microsoft Defender para puntos de conexión

[Las capacidades de EDR](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)para macOS ya han llegado, en el blog de Microsoft Defender para endpoints, proporciona instrucciones detalladas sobre lo que se espera en Microsoft Defender para endpoint Security Center.
