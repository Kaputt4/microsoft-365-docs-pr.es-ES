---
title: Solucionar problemas de rendimiento
description: Solucionar problemas de uso elevado de CPU relacionados con el servicio de protección en tiempo real en Microsoft Defender para endpoint.
keywords: troubleshoot, performance, high CPU utilization, high CPU usage, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: normal
manager: dansimp
ms.date: 04/14/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1a969b6430914eb2dd667a906dc071d3cd49be8b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625334"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a>Solucionar problemas de rendimiento relacionados con la protección en tiempo real


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
 
Si el sistema tiene problemas de alto uso de CPU o rendimiento relacionados con el servicio de protección en tiempo real en Microsoft Defender para endpoint, puede enviar un vale al soporte técnico de Microsoft. Siga los pasos descritos [en Recopilar Antivirus de Microsoft Defender datos de diagnóstico](collect-diagnostic-data.md).

Como administrador, también puede solucionar estos problemas por su cuenta. 

En primer lugar, es posible que desee comprobar si el problema está causado por otro software. Lea [Comprobar con el proveedor las exclusiones de antivirus.](#check-with-vendor-for-antivirus-exclusions)

De lo contrario, puede identificar qué software está relacionado con el problema de rendimiento identificado siguiendo los pasos descritos [en Analizar el registro de Microsoft Protection](#analyze-the-microsoft-protection-log). 

También puede proporcionar registros adicionales al envío a soporte técnico de Microsoft siguiendo los pasos descritos en:
- [Capturar registros de proceso con el Monitor de procesos](#capture-process-logs-using-process-monitor)
- [Capturar registros de rendimiento con Windows grabadora de rendimiento](#capture-performance-logs-using-windows-performance-recorder) 

## <a name="check-with-vendor-for-antivirus-exclusions"></a>Comprobar con el proveedor si hay exclusiones de antivirus

Si puede identificar fácilmente el software que afecta al rendimiento del sistema, vaya al centro de soporte o la base de conocimientos del proveedor de software. Busque si tiene recomendaciones sobre las exclusiones antivirus. Si el sitio web del proveedor no los tiene, puede abrir un vale de soporte técnico con ellos y pedirles que publiquen uno. 

Se recomienda que los proveedores de software sigan las distintas directrices de Asociación con [el sector para minimizar los falsos positivos.](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/) El proveedor puede enviar su software a través del portal de inteligencia de seguridad [de Microsoft Defender (MDSI).](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)


## <a name="analyze-the-microsoft-protection-log"></a>Analizar el registro de Microsoft Protection

En **MPLog-xxxxxxxx-xxxxxx.log**, puede encontrar la información de impacto en el rendimiento estimado de la ejecución de software como *EstimatedImpact*:
    
`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

| Nombre del campo | Descripción |
|---|---|
|ProcessImageName | Nombre de imagen de proceso |
| TotalTime | Duración acumulativa en milisegundos invertidos en exámenes de archivos a los que se accede mediante este proceso |
|Count | Número de archivos escaneados a los que accede este proceso |
|MaxTime |  Duración en milisegundos en el examen único más largo de un archivo al que tiene acceso este proceso |
| MaxTimeFile | Ruta de acceso del archivo al que ha accedido este proceso para el que se registró el examen más largo `MaxTime` de duración |
| EstimatedImpact | El porcentaje de tiempo invertido en exámenes para los archivos a los que tiene acceso este proceso fuera del período en el que este proceso experimentó actividad de examen |

Si el impacto en el rendimiento es alto, intente agregar el proceso a las exclusiones de ruta de acceso o proceso siguiendo los pasos descritos en Configurar y validar [exclusiones](collect-diagnostic-data.md)para Antivirus de Microsoft Defender exámenes .

Si el paso anterior no resuelve el problema, puede recopilar más [](#capture-performance-logs-using-windows-performance-recorder) información a través del [Monitor](#capture-process-logs-using-process-monitor) de procesos o la grabadora de rendimiento Windows en las secciones siguientes.
     
## <a name="capture-process-logs-using-process-monitor"></a>Capturar registros de proceso con el Monitor de procesos

Process Monitor (ProcMon) es una herramienta de supervisión avanzada que puede mostrar procesos en tiempo real. Puede usar esto para capturar el problema de rendimiento tal como se está produciendo.

1. Descargar [Process Monitor v3.60](/sysinternals/downloads/procmon) en una carpeta como `C:\temp` .

2. Para quitar la marca del archivo de la web:
    1. Haga clic con el **botónProcessMonitor.zip** y seleccione **Propiedades**.
    1. En la *pestaña General,* busque *Seguridad*.
    1. Active la casilla situada junto **a Desbloquear**.
    1. Seleccione **Aplicar**.
    
    ![Quitar MOTW](images/procmon-motw.png) 

3. Descomprima el archivo `C:\temp` para que la ruta de acceso de carpeta sea `C:\temp\ProcessMonitor` . 

4. Copie **ProcMon.exe** en el Windows o Windows cliente que está solucionando problemas.  

5. Antes de ejecutar ProcMon, asegúrese de que se cierren todas las demás aplicaciones que no estén relacionadas con el alto problema de uso de CPU. Al hacerlo, se minimizará el número de procesos que se van a comprobar.

6. Puede iniciar ProcMon de dos maneras.
    1. Haga clic con **el botónProcMon.exe** y seleccione Ejecutar como **administrador**. 
    

        Dado que el registro se inicia automáticamente, seleccione el icono de lupa para detener la captura actual o use el método abreviado **de teclado Ctrl+E**.
 
        ![icono de lupa](images/procmon-magglass.png)

        Para comprobar que ha detenido la captura, compruebe si el icono de lupa aparece ahora con una X roja.

        ![barra diagonal roja](images/procmon-magglass-stop.png)         

        Después, para borrar la captura anterior, seleccione el icono del borrador.

        ![icono clear](images/procmon-eraser-clear.png)

        O use el método abreviado **de teclado Ctrl+X**.

    2. La segunda forma es ejecutar la línea **de** comandos como administrador y, a continuación, desde la ruta de acceso del Monitor de procesos, ejecute:

        ![cmd procmon](images/cmd-procmon.png)
 
        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```
        
        >[!TIP] 
        >Haga que la ventana de ProcMon sea lo más pequeña posible al capturar datos para que pueda iniciar y detener fácilmente el seguimiento.
        > 
        >![Minimizar Procmon](images/procmon-minimize.png)
    
7. Después de seguir uno de los procedimientos del paso 6, verá una opción para establecer filtros. Seleccione **Aceptar**. Siempre puede filtrar los resultados una vez completada la captura.
 
    ![Filter out Process Name is System Exclude](images/procmon-filter-options.png) 

8. Para iniciar la captura, vuelva a seleccionar el icono de lupa.
     
9. Reproduce el problema.
 
    >[!TIP] 
    >Espere a que el problema se reproduzca por completo y, a continuación, tome nota de la marca de tiempo cuando se inició el seguimiento.

10. Una vez que tenga entre dos y cuatro minutos de actividad de proceso durante la condición de uso de CPU alta, detenga la captura seleccionando el icono de lupa.

11. Para guardar la captura con un nombre único y  con el formato .pml, seleccione Archivo y, a continuación, **seleccione Guardar...**. Asegúrese de seleccionar los botones de radio **Todos los eventos** y Formato de monitor de proceso nativo **(PML).**

    ![guardar configuración](images/procmon-savesettings1.png)

12. Para un mejor seguimiento, cambie la ruta de acceso predeterminada `C:\temp\ProcessMonitor\LogFile.PML` desde `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` donde:
    - `%ComputerName%` es el nombre del dispositivo
    - `MMDDYEAR` es el mes, día y año
    -  `Repro_of_issue` es el nombre del problema que está intentando reproducir

    >[!TIP] 
    > Si tiene un sistema de trabajo, es posible que desee obtener un registro de ejemplo para comparar.

13. Zip the .pml file and submit it to Microsoft support.


## <a name="capture-performance-logs-using-windows-performance-recorder"></a>Capturar registros de rendimiento con Windows grabadora de rendimiento

Puede usar la grabadora Windows rendimiento (WPR) para incluir información adicional en el envío al soporte técnico de Microsoft. WPR es una herramienta de grabación eficaz que crea el seguimiento de eventos para Windows grabaciones. 

WPR forma parte del kit de evaluación e implementación de Windows (Windows ADK) y se puede descargar desde Descargar e instalar el Windows [ADK](/windows-hardware/get-started/adk-install). También puede descargarlo como parte del kit de desarrollo Windows 10 software en [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).

Puede usar la interfaz de usuario de WPR siguiendo los pasos descritos en Capturar registros de rendimiento mediante la interfaz de usuario [de WPR](#capture-performance-logs-using-the-wpr-ui). 

Como alternativa, también puede usar la herramienta de línea de comandos *wpr.exe*, que está disponible en Windows 8 y versiones posteriores siguiendo los pasos descritos en Capturar registros de rendimiento mediante la CLI de [WPR](#capture-performance-logs-using-the-wpr-cli).


### <a name="capture-performance-logs-using-the-wpr-ui"></a>Capturar registros de rendimiento con la interfaz de usuario de WPR

>[!TIP]
>Si tienes varios dispositivos donde se está produciendo el problema, usa el que tenga la mayor cantidad de RAM.

1. Descargue e instale WPR.

2. En *Windows kits,* haga clic con el botón secundario **en Windows Grabadora de rendimiento**. 

    ![Menú Inicio](images/wpr-01.png)

    Seleccione **Más**. Seleccione **Ejecutar como administrador**.

3. Cuando aparezca el cuadro de diálogo Control de cuentas de usuario, seleccione **Sí**.

    ![UAC](images/wpt-yes.png)

4. A continuación, descargue el perfil [de análisis de Microsoft Defender para](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) puntos de conexión y guárdelo en una carpeta como `MDAV.wprp` `C:\temp` . 
     
5. En el cuadro de diálogo WPR, seleccione **Más opciones**.

    ![Seleccionar más opciones](images/wpr-03.png)

6. Seleccione **Agregar perfiles...** y vaya a la ruta de acceso del `MDAV.wprp` archivo.

7. Después de eso, debería ver un nuevo conjunto de perfiles en *Medidas personalizadas* denominada *Microsoft Defender para el análisis de puntos de conexión* debajo de él.

    ![in-file](images/wpr-infile.png)

    >[!WARNING]
    >Si el servidor Windows tiene 64 GB de RAM o más, use la medida personalizada `Microsoft Defender for Endpoint analysis for large servers` en lugar de `Microsoft Defender for Endpoint analysis` . De lo contrario, el sistema podría consumir una gran cantidad de memoria de grupo no paginada o búferes que pueden provocar inestabilidad en el sistema. Puede elegir qué perfiles agregar expandiendo **Análisis de recursos**. Este perfil personalizado proporciona el contexto necesario para un análisis detallado del rendimiento.
 
8. Para usar el perfil de análisis detallado de Medida personalizada de Microsoft Defender para extremo en la interfaz de usuario de WPR:

    1. Asegúrese de que no hay perfiles seleccionados en los grupos de *triaje* de primer nivel, *Análisis* de recursos y *Análisis de* escenarios.
    2. Seleccione **Medidas personalizadas**.
    3. Seleccione **Microsoft Defender para el análisis de extremo.**
    4. Seleccione **Detallado en** Nivel *de* detalle.
    1. Seleccione **Archivo** o **Memoria en** modo de registro. 

    >[!important]
    >Debe seleccionar *Archivo para* usar el modo de registro de archivos si el usuario puede reproducir directamente el problema de rendimiento. La mayoría de los problemas están en esta categoría. Sin embargo, si el usuario no puede reproducir directamente el problema, pero  puede observarlo fácilmente una vez que se produce el problema, el usuario debe seleccionar Memoria para usar el modo de registro de memoria. Esto garantiza que el registro de seguimiento no se infle demasiado debido al largo tiempo de ejecución.

9. Ahora ya está listo para recopilar datos. Salga de todas las aplicaciones que no son relevantes para reproducir el problema de rendimiento. Puede seleccionar Ocultar **opciones para** que el espacio ocupado por la ventana de WPR sea pequeño.

    ![Opciones de hipe](images/wpr-08.png)

    >[!TIP]
    >Intente iniciar el seguimiento en segundos enteros. Por ejemplo, 01:30:00. Esto facilitará el análisis de los datos. También intente realizar un seguimiento de la marca de tiempo de exactamente cuando se reproduce el problema.

10. Seleccione **Inicio**.

    ![Seleccionar inicio del seguimiento](images/wpr-09.png)

11. Reproduce el problema.

    >[!TIP]
    >Mantenga la colección de datos en no más de cinco minutos. De dos a tres minutos es un buen intervalo, ya que se recopilan muchos datos.

12. Seleccione **Guardar**.

    ![Seleccionar guardar](images/wpr-10.png)

13. Rellene **Tipo en una descripción detallada del problema:** con información sobre el problema y cómo se reprodujo el problema.

    ![Rellenar detalles](images/wpr-12.png)

    1. Seleccione **Nombre de archivo:** para determinar dónde se guardará el archivo de seguimiento. De forma predeterminada, 1.is guardado en `%user%\Documents\WPR Files\` .
    1. Seleccione **Guardar**.

14. Espere mientras se combina el seguimiento.

    ![Seguimiento general de la recopilación de WPR](images/wpr-13.png)

15. Una vez guardado el seguimiento, seleccione **Abrir carpeta**.

    ![Seguimiento de WPR guardado](images/wpr-14.png)

    Incluya el archivo y la carpeta en el envío al soporte técnico de Microsoft.

    ![Archivo y carpeta](images/wpr-15.png)

### <a name="capture-performance-logs-using-the-wpr-cli"></a>Capturar registros de rendimiento con la CLI de WPR

La herramienta de línea *de comandoswpr.exe* forma parte del sistema operativo a partir de Windows 8. Para recopilar un seguimiento de WPR mediante la herramienta de línea de comandos wpr.exe:

1. Descargue **[el perfil de análisis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** de Microsoft Defender para puntos de conexión para realizar seguimientos de rendimiento en un archivo denominado en un directorio local como `MDAV.wprp` `C:\traces` .

3. Haga clic con el **botón** secundario en el icono menú Inicio y seleccione **Windows PowerShell (administrador)** o símbolo del sistema **(administrador)** para abrir una ventana del símbolo del sistema de administración.

4. Cuando aparezca el cuadro de diálogo Control de cuentas de usuario, seleccione **Sí**.

5. En el símbolo del sistema con privilegios elevados, ejecute el siguiente comando para iniciar un seguimiento de rendimiento de Microsoft Defender para endpoint:

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```
    
    >[!WARNING]
    >Si el servidor Windows tiene 64 GB o RAM o más, use perfiles y en lugar de perfiles `WDForLargeServers.Light` `WDForLargeServers.Verbose` y , `WD.Light` `WD.Verbose` respectivamente. De lo contrario, el sistema podría consumir una gran cantidad de memoria de grupo no paginada o búferes que pueden provocar inestabilidad en el sistema.

6. Reproduce el problema.

    >[!TIP]
    >Mantenga la colección de datos no en más de cinco minutos.  Según el escenario, de dos a tres minutos es un buen intervalo, ya que se recopilan muchos datos.

7. En el símbolo del sistema con privilegios elevados, ejecute el siguiente comando para detener el seguimiento de rendimiento, asegurándose de proporcionar información sobre el problema y cómo reprodujo el problema:

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

8. Espere hasta que se combine el seguimiento. 

9. Incluya el archivo y la carpeta en el envío al soporte técnico de Microsoft.

## <a name="see-also"></a>Consulte también

- [Recopilar Antivirus de Microsoft Defender de diagnóstico](collect-diagnostic-data.md)
- [Configurar y validar exclusiones para Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md)
