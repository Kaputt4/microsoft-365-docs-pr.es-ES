---
title: Solucionar problemas de rendimiento
description: Solucionar problemas de uso elevado de CPU relacionados con el servicio de protección en tiempo real en Microsoft Defender para endpoint.
keywords: 'troubleshoot, performance, high CPU utilization, high CPU usage, error, fix, update compliance, oms, monitor, report, Antivirus de Microsoft Defender'
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
ms.date: 10/19/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.collection: m365-security-compliance
---

# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a>Solucionar problemas de rendimiento relacionados con la protección en tiempo real


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Si el sistema tiene problemas de alto uso de CPU o rendimiento relacionados con el servicio de protección en tiempo real en Microsoft Defender para endpoint, puede enviar un vale al soporte técnico de Microsoft. Siga los pasos descritos en [Recopilar Antivirus de Microsoft Defender de diagnóstico](collect-diagnostic-data.md).

Como administrador, también puede solucionar estos problemas por su cuenta.

En primer lugar, es posible que desee comprobar si el problema está causado por otro software. Lea [Comprobar con el proveedor las exclusiones de antivirus](#check-with-vendor-for-antivirus-exclusions).

De lo contrario, puede identificar qué software está relacionado con el problema de rendimiento identificado siguiendo los pasos descritos [en Analizar el registro de Microsoft Protection](#analyze-the-microsoft-protection-log).

También puede proporcionar registros adicionales al envío a soporte técnico de Microsoft siguiendo los pasos descritos en:

- [Capturar registros de proceso con el Monitor de procesos](#capture-process-logs-using-process-monitor)
- [Capturar registros de rendimiento con Windows grabadora de rendimiento](#capture-performance-logs-using-windows-performance-recorder)

## <a name="check-with-vendor-for-antivirus-exclusions"></a>Comprobar con el proveedor si hay exclusiones de antivirus

Si puede identificar fácilmente el software que afecta al rendimiento del sistema, vaya al centro de soporte o la base de conocimientos del proveedor de software. Busque si tiene recomendaciones sobre las exclusiones antivirus. Si el sitio web del proveedor no los tiene, puede abrir un vale de soporte técnico con ellos y pedirles que publiquen uno.

Se recomienda que los proveedores de software sigan las distintas directrices de [Asociación con el sector para minimizar falsos positivos](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/). El proveedor puede enviar su software a través [Inteligencia de seguridad de Microsoft portal](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper).

## <a name="analyze-the-microsoft-protection-log"></a>Analizar el registro de Microsoft Protection

En **MPLog-xxxxxxxx-xxxxxx.log**, puede encontrar la información de impacto en el rendimiento estimado de la ejecución de software como *EstimatedImpact*:

`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

<br>

****

|Nombre del campo|Descripción|
|---|---|
|ProcessImageName|Nombre de imagen de proceso|
|TotalTime|Duración acumulativa en milisegundos invertidos en exámenes de archivos a los que se accede mediante este proceso|
|Count|Número de archivos escaneados a los que accede este proceso|
|MaxTime|Duración en milisegundos en el examen único más largo de un archivo al que tiene acceso este proceso|
|MaxTimeFile|Ruta de acceso del archivo al que ha accedido este proceso para el que se registró el examen más `MaxTime` largo de duración|
|EstimatedImpact|El porcentaje de tiempo invertido en exámenes para los archivos a los que tiene acceso este proceso fuera del período en el que este proceso experimentó actividad de examen|
|

Si el impacto en el rendimiento es alto, intente agregar el proceso a las exclusiones de ruta de acceso o proceso siguiendo los pasos descritos en Configurar y validar [exclusiones](collect-diagnostic-data.md) para Antivirus de Microsoft Defender exámenes.

Si el paso anterior no resuelve el problema, puede recopilar más información a través del [Monitor](#capture-process-logs-using-process-monitor) de procesos o la grabadora de rendimiento [Windows](#capture-performance-logs-using-windows-performance-recorder) en las secciones siguientes.

## <a name="capture-process-logs-using-process-monitor"></a>Capturar registros de proceso con el Monitor de procesos

Process Monitor (ProcMon) es una herramienta de supervisión avanzada que puede mostrar procesos en tiempo real. Puede usar esto para capturar el problema de rendimiento tal como se está produciendo.

1. Descargar [Process Monitor v3.60](/sysinternals/downloads/procmon) en una carpeta como `C:\temp`.

2. Para quitar la marca del archivo de la web:
    1. Haga clic con el **botónProcessMonitor.zip** y seleccione **Propiedades**.
    1. En la *pestaña General* , busque *Seguridad*.
    1. Active la casilla situada junto **a Desbloquear**.
    1. Seleccione **Aplicar**.

    :::image type="content" source="images/procmon-motw.png" alt-text="La página Quitar MOTW" lightbox="images/procmon-motw.png":::

3. Descomprima el archivo para `C:\temp` que la ruta de acceso de carpeta sea `C:\temp\ProcessMonitor`.

4. Copie **ProcMon.exe** en el Windows cliente o Windows cliente que está solucionando problemas.

5. Antes de ejecutar ProcMon, asegúrese de que se cierren todas las demás aplicaciones que no estén relacionadas con el alto problema de uso de CPU. Al hacerlo, se minimizará el número de procesos que se van a comprobar.

6. Puede iniciar ProcMon de dos maneras.
    1. Haga clic con el **ProcMon.exe** y seleccione **Ejecutar como administrador**.

        Dado que el registro se inicia automáticamente, selecciona el icono de lupa para detener la captura actual o usa el método abreviado **de teclado Ctrl+E**.

        :::image type="content" source="images/procmon-magglass.png" alt-text="Icono de lupa" lightbox="images/procmon-magglass.png":::

        Para comprobar que ha detenido la captura, compruebe si el icono de lupa aparece ahora con una X roja.

        :::image type="content" source="images/procmon-magglass-stop.png" alt-text="Barra diagonal roja" lightbox="images/procmon-magglass-stop.png":::

        Después, para borrar la captura anterior, seleccione el icono del borrador.

        :::image type="content" source="images/procmon-eraser-clear.png" alt-text="El icono borrar" lightbox="images/procmon-eraser-clear.png":::

        O use el método abreviado de **teclado Ctrl+X**.

    2. La segunda forma es ejecutar la línea **de** comandos como administrador y, a continuación, desde la ruta de acceso del Monitor de procesos, ejecute:

       :::image type="content" source="images/cmd-procmon.png" alt-text="El cmd procmon" lightbox="images/cmd-procmon.png":::

        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```

        > [!TIP]
        > Haga que la ventana de ProcMon sea lo más pequeña posible al capturar datos para que pueda iniciar y detener fácilmente el seguimiento.
        >
        > :::image type="content" source="images/procmon-minimize.png" alt-text="La página que muestra un procmon minimizado" lightbox="images/procmon-minimize.png":::

7. Después de seguir uno de los procedimientos del paso 6, verá una opción para establecer filtros. Seleccione **Aceptar**. Siempre puede filtrar los resultados una vez completada la captura.

   :::image type="content" source="images/procmon-filter-options.png" alt-text="La página en la que se elige Excluir sistema como Nombre de proceso de filtro" lightbox="images/procmon-filter-options.png":::

8. Para iniciar la captura, vuelva a seleccionar el icono de lupa.

9. Reproduce el problema.

    > [!TIP]
    > Espere a que el problema se reproduzca por completo y, a continuación, tome nota de la marca de tiempo cuando se inició el seguimiento.

10. Una vez que tenga entre dos y cuatro minutos de actividad de proceso durante la condición de uso de CPU alta, detenga la captura seleccionando el icono de lupa.

11. Para guardar la captura con un nombre único y con el formato .pml, seleccione **Archivo** y, a continuación, **seleccione Guardar...**. Asegúrese de seleccionar los botones de radio **Todos los eventos** y **Formato de monitor de proceso nativo (PML).**.

    :::image type="content" source="images/procmon-savesettings1.png" alt-text="La página guardar configuración" lightbox="images/procmon-savesettings1.png":::

12. Para un mejor seguimiento, cambie la ruta de acceso predeterminada desde `C:\temp\ProcessMonitor\LogFile.PML` donde `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` :
    - `%ComputerName%` es el nombre del dispositivo
    - `MMDDYEAR` es el mes, día y año
    - `Repro_of_issue` es el nombre del problema que está intentando reproducir

    > [!TIP]
    > Si tiene un sistema de trabajo, es posible que desee obtener un registro de ejemplo para comparar.

13. Zip the .pml file and submit it to Microsoft support.

## <a name="capture-performance-logs-using-windows-performance-recorder"></a>Capturar registros de rendimiento con Windows grabadora de rendimiento

Puede usar la grabadora Windows rendimiento (WPR) para incluir información adicional en el envío al soporte técnico de Microsoft. WPR es una herramienta de grabación eficaz que crea seguimiento de eventos para Windows grabaciones.

WPR forma parte del kit de evaluación e implementación de Windows (Windows ADK) y se puede descargar desde Descargar e instalar el [Windows ADK](/windows-hardware/get-started/adk-install). También puedes descargarlo como parte del kit de desarrollo Windows 10 software en [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).

Puede usar la interfaz de usuario de WPR siguiendo los pasos descritos en [Capturar registros de rendimiento mediante la interfaz de usuario de WPR](#capture-performance-logs-using-the-wpr-ui).

Como alternativa, también puede usar la herramienta de línea de comandos *wpr.exe*, que está disponible en Windows 8 y versiones posteriores siguiendo los pasos descritos en Capturar registros de rendimiento mediante la [CLI de WPR](#capture-performance-logs-using-the-wpr-cli).

### <a name="capture-performance-logs-using-the-wpr-ui"></a>Capturar registros de rendimiento con la interfaz de usuario de WPR

> [!TIP]
> Si varios dispositivos están experimentando este problema, usa el que tiene más RAM.

1. Descargue e instale WPR.

2. En *Windows kits*, haga clic con el botón secundario **en Windows Grabadora de rendimiento**.

   :::image type="content" source="images/wpr-01.png" alt-text="El menú Inicio" lightbox="images/wpr-01.png":::

    Seleccione **Más**. Seleccione **Ejecutar como administrador**.

3. Cuando aparezca el cuadro de diálogo Control de cuentas de usuario, seleccione **Sí**.

   :::image type="content" source="images/wpt-yes.png" alt-text="La página UAC" lightbox="images/wpt-yes.png":::

4. A continuación, descargue el perfil [de análisis de Microsoft Defender para](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) puntos de conexión y guárdelo en `MDAV.wprp` una carpeta como `C:\temp`.

5. En el cuadro de diálogo WPR, seleccione **Más opciones**.

   :::image type="content" source="images/wpr-03.png" alt-text="La página en la que puede seleccionar más opciones" lightbox="images/wpr-03.png":::


6. Seleccione **Agregar perfiles...** y vaya a la ruta de acceso del `MDAV.wprp` archivo.

7. Después de eso, debería ver un nuevo conjunto de perfiles en *Medidas personalizadas* denominada *Microsoft Defender para el análisis de puntos de conexión* debajo de él.

   :::image type="content" source="images/wpr-infile.png" alt-text="El archivo en" lightbox="images/wpr-infile.png":::

    > [!WARNING]
    > Si el servidor Windows tiene 64 GB de RAM o más, use la medida personalizada `Microsoft Defender for Endpoint analysis for large servers` en lugar de `Microsoft Defender for Endpoint analysis`. De lo contrario, el sistema podría consumir una gran cantidad de memoria de grupo no paginada o búferes que pueden provocar inestabilidad en el sistema. Puede elegir qué perfiles agregar expandiendo **Análisis de recursos**.
    Este perfil personalizado proporciona el contexto necesario para un análisis detallado del rendimiento.

8. Para usar el perfil de análisis detallado de Medida personalizada de Microsoft Defender para extremo en la interfaz de usuario de WPR:

    1. Asegúrese de que no hay perfiles seleccionados en los grupos *de análisis de recursos**, análisis* de recursos y análisis *de escenarios de* primer nivel.
    2. Seleccione **Medidas personalizadas**.
    3. Seleccione **Microsoft Defender para el análisis de puntos de conexión**.
    4. Seleccione **Detallado en** *Nivel de* detalle.
    5. Seleccione **Archivo** o **Memoria en** modo de registro.

    > [!IMPORTANT]
    > Debe seleccionar *Archivo para* usar el modo de registro de archivos si el usuario puede reproducir directamente el problema de rendimiento. La mayoría de los problemas están en esta categoría. Sin embargo, si el usuario no puede reproducir directamente el problema, pero puede observarlo fácilmente una vez que se produce el problema, el usuario debe seleccionar Memoria para usar el modo de registro de memoria. Esto garantiza que el registro de seguimiento no se infle demasiado debido al largo tiempo de ejecución.

9. Ahora ya está listo para recopilar datos. Salga de todas las aplicaciones que no son relevantes para reproducir el problema de rendimiento. Puede seleccionar Ocultar **opciones para** que el espacio ocupado por la ventana de WPR sea pequeño.

   :::image type="content" source="images/wpr-08.png" alt-text="Las opciones Ocultar" lightbox="images/wpr-08.png":::

    > [!TIP]
    > Intente iniciar el seguimiento en segundos enteros. Por ejemplo, 01:30:00. Esto facilitará el análisis de los datos. También intente realizar un seguimiento de la marca de tiempo de exactamente cuando se reproduce el problema.

10. Seleccione **Inicio**.

    :::image type="content" source="images/wpr-09.png" alt-text="Página De información del sistema de registro" lightbox="images/wpr-09.png":::

11. Reproduce el problema.

    > [!TIP]
    > Mantenga la colección de datos en no más de cinco minutos. De dos a tres minutos es un buen intervalo, ya que se recopilan muchos datos.

12. Haga clic en **Guardar**.

    :::image type="content" source="images/wpr-10.png" alt-text="La opción Guardar" lightbox="images/wpr-10.png":::

13. Rellene **Tipo en una descripción detallada del problema:** con información sobre el problema y cómo se reprodujo el problema.

    :::image type="content" source="images/wpr-12.png" alt-text="Panel en el que se rellena" lightbox="images/wpr-12.png":::

    1. Seleccione **Nombre de archivo:** para determinar dónde se guardará el archivo de seguimiento. De forma predeterminada, se guarda en `%user%\Documents\WPR Files\`.
    1. Haga clic en **Guardar**.

14. Espere mientras se combina el seguimiento.

    :::image type="content" source="images/wpr-13.png" alt-text="Seguimiento general de la recopilación de WPR" lightbox="images/wpr-13.png":::

15. Una vez guardado el seguimiento, seleccione **Abrir carpeta**.

    :::image type="content" source="images/wpr-14.png" alt-text="La página que muestra la notificación de que se ha guardado el seguimiento de WPR" lightbox="images/wpr-14.png":::

    Incluya el archivo y la carpeta en el envío al Soporte técnico de Microsoft.

    :::image type="content" source="images/wpr-15.png" alt-text="Los detalles del archivo y la carpeta" lightbox="images/wpr-15.png":::

### <a name="capture-performance-logs-using-the-wpr-cli"></a>Capturar registros de rendimiento con la CLI de WPR

La herramienta de línea *de comandoswpr.exe* forma parte del sistema operativo a partir de Windows 8. Para recopilar un seguimiento de WPR mediante la herramienta de línea de comandos wpr.exe:

1. Descargue **[el perfil de análisis de Microsoft Defender](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** para puntos de conexión para realizar seguimientos de rendimiento en un archivo denominado `MDAV.wprp` en un directorio local como `C:\traces`.

2. Haga clic con **el botón secundario** en el icono menú Inicio y **seleccione Windows PowerShell (administrador)** o símbolo del sistema **(administrador)** para abrir una ventana del símbolo del sistema de administración.

3. Cuando aparezca el cuadro de diálogo Control de cuentas de usuario, seleccione **Sí**.

4. En el símbolo del sistema con privilegios elevados, ejecute el siguiente comando para iniciar un seguimiento de rendimiento de Microsoft Defender para endpoint:

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```

    > [!WARNING]
    > Si el servidor Windows tiene 64 GB o RAM o más, use `WDForLargeServers.Light` `WDForLargeServers.Verbose` `WD.Light` perfiles y en lugar de perfiles y `WD.Verbose`, respectivamente. De lo contrario, el sistema podría consumir una gran cantidad de memoria de grupo no paginada o búferes que pueden provocar inestabilidad en el sistema.

5. Reproduce el problema.

    > [!TIP]
    > Mantenga la colección de datos no en más de cinco minutos. Según el escenario, de dos a tres minutos es un buen intervalo, ya que se recopilan muchos datos.

6. En el símbolo del sistema con privilegios elevados, ejecute el siguiente comando para detener el seguimiento de rendimiento, asegurándose de proporcionar información sobre el problema y cómo reprodujo el problema:

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

7. Espere hasta que se combine el seguimiento.

8. Incluya el archivo y la carpeta en el envío al soporte técnico de Microsoft.

## <a name="see-also"></a>Vea también

- [Recopilar Antivirus de Microsoft Defender de diagnóstico](collect-diagnostic-data.md)
- [Configurar y validar exclusiones para Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md)
