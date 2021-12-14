---
title: Solucionar problemas de rendimiento de Microsoft Defender para Endpoint en Linux
description: Solucionar problemas de rendimiento en Microsoft Defender para Endpoint en Linux.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, rendimiento
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
ms.openlocfilehash: 65288d0644fa7761e91ad08a433d42bd85016e46
ms.sourcegitcommit: f1e227decbfdbac00dcf5aa72cf2285cecae14f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "61436661"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solucionar problemas de rendimiento de Microsoft Defender para Endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este documento se proporcionan instrucciones sobre cómo reducir los problemas de rendimiento relacionados con Defender para Endpoint en Linux con las herramientas de diagnóstico disponibles para poder comprender y mitigar la escasez de recursos existente y los procesos que están haciendo que el sistema entre en tales situaciones. Los problemas de rendimiento se producen principalmente por cuellos de botella en uno o varios subsistemas de hardware, según el perfil de uso de recursos en el sistema. A veces, las aplicaciones son sensibles a los recursos de E/S de disco y pueden necesitar más capacidad de CPU, y a veces algunas configuraciones no son sostenibles y pueden desencadenar demasiados procesos nuevos y abrir demasiados descriptores de archivo.

Según las aplicaciones que ejecutes y las características del dispositivo, es posible que experimentes un rendimiento subóptimo al ejecutar Defender para Endpoint en Linux. En particular, las aplicaciones o los procesos del sistema que tienen acceso a muchos recursos, como CPU, disco y memoria en un corto período de tiempo, pueden provocar problemas de rendimiento en Defender para Endpoint en Linux.

> [!WARNING]
> Antes de empezar, **asegúrate de que otros productos de seguridad no se estén ejecutando actualmente en el dispositivo**. Varios productos de seguridad pueden tener conflictos e impactar en el rendimiento del host.

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>Solucionar problemas de rendimiento mediante estadísticas de protección en tiempo real

**Se aplica a:**
- Solo problemas de rendimiento relacionados con AV

La protección en tiempo real (RTP) es una característica de Defender para Endpoint en Linux que supervisa y protege continuamente el dispositivo contra amenazas. Consiste en la supervisión de archivos y procesos y otras heurísticas.
Se pueden usar los siguientes pasos para solucionar y mitigar estos problemas:
1. Deshabilite la protección en tiempo real con uno de los siguientes métodos y observe si el rendimiento mejora. Este enfoque ayuda a reducir si Defender for Endpoint en Linux está contribuyendo a los problemas de rendimiento.
    Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar desde la línea de comandos:
    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```
    Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real con las instrucciones de Establecer preferencias para Defender para Endpoint [en Linux](linux-preferences.md).
    > [!NOTE]
    > Si el problema de rendimiento persiste mientras la protección en tiempo real está desactivada, el origen del problema podría ser el componente detección y respuesta de puntos de conexión (EDR). En este caso, siga los pasos de la sección Solucionar problemas de rendimiento con **Microsoft Defender para** endpoint Client Analyzer de este artículo.

2. Para buscar las aplicaciones que desencadenan la mayoría de los exámenes, puede usar estadísticas en tiempo real recopiladas por Defender para Endpoint en Linux.

    > [!NOTE]
    > Esta característica está disponible en la versión 100.90.70 o posterior.

    Esta característica está habilitada de forma predeterminada en los `Dogfood` `InsiderFast` canales y. Si usa un canal de actualización diferente, esta característica se puede habilitar desde la línea de comandos:
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```
    Esta característica requiere protección en tiempo real para habilitarse. Para comprobar el estado de la protección en tiempo real, ejecute el siguiente comando:
    ```bash
    mdatp health --field real_time_protection_enabled
    ```
    Compruebe que la `real_time_protection_enabled` entrada es `true` . De lo contrario, ejecute el siguiente comando para habilitarlo:
    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```
    Para recopilar estadísticas actuales, ejecute:
    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```
    > [!NOTE]
    > El uso (tenga en cuenta el ```--output json``` guión doble) garantiza que el formato de salida esté listo para el análisis. El resultado de este comando mostrará todos los procesos y su actividad de examen asociada.

3. En el sistema Linux, descargue el analizador python de **ejemplo high_cpu_parser.py** mediante el comando:
    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    El resultado de este comando debe ser similar al siguiente:
    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```
4. A continuación, escriba los siguientes comandos:
    ```bash
    chmod +x high_cpu_parser.py
    ```
    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```
      El resultado de lo anterior es una lista de los principales colaboradores de problemas de rendimiento. La primera columna es el identificador de proceso (PID), la segunda columna es el nombre del proceso y la última columna es el número de archivos analizados, ordenados por impacto.
    Por ejemplo, el resultado del comando será algo parecido al siguiente: 
    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```
    Para mejorar el rendimiento de Defender para Endpoint en Linux, busque el que tiene el número más alto debajo de la fila y `Total files scanned` agregue una exclusión para él. Para obtener más información, vea [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).
    
    > [!NOTE]
    > La aplicación almacena estadísticas en la memoria y solo realiza un seguimiento de la actividad del archivo desde que se inició y se ha habilitado la protección en tiempo real. Los procesos que se iniciaron antes o durante períodos en los que la protección en tiempo real estaba desactivada no se cuentan. Además, solo se cuentan los eventos que desencadenaron exámenes.

5. Configure Microsoft Defender para Endpoint en Linux con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelva a habilitar la protección en tiempo real.

    Para más información, consulte [Configurar y validar exclusiones de Microsoft Defender para punto de conexión en Linux](linux-exclusions.md).

## <a name="diagnose-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Diagnosticar problemas de rendimiento con Microsoft Defender para Endpoint Client Analyzer

**Se aplica a:**
- Problemas de rendimiento de todos los componentes disponibles de Defender para endpoint, como AV y EDR  

Microsoft Defender para endpoint client Analyzer (MDECA) puede recopilar seguimientos, registros e información de diagnóstico para solucionar problemas de rendimiento en dispositivos incorporados [en](/microsoft-365/security/defender-endpoint/onboard-configure) Linux.

> [!NOTE]
> Los Servicios de soporte al cliente (CSS) de Microsoft Defender para endpoints usan regularmente la herramienta Analizador de cliente de Microsoft Defender para recopilar información como, entre otras, direcciones IP, nombres de equipo que ayudarán a solucionar problemas que puedan estar experimentando con Microsoft Defender para endpoint. Para obtener más información acerca de nuestra declaración de privacidad, vea [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

### <a name="requirements"></a>Requisitos

- El analizador de cliente puede ejecutarse en distros compatibles de [Linux](microsoft-defender-endpoint-linux.md#system-requirements) antes o después de la incorporación a Microsoft Defender para Endpoint.
- Descargue el analizador de cliente para Linux desde la última edición de vista previa disponible para su descarga aquí: <https://aka.ms/XMDEClientAnalyzer>
- Si el dispositivo está detrás de un proxy, simplemente puedes pasar el servidor proxy como una variable de entorno al script mde_support_tool.sh. Por ejemplo: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

### <a name="run-the-client-analyzer-on-linux"></a>Ejecutar el analizador de cliente en Linux

Abra un terminal o SSH en la máquina correspondiente y ejecute los siguientes comandos:

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`
2. `unzip -q XMDEClientAnalyzer.zip`
3. `cd XMDEClientAnalyzer`
4. `chmod +x mde_support_tool.sh`
5. Ejecutar como uso no raíz para instalar pip y lxml necesarios qué componentes: `./mde_support_tool.sh`
6. Para recopilar el paquete de diagnóstico real y generar el archivo de archivo de resultados, vuelva a ejecutarse como raíz: `./mde_support_tool.sh -d` Ejemplo:

   ![Imagen del ejemplo de línea de comandos.](images/4ca188f6c457e335abe3c9ad3eddda26.png)

> [!NOTE]
> - El analizador requiere 'lxml' para producir el resultado. Si no está instalado, el analizador intentará capturarlo desde el repositorio oficial para los paquetes python siguientes: <https://files.pythonhosted.org/packages/\*/lxml\*.whl>
> 
> - Además, la herramienta requiere actualmente la instalación de Python versión 3 o posterior.
>
> - Si se ejecuta en una máquina que no puede usar Python 3 o capturar el componente lxml, puede descargar una versión basada en binarios del analizador que no tenga ninguno de los requisitos: [XMDE Client Analyzer Binary](https://aka.ms/XMDEClientAnalyzerBinary)

### <a name="additional-syntax-help"></a>Ayuda de sintaxis adicional:

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

### <a name="result-package-contents"></a>Contenido del paquete de resultados

- report.html

  Descripción: el archivo de salida HTML principal que contendrá los resultados y las instrucciones que puede producir el script del analizador en la máquina.

- mde_diagnostic.zip

  Descripción: el mismo resultado de diagnóstico que se genera al ejecutar *la creación de diagnóstico de mdatp* en [Linux](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

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

> [!NOTE]
> En caso de que después de seguir los pasos anteriores el problema de rendimiento persista, póngase en contacto con el soporte técnico del cliente para obtener más instrucciones y mitigación.



## <a name="see-also"></a>Consulte también

- [Investigar problemas de estado del agente](health-status.md)
