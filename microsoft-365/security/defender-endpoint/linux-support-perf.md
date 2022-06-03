---
title: Solución de problemas de rendimiento de Microsoft Defender para punto de conexión en Linux
description: Solución de problemas de rendimiento en Microsoft Defender para punto de conexión en Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, performance
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3452f36068facc92885047184f7e00828f569cbc
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65873014"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solución de problemas de rendimiento de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este documento se proporcionan instrucciones sobre cómo restringir los problemas de rendimiento relacionados con Defender para punto de conexión en Linux mediante las herramientas de diagnóstico disponibles para poder comprender y mitigar la escasez de recursos existente y los procesos que hacen que el sistema se encuentre en tales situaciones. Los problemas de rendimiento se deben principalmente a cuellos de botella en uno o varios subsistemas de hardware, en función del perfil de uso de recursos en el sistema. A veces, las aplicaciones son sensibles a los recursos de E/S de disco y pueden necesitar más capacidad de CPU, y a veces algunas configuraciones no son sostenibles y pueden desencadenar demasiados procesos nuevos y abrir demasiados descriptores de archivo.

En función de las aplicaciones que ejecute y de las características del dispositivo, puede experimentar un rendimiento poco óptimo al ejecutar Defender para punto de conexión en Linux. En concreto, las aplicaciones o los procesos del sistema que acceden a muchos recursos, como CPU, disco y memoria a través de un intervalo de tiempo corto, pueden provocar problemas de rendimiento en Defender para punto de conexión en Linux.

> [!WARNING]
> Antes de comenzar, **asegúrese de que otros productos de seguridad no se ejecutan actualmente en el dispositivo**. Varios productos de seguridad pueden entrar en conflicto e afectar al rendimiento del host.

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>Solución de problemas de rendimiento mediante estadísticas de protección en tiempo real

**Se aplica a:**
- Solo problemas de rendimiento relacionados con AV

La protección en tiempo real (RTP) es una característica de Defender para punto de conexión en Linux que supervisa y protege continuamente el dispositivo frente a amenazas. Consta de supervisión de archivos y procesos y otras heurísticas.

Los pasos siguientes se pueden usar para solucionar y mitigar estos problemas:

1. Deshabilite la protección en tiempo real mediante uno de los métodos siguientes y observe si el rendimiento mejora. Este enfoque ayuda a restringir si Defender para punto de conexión en Linux está contribuyendo a los problemas de rendimiento.

    Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar desde la línea de comandos:

    ```bash
    mdatp config real-time-protection --value disabled
    ```

    ```Output
    Configuration property updated
    ```

    Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real mediante las instrucciones de [Establecer preferencias para Defender para punto de conexión en Linux](linux-preferences.md).

    > [!NOTE]
    > Si el problema de rendimiento persiste mientras la protección en tiempo real está desactivada, el origen del problema podría ser el componente detección y respuesta de puntos de conexión (EDR). En este caso, siga los pasos de la sección **Solución de problemas de rendimiento mediante Microsoft Defender para punto de conexión Analizador de cliente** de este artículo.

2. Para buscar las aplicaciones que desencadenan la mayoría de los exámenes, puede usar estadísticas en tiempo real recopiladas por Defender para punto de conexión en Linux.

    > [!NOTE]
    > Esta característica está disponible en la versión 100.90.70 o posterior.

    Esta característica está habilitada de forma predeterminada en los `Dogfood` canales y `InsiderFast` . Si usa un canal de actualización diferente, esta característica se puede habilitar desde la línea de comandos:

    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    Esta característica requiere que se habilite la protección en tiempo real. Para comprobar el estado de la protección en tiempo real, ejecute el siguiente comando:

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    Compruebe que la `real_time_protection_enabled` entrada es `true`. De lo contrario, ejecute el siguiente comando para habilitarlo:

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
    > El uso ```--output json``` de (tenga en cuenta el guion doble) garantiza que el formato de salida esté listo para el análisis.

    La salida de este comando mostrará todos los procesos y su actividad de examen asociada.

3. En el sistema Linux, descargue el analizador de Python de ejemplo **high_cpu_parser.py** mediante el comando :

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    La salida de este comando debe ser similar a la siguiente:


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

      La salida de la anterior es una lista de los principales colaboradores de los problemas de rendimiento. La primera columna es el identificador de proceso (PID), la segunda columna es el nombre del proceso y la última columna es el número de archivos examinados, ordenados por impacto.
    Por ejemplo, la salida del comando será similar a la siguiente: 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool    1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd     407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    Para mejorar el rendimiento de Defender para punto de conexión en Linux, busque el que tenga el número más alto bajo la `Total files scanned` fila y agregue una exclusión para él. Para obtener más información, consulte [Configuración y validación de exclusiones de Defender para punto de conexión en Linux](linux-exclusions.md).

    > [!NOTE]
    > La aplicación almacena estadísticas en memoria y solo realiza un seguimiento de la actividad del archivo desde que se inició y se ha habilitado la protección en tiempo real. Los procesos que se iniciaron antes o durante períodos en los que la protección en tiempo real estaba desactivada no se cuentan. Además, solo se cuentan los eventos que desencadenaron exámenes.

5. Configure Microsoft Defender para punto de conexión en Linux con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelvan a habilitar la protección en tiempo real.

    Para más información, consulte [Configurar y validar exclusiones de Microsoft Defender para punto de conexión en Linux](linux-exclusions.md).

## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Solución de problemas de rendimiento mediante Microsoft Defender para punto de conexión Analizador de cliente

**Se aplica a:**
- Problemas de rendimiento de todos los componentes disponibles de Defender para punto de conexión, como AV y EDR  

El analizador de cliente de Microsoft Defender para punto de conexión (MDECA) puede recopilar seguimientos, registros e información de diagnóstico para solucionar problemas de rendimiento en [dispositivos incorporados](/microsoft-365/security/defender-endpoint/onboard-configure) en Linux.

> [!NOTE]
> Los servicios de soporte al cliente (CSS) de Microsoft usan periódicamente la herramienta Microsoft Defender para punto de conexión Client Analyzer para recopilar información como direcciones IP, nombres de PC que le ayudarán a solucionar problemas que pueda estar experimentando. Microsoft Defender para punto de conexión. Para obtener más información sobre nuestra declaración de privacidad, consulte [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

### <a name="requirements"></a>Requisitos

- El analizador de cliente se puede ejecutar en distribuciones admitidas de [Linux](microsoft-defender-endpoint-linux.md#system-requirements) antes o después de la incorporación a Microsoft Defender para punto de conexión.
- Descargue el analizador de cliente para Linux desde la última edición en versión preliminar disponible para su descarga aquí: <https://aka.ms/XMDEClientAnalyzer>
- Si el dispositivo está detrás de un proxy, simplemente puede pasar el servidor proxy como variable de entorno al script mde_support_tool.sh. Por ejemplo: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

### <a name="run-the-client-analyzer-on-linux"></a>Ejecución del analizador de cliente en Linux

Abra un terminal o SSH en la máquina correspondiente y ejecute los siguientes comandos:

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`
2. `unzip -q XMDEClientAnalyzer.zip`
3. `cd XMDEClientAnalyzer`
4. `chmod +x mde_support_tool.sh`
5. Ejecute como uso no raíz para instalar los componentes pip y lxml necesarios: `./mde_support_tool.sh`
6. Para recopilar el paquete de diagnóstico real y generar el archivo de archivo de resultados, vuelva a ejecutarse como raíz: `./mde_support_tool.sh -d` Ejemplo:

   ![Imagen del ejemplo de línea de comandos.](images/4ca188f6c457e335abe3c9ad3eddda26.png)

> [!NOTE]
> - El analizador requiere "lxml" para generar la salida del resultado. Si no está instalado, el analizador intentará capturarlo del repositorio oficial para los paquetes de Python siguientes: <https://pypi.org/search/?q=lxml>
> 
> - Además, la herramienta requiere actualmente la versión 3 o posterior de Python para instalarse.
>
> - Si se ejecuta en un equipo que no puede usar Python 3 ni capturar el componente lxml, puede descargar una versión basada en binarios del analizador que no tenga ninguno de los requisitos: [Binario del analizador de cliente XMDE](https://aka.ms/XMDEClientAnalyzerBinary)

### <a name="additional-syntax-help"></a>Ayuda de sintaxis adicional:

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

### <a name="result-package-contents"></a>Contenido del paquete de resultados

- report.html

  Descripción: el archivo de salida HTML principal que contendrá los resultados y las instrucciones que puede generar el script del analizador que se ejecuta en la máquina.

- mde_diagnostic.zip

  Descripción: la misma salida de diagnóstico que se genera al ejecutar *mdatp diagnostic create* en [Linux](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

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

> [!NOTE]
> En caso de que después de seguir los pasos anteriores, el problema de rendimiento persiste, póngase en contacto con el soporte técnico para obtener más instrucciones y mitigación.



## <a name="see-also"></a>Vea también

- [Investigar problemas de estado del agente](health-status.md)
