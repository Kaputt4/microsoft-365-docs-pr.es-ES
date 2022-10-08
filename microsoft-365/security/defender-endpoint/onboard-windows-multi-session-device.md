---
title: Incorporación de dispositivos Windows en Azure Virtual Desktop
description: Información sobre la incorporación de dispositivos Windows a Defender para punto de conexión en Azure Virtual Desktop
keywords: Azure Virtual Desktop, AVD, Microsoft Defender, punto de conexión, incorporación
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection:
- m365-security
- tier3
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: a4af85a358d51b039d9a8596bd911eaf12f3d54f
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231624"
---
# <a name="onboard-windows-devices-in-azure-virtual-desktop"></a>Incorporación de dispositivos Windows en Azure Virtual Desktop

6 minutos para leer

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Sesión múltiple de Windows que se ejecuta en Azure Virtual Desktop (AVD)
- [Windows 10 Enterprise multisesión](/microsoft-365/security/defender-endpoint/azure-server-integration)

Microsoft Defender para punto de conexión admite la supervisión de sesiones de VDI y Azure Virtual Desktop. En función de las necesidades de su organización, es posible que tenga que implementar sesiones de VDI o Azure Virtual Desktop para ayudar a los empleados a acceder a datos corporativos y aplicaciones desde un dispositivo no administrado, una ubicación remota o un escenario similar. Con Microsoft Defender para punto de conexión, puede supervisar estas máquinas virtuales para detectar actividad anómala.

## <a name="before-you-begin"></a>Antes de empezar

Familiarícese con las [consideraciones de VDI no persistente](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1). Aunque [Azure Virtual Desktop](/azure/virtual-desktop/overview) no proporciona opciones de no persistencia, proporciona formas de usar una imagen dorada de Windows que se puede usar para aprovisionar nuevos hosts y volver a implementar máquinas. Esto aumenta la volatilidad en el entorno y, por tanto, afecta a las entradas que se crean y mantienen en el portal de Microsoft Defender para punto de conexión, lo que potencialmente reduce la visibilidad de los analistas de seguridad.

> [!NOTE]
> En función del método de incorporación que elija, los dispositivos pueden aparecer en Microsoft Defender para punto de conexión portal como:
>
> - Entrada única para cada escritorio virtual
> - Varias entradas para cada escritorio virtual

Microsoft recomienda incorporar Azure Virtual Desktop como una sola entrada por escritorio virtual. Esto garantiza que la experiencia de investigación en el portal de Microsoft Defender para punto de conexión se encuentra en el contexto de un dispositivo en función del nombre del equipo. Las organizaciones que eliminan y vuelven a implementar hosts AVD con frecuencia deben considerar el uso de este método, ya que impide que se creen varios objetos para la misma máquina en el portal de Microsoft Defender para punto de conexión. Esto puede provocar confusión al investigar incidentes. Para entornos de prueba o no volátiles, puede optar por elegir de forma diferente.

Microsoft recomienda agregar el script de incorporación de Microsoft Defender para punto de conexión a la imagen dorada de AVD. De este modo, puede estar seguro de que este script de incorporación se ejecuta inmediatamente en el primer arranque. Se ejecuta como un script de inicio en el primer arranque en todas las máquinas AVD aprovisionadas desde la imagen dorada de AVD. Sin embargo, si usa una de las imágenes de la galería sin modificaciones, coloque el script en una ubicación compartida y llámalo desde la directiva de grupo local o de dominio.

> [!NOTE]
> La ubicación y configuración del script de inicio de incorporación de VDI en la imagen dorada de AVD lo configura como un script de inicio que se ejecuta cuando se inicia el AVD. No **se recomienda** incorporar la imagen dorada real de AVD. Otra consideración es el método usado para ejecutar el script. Debe ejecutarse lo antes posible en el proceso de inicio o aprovisionamiento para reducir el tiempo entre la máquina que está disponible para recibir sesiones y la incorporación del dispositivo al servicio. Los siguientes escenarios 1 y 2 tienen esto en cuenta.

### <a name="scenarios"></a>Escenarios

Hay varias maneras de incorporar una máquina host avd:

- Ejecute el script en la imagen dorada (o desde una ubicación compartida) durante el inicio.
- Use una herramienta de administración para ejecutar el script.
- Mediante [la integración con Microsoft Defender for Cloud](azure-server-integration.md)

#### <a name="scenario-1-using-local-group-policy"></a>*Escenario 1: Uso de la directiva de grupo local*

Este escenario requiere colocar el script en una imagen dorada y usa la directiva de grupo local para ejecutarse al principio del proceso de arranque.

Use las instrucciones de [Incorporación de dispositivos de infraestructura de escritorio virtual (VDI) no persistentes](configure-endpoints-vdi.md).

Siga las instrucciones de una sola entrada para cada dispositivo.

#### <a name="scenario-2-using-domain-group-policy"></a>*Escenario 2: Uso de la directiva de grupo de dominio*

En este escenario se usa un script de ubicación central y se ejecuta mediante una directiva de grupo basada en dominio. También puede colocar el script en la imagen dorada y ejecutarlo de la misma manera.

##### <a name="download-the-windowsdefenderatponboardingpackagezip-file-from-the-microsoft-365-defender-portal"></a>Descargue el archivo WindowsDefenderATPOnboardingPackage.zip desde el portal de Microsoft 365 Defender.

1. Abra el archivo de .zip del paquete de configuración de VDI (WindowsDefenderATPOnboardingPackage.zip)

    1. En el panel de navegación del portal de Microsoft 365 Defender, seleccione **Configuración** \> **Puntos de conexión** \> **Incorporación** (en **Administración de dispositivos**).
    1. Seleccione Windows 10 o Windows 11 como sistema operativo.
    1. En el campo **Método de implementación** , seleccione Scripts de incorporación de VDI para puntos de conexión no persistentes.
    1. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener una carpeta denominada **OptionalParamsPolicy** y los archivos **WindowsDefenderATPOnboardingScript.cmd** y **Onboard-NonPersistentMachine.ps1**.

##### <a name="use-group-policy-management-console-to-run-the-script-when-the-virtual-machine-starts"></a>Use directiva de grupo consola de administración para ejecutar el script cuando se inicie la máquina virtual.

1. Abra la consola de administración de directiva de grupo (GPMC), haga clic con el botón derecho en el objeto directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

2. En el Editor de administración de directiva de grupo, vaya a Configuración **del equipo** \> **Preferencias** \> **Configuración del panel de control**.

3. Haga clic con el botón derecho en **Tareas programadas**, haga clic en **Nuevoy**, a continuación, haga clic en **Tarea inmediata** (al menos Windows 7).

4. En la ventana Tarea que se abre, vaya a la pestaña **General** . En **Opciones de seguridad** , haga clic en **Cambiar usuario o grupo** y escriba SYSTEM. Haga clic en **Comprobar nombres** y, a continuación, haga clic en Aceptar. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario como se ejecutará la tarea.

5. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con los privilegios más altos** .

6. Vaya a la pestaña **Acciones** y haga clic en **Nuevo**. Asegúrese de que **Iniciar un programa** está seleccionado en el campo Acción. Especifique lo siguiente:

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   A continuación, seleccione **Aceptar** y cierre las ventanas de GPMC abiertas.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Escenario 3: Incorporación mediante herramientas de administración*

Si planea administrar las máquinas mediante una herramienta de administración, puede incorporar dispositivos con Microsoft Endpoint Configuration Manager.

Para obtener más información, consulte [Incorporación de dispositivos Windows mediante Configuration Manager](configure-endpoints-sccm.md).

> [!WARNING]
> Si tiene previsto usar la [referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md), tenga en cuenta que no se debe usar la regla "[Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands)", ya que esa regla no es compatible con la administración a través de Microsoft Endpoint Configuration Manager. La regla bloquea los comandos WMI que el cliente Configuration Manager usa para funcionar correctamente.

> [!TIP]
> Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que el dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Etiquetado de las máquinas al compilar la imagen dorada

Como parte de la incorporación, es posible que quiera considerar la posibilidad de establecer una etiqueta de máquina para diferenciar las máquinas AVD más fácilmente en Microsoft Security Center. Para obtener más información, vea [Agregar etiquetas de dispositivo estableciendo un valor de clave del Registro](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).

#### <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

Al compilar la imagen dorada, es posible que también quiera configurar los valores de protección iniciales. Para obtener más información, consulte [Otras opciones de configuración recomendadas](configure-endpoints-gp.md#other-recommended-configuration-settings).

Además, si usa perfiles de usuario de FSlogix, se recomienda excluir los siguientes archivos de la protección always-on:

**Excluir archivos:**

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**Excluir procesos:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>Requisitos de licencias

Nota sobre las licencias: Al usar windows Enterprise multisesión, en función de sus requisitos, puede optar por tener a todos los usuarios con licencia a través de Microsoft Defender para punto de conexión (por usuario), Windows Enterprise E5, Microsoft 365 Security o Microsoft 365 E5, o bien tener la máquina virtual con licencia a través de Microsoft Defender para la nube.
Los requisitos de licencia para Microsoft Defender para punto de conexión se pueden encontrar en: [Requisitos de licencia](minimum-requirements.md#licensing-requirements).

### <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

Solo Se admite Microsoft Edge para el filtrado web en Windows 10 sesión múltiple.

#### <a name="related-links"></a>Vínculos relacionados

[Adición de exclusiones para Defender para punto de conexión a través de PowerShell](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-microsoft-defender-by-using-powershell)
