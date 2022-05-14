---
title: Solucionar problemas de rendimiento
description: Solución de problemas de uso elevado de CPU relacionados con el servicio de protección en tiempo real en Microsoft Defender para punto de conexión.
keywords: solución de problemas, rendimiento, uso elevado de CPU, uso elevado de CPU, error, corrección, cumplimiento de actualizaciones, oms, supervisión, informe, Antivirus de Microsoft Defender
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
ms.openlocfilehash: 01db84f3ddd4eae79cae2fa97400f4d3d78ba8da
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419756"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a>Solucionar problemas de rendimiento relacionados con la protección en tiempo real


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Si el sistema tiene problemas elevados de uso de CPU o rendimiento relacionados con el servicio de protección en tiempo real en Microsoft Defender para punto de conexión, puede enviar una incidencia al soporte técnico de Microsoft. Siga los pasos [descritos en Recopilación de Antivirus de Microsoft Defender datos de diagnóstico](collect-diagnostic-data.md).

Como administrador, también puede solucionar estos problemas por su cuenta.

En primer lugar, es posible que quiera comprobar si otro software está causando el problema. Lea [Comprobar con el proveedor si hay exclusiones de antivirus](#check-with-vendor-for-antivirus-exclusions).

De lo contrario, puede identificar qué software está relacionado con el problema de rendimiento identificado siguiendo los pasos descritos en [Analizar el registro de protección de Microsoft](#analyze-the-microsoft-protection-log).

También puede proporcionar registros adicionales al envío al soporte técnico de Microsoft siguiendo los pasos descritos en:

- [Captura de registros de procesos mediante el Monitor de procesos](#capture-process-logs-using-process-monitor)
- [Captura de registros de rendimiento mediante Windows Grabadora de rendimiento](#capture-performance-logs-using-windows-performance-recorder)

## <a name="check-with-vendor-for-antivirus-exclusions"></a>Comprobación con el proveedor de exclusiones de antivirus

Si puede identificar fácilmente el software que afecta al rendimiento del sistema, vaya al centro de soporte técnico o knowledge base del proveedor de software. Busque si tiene recomendaciones sobre exclusiones antivirus. Si el sitio web del proveedor no los tiene, puede abrir una incidencia de soporte técnico con ellos y pedirle que publique una.

Se recomienda que los proveedores de software sigan las distintas directrices de [Asociación con el sector para minimizar los falsos positivos](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/). El proveedor puede enviar su software a través del [portal de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper).

## <a name="analyze-the-microsoft-protection-log"></a>Análisis del registro de Microsoft Protection

En **MPLog-xxxxxxxx-xxxxxx.log**, puede encontrar la información de impacto estimado del rendimiento de la ejecución de software como *EstimatedImpact*:

`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

<br>

****

|Nombre del campo|Descripción|
|---|---|
|ProcessImageName|Nombre de la imagen de proceso|
|TotalTime|La duración acumulativa en milisegundos que se dedica a los exámenes de los archivos a los que accede este proceso|
|Count|Número de archivos digitalizados a los que accede este proceso|
|MaxTime|Duración en milisegundos en el examen único más largo de un archivo al que accede este proceso|
|MaxTimeFile|Ruta de acceso del archivo al que accede este proceso para el que se registró el examen más largo de `MaxTime` la duración|
|EstimatedImpact|El porcentaje de tiempo dedicado a los exámenes para los archivos a los que accede este proceso fuera del período en el que este proceso experimentó la actividad de examen|
|

Si el impacto en el rendimiento es alto, intente agregar el proceso a las exclusiones de ruta de acceso o proceso siguiendo los pasos [descritos en Configuración y validación de exclusiones para exámenes de Antivirus de Microsoft Defender](collect-diagnostic-data.md).

Si el paso anterior no resuelve el problema, puede recopilar más información a través del Monitor de [procesos](#capture-process-logs-using-process-monitor) o la [grabadora de rendimiento de Windows](#capture-performance-logs-using-windows-performance-recorder) en las secciones siguientes.

## <a name="capture-process-logs-using-process-monitor"></a>Captura de registros de procesos mediante el Monitor de procesos

Monitor de procesos (ProcMon) es una herramienta de supervisión avanzada que puede mostrar procesos en tiempo real. Puede usarlo para capturar el problema de rendimiento a medida que se está produciendo.

1. Descargue [Process Monitor v3.60](/sysinternals/downloads/procmon) en una carpeta como `C:\temp`.

2. Para quitar la marca del archivo de la web:
    1. Haga clic con el botón derecho en **ProcessMonitor.zip** y seleccione **Propiedades**.
    1. En la pestaña *General* , busque *Seguridad*.
    1. Active la casilla situada junto a **Desbloquear**.
    1. Seleccione **Aplicar**.

    :::image type="content" source="images/procmon-motw.png" alt-text="La página Quitar MOTW" lightbox="images/procmon-motw.png":::

3. Descomprima el archivo en `C:\temp` para que la ruta de acceso de la carpeta sea `C:\temp\ProcessMonitor`.

4. Copie **ProcMon.exe** en el cliente de Windows o Windows servidor que está solucionando problemas.

5. Antes de ejecutar ProcMon, asegúrese de que todas las demás aplicaciones no relacionadas con el problema de uso elevado de cpu estén cerradas. Al hacerlo, se minimizará el número de procesos que se van a comprobar.

6. Puede iniciar ProcMon de dos maneras.
    1. Haga clic con el botón derecho en **ProcMon.exe** y seleccione **Ejecutar como administrador**.

        Puesto que el registro se inicia automáticamente, seleccione el icono de lupa para detener la captura actual o use el método abreviado **de teclado Ctrl+E**.

        :::image type="content" source="images/procmon-magglass.png" alt-text="Icono de lupa" lightbox="images/procmon-magglass.png":::

        Para comprobar que ha detenido la captura, compruebe si el icono de lupa aparece ahora con una X roja.

        :::image type="content" source="images/procmon-magglass-stop.png" alt-text="Barra diagonal roja" lightbox="images/procmon-magglass-stop.png":::

        A continuación, para borrar la captura anterior, seleccione el icono de borrador.

        :::image type="content" source="images/procmon-eraser-clear.png" alt-text="Icono de borrar" lightbox="images/procmon-eraser-clear.png":::

        También puede usar el método abreviado de teclado **Ctrl+X**.

    2. La segunda manera es ejecutar la **línea de comandos** como administrador y, a continuación, desde la ruta de acceso del Monitor de procesos, ejecute:

       :::image type="content" source="images/cmd-procmon.png" alt-text="El procmon de cmd" lightbox="images/cmd-procmon.png":::

        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```

        > [!TIP]
        > Haga que la ventana ProcMon sea lo más pequeña posible al capturar datos para que pueda iniciar y detener fácilmente el seguimiento.
        >
        > :::image type="content" source="images/procmon-minimize.png" alt-text="Página en la que se muestra un procmon minimizado" lightbox="images/procmon-minimize.png":::

7. Después de seguir uno de los procedimientos del paso 6, verá una opción para establecer filtros. Seleccione **Aceptar**. Siempre puede filtrar los resultados una vez completada la captura.

   :::image type="content" source="images/procmon-filter-options.png" alt-text="Página en la que se elige Excluir sistema como nombre de proceso de filtrado" lightbox="images/procmon-filter-options.png":::

8. Para iniciar la captura, vuelva a seleccionar el icono de lupa.

9. Reproduzca el problema.

    > [!TIP]
    > Espere a que el problema se reproduzca por completo y, a continuación, tome nota de la marca de tiempo cuando se inició el seguimiento.

10. Una vez que tenga entre dos y cuatro minutos de actividad de proceso durante la condición de uso elevado de la CPU, detenga la captura seleccionando el icono de lupa.

11. Para guardar la captura con un nombre único y con el formato .pml, seleccione **Archivo** y, a continuación, seleccione **Guardar...**. Asegúrese de seleccionar los botones de radio **Todos los eventos** y **Formato de monitor de proceso nativo (PML).**

    :::image type="content" source="images/procmon-savesettings1.png" alt-text="Página guardar configuración" lightbox="images/procmon-savesettings1.png":::

12. Para un mejor seguimiento, cambie la ruta de acceso predeterminada de `C:\temp\ProcessMonitor\LogFile.PML` a `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` dónde:
    - `%ComputerName%` es el nombre del dispositivo
    - `MMDDYEAR` es el mes, el día y el año
    - `Repro_of_issue` es el nombre del problema que intenta reproducir

    > [!TIP]
    > Si tiene un sistema de trabajo, es posible que desee obtener un registro de ejemplo para compararlo.

13. Comprima el archivo .pml y envíelo al soporte técnico de Microsoft.

## <a name="capture-performance-logs-using-windows-performance-recorder"></a>Captura de registros de rendimiento mediante Windows Grabadora de rendimiento

Puede usar Windows Grabadora de rendimiento (WPR) para incluir información adicional en el envío al soporte técnico de Microsoft. WPR es una potente herramienta de grabación que crea seguimiento de eventos para grabaciones Windows.

WPR forma parte del kit de evaluación e implementación de Windows (Windows ADK) y se puede descargar desde [Descargar e instalar el Windows ADK](/windows-hardware/get-started/adk-install). También puede descargarlo como parte del kit de desarrollo de software de Windows 10 en [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).

Puede usar la interfaz de usuario de WPR siguiendo los pasos descritos en [Capturar registros de rendimiento mediante la interfaz de usuario de WPR](#capture-performance-logs-using-the-wpr-ui).

Como alternativa, también puede usar la herramienta de línea de comandos *wpr.exe*, que está disponible en Windows 8 y versiones posteriores siguiendo los pasos descritos en [Captura de registros de rendimiento mediante la CLI de WPR](#capture-performance-logs-using-the-wpr-cli).

### <a name="capture-performance-logs-using-the-wpr-ui"></a>Captura de registros de rendimiento mediante la interfaz de usuario de WPR

> [!TIP]
> Si varios dispositivos experimentan este problema, use el que tenga más RAM.

1. Descargue e instale WPR.

2. En *Windows Kits*, haga clic con el botón derecho en **Windows Grabador de rendimiento**.

   :::image type="content" source="images/wpr-01.png" alt-text="El menú Inicio" lightbox="images/wpr-01.png":::

    Seleccione **Más**. Seleccione **Ejecutar como administrador**.

3. Cuando aparezca el cuadro de diálogo Control de cuentas de usuario, seleccione **Sí**.

   :::image type="content" source="images/wpt-yes.png" alt-text="Página de UAC" lightbox="images/wpt-yes.png":::

4. A continuación, descargue el perfil [de análisis Microsoft Defender para punto de conexión](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) y guárdelo en `MDAV.wprp` una carpeta como `C:\temp`.

5. En el cuadro de diálogo WPR, seleccione **Más opciones**.

   :::image type="content" source="images/wpr-03.png" alt-text="Página en la que puede seleccionar más opciones" lightbox="images/wpr-03.png":::


6. Seleccione **Agregar perfiles...** y vaya a la ruta de acceso del `MDAV.wprp` archivo.

7. Después, debería ver un nuevo perfil establecido en *Medidas personalizadas denominadas* *Microsoft Defender para punto de conexión análisis* debajo de él.

   :::image type="content" source="images/wpr-infile.png" alt-text="El archivo en" lightbox="images/wpr-infile.png":::

    > [!WARNING]
    > Si el Windows Server tiene 64 GB de RAM o más, use la medida `Microsoft Defender for Endpoint analysis for large servers` personalizada en lugar de `Microsoft Defender for Endpoint analysis`. De lo contrario, el sistema podría consumir una gran cantidad de memoria de grupo no paginado o búferes, lo que puede provocar inestabilidad en el sistema. Puede elegir qué perfiles agregar expandiendo **Análisis de recursos**.
    Este perfil personalizado proporciona el contexto necesario para un análisis detallado del rendimiento.

8. Para usar la medición personalizada Microsoft Defender para punto de conexión perfil de análisis detallado en la interfaz de usuario de WPR:

    1. Asegúrese de que no hay perfiles seleccionados en los grupos De *evaluación de prioridades de primer nivel*, *Análisis de recursos* y *Análisis de escenarios* .
    2. Seleccione **Medidas personalizadas**.
    3. Seleccione **Microsoft Defender para punto de conexión análisis**.
    4. Seleccione **Detallado** en *Nivel de detalle* .
    5. Seleccione **Archivo** o **memoria** en Modo de registro.

    > [!IMPORTANT]
    > Debe seleccionar *Archivo* para usar el modo de registro de archivos si el usuario puede reproducir directamente el problema de rendimiento. La mayoría de los problemas se encuentran en esta categoría. Sin embargo, si el usuario no puede reproducir directamente el problema, pero puede observarlo fácilmente una vez que se produce el problema, el usuario debe seleccionar *Memoria* para usar el modo de registro de memoria. Esto garantiza que el registro de seguimiento no se inflará excesivamente debido al tiempo de ejecución prolongado.

9. Ahora está listo para recopilar datos. Salga de todas las aplicaciones que no son pertinentes para reproducir el problema de rendimiento. Puede seleccionar **Ocultar opciones** para mantener pequeño el espacio ocupado por la ventana wpr.

   :::image type="content" source="images/wpr-08.png" alt-text="Las opciones Ocultar" lightbox="images/wpr-08.png":::

    > [!TIP]
    > Intente iniciar el seguimiento en un número entero de segundos. Por ejemplo, 01:30:00. Esto facilitará el análisis de los datos. También intente realizar un seguimiento de la marca de tiempo de exactamente cuando se reproduce el problema.

10. Seleccione **Inicio**.

    :::image type="content" source="images/wpr-09.png" alt-text="Página Información del sistema de registros" lightbox="images/wpr-09.png":::

11. Reproduzca el problema.

    > [!TIP]
    > Mantenga la recopilación de datos en no más de cinco minutos. De dos a tres minutos es un buen intervalo, ya que se recopilan muchos datos.

12. Seleccione **Guardar**.

    :::image type="content" source="images/wpr-10.png" alt-text="La opción Guardar" lightbox="images/wpr-10.png":::

13. Rellene **Tipo en una descripción detallada del problema:** con información sobre el problema y cómo ha reproducido el problema.

    :::image type="content" source="images/wpr-12.png" alt-text="Panel en el que se rellena" lightbox="images/wpr-12.png":::

    1. Seleccione **Nombre de archivo:** para determinar dónde se guardará el archivo de seguimiento. De forma predeterminada, se guarda en `%user%\Documents\WPR Files\`.
    1. Seleccione **Guardar**.

14. Espere mientras se combina el seguimiento.

    :::image type="content" source="images/wpr-13.png" alt-text="El seguimiento general de recopilación de WPR" lightbox="images/wpr-13.png":::

15. Una vez guardado el seguimiento, seleccione **Abrir carpeta**.

    :::image type="content" source="images/wpr-14.png" alt-text="Página que muestra la notificación de que se ha guardado el seguimiento de WPR" lightbox="images/wpr-14.png":::

    Incluya el archivo y la carpeta en el envío a Soporte técnico de Microsoft.

    :::image type="content" source="images/wpr-15.png" alt-text="Detalles del archivo y la carpeta" lightbox="images/wpr-15.png":::

### <a name="capture-performance-logs-using-the-wpr-cli"></a>Captura de registros de rendimiento mediante la CLI de WPR

La herramienta de línea de comandos *wpr.exe* forma parte del sistema operativo a partir de Windows 8. Para recopilar un seguimiento de WPR mediante la herramienta de línea de comandos wpr.exe:

1. Descargue **[Microsoft Defender para punto de conexión](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** perfil de análisis para los seguimientos de rendimiento en un archivo denominado `MDAV.wprp` en un directorio local como `C:\traces`.

2. Haga clic con el botón derecho en el icono **menú Inicio** y seleccione **Windows PowerShell (administrador)** o **símbolo del sistema (administrador)** para abrir una ventana del símbolo del sistema del administrador.

3. Cuando aparezca el cuadro de diálogo Control de cuentas de usuario, seleccione **Sí**.

4. En el símbolo del sistema con privilegios elevados, ejecute el siguiente comando para iniciar un seguimiento de rendimiento Microsoft Defender para punto de conexión:

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```

    > [!WARNING]
    > Si Windows Server tiene 64 GB o RAM o más, use perfiles `WDForLargeServers.Light` y `WDForLargeServers.Verbose` en lugar de perfiles `WD.Light` y `WD.Verbose`, respectivamente. De lo contrario, el sistema podría consumir una gran cantidad de memoria de grupo no paginado o búferes, lo que puede provocar inestabilidad en el sistema.

5. Reproduzca el problema.

    > [!TIP]
    > Mantenga la recopilación de datos no hasta más de cinco minutos. En función del escenario, dos o tres minutos son un buen intervalo, ya que se recopilan muchos datos.

6. En el símbolo del sistema con privilegios elevados, ejecute el siguiente comando para detener el seguimiento de rendimiento, asegurándose de proporcionar información sobre el problema y cómo ha reproducido el problema:

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

7. Espere hasta que se combine el seguimiento.

8. Incluya el archivo y la carpeta en el envío al soporte técnico de Microsoft.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Recopilación de datos de diagnóstico de Antivirus de Microsoft Defender](collect-diagnostic-data.md)
- [Configuración y validación de exclusiones para exámenes de Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)
