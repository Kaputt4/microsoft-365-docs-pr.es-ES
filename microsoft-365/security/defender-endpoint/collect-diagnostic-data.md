---
title: Recopilación de datos de diagnóstico de Antivirus de Microsoft Defender
description: Uso de una herramienta para recopilar datos para solucionar problemas del Antivirus de Microsoft Defender
keywords: solución de problemas, error, corrección, cumplimiento de actualizaciones, oms, monitor, informe, av de Microsoft Defender, objeto de directiva de grupo, configuración, datos de diagnóstico, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 02225524e2b0c38e652fa2567564b086e412a2e8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679479"
---
# <a name="collect-microsoft-defender-antivirus-diagnostic-data"></a>Recopilación de datos de diagnóstico del Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En este artículo se describe cómo recopilar datos de diagnóstico que pueden usar los equipos de ingeniería y soporte técnico de Microsoft para ayudar a solucionar problemas que pueda encontrar al usar el Antivirus de Microsoft Defender.

> [!NOTE]
> Como parte del proceso de investigación o respuesta, puede recopilar un paquete de investigación de un dispositivo. A continuación se muestra cómo: [Recopilar el paquete de investigación de los dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).

En al menos dos dispositivos que experimentan el mismo problema, obtenga el archivo de diagnóstico .cab siguiendo estos pasos:

1. Abra una versión de nivel de administrador del símbolo del sistema como se indica a continuación:

    a. Abra el menú **Inicio** .

    b. Escriba **cmd**. Haga clic con el botón derecho en símbolo **del sistema** y seleccione **Ejecutar como administrador**.

    c. Especifique las credenciales de administrador o apruebe el símbolo del sistema.

2. Vaya al directorio del Antivirus de Microsoft Defender. El valor predeterminado es `C:\Program Files\Windows Defender`

   > [!NOTE]
   > Si ejecuta una [versión actualizada de la plataforma antimalware de Microsoft Defender](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), ejecute `MpCmdRun` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.

3. Escriba el comando siguiente y, a continuación, presione **Entrar.**

    ```Dos
    mpcmdrun.exe -GetFiles
    ```

4. Se generará un archivo .cab que contiene varios registros de diagnóstico. La ubicación del archivo se especificará en la salida del símbolo del sistema. De forma predeterminada, la ubicación es `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.

   > [!NOTE]
   > Para redirigir el archivo cab a otra ruta de acceso o recurso compartido UNC, use el siguiente comando:
   >
   > `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`
   >
   > Para obtener más información, consulte [Redirección de datos de diagnóstico a un recurso compartido UNC](#redirect-diagnostic-data-to-a-unc-share).

5. Copie estos archivos .cab en una ubicación a la que pueda acceder el soporte técnico de Microsoft. Un ejemplo podría ser una carpeta de OneDrive protegida con contraseña que puede compartir con nosotros.

> [!NOTE]
> Si tiene un problema con el cumplimiento de actualizaciones, envíe un correo electrónico con la <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">plantilla de correo electrónico de soporte técnico de cumplimiento</a> de actualizaciones y rellene la plantilla con la siguiente información:
>
> Estoy experimentando el siguiente problema al usar el Antivirus de Microsoft Defender en Cumplimiento de actualizaciones:
>
> He proporcionado al menos 2 archivos de soporte técnico .cab en la siguiente ubicación:
>
> \<accessible share, including access details such as password\>
>
> Mi identificador de área de trabajo de OMS es:
>
> Póngase en contacto conmigo en:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>Redirigir datos de diagnóstico a un recurso compartido UNC

Para recopilar datos de diagnóstico en un repositorio central, puede especificar el parámetro SupportLogLocation.

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

Copia los datos de diagnóstico en la ruta de acceso especificada. Si no se especifica la ruta de acceso, los datos de diagnóstico se copiarán en la ubicación especificada en configuración de ubicación del registro de soporte técnico.

Cuando se usa el parámetro SupportLogLocation, se creará una estructura de carpetas como la siguiente en la ruta de acceso de destino:

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

<br>

****

|campo|Descripción|
|---|---|
|ruta de acceso|Ruta de acceso especificada en la línea de comandos o recuperada de la configuración|
|MMDD|Mes y día en que se recopilaron los datos de diagnóstico (por ejemplo, 0530)|
|Host|Nombre de host del dispositivo en el que se recopilaron los datos de diagnóstico|
|HHMM|Horas y minutos en que se recopilaron los datos de diagnóstico (por ejemplo, 1422)|
|

> [!NOTE]
> Al usar un recurso compartido de archivos, asegúrese de que la cuenta usada para recopilar el paquete de diagnóstico tiene acceso de escritura al recurso compartido.

## <a name="specify-location-where-diagnostic-data-is-created"></a>Especificar la ubicación donde se crean los datos de diagnóstico

También puede especificar dónde se creará el archivo de .cab de diagnóstico mediante un objeto directiva de grupo (GPO).

1. Abra el Editor de directiva de grupo local y busque el GPO SupportLogLocation en: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`.

2. Seleccione **Definir la ruta de acceso del directorio para copiar los archivos de registro compatibles**.

   :::image type="content" source="images/GPO1-SupportLogLocationDefender.png" alt-text="Editor de directivas de grupo local" lightbox="images/GPO1-SupportLogLocationDefender.png":::

   :::image type="content" source="images/GPO2-SupportLogLocationGPPage.png" alt-text="Definición de la ruta de acceso para la configuración de archivos de registro" lightbox="images/GPO2-SupportLogLocationGPPage.png":::

   :::image type="content" source="images/GPO1-SupportLogLocationDefender.png" alt-text="Editor de directivas de grupo local" lightbox="images/GPO1-SupportLogLocationDefender.png"::: 
        
   :::image type="content" source="images/GPO2-SupportLogLocationGPPage.png" alt-text="Ruta de acceso definida para configurar la configuración de archivos de registro" lightbox="images/GPO2-SupportLogLocationGPPage.png":::
 
3. Dentro del editor de directivas, seleccione **Habilitado**.

4. Especifique la ruta de acceso del directorio donde desea copiar los archivos de registro de soporte técnico en el campo **Opciones** .
   :::image type="content" source="images/GPO3-SupportLogLocationGPPageEnabledExample.png" alt-text="Configuración personalizada de ruta de acceso de directorio habilitada" lightbox="images/GPO3-SupportLogLocationGPPageEnabledExample.png":::
5. Seleccione **Aceptar** o **Aplicar**.

## <a name="see-also"></a>Vea también

- [Solución de problemas de informes del Antivirus de Microsoft Defender](troubleshoot-reporting.md)
