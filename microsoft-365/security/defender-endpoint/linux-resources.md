---
title: Microsoft Defender para punto de conexión en recursos de Linux
ms.reviewer: ''
description: Describe los recursos para Microsoft Defender para punto de conexión en Linux, incluido cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos de la CLI y problemas conocidos con el producto.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 5e3f8cb9cc826894f816fcebf28ef73213548f22
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233340"
---
# <a name="resources"></a>Recursos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Recopilación de información de diagnóstico

Si puede reproducir un problema, aumente primero el nivel de registro, ejecute el sistema durante algún tiempo y, a continuación, restaure el nivel de registro al valor predeterminado.

1. Aumentar el nivel de registro:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduzca el problema.

3. Ejecute el siguiente comando para hacer una copia de seguridad de los registros de Defender para punto de conexión. Los archivos se almacenarán dentro de un archivo .zip.

   ```bash
   sudo mdatp diagnostic create
   ```

    Este comando también imprimirá la ruta de acceso del archivo a la copia de seguridad después de que la operación se realice correctamente:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Restaurar el nivel de registro:

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Problemas de instalación de registros

Si se produce un error durante la instalación, el instalador solo notificará un error general.

El registro detallado se guardará en `/var/log/microsoft/mdatp/install.log`.
Si experimenta problemas durante la instalación, envíenos este archivo para que podamos ayudar a diagnosticar la causa.

## <a name="uninstall"></a>Desinstalar

Hay varias maneras de desinstalar Defender para punto de conexión en Linux. Si usa una herramienta de configuración como Puppet, siga las instrucciones de desinstalación del paquete para la herramienta de configuración.

### <a name="manual-uninstallation"></a>Desinstalación manual

- `sudo yum remove mdatp` para RHEL y variantes (CentOS y Oracle Linux).
- `sudo zypper remove mdatp` para SLES y variantes.
- `sudo apt-get purge mdatp` para sistemas Ubuntu y Debian.

## <a name="configure-from-the-command-line"></a>Configuración desde la línea de comandos

Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos.

### <a name="global-options"></a>Opciones globales

De forma predeterminada, la herramienta de línea de comandos genera el resultado en formato legible. Además, la herramienta también admite la salida del resultado como JSON, lo que resulta útil para escenarios de automatización. Para cambiar la salida a JSON, pase `--output json` a cualquiera de los comandos siguientes.

### <a name="supported-commands"></a>Comandos admitidos

En la tabla siguiente se enumeran los comandos de algunos de los escenarios más comunes. Ejecute `mdatp help` desde terminal para ver la lista completa de comandos admitidos.

<br>

****

|Grupo|Escenario|Get-Help|
|---|---|---|
|Configuración|Activar o desactivar la protección en tiempo real|`mdatp config real-time-protection --value [enabled\|disabled]`|
|Configuración|Activar o desactivar la supervisión del comportamiento|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|Configuración|Activar o desactivar la protección en la nube|`mdatp config cloud --value [enabled\|disabled]`|
|Configuración|Activar o desactivar diagnósticos de productos|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|Configuración|Activar o desactivar el envío automático de ejemplos|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|Configuración|Activar o desactivar el modo pasivo av|`mdatp config passive-mode --value [enabled\|disabled]`|
|Configuración|Agregar o quitar una exclusión antivirus para una extensión de archivo|`mdatp exclusion extension [add\|remove] --name [extension]`|
|Configuración|Adición o eliminación de una exclusión de antivirus para un archivo|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|Configuración|Adición o eliminación de una exclusión de antivirus para un directorio|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|Configuración|Adición o eliminación de una exclusión de antivirus para un proceso|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|Configuración|Enumerar todas las exclusiones de antivirus|`mdatp exclusion list`|
|Configuración|Agregar un nombre de amenaza a la lista permitida|`mdatp threat allowed add --name [threat-name]`|
|Configuración|Quitar un nombre de amenaza de la lista permitida|`mdatp threat allowed remove --name [threat-name]`|
|Configuración|Enumerar todos los nombres de amenazas permitidos|`mdatp threat allowed list`|
|Configuración|Activar la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|Configuración|Desactivar la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|Configuración|Activar el modo de auditoría para la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|Configuración|Configuración del grado de paralelismo para los exámenes a petición|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|Configuración|Activar o desactivar exámenes después de las actualizaciones de inteligencia de seguridad|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|Configuración|Activar o desactivar el examen de archivos (solo exámenes a petición)|`mdatp config scan-archives --value [enabled/disabled]`|
|Configuración|Activación o desactivación del cálculo de hash de archivos|`mdatp config enable-file-hash-computation --value [enabled/disabled]`|
|Diagnóstico|Cambio del nivel de registro|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|Diagnóstico|Generación de registros de diagnóstico|`mdatp diagnostic create --path [directory]`|
|Mantenimiento|Comprobar el estado del producto|`mdatp health`|
|Protección|Examen de una ruta de acceso|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|Protección|Realizar un examen rápido|`mdatp scan quick`|
|Protección|Realizar un examen completo|`mdatp scan full`|
|Protección|Cancelación de un examen a petición en curso|`mdatp scan cancel`|
|Protección|Solicitud de una actualización de inteligencia de seguridad|`mdatp definitions update`|
|Historial de protección|Imprimir el historial de protección completo|`mdatp threat list`|
|Historial de protección|Obtener detalles de amenazas|`mdatp threat get --id [threat-id]`|
|Administración de cuarentena|Enumerar todos los archivos en cuarentena|`mdatp threat quarantine list`|
|Administración de cuarentena|Quitar todos los archivos de la cuarentena|`mdatp threat quarantine remove-all`|
|Administración de cuarentena|Adición de un archivo detectado como una amenaza a la cuarentena|`mdatp threat quarantine add --id [threat-id]`|
|Administración de cuarentena|Eliminación de un archivo detectado como amenaza de la cuarentena|`mdatp threat quarantine remove --id [threat-id]`|
|Administración de cuarentena|Restauración de un archivo desde la cuarentena|`mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`|
|Detección y respuesta de puntos de conexión|Establecer la versión preliminar temprana (sin usar)|`mdatp edr early-preview [enable|disable]`|
|Detección y respuesta de puntos de conexión|Establecimiento de group-id|`mdatp edr group-ids --group-id [group-id]`|
|Detección y respuesta de puntos de conexión|Establecer o quitar etiqueta, solo `GROUP` compatible|`mdatp edr tag set --name GROUP --value [tag]`|
|Detección y respuesta de puntos de conexión|Exclusiones de lista (raíz)|`mdatp edr exclusion list [processes|paths|extensions|all]`|
|
