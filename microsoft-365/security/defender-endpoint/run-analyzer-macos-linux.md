---
title: Ejecutar el Analizador de clientes en macOS o Linux
description: Aprenda a ejecutar Microsoft Defender para punto de conexión Client Analyzer en macOS o Linux.
keywords: analizador de cliente, solución de problemas de sensor, analizador, mdeanalyzer, macos, linux, mdeanalyzer
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3e7490f4f7141aaf5c350a146c56de2432d58d21
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300397"
---
# <a name="run-the-client-analyzer-on-macos-and-linux"></a>Ejecutar el analizador de clientes en macOS o Linux


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="running-the-analyzer-through-gui-scenario"></a>Ejecución del analizador a través del escenario de GUI

1. Descargue la herramienta [XMDE Client Analyzer](https://aka.ms/XMDEClientAnalyzer) en la máquina macOS o Linux que necesita investigar.

   > [!NOTE]
   > El hash SHA256 actual de "XMDEClientAnalyzer.zip" que se descarga del vínculo anterior es: "bf102a79626c88fe58b5be3034640835f96f54230292486716d72f515875966c".

2. Extraiga el contenido de XMDEClientAnalyzer.zip en el equipo.

3. Abra una sesión de terminal, cambie el directorio a la ubicación extraída y ejecute:

   `./mde_support_tool.sh -d`

   > [!NOTE]
   > En Linux, si el script no tiene permisos para ejecutarse, primero tendrá que ejecutar:
   >
   > `chmod a+x mde_support_tool.sh`

## <a name="running-the-analyzer-using-a-terminal-or-ssh-scenario"></a>Ejecución del analizador mediante un escenario de terminal o SSH

Abra un terminal o SSH en la máquina correspondiente y ejecute los siguientes comandos:

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`

2. `unzip -q XMDEClientAnalyzer.zip`

3. `cd XMDEClientAnalyzer`

4. `chmod +x mde_support_tool.sh`

3. Ejecute como uso no raíz para instalar los componentes pip y lxml necesarios: `./mde_support_tool.sh`

4. Para recopilar el paquete de diagnóstico real y generar el archivo de archivo de resultados, vuelva a ejecutarse como raíz: `./mde_support_tool.sh -d`

> [!NOTE]
> - Para Linux, el analizador requiere "lxml" para generar la salida del resultado. Si no está instalado, el analizador intentará capturarlo del repositorio oficial para los paquetes de Python siguientes: <https://pypi.org/search/?q=lxml>
> 
> - Además, la herramienta requiere actualmente la versión 3 o posterior de Python para instalarse.
>
> - Si se ejecuta en un equipo que no puede usar Python 3 ni capturar el componente lxml, puede descargar una versión basada en binario del analizador que no tenga ninguno de los requisitos: [Binario del analizador de cliente XMDE](https://aka.ms/XMDEClientAnalyzerBinary). <br> Tenga en cuenta que el binario está sin signo actualmente. Para permitir que el paquete se ejecute en MacOS, deberá usar la sintaxis : "spctl --add /Path/To/Application.app".
> - El hash SHA256 actual de "XMDEClientAnalyzerBinary.zip" que se descarga del vínculo anterior es: "7FE67373CDF493BF2748FD778BD106EE85A71C968D594BCC67C7374620506EF2"
>
> - Si el dispositivo está detrás de un proxy, simplemente puede pasar el servidor proxy como variable de entorno al script mde_support_tool.sh. Por ejemplo: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

Ejemplo:

:::image type="content" source="images/4ca188f6c457e335abe3c9ad3eddda26.png" alt-text="Ejemplo de línea de comandos" lightbox="images/4ca188f6c457e335abe3c9ad3eddda26.png":::

Ayuda de sintaxis adicional:

**-h** \# Ayuda<br>
\# Mostrar mensaje de ayuda

**Rendimiento** \# Rendimiento<br>
\# Recopila un seguimiento exhaustivo para analizar un problema de rendimiento que se puede reproducir a petición. Usar `--length=<seconds>` para especificar la duración de la prueba comparativa.

**-o** \# Salida<br>
\# Especificar la ruta de acceso de destino para el archivo de resultados

**-nz** \# No-Zip<br>
\# Si se establece, se creará un directorio en lugar de un archivo de archivo resultante.

**-f** \# Fuerza<br>
\# Sobrescribir si la salida ya existe en la ruta de acceso de destino

## <a name="result-package-contents-on-macos-and-linux"></a>Contenido del paquete de resultados en macOS y Linux

- report.html

  Descripción: el archivo de salida HTML principal que contendrá los resultados y las instrucciones que puede generar el script del analizador que se ejecuta en la máquina.

- mde_diagnostic.zip

  Descripción: la misma salida de diagnóstico que se genera al ejecutar *mdatp diagnostic create* en [cualquiera de los macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-resources#collecting-diagnostic-information).

  o

  [Linux](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

- mde.xml

  Descripción: salida XML que se genera durante la ejecución y se usa para compilar el archivo de informe html.

- Processes_information.txt

  Descripción: contiene los detalles de la ejecución Microsoft Defender para punto de conexión procesos relacionados en el sistema.

- Log.txt

  Descripción: contiene los mismos mensajes de registro escritos en pantalla durante la recopilación de datos.

- Health.txt

  Descripción: la misma salida de estado básico que se muestra al ejecutar *el comando de mantenimiento mdatp* .

- Events.xml

  Descripción: archivo XML adicional que usa el analizador al compilar el informe HTML.

- Audited_info.txt

  Descripción: detalles sobre el servicio auditado y los componentes relacionados para el sistema operativo [Linux](/microsoft-365/security/defender-endpoint/linux-resources)

- perf_benchmark.tar.gz

  Descripción: los informes de pruebas de rendimiento. Solo verá esto si usa el parámetro de rendimiento.
