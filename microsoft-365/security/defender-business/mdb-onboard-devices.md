---
title: Incorporación de dispositivos a Microsoft Defender para empresas
description: Obtenga información sobre las opciones de incorporación de dispositivos en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/14/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 6b475a1f56f66c6ec9e1ed09b5311515c5eb31c8
ms.sourcegitcommit: 9af389e4787383cd97bc807f7799ef6ecf0664d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2022
ms.locfileid: "63468700"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos a Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Con Microsoft Defender para empresas, tienes varias opciones entre las que elegir para incorporar los dispositivos de tu organización. En este artículo se le guía por las opciones e incluye información general sobre cómo funciona la incorporación.

## <a name="what-to-do"></a>Qué hacer

1. Consulta las opciones de [incorporación de dispositivos](#device-onboarding-methods) y selecciona uno de los siguientes métodos: 

   - [Incorporación automática para Windows dispositivos inscritos en Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [Script local para dispositivos Windows y Mac](#local-script-in-defender-for-business)
   - [Microsoft Endpoint Manager (Microsoft Intune)](#microsoft-endpoint-manager)
   - [Configuración de seguridad de Microsoft Defender para empresas](#microsoft-defender-for-business-security-configuration)

2. [Ejecute una prueba de detección](#run-a-detection-test) para dispositivos Windows recién incorporados.

3. [Consulta los pasos siguientes](#next-steps). 

En este artículo también se incluye información sobre cómo ejecutar una prueba de detección [para Windows dispositivos y](#run-a-detection-test) [offboarding de un dispositivo](#offboarding-a-device).

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="device-onboarding-methods"></a>Métodos de incorporación de dispositivos

En la tabla siguiente se describen los métodos más usados para incorporar dispositivos a Defender para empresas. 

| Método de incorporación  | Descripción  | SO |
|---------|---------|---------|
| **Incorporación automática**<br/>(*disponible para clientes que ya usan Microsoft Endpoint Manager*) | *Microsoft 365 Empresa Premium clientes ya tienen Microsoft Intune y pueden usar esta opción*. La incorporación automática configura una conexión entre Defender para empresas y Microsoft Endpoint Manager y, a continuación, se incorpora Windows dispositivos a Defender para empresas. Para poder usar esta opción, los dispositivos ya deben estar inscritos en Endpoint Manager.<br/><br/>Para obtener más información, consulte [Incorporación automática](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager). | Windows |
| **Script local** <br/> | Esta opción te permite incorporar dispositivos individuales a Defender para empresas manualmente. Puedes incorporar hasta 10 dispositivos a la vez mediante el script local.<br/><br/>Para obtener más información, [vea Script local en Defender for Business](#local-script-in-defender-for-business). | Windows <br/>macOS |
| **Microsoft Intune** o **Microsoft Endpoint Manager**<br/>(*disponible para clientes que usan Microsoft Intune o Endpoint Manager*) | [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) [y administración de](/mem/intune/enrollment/device-enrollment) dispositivos móviles forman parte de Endpoint Manager. (Microsoft 365 Empresa Premium clientes ya tienen Microsoft Intune).<br/><br/>Si ya usaste Endpoint Manager antes de obtener Defender para empresas, puedes optar por seguir usando Endpoint Manager para incorporar y administrar tus dispositivos.<br/><br/>Para usar este método, vea [Microsoft Endpoint Manager](#microsoft-endpoint-manager). | Windows <br/>macOS<br/>iOS<br/>Sistema operativo Android | 
| **Configuración de seguridad de Microsoft Defender para empresas** <br/>(*usa el Microsoft 365 Defender web*) | Para usar esta opción, debe configurar determinadas opciones para facilitar la comunicación entre Defender para empresas y Endpoint Manager. A continuación, incorporas dispositivos en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) mediante el uso de un paquete que descargues y ejecutes en cada dispositivo. Se establece una confianza entre dispositivos y Azure Active Directory (Azure AD) y las directivas de seguridad de Defender para empresas se insertan en dispositivos.<br/><br/>Para obtener más información, consulta [Configuración de seguridad de Microsoft Defender para empresas](#microsoft-defender-for-business-security-configuration). | Windows <br/>macOS |

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, consulta Solución de problemas de [Microsoft Defender para empresas](mdb-troubleshooting.yml).

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>Incorporación automática para Windows dispositivos inscritos en Microsoft Endpoint Manager

La opción de incorporación automática solo se aplica Windows dispositivos. La incorporación automática está disponible si se cumplen las siguientes condiciones:

- Su organización ya usaba Microsoft Endpoint Manager, Microsoft Intune o administración de dispositivos móviles (MDM) en Microsoft Intune antes de obtener Defender for Business
- Ya tienes Windows dispositivos inscritos en Endpoint Manager

Si Windows dispositivos ya están inscritos en Endpoint Manager, Defender para empresas detectará esos dispositivos mientras se está configurando y configurando Defender para empresas. Se te preguntará si quieres usar la incorporación automática para todos o algunos de tus Windows dispositivos. Puedes incorporar todos los Windows a la vez, o seleccionar dispositivos específicos para empezar y, a continuación, agregar más dispositivos más adelante.

> [!TIP]
> Se recomienda seleccionar la opción "todos los dispositivos inscritos". De este modo, Windows los dispositivos se inscriben en Endpoint Manager más adelante, se incorporarán automáticamente a Defender for Business.

Para obtener más información sobre la incorporación automática, consulta el paso 2 de [Usar el asistente para configurar Microsoft Defender para empresas](mdb-use-wizard.md).

## <a name="local-script-in-defender-for-business"></a>Script local en Defender para empresas

Puedes usar un script local para incorporar dispositivos Windows y Mac. Al ejecutar el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory (si esa confianza aún no existe), inscribe el dispositivo en Microsoft Endpoint Manager (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender para empresas. Este método es útil para incorporar dispositivos en Defender para empresas. Puedes incorporar hasta 10 dispositivos a la vez.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, **elija Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11** o **macOS** y, a continuación, en la sección Método de  implementación, elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble. (Si seleccionó **macOS**, también seleccione **Descargar paquete de instalación** y guárdelo en el dispositivo extraíble).

5. Siga las instrucciones de la tabla siguiente:

   | Sistema operativo | Procedure |
   |---|---|
   | Windows | 1. En un dispositivo Windows, extraiga el contenido del paquete de configuración en una ubicación, como la carpeta Escritorio. Debe tener un archivo denominado `WindowsDefenderATPLocalOnboardingScript.cmd`. <br/><br/>2. Abra el símbolo del sistema como administrador.<br/><br/>3. Escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta Escritorio, escribiría: `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`y, a continuación, presionaría la tecla Entrar (o bien, **seleccionarÍa Aceptar**).<br/><br/>4. Después de que se ejecute el script, continúe con [Ejecutar una prueba de detección](#run-a-detection-test). |
   | macOS | 1. En un equipo Mac, guarde el paquete de instalación en `wdav.pkg` un directorio local. <br/><br/>2. Guarde el paquete de incorporación en `WindowsDefenderATPOnboardingPackage.zip` el mismo directorio que usó para el paquete de instalación. <br/><br/>3. Use Finder para navegar `wdav.pkg` hasta que guardó y, a continuación, ábralo.<br/><br/>4. Seleccione **Continuar**, acepte los términos de licencia y, a continuación, escriba la contraseña cuando se le solicite.<br/><br/>5. Se le pedirá que permita la instalación de un controlador de Microsoft (ya sea "System Extension Blocked" o "Installation is on hold", o ambos. Se debe permitir la instalación del controlador. Para permitir la instalación, seleccione **Abrir** preferencias de seguridad o **Abrir Preferencias** >  del **sistemaSecurity & Privacidad** y, a continuación, **seleccione Permitir**.<br/><br/>6. Use el siguiente comando python en Bash para ejecutar el paquete de incorporación: `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py`. <br/><br/>7. Para confirmar que el dispositivo está asociado a su organización, use el siguiente comando python en Bash: `mdatp health --field org_id`.<br/><br/>8. Si usa macOS 10.15 (Catalina) o posterior, conceda a Defender for Business su consentimiento para proteger el dispositivo. Vaya a **System PreferencesSecurity** >  **&** **PrivacyPrivacyFull** >  >  **Disk Access**.  Seleccione el icono de bloqueo para realizar cambios (parte inferior del cuadro de diálogo) y, a continuación, seleccione Microsoft Defender para empresas (o Defender para endpoint, si eso es lo que ve). <br/><br/>9. Para comprobar que el dispositivo está incorporado, use el siguiente comando en Bash: `mdatp health --field real_time_protection_enabled`.    |

## <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

Si ya usaste Endpoint Manager (que incluye Microsoft Intune y Administración de dispositivos móviles), antes de obtener Defender para empresas, puedes seguir usando Endpoint Manager para incorporar los dispositivos de la organización. Con Endpoint Manager, puedes incorporar equipos, tabletas y teléfonos, incluidos dispositivos iOS y Android.

Consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).

## <a name="microsoft-defender-for-business-security-configuration"></a>Configuración de seguridad de Microsoft Defender para empresas

> [!NOTE]
> Si ya estás usando Endpoint Manager para administrar tus dispositivos y directivas de seguridad, omite este método y consulta Microsoft Endpoint Manager en su [lugar](#microsoft-endpoint-manager).

La configuración de seguridad de Microsoft Defender para empresas se ha basado en una funcionalidad conocida como Administración de seguridad para [Microsoft Defender para endpoint (versión preliminar).](/mem/intune/protect/mde-security-integration) Le permite incorporar dispositivos a Defender para empresas en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) sin necesidad de que dichos dispositivos se inscriba por completo en Microsoft Endpoint Manager de antemano. 

Este método le permite incorporar dispositivos y administrar las directivas de antivirus y firewall en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Así es como funciona todo:

1. Descargue un paquete de incorporación desde el portal de Microsoft 365 Defender y, a continuación, ejecute el paquete en los dispositivos para incorporarlos a Defender para empresas.

2. La ejecución del paquete establece una confianza entre cada dispositivo (si la confianza aún no existe) y Azure Active Directory (Azure AD). 

3. Los dispositivos se Endpoint Manager con su Azure AD identidad y las directivas de seguridad de Defender para empresas se insertan en los dispositivos.

4. Puede ver sus dispositivos y directivas en el portal de Microsoft 365 Defender y en el centro Endpoint Manager administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).

Para usar esta opción, se deben configurar determinadas opciones de antemano. Para obtener más información, incluidos los requisitos previos y los sistemas operativos compatibles, consulte [Manage Microsoft Defender for Endpoint on devices with Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration).

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Después de incorporar Windows dispositivos a Defender para empresas, puedes ejecutar una prueba de detección en un dispositivo Windows para asegurarte de que todo funciona correctamente.

1. En el Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra el símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="gradual-device-onboarding"></a>Incorporación gradual de dispositivos

Puedes incorporar los dispositivos de la organización en fases. *Llamamos a esta incorporación gradual de dispositivos*. 

1. Identificar un conjunto de dispositivos que se incorporarán.

2. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

3. En el panel de navegación, **elija Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

4. Seleccione un sistema operativo (como **Windows 10 y 11)** y, a continuación, elija un método de incorporación (como **script local**). Siga las instrucciones proporcionadas para el método seleccionado.

5. Repita este proceso para cada conjunto de dispositivos que desee incorporar. 

> [!TIP]
> No tienes que usar el mismo paquete de incorporación cada vez que incorpores dispositivos. Por ejemplo, puedes usar un script local para incorporar algunos dispositivos y, más adelante, puedes elegir otro método para incorporar más dispositivos.

## <a name="offboarding-a-device"></a>Offboarding a device

Si quieres salir de un dispositivo, usa uno de los siguientes procedimientos:

| Sistema operativo | Procedure |
|---|---|
| Windows | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.<br/><br/>2. En el panel de navegación, **elija Configuración** y, a continuación, elija **Extremos**.<br/><br/>3. En **Administración de dispositivos**, elija **Offboarding**.<br/><br/>4. Seleccione un sistema operativo, como Windows 10 y **11**, y, a continuación, en **Offboard a device**, en la sección **Método** de implementación, elija **Script local**. <br/><br/>5. En la pantalla de confirmación, revise la información y, a continuación, elija **Descargar** para continuar.<br/><br/>6. Seleccione **Descargar paquete de offboarding**. Se recomienda guardar el paquete de offboarding en una unidad extraíble.<br/><br/>7. Ejecute el script en cada dispositivo que desee desactivar.| 
| macOS | 1. Vaya a **FinderApplications** > . <br/><br/>2. Haga clic con el botón secundario en Microsoft Defender para empresas y, a continuación, elija **Mover a la papelera**. <br/><br/>--- o --- <br/><br/> Use el siguiente comando: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.|

> [!IMPORTANT]
> La salida de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes del offboarding se conservan durante un máximo de seis (6) meses.

## <a name="next-steps"></a>Pasos siguientes

Continúe con:

- [Paso 5: Configurar la configuración de seguridad y las directivas en Microsoft Defender para empresas](mdb-configure-security-settings.md)

- [Introducción al uso de Microsoft Defender para empresas](mdb-get-started.md) 
