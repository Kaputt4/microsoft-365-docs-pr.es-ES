---
title: Ejecutar el Analizador de clientes en macOS o Linux
description: Obtenga información sobre cómo ejecutar el Analizador de cliente de Microsoft Defender para endpoint en macOS o Linux
keywords: analizador de cliente, sensor de solución de problemas, analizador, mdeanalyzer, macos, linux, mdeanalyzer
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
ms.openlocfilehash: a49e2a862f3b95bde40620f3093d2f149111ad3d
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889824"
---
# <a name="run-the-client-analyzer-on-macos-and-linux"></a>Ejecutar el analizador de clientes en macOS o Linux

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

## <a name="running-the-analyzer-through-gui-scenario"></a>Ejecución del analizador a través del escenario gui

1. Descargue la [herramienta analizador de cliente XMDE](https://aka.ms/XMDEClientAnalyzer) en la máquina macOS o Linux que necesita investigar.

   > [!NOTE]
   > El hash SHA256 actual de "XMDEClientAnalyzer.zip" que se descarga del vínculo anterior es: "34C7F04321157544BB2C9CE30AB0998172066E44CD51E1CA018EDE9C96AB834".

2. Extraiga el contenido de XMDEClientAnalyzer.zip en el equipo.

3. Abra una sesión de terminal, cambie el directorio a la ubicación extraída y ejecute:

   `./mde_support_tool.sh -d`

   > [!NOTE]
   > En Linux, si el script no tiene permisos para ejecutarse, deberá ejecutar primero:
   >
   > `chmod a+x mde_support_tool.sh`

## <a name="running-the-analyzer-using-a-terminal-or-ssh-scenario"></a>Ejecución del analizador mediante un escenario de terminal o SSH

Abra un terminal o SSH en la máquina correspondiente y ejecute los siguientes comandos:

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`

2. `unzip -q XMDEClientAnalyzer.zip`

3. `cd XMDEClientAnalyzer`

4. `chmod +x mde_support_tool.sh`

3. Ejecutar como uso no raíz para instalar pip y lxml necesarios qué componentes: `./mde_support_tool.sh`

4. Para recopilar el paquete de diagnóstico real y generar el archivo de archivo de resultados, vuelva a ejecutarse como raíz: `./mde_support_tool.sh -d`

> [!NOTE]
> - Para Linux, el analizador requiere 'lxml' para producir el resultado. Si no está instalado, el analizador intentará capturarlo desde el repositorio oficial para los paquetes python siguientes: <https://files.pythonhosted.org/packages/\*/lxml\*.whl>
> 
> - Además, la herramienta requiere actualmente la instalación de Python versión 3 o posterior.
>
> - Si se ejecuta en una máquina que no puede usar Python 3 o capturar el componente lxml, puede descargar una versión basada en binarios del analizador que no tenga ninguno de los requisitos: [XMDE Client Analyzer Binary](https://aka.ms/XMDEClientAnalyzerBinary)
>
> - Si el dispositivo está detrás de un proxy, simplemente puedes pasar el servidor proxy como una variable de entorno al script mde_support_tool.sh. Por ejemplo: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

Ejemplo:

![Imagen del ejemplo de línea de comandos.](images/4ca188f6c457e335abe3c9ad3eddda26.png)

Ayuda de sintaxis adicional:

**-h** \# Ayuda<br>
\# Mostrar mensaje de ayuda

**rendimiento** \# Rendimiento<br>
\# Recopila un seguimiento extensivo para analizar un problema de rendimiento que se puede reproducir a petición. Se `--length=<seconds>` usa para especificar la duración del punto de referencia.

**-o** \# Salida<br>
\# Especificar la ruta de destino del archivo de resultados

**-nz** \# No-Zip<br>
\# Si se establece, se creará un directorio en lugar de un archivo de archivo resultante

**-f** \# Forzar<br>
\# Sobrescribir si el resultado ya existe en la ruta de destino

## <a name="result-package-contents-on-macos-and-linux"></a>Contenido del paquete de resultados en macOS y Linux

- report.html

  Descripción: el archivo de salida HTML principal que contendrá los resultados y las instrucciones que puede producir el script del analizador en la máquina.

- mde_diagnostic.zip

  Descripción: el mismo resultado de diagnóstico que se genera al ejecutar la creación de diagnóstico de *mdatp* en [macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-resources#collecting-diagnostic-information)

  Otra posibilidad:

  [Linux](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

- mde.xml

  Descripción: salida XML que se genera mientras se ejecuta y se usa para crear el archivo de informe html.

- Processes_information.txt

  Descripción: contiene los detalles de los procesos relacionados con Microsoft Defender para endpoint en ejecución en el sistema.

- Log.txt

  Descripción: contiene los mismos mensajes de registro escritos en pantalla durante la recopilación de datos.

- Health.txt

  Descripción: el mismo resultado de mantenimiento básico que se muestra al ejecutar el comando de mantenimiento *mdatp.*

- Events.xml

  Descripción: archivo XML adicional usado por el analizador al compilar el informe HTML.

- Auditd_info.txt

  Descripción: detalles sobre el servicio auditado y los componentes relacionados para el sistema operativo [Linux](/windows/security/threat-protection/microsoft-defender-atp/linux-support-events)

- perf_benchmark.tar.gz

  Descripción: los informes de prueba de rendimiento. Esto solo se verá si usa el parámetro de rendimiento.
