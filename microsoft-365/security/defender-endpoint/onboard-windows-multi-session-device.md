---
title: Incorporación Windows de varias sesiones en Azure Virtual Desktop
description: Lea más en este artículo sobre la incorporación Windows dispositivos de varias sesiones en Azure Virtual Desktop
keywords: Azure Virtual Desktop, WVD, microsoft defender, endpoint, onboard
ms.prod: w10
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
ms.collection: M365-security-compliance
ms.openlocfilehash: d97326987af49b9bac44b3578884c72d756d5595
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324065"
---
# <a name="onboard-windows-multi-session-devices-in-azure-virtual-desktop"></a>Incorporación Windows de varias sesiones en Azure Virtual Desktop

6 minutos para leer

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Windows varias sesiones que se ejecutan en Azure Virtual Desktop (AVD)

Microsoft Defender para endpoint admite la supervisión de sesiones de VDI y Azure Virtual Desktop. Según las necesidades de la organización, es posible que deba implementar sesiones de VDI o Azure Virtual Desktop para ayudar a los empleados a tener acceso a datos corporativos y aplicaciones desde un dispositivo no administrado, una ubicación remota o un escenario similar. Con Microsoft Defender para endpoint, puede supervisar estas máquinas virtuales en busca de actividad anómala.

## <a name="before-you-begin"></a>Antes de empezar

Familiarícese con las [consideraciones de VDI no persistente](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1). Aunque [Azure Virtual Desktop](/azure/virtual-desktop/overview) no proporciona opciones de no persistencia, sí proporciona formas de usar una imagen de Windows dorada que se puede usar para aprovisionar nuevos hosts y volver a implementar máquinas. Esto aumenta la inestabilidad en el entorno y, por lo tanto, afecta a las entradas que se crean y mantienen en el portal de Microsoft Defender para endpoints, lo que potencialmente reduce la visibilidad de los analistas de seguridad.

> [!NOTE]
> Según la elección del método de incorporación, los dispositivos pueden aparecer en el portal de Microsoft Defender para endpoints como:
>
> - Entrada única para cada escritorio virtual
> - Varias entradas para cada escritorio virtual

Microsoft recomienda incorporar Azure Virtual Desktop como una sola entrada por escritorio virtual. Esto garantiza que la experiencia de investigación en el portal de Microsoft Defender para endpoints se encuentra en el contexto de un dispositivo basado en el nombre del equipo. Las organizaciones que suelen eliminar y volver a implementar hosts WVD deben considerar encarecidamente el uso de este método, ya que impide que se cree varios objetos para la misma máquina en el portal de Microsoft Defender para endpoint. Esto puede provocar confusión al investigar incidentes. Para entornos de prueba o no volátiles, puede optar por elegir de forma diferente.

Microsoft recomienda agregar el script de incorporación de Microsoft Defender para endpoint a la imagen dorada de WVD. De esta forma, puede asegurarse de que este script de incorporación se ejecute inmediatamente al primer arranque. Se ejecuta como un script de inicio al inicio en todas las máquinas WVD aprovisionadas desde la imagen dorada de WVD. Sin embargo, si usa una de las imágenes de la galería sin modificaciones, coloque el script en una ubicación compartida y llámelo desde una directiva de grupo local o de dominio.

> [!NOTE]
> La ubicación y configuración del script de inicio de incorporación de VDI en la imagen dorada de WVD lo configura como un script de inicio que se ejecuta cuando se inicia WVD. No se recomienda **incorporar** la imagen dorada de WVD real. Otra consideración es el método usado para ejecutar el script. Debe ejecutarse lo antes posible en el proceso de inicio o aprovisionamiento para reducir el tiempo entre la máquina que está disponible para recibir sesiones y la incorporación del dispositivo al servicio. Los siguientes escenarios 1 y 2 tienen esto en cuenta.

### <a name="scenarios"></a>Escenarios

Hay varias formas de incorporar un equipo host WVD:

- Ejecute el script en la imagen dorada (o desde una ubicación compartida) durante el inicio.
- Use una herramienta de administración para ejecutar el script.
- A [través de la integración con Microsoft Defender para la nube](azure-server-integration.md)

#### <a name="scenario-1-using-local-group-policy"></a>*Escenario 1: Uso de la directiva de grupo local*

Este escenario requiere colocar el script en una imagen dorada y usa la directiva de grupo local para ejecutarse al principio del proceso de arranque.

Use las instrucciones de [Incorporación de dispositivos de infraestructura de escritorio virtual (VDI) no persistentes](configure-endpoints-vdi.md).

Siga las instrucciones de una sola entrada para cada dispositivo.

#### <a name="scenario-2-using-domain-group-policy"></a>*Escenario 2: Uso de la directiva de grupo de dominio*

Este escenario usa un script ubicado centralmente y lo ejecuta mediante una directiva de grupo basada en dominio. También puede colocar el script en la imagen dorada y ejecutarlo de la misma manera.

##### <a name="download-the-windowsdefenderatponboardingpackagezip-file-from-the-windows-365-defender-portal"></a>Descargue el WindowsDefenderATPOnboardingPackage.zip desde el portal de Windows 365 Defender

1. Abra el archivo de configuración .zip VDI (WindowsDefenderATPOnboardingPackage.zip)

    1. En el panel Microsoft 365 Defender navegación del portal, **seleccione Configuración** \> **incorporación** \> de puntos de **conexión (en** **Administración de dispositivos**).
    1. Seleccione Windows 10 o Windows 11 como sistema operativo.
    1. En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no persistentes.
    1. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Extrae el contenido del archivo .zip a una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener una carpeta denominada **OptionalParamsPolicy** y los archivos **WindowsDefenderATPOnboardingScript.cmd** **yOnboard-NonPersistentMachine.ps1**.

##### <a name="use-group-policy-management-console-to-run-the-script-when-the-virtual-machine-starts"></a>Usar la consola de administración de directivas de grupo para ejecutar el script cuando se inicia la máquina virtual

1. Abra la Consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

2. En el Editor de administración de directivas de grupo, vaya a **Configuración** \>  \> del equipo Preferencias **configuración Configuración Del panel de control**.

3. Haga clic con el botón secundario en **Tareas programadas**, haga clic en **Nuevo** y, a continuación, haga clic en Tarea **inmediata** (al menos Windows 7).

4. En la ventana Tarea que se abre, vaya a la **pestaña General** . En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA. Haga **clic en Comprobar nombres** y, a continuación, en Aceptar. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.

5. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con privilegios** más altos.

6. Vaya a la **pestaña Acciones** y haga clic en **Nuevo**. Asegúrese de **que Iniciar un programa** está seleccionado en el campo Acción. Especifique lo siguiente:

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   A continuación **, seleccione Aceptar** y cierre las ventanas GPMC abiertas.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Escenario 3: Incorporación con herramientas de administración*

Si planea administrar las máquinas con una herramienta de administración, puede incorporar dispositivos con Microsoft Endpoint Configuration Manager.

Para obtener más información, consulte [Onboard Windows devices using Configuration Manager](configure-endpoints-sccm.md).

> [!WARNING]
> Si tiene previsto usar la referencia de reglas de reducción de superficie de [ataque, tenga](attack-surface-reduction-rules-reference.md) en cuenta que no se debe usar la regla "Bloquear creaciones de procesos [procedentes de comandos PSExec y WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands)", ya que dicha regla es incompatible con la administración a través de Microsoft Endpoint Configuration Manager. La regla bloquea los comandos WMI que el cliente de Configuration Manager usa para funcionar correctamente.

> [!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que el dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado](run-detection-test.md).

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Etiquetar las máquinas al crear la imagen dorada

Como parte de la incorporación, es posible que quieras establecer una etiqueta de máquina para diferenciar los equipos WVD más fácilmente en el Centro de seguridad de Microsoft. Para obtener más información, consulta [Agregar etiquetas de dispositivo estableciendo un valor de clave del Registro](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).

#### <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

Al crear la imagen dorada, es posible que también quieras configurar la configuración de protección inicial. Para obtener más información, consulta [Otras opciones de configuración recomendadas](configure-endpoints-gp.md#other-recommended-configuration-settings).

Además, si usa perfiles de usuario FSlogix, se recomienda excluir los siguientes archivos de la protección siempre en uso:

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

Nota sobre las licencias: al usar Windows Enterprise varias sesiones, según sus requisitos, puede elegir que todos los usuarios tengan licencia a través de Microsoft Defender para Endpoint (por usuario), Windows Enterprise E5, Microsoft 365 Security o Microsoft 365 E5 , o tener la vm con licencia a través de Microsoft Defender para la nube.
Los requisitos de licencias para Microsoft Defender para endpoint se pueden encontrar en: [Requisitos de licencias](minimum-requirements.md#licensing-requirements).

### <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

Solo Microsoft Edge para el filtrado web en Windows 10 multi-sesión.

#### <a name="related-links"></a>Vínculos relacionados

[Agregar exclusiones para Defender for Endpoint a través de PowerShell](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-microsoft-defender-by-using-powershell)
