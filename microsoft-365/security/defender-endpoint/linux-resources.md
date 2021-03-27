---
title: Recursos de ATP para Linux de Microsoft Defender
ms.reviewer: ''
description: Describe recursos para ATP de Microsoft Defender para Linux, incluido cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos de CLI y problemas conocidos con el producto.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ab5400a197a1f0ac61c8b298a06165d217f44fd1
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394739"
---
# <a name="resources"></a>Recursos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

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

3. Ejecute el siguiente comando para realizar una copia de seguridad de Defender para los registros del extremo. Los archivos se almacenarán dentro de un archivo .zip.

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

El registro detallado se guardará en `/var/log/microsoft/mdatp_install.log` . Si tiene problemas durante la instalación, envíenos este archivo para que podamos diagnosticar la causa.

## <a name="uninstall"></a>Uninstall

Hay varias maneras de desinstalar Defender para Endpoint para Linux. Si usa una herramienta de configuración como Puppet, siga las instrucciones de desinstalación del paquete para la herramienta de configuración.

### <a name="manual-uninstallation"></a>Desinstalación manual

- `sudo yum remove mdatp` para RHEL y variantes (CentOS y Oracle Linux).
- `sudo zypper remove mdatp` para SLES y variantes.
- `sudo apt-get purge mdatp` para sistemas Ubuntu y Debian.

## <a name="configure-from-the-command-line"></a>Configurar desde la línea de comandos

Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos.

### <a name="global-options"></a>Opciones globales

De forma predeterminada, la herramienta de línea de comandos genera el resultado en formato legible. Además, la herramienta también admite la salida del resultado como JSON, lo que resulta útil para escenarios de automatización. Para cambiar el resultado a JSON, pase `--output json` a cualquiera de los comandos siguientes.

### <a name="supported-commands"></a>Comandos compatibles

En la tabla siguiente se enumeran los comandos de algunos de los escenarios más comunes. Ejecute `mdatp help` desde terminal para ver la lista completa de comandos admitidos.

|Grupo                 |Escenario                                                |Comando                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Configuración         |Activar/desactivar la protección en tiempo real                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Configuración         |Activar/desactivar la supervisión del comportamiento                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|Configuración         |Activar/desactivar la protección en la nube                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Configuración         |Activar/desactivar diagnósticos de productos                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Configuración         |Activar/desactivar el envío automático de muestra                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Configuración         |Activar/desactivar el modo pasivo de AV                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Configuración         |Agregar o quitar una exclusión antivirus para una extensión de archivo  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Configuración         |Agregar o quitar una exclusión antivirus para un archivo            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Configuración         |Agregar o quitar una exclusión antivirus para un directorio       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Configuración         |Agregar o quitar una exclusión antivirus para un proceso         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Configuración         |Enumerar todas las exclusiones de antivirus                           |`mdatp exclusion list`                                                 |
|Configuración         |Agregar un nombre de amenaza a la lista permitida                   |`mdatp threat allowed add --name [threat-name]`                        |
|Configuración         |Quitar un nombre de amenaza de la lista permitida              |`mdatp threat allowed remove --name [threat-name]`                     |
|Configuración         |Enumerar todos los nombres de amenazas permitidos                           |`mdatp threat allowed list`                                            |
|Configuración         |Activar la protección de LA PUA                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Configuración         |Desactivar la protección de LA PUA                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Configuración         |Activar el modo de auditoría para la protección de PUA                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnostics           |Cambiar el nivel de registro                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnostics           |Generar registros de diagnóstico                                |`mdatp diagnostic create --path [directory]`                           |
|Salud                |Comprobar el estado del producto                              |`mdatp health`                                                         |
|Protection            |Examinar una ruta de acceso                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Protection            |Realizar un examen rápido                                         |`mdatp scan quick`                                                     |
|Protection            |Realizar un examen completo                                          |`mdatp scan full`                                                      |
|Protection            |Cancelar un examen a petición en curso                        |`mdatp scan cancel`                                                    |
|Protection            |Solicitar una actualización de inteligencia de seguridad                  |`mdatp definitions update`                                             |
|Historial de protección    |Imprimir el historial de protección completo                       |`mdatp threat list`                                                    |
|Historial de protección    |Obtener detalles de amenazas                                      |`mdatp threat get --id [threat-id]`                                    |
|Administración de cuarentena |Enumerar todos los archivos en cuarentena                              |`mdatp threat quarantine list`                                         |
|Administración de cuarentena |Quitar todos los archivos de la cuarentena                    |`mdatp threat quarantine remove-all`                                   |
|Administración de cuarentena |Agregar un archivo detectado como una amenaza a la cuarentena       |`mdatp threat quarantine add --id [threat-id]`                         |
|Administración de cuarentena |Quitar un archivo detectado como una amenaza de la cuarentena  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Administración de cuarentena |Restaurar un archivo desde la cuarentena                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Detección y respuesta de extremos |Establecer la vista previa anticipada (sin usar)                    |`mdatp edr early-preview [enable|disable]`                             |
|Detección y respuesta de extremos |Establecer group-id                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Detección y respuesta de extremos |Establecer o quitar etiqueta, solo `GROUP` compatible        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Detección y respuesta de extremos |exclusiones de lista (raíz)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Información del portal de Microsoft Defender para puntos de conexión

En el portal de Defender para endpoint, verá dos categorías de información:

- Alertas antivirus, incluidas:
  - Severity
  - Tipo de examen
  - Información del dispositivo (nombre de host, identificador de dispositivo, identificador de inquilino, versión de aplicación y tipo de sistema operativo)
  - Información de archivo (nombre, ruta de acceso, tamaño y hash)
  - Información sobre amenazas (nombre, tipo y estado)
- Información del dispositivo, incluida:
  - Identificador de dispositivo
  - Identificador de inquilino
  - Versión de la aplicación
  - Nombre de host
  - Tipo de sistema operativo
  - Versión del sistema operativo
  - Modelo de equipo
  - Arquitectura del procesador
  - Si el dispositivo es una máquina virtual

### <a name="known-issues"></a>Problemas conocidos

- Es posible que vea "Sin datos de sensores, comunicaciones deficientes" en la página de información de la máquina del portal del Centro de seguridad de Microsoft Defender, aunque el producto funciona como se esperaba. Estamos trabajando en solucionar este problema.
- Los usuarios que han iniciado sesión no aparecen en el portal del Centro de seguridad de Microsoft Defender.
- En las distribuciones de SUSE, si se produce un error en la instalación de *libatomic1,* debe validar que el sistema operativo está registrado:

   ```bash
   sudo SUSEConnect --status-text
   ```
