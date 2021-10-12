---
title: Recursos de Microsoft Defender para endpoint en Linux
ms.reviewer: ''
description: Describe recursos para Microsoft Defender para Endpoint en Linux, como cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos cli y problemas conocidos con el producto.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8d7de5d6b897d93b0112745ed566879a451e5448
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268559"
---
# <a name="resources"></a>Recursos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Recopilar información de diagnóstico

Si puede reproducir un problema, aumente primero el nivel de registro, ejecute el sistema durante algún tiempo y, a continuación, restaure el nivel de registro en el valor predeterminado.

1. Aumentar el nivel de registro:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduce el problema.

3. Ejecute el siguiente comando para realizar una copia de seguridad de Defender para los registros del extremo. Los archivos se almacenarán dentro de un .zip archivo.

   ```bash
   sudo mdatp diagnostic create
   ```

    Este comando también imprimirá la ruta de acceso del archivo a la copia de seguridad después de que la operación se realice correctamente:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Restaurar nivel de registro:

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Problemas de instalación del registro

Si se produce un error durante la instalación, el instalador solo informará de un error general.

El registro detallado se guardará en `/var/log/microsoft/mdatp/install.log` .
Si tiene problemas durante la instalación, envíenos este archivo para que podamos diagnosticar la causa.

## <a name="uninstall"></a>Desinstalar

Hay varias maneras de desinstalar Defender for Endpoint en Linux. Si usa una herramienta de configuración como Puppet, siga las instrucciones de desinstalación del paquete para la herramienta de configuración.

### <a name="manual-uninstallation"></a>Desinstalación manual

- `sudo yum remove mdatp` para RHEL y variantes (CentOS y Oracle Linux).
- `sudo zypper remove mdatp` para SLES y variantes.
- `sudo apt-get purge mdatp` para sistemas Ubuntu y Debian.

## <a name="configure-from-the-command-line"></a>Configurar desde la línea de comandos

Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos.

### <a name="global-options"></a>Opciones globales

De forma predeterminada, la herramienta de línea de comandos genera el resultado en formato legible. Además, la herramienta también admite la salida del resultado como JSON, lo que resulta útil para escenarios de automatización. Para cambiar el resultado a JSON, pase `--output json` a cualquiera de los comandos siguientes.

### <a name="supported-commands"></a>Comandos admitidos

En la tabla siguiente se enumeran los comandos de algunos de los escenarios más comunes. Ejecute `mdatp help` desde terminal para ver la lista completa de comandos admitidos.

<br>

****

|Grupo|Escenario|Comando|
|---|---|---|
|Configuración|Activar/desactivar la protección en tiempo real|`mdatp config real-time-protection --value [enabled\|disabled]`|
|Configuración|Activar/desactivar la supervisión del comportamiento|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|Configuración|Activar/desactivar la protección en la nube|`mdatp config cloud --value [enabled\|disabled]`|
|Configuración|Activar/desactivar diagnósticos de productos|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|Configuración|Activar/desactivar el envío automático de muestra|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|Configuración|Activar/desactivar el modo pasivo de AV|`mdatp config passive-mode --value [enabled\|disabled]`|
|Configuración|Agregar o quitar una exclusión antivirus para una extensión de archivo|`mdatp exclusion extension [add\|remove] --name [extension]`|
|Configuración|Agregar o quitar una exclusión antivirus para un archivo|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|Configuración|Agregar o quitar una exclusión antivirus para un directorio|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|Configuración|Agregar o quitar una exclusión antivirus para un proceso|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|Configuración|Enumerar todas las exclusiones de antivirus|`mdatp exclusion list`|
|Configuración|Agregar un nombre de amenaza a la lista permitida|`mdatp threat allowed add --name [threat-name]`|
|Configuración|Quitar un nombre de amenaza de la lista permitida|`mdatp threat allowed remove --name [threat-name]`|
|Configuración|Enumerar todos los nombres de amenazas permitidos|`mdatp threat allowed list`|
|Configuración|Activar la protección de LA PUA|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|Configuración|Desactivar la protección de LA PUA|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|Configuración|Activar el modo de auditoría para la protección de PUA|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|Configuración|Configurar el grado de paralelismo para los exámenes a petición|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|Configuración|Activar y desactivar exámenes después de las actualizaciones de inteligencia de seguridad|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|Configuración|Activar/desactivar el examen del archivo (solo exámenes a petición)|`mdatp config scan-archives --value [enabled/disabled]`|
|Diagnostics|Cambiar el nivel de registro|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|Diagnostics|Generar registros de diagnóstico|`mdatp diagnostic create --path [directory]`|
|Mantenimiento|Comprobar el estado del producto|`mdatp health`|
|Protection|Examinar una ruta de acceso|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|Protection|Realizar un examen rápido|`mdatp scan quick`|
|Protection|Realizar un examen completo|`mdatp scan full`|
|Protection|Cancelar un examen a petición en curso|`mdatp scan cancel`|
|Protection|Solicitar una actualización de inteligencia de seguridad|`mdatp definitions update`|
|Historial de protección|Imprimir el historial de protección completo|`mdatp threat list`|
|Historial de protección|Obtener detalles de amenazas|`mdatp threat get --id [threat-id]`|
|Administración de cuarentena|Enumerar todos los archivos en cuarentena|`mdatp threat quarantine list`|
|Administración de cuarentena|Quitar todos los archivos de la cuarentena|`mdatp threat quarantine remove-all`|
|Administración de cuarentena|Agregar un archivo detectado como una amenaza a la cuarentena|`mdatp threat quarantine add --id [threat-id]`|
|Administración de cuarentena|Quitar un archivo detectado como una amenaza de la cuarentena|`mdatp threat quarantine remove --id [threat-id]`|
|Administración de cuarentena|Restaurar un archivo desde la cuarentena|`mdatp threat quarantine restore --id [threat-id]`|
|Detección y respuesta de extremos|Establecer la vista previa anticipada (sin usar)|`mdatp edr early-preview [enable|disable]`|
|Detección y respuesta de extremos|Establecer group-id|`mdatp edr group-ids --group-id [group-id]`|
|Detección y respuesta de extremos|Establecer o quitar etiqueta, solo `GROUP` compatible|`mdatp edr tag set --name GROUP --value [tag]`|
|Detección y respuesta de extremos|Enumerar exclusiones (raíz)|`mdatp edr exclusion list [processes|paths|extensions|all]`|
|
