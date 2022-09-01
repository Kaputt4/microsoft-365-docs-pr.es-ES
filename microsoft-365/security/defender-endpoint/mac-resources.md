---
title: Recursos para Microsoft Defender para punto de conexión en Mac
description: Recursos para Microsoft Defender para punto de conexión en Mac, incluido cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos de la CLI y problemas conocidos con el producto.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 8796a3d5317410278ada48205e1fe578c8c712bf
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522001"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>Recursos para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Recopilación de información de diagnóstico

Si puede reproducir un problema, aumente el nivel de registro, ejecute el sistema durante algún tiempo y restaure el nivel de registro al valor predeterminado.

1. Aumentar el nivel de registro:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproducir el problema

3. Ejecute `sudo mdatp diagnostic create` para realizar una copia de seguridad de los registros de Microsoft Defender para punto de conexión. Los archivos se almacenarán dentro de un archivo de .zip. Este comando también imprimirá la ruta de acceso del archivo a la copia de seguridad después de que la operación se realice correctamente.

   > [!TIP]
   > De forma predeterminada, los registros de diagnóstico se guardan en `/Library/Application Support/Microsoft/Defender/wdavdiag/`. Para cambiar el directorio donde se guardan los registros de diagnóstico, pase `--path [directory]` al siguiente comando y reemplace por `[directory]` el directorio deseado.

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Restaurar el nivel de registro:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Problemas de instalación de registro

Si se produce un error durante la instalación, el instalador solo notificará un error general.

El registro detallado se guardará en `/Library/Logs/Microsoft/mdatp/install.log`. Si experimenta problemas durante la instalación, envíenos este archivo para que podamos ayudar a diagnosticar la causa.

## <a name="uninstalling"></a>Desinstalar

Hay varias maneras de desinstalar Microsoft Defender para punto de conexión en macOS. Tenga en cuenta que aunque la desinstalación administrada centralmente está disponible en JAMF, aún no está disponible para Microsoft Intune.

### <a name="interactive-uninstallation"></a>Desinstalación interactiva

- Abra **Finder > Applications( Aplicaciones de Finder >).** Haga clic con el botón derecho en **Microsoft Defender para punto de conexión > Mover a la papelera**.

### <a name="supported-output-types"></a>Tipos de salida admitidos

Admite tipos de salida de formato JSON y tabla. Para cada comando, hay un comportamiento de salida predeterminado. Puede modificar la salida en el formato de salida que prefiera mediante los siguientes comandos:

`-output json`

`-output table`

### <a name="from-the-command-line"></a>Desde la línea de comandos

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>Configuración desde la línea de comandos

Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos:

|Grupo|Escenario|Comando|
|---|---|---|
|Configuración|Activar o desactivar la protección en tiempo real|`mdatp config real-time-protection --value [enabled/disabled]`|
|Configuración|Activar o desactivar la protección en la nube|`mdatp config cloud --value [enabled/disabled]`|
|Configuración|Activar o desactivar diagnósticos de productos|`mdatp config cloud-diagnostic --value [enabled/disabled]`|
|Configuración|Activar o desactivar el envío automático de ejemplos|`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`|
|Configuración|Agregar un nombre de amenaza a la lista permitida|`mdatp threat allowed add --name [threat-name]`|
|Configuración|Quitar un nombre de amenaza de la lista permitida|`mdatp threat allowed remove --name [threat-name]`|
|Configuración|Enumerar todos los nombres de amenazas permitidos|`mdatp threat allowed list`|
|Configuración|Activar la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application -- action block`|
|Configuración|Desactivar la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application -- action off`|
|Configuración|Activar el modo de auditoría para la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application -- action audit`|
|Configuración|Activar o desactivar el modo pasivo antivirus|`mdatp config passive-mode --value [enabled/disabled]`|
|Configuración|Configuración del grado de paralelismo para los exámenes a petición|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|Configuración|Activar o desactivar exámenes después de las actualizaciones de inteligencia de seguridad|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|Configuración|Activar o desactivar el examen de archivos (solo exámenes a petición)|`mdatp config scan-archives --value [enabled/disabled]`|
|Configuración|Activación o desactivación del cálculo de hash de archivos|`mdatp config enable-file-hash-computation --value [enabled/disabled]`|
|Configuración|Activar o desactivar data_loss_prevention|`mdatp config data_loss_prevention --value [enabled/disabled]`|
|Diagnóstico|Cambio del nivel de registro|`mdatp log level set --level [error/warning/info/verbose]`|
|Diagnóstico|Generación de registros de diagnóstico|`mdatp diagnostic create --path [directory]`|
|Mantenimiento|Comprobar el estado del producto|`mdatp health`|
|Mantenimiento|Comprobación de un atributo de producto spefic|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|Protección|Examen de una ruta de acceso|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|Protección|Realizar un examen rápido|`mdatp scan quick`|
|Protección|Realizar un examen completo|`mdatp scan full`|
|Protección|Cancelación de un examen a petición en curso|`mdatp scan cancel`|
|Protección|Solicitud de una actualización de inteligencia de seguridad|`mdatp definitions update`|
|Edr|Establecer o quitar etiqueta, solo se admite GROUP|`mdatp edr tag set --name GROUP --value [name]`|
|Edr|Eliminación de la etiqueta de grupo del dispositivo|`mdatp edr tag remove --tag-name [name]`|
|Edr|Agregar id. de grupo|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>Habilitación de lacompletar automática

Para habilitar la autocompletar en Bash, ejecute el siguiente comando y reinicie la sesión de Terminal:

```bash
echo "source /Applications/Microsoft\ Defender.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Para habilitar la autocompletar en zsh:

- Compruebe si la función de autocompletar está habilitada en el dispositivo:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Si el comando anterior no genera ninguna salida, puede habilitar la autocompletar mediante el siguiente comando:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Ejecute los siguientes comandos para habilitar la autocompletar para Microsoft Defender para punto de conexión en macOS y reinicie la sesión de Terminal:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions

   sudo ln -svf "/Applications/Microsoft Defender.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Directorio de cuarentena de Microsoft Defender para punto de conexión cliente

`/Library/Application Support/Microsoft/Defender/quarantine/` contiene los archivos en cuarentena por `mdatp`. Los archivos se denominan después del id. de seguimiento de amenazas. El trackingIds actual se muestra con `mdatp threat list`.

## <a name="microsoft-defender-for-endpoint-portal-information"></a>información del portal de Microsoft Defender para punto de conexión

[Las funcionalidades de EDR para macOS ya han llegado](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), en el blog de Microsoft Defender para punto de conexión, proporciona instrucciones detalladas sobre lo que se espera en Microsoft Defender para punto de conexión Security Center.
