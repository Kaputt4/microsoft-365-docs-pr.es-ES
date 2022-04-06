---
title: Incorporar dispositivos para Microsoft Defender für Unternehmen
description: Obtenga información sobre las opciones de incorporación de dispositivos en Microsoft Defender für Unternehmen
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 78a8eaa5a9472a32c9615dfb7c7f5b08afe548ff
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634743"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Incorporar dispositivos para Microsoft Defender für Unternehmen

> [!IMPORTANT]
> Microsoft Defender für Unternehmen se está implementando para [Microsoft 365 Business Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Con Microsoft Defender für Unternehmen, tienes varias opciones entre las que elegir para incorporar los dispositivos de tu empresa. En este artículo se le guía por las opciones e incluye información general sobre cómo funciona la incorporación.

>
> **¿Tiene un minuto?**
> Por favor, <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">haga nuestra breve encuesta sobre Microsoft Defender für Unternehmen</a>. Nos encantaría conocer su opinión.
>

## <a name="what-to-do"></a>Qué hacer

1. [Consulta las opciones de incorporación de dispositivos](#device-onboarding-methods) y selecciona un método. 

   - [Usar la incorporación automática para Windows dispositivos ya inscritos en Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [Usar un script local para incorporar dispositivos Windows o macOS](#local-script-in-defender-for-business)
   - [Usar Microsoft Endpoint Manager para incorporar Windows, macOS o dispositivos móviles](#microsoft-endpoint-manager)

2. [Ejecute una prueba de detección](#run-a-detection-test) en dispositivos Windows recién incorporados.

3. [Consulta los pasos siguientes](#next-steps). 

En este artículo también se incluye información sobre [la offboarding de un dispositivo](#offboarding-a-device).

## <a name="device-onboarding-methods"></a>Métodos de incorporación de dispositivos

Defender para empresas te ofrece varios métodos diferentes para la incorporación de dispositivos, ya sea que ya estés usando Microsoft Endpoint Manager, o simplemente quieres una experiencia de incorporación simplificada. Los métodos más usados para incorporar dispositivos a Defender para empresas son:

- **Incorporación automática para** Windows dispositivos que ya están inscritos en Microsoft Endpoint Manager. La incorporación automática configura una conexión entre Defender para empresas y Microsoft Endpoint Manager y, a continuación, se incorpora Windows dispositivos a Defender para empresas. Para poder usar esta opción, los dispositivos ya deben estar inscritos en Endpoint Manager. Para obtener más información, consulte [Incorporación automática](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager).

- **Script local para** incorporar Windows y dispositivos macOS a Defender para empresas manualmente. Puedes incorporar hasta 10 dispositivos a la vez mediante el script local. Para obtener más información, [vea Script local en Defender for Business](#local-script-in-defender-for-business).

- **Microsoft Intune** o **Microsoft Endpoint Manager** para incorporar Windows, macOS y dispositivos móviles. Puedes inscribir dispositivos en Endpoint Manager y, a continuación, incorporar los dispositivos a Defender para empresas. [Microsoft 365 Business Premium](../../business-premium/index.md) clientes ya tienen [Microsoft Intune](/mem/intune/fundamentals/what-is-intune), y tanto Microsoft Intune [como mobile Administración de dispositivos](/mem/intune/enrollment/device-enrollment) ahora forman parte de Endpoint Manager. Para usar este método, vea [Microsoft Endpoint Manager](#microsoft-endpoint-manager).

> [!IMPORTANT]
> Si algo sale mal y se produce un error en el proceso de incorporación, [consulte Microsoft Defender für Unternehmen solución de problemas](mdb-troubleshooting.yml).

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>Incorporación automática para Windows dispositivos inscritos en Microsoft Endpoint Manager

La opción de incorporación automática solo se aplica Windows dispositivos. La incorporación automática está disponible si se cumplen las siguientes condiciones:

- Tu empresa ya usaba Microsoft Endpoint Manager, Microsoft Intune o Mobile Administración de dispositivos (MDM) en Microsoft Intune antes de obtener Defender for Business

- Ya tienes Windows dispositivos inscritos en Endpoint Manager

Si Windows dispositivos ya están inscritos en Endpoint Manager, Defender para empresas detectará esos dispositivos mientras se está configurando y configurando Defender para empresas. Se te preguntará si quieres usar la incorporación automática para todos o algunos de tus Windows dispositivos. Puedes incorporar todos los Windows a la vez, o seleccionar dispositivos específicos para empezar y, a continuación, agregar más dispositivos más adelante.

> [!TIP]
> Se recomienda seleccionar la opción "todos los dispositivos inscritos". De este modo, Windows los dispositivos se inscriben en Endpoint Manager más adelante, se incorporarán automáticamente a Defender for Business. Además, si has estado administrando las directivas de seguridad y la configuración en Endpoint Manager, te recomendamos que cambies al portal de Microsoft 365 Defender para administrar tus dispositivos, directivas y configuración. Para obtener más información, consulta [Elegir dónde administrar dispositivos y directivas de seguridad](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices).

Para obtener más información sobre la incorporación automática, consulte el paso 2 en [Usar el asistente para configurar](mdb-use-wizard.md) Microsoft Defender für Unternehmen.

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
   | macOS | 1. En un equipo Mac, guarde el paquete de instalación en `wdav.pkg` un directorio local. <br/><br/>2. Guarde el paquete de incorporación en `WindowsDefenderATPOnboardingPackage.zip` el mismo directorio que usó para el paquete de instalación. <br/><br/>3. Use Finder para navegar `wdav.pkg` hasta que guardó y, a continuación, ábralo.<br/><br/>4. Seleccione **Continuar**, acepte los términos de licencia y, a continuación, escriba la contraseña cuando se le solicite.<br/><br/>5. Se le pedirá que permita la instalación de un controlador de Microsoft (ya sea "System Extension Blocked" o "Installation is on hold", o ambos. Se debe permitir la instalación del controlador. Para permitir la instalación, seleccione **Abrir** preferencias de seguridad o **Abrir Preferencias** >  del **sistemaSecurity & Privacidad** y, a continuación, **seleccione Permitir**.<br/><br/>6. Use el siguiente comando python en Bash para ejecutar el paquete de incorporación: `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py`. <br/><br/>7. Para confirmar que el dispositivo está asociado a su empresa, use el siguiente comando python en Bash: `mdatp health --field org_id`.<br/><br/>8. Si usa macOS 10.15 (Catalina) o posterior, conceda a Defender for Business su consentimiento para proteger el dispositivo. Vaya a **System PreferencesSecurity** >  **&** **PrivacyPrivacyFull** >  >  **Disk Access**.  Seleccione el icono de bloqueo para realizar cambios (en la parte inferior del cuadro de diálogo) y, a continuación, seleccione Microsoft Defender für Unternehmen (o Defender para Endpoint, si eso es lo que ve). <br/><br/>9. Para comprobar que el dispositivo está incorporado, use el siguiente comando en Bash: `mdatp health --field real_time_protection_enabled`.    |

## <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

Si ya estaba usando Endpoint Manager (que incluye Microsoft Intune y Mobile Administración de dispositivos), antes de obtener Defender para empresas, puede seguir usando Endpoint Manager para incorporar los dispositivos de su empresa. Con Endpoint Manager, puedes incorporar equipos, tabletas y teléfonos, incluidos dispositivos iOS y Android.

Consulta [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/device-enrollment).

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

Puedes incorporar los dispositivos de tu empresa en fases. *Llamamos a esta incorporación gradual de dispositivos*. 

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
| macOS | 1. Vaya a **FinderApplications** > . <br/><br/>2. Haga clic con el botón secundario en Microsoft Defender für Unternehmen y, a continuación, elija **Mover a la papelera**. <br/><br/>--- o --- <br/><br/> Use el siguiente comando: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.|

> [!IMPORTANT]
> La salida de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes del offboarding se conservan durante un máximo de seis (6) meses.

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 5: Configurar la configuración de seguridad y las directivas en Microsoft Defender für Unternehmen](mdb-configure-security-settings.md)

- [Comenzar usar Microsoft Defender für Unternehmen](mdb-get-started.md) 
