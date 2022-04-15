---
title: Incorporación de dispositivos a Microsoft Defender para Empresas
description: Obtenga información sobre las opciones de incorporación de dispositivos en Microsoft Defender para Empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/14/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ba816430521db2848273a4f7c6ca7d1a61703690
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862286"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos a Microsoft Defender para Empresas

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

Con Microsoft Defender para Empresas, tiene varias opciones entre las que elegir para incorporar los dispositivos de su empresa. Este artículo le guiará por las opciones e incluye información general sobre cómo funciona la incorporación.

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="what-to-do"></a>Qué hacer

1. Seleccione la pestaña del sistema operativo: 

   - clientes Windows
   - Windows Server (versión preliminar)
   - equipos macOS
   - dispositivos móviles

2. Vea las opciones de incorporación y siga las instrucciones de la pestaña seleccionada.

3. Continúe con los pasos siguientes.

## <a name="windows-clients"></a>[**clientes Windows**](#tab/WindowsClientDevices)

## <a name="windows-clients"></a>clientes Windows

Elija una de las siguientes opciones para incorporar Windows dispositivos cliente a Defender for Business:

- [Script local](#local-script-for-windows-clients) (para la incorporación manual de dispositivos en el portal de Microsoft 365 Defender)
- [Microsoft Endpoint Manager](#endpoint-manager-for-windows-clients) (incluido en [Microsoft 365 Empresa Premium](../../business-premium/index.md))


### <a name="local-script-for-windows-clients"></a>Script local para clientes Windows

Puede usar un script local para incorporar Windows dispositivos cliente. Al ejecutar el script de incorporación en un dispositivo, crea una confianza con Azure Active Directory (si esa confianza no existe aún), inscribe el dispositivo en Microsoft Endpoint Manager (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender for Business. El método de script local funciona incluso si actualmente no tiene Endpoint Manager (o Microsoft Intune). Se recomienda incorporar hasta 10 dispositivos a la vez mediante este método.

> [!TIP]
> Se recomienda incorporar hasta 10 dispositivos a la vez cuando se usa el método de script local.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

3. Seleccione un sistema operativo, como **Windows 10 y 11**, y, a continuación, en la sección **Método de implementación**, elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble.

5. En un dispositivo Windows, extraiga el contenido del paquete de configuración en una ubicación, como la carpeta Escritorio. Debe tener un archivo denominado `WindowsDefenderATPLocalOnboardingScript.cmd`. 

6. Abra el símbolo del sistema como administrador.

7. Escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta Escritorio, escriba `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`y, a continuación, presione la tecla Entrar (o seleccione **Aceptar**).

8. Después de ejecutar el script, vaya a [Ejecutar una prueba de detección](#running-a-detection-test-on-a-windows-client).

### <a name="endpoint-manager-for-windows-clients"></a>Endpoint Manager para clientes Windows

Si la suscripción incluye [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), puede incorporar Windows clientes y otros dispositivos en el centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)). Por ejemplo, si tiene [Microsoft 365 Empresa Premium](../../business/index.yml), tiene Endpoint Manager como parte de la suscripción. Endpoint Manager incluye [funcionalidades de Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [mobile Administración de dispositivos](/mem/intune/fundamentals/what-is-device-management). 

Hay varios métodos disponibles para inscribir dispositivos en Intune. Se recomienda empezar por uno de los métodos siguientes:

- [Habilitación Windows inscripción automática](/mem/intune/enrollment/windows-enroll) para dispositivos propiedad de la empresa o administrados por la empresa
- [Pida a los usuarios que inscriban sus propios dispositivos Windows 10/11 en Intune](/mem/intune/user-help/enroll-windows-10-device)

#### <a name="to-enable-automatic-enrollment-for-windows-devices"></a>Para habilitar la inscripción automática para dispositivos Windows

Al configurar la inscripción automática, los usuarios agregan su cuenta profesional al dispositivo. En segundo plano, el dispositivo se registra y se une a Azure Active Directory (Azure AD) y se inscribe en Intune.

1. Vaya a la Azure Portal ([https://portal.azure.com/](https://portal.azure.com/)) e inicie sesión. 

2. Seleccione **Azure Active Directory** >  **Mobility (MDM y MAM)** > **Microsoft Intune**.

3. Configure el ámbito de usuario mdm y el ámbito de usuario mam.

   :::image type="content" source="media/mem-mam-scope-azure-ad.png" alt-text="Captura de pantalla de la configuración del ámbito de usuario MDM y el ámbito de usuario MAM en Intune.":::

   - En ámbito de usuario de MDM, se recomienda seleccionar **Todo** para que todos los usuarios puedan inscribir automáticamente sus dispositivos Windows.
   - En la sección Ámbito de usuario mam, se recomienda usar los siguientes valores predeterminados para las direcciones URL:

       - **URL de los términos de uso de MDM**
       - **URL de detección de MDM**
       - **URL de cumplimiento de MDM**

4. Seleccione **Guardar**.

5. Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Microsoft Defender para Empresas](mdb-create-edit-device-groups.md).


> [!TIP]
> Para más información sobre la inscripción automática, consulte [Habilitación Windows inscripción automática](/mem/intune/enrollment/windows-enroll).

#### <a name="to-have-users-enroll-their-own-windows-devices"></a>Para que los usuarios inscriban sus propios dispositivos Windows

1. Vea el siguiente vídeo para ver cómo funciona la inscripción: <br/><br/>

   > [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]  

2. Comparta este artículo con los usuarios de su organización: [Inscriba dispositivos Windows 10/11 en Intune](/mem/intune/user-help/enroll-windows-10-device).

3. Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Microsoft Defender para Empresas](mdb-create-edit-device-groups.md).

### <a name="running-a-detection-test-on-a-windows-client"></a>Ejecución de una prueba de detección en un cliente de Windows

Después de incorporar Windows dispositivos a Defender for Business, puede ejecutar una prueba de detección en un dispositivo Windows para asegurarse de que todo funciona correctamente.

1. En el dispositivo Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra el símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos que se incorporan a Defender for Business, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, en **Puntos de conexión**, elija **Dispositivo invetory**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña correspondiente al sistema operativo de los dispositivos [(Windows clientes, Windows Server, macOS o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Microsoft Defender para Empresas](mdb-configure-security-settings.md)
- Consulte [Comenzar con Microsoft Defender para Empresas](mdb-get-started.md).

## <a name="windows-server"></a>[**Windows Server**](#tab/WindowsServerEndpoints)

## <a name="windows-server-preview"></a>Windows Server (versión preliminar)

Puede incorporar un dispositivo Windows Server mediante un script local. 

> [!IMPORTANT]
> La capacidad de incorporar puntos de conexión de Windows Server está actualmente en versión preliminar.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

3. Seleccione un sistema operativo, como **Windows Server 1803, 2019 y 2022**, y, a continuación, en la sección **Método de implementación**, elija **Script local**. 

   Si selecciona **Windows Server 2012 R2 y 2016**, tendrá dos paquetes para descargar y ejecutar: un paquete de instalación y un paquete de incorporación. El paquete de instalación contiene un archivo MSI que instala el agente de Microsoft Defender para Empresas. El paquete de incorporación contiene el script para incorporar el punto de conexión de Windows Server a Defender for Business. 

4. Seleccione **Descargar paquete de incorporación**. Se recomienda guardar el paquete de incorporación en una unidad extraíble.

   Si seleccionó **Windows Server 2012 R2 y 2016**, seleccione también **Descargar paquete de instalación** y guárdelo en una unidad extraíble.

5. En el punto de conexión de Windows Server, extraiga el contenido de los paquetes de instalación o incorporación a una ubicación, como la carpeta Escritorio. Debe tener un archivo denominado `WindowsDefenderATPLocalOnboardingScript.cmd`. 

   Si va a incorporar Windows Server 2012 R2 o Windows Server 2016, extraiga primero el paquete de instalación.

6. Abra el símbolo del sistema como administrador.

7. Si va a incorporar Windows Server 2012R2 o Windows Server 2016, ejecute el siguiente comando: `Msiexec /i md4ws.msi /quiet`. 

   Si va a incorporar Windows Server 1803, 2019 o 2022, omita este paso y continúe con el paso 8.

8. Escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta Escritorio, escriba `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`y, a continuación, presione la tecla Entrar (o seleccione **Aceptar**).

9. Continúe con [Ejecutar una prueba de detección en Windows Server](#running-a-detection-test-on-windows-server)

### <a name="running-a-detection-test-on-windows-server"></a>Ejecución de una prueba de detección en Windows Server

Después de incorporar el punto de conexión de Windows Server a Defender for Business, puede ejecutar una prueba de detección para asegurarse de que todo funciona correctamente.

1. En el dispositivo Windows Server, cree una carpeta: `C:\test-MDATP-test`.

2. Abra el símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez ejecutado el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos que se incorporan a Defender for Business, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, en **Puntos de conexión**, elija **Dispositivo invetory**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña correspondiente al sistema operativo de los dispositivos [(Windows clientes, Windows Server, macOS o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Microsoft Defender para Empresas](mdb-configure-security-settings.md)
- Consulte [Comenzar con Microsoft Defender para Empresas](mdb-get-started.md).

## <a name="macos"></a>[**macOS**](#tab/macOSdevices)

## <a name="macos-computers"></a>equipos macOS

> [!NOTE]
> - Se recomienda usar un [script local para incorporar dispositivos macOS](#local-script-for-macos). Aunque puede [configurar la inscripción para dispositivos macOS en Intune](/mem/intune/enrollment/macos-enroll), el script local es el método más sencillo para incorporar dispositivos macOS a Defender for Business. 

Elija una de las siguientes opciones para incorporar dispositivos macOS:

- [Script local para macOS](#local-script-for-macos) (*recomendado*)
- [Endpoint Manager para macOS](#endpoint-manager-for-macos)

### <a name="local-script-for-macos"></a>Script local para macOS

Cuando ejecuta el script local en un dispositivo macOS, crea una confianza con Azure Active Directory (si esa confianza no existe aún), inscribe el dispositivo en Microsoft Endpoint Manager (si aún no está inscrito) y, a continuación, incorpora el dispositivo a Defender for Business. El método de script local funciona incluso si actualmente no tiene Endpoint Manager (o Microsoft Intune). Se recomienda incorporar hasta 10 dispositivos a la vez mediante este método.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración** >  **Endpoints** y, a continuación, en **Administración** de dispositivos, elija **Incorporación**.

3. Seleccione **macOS** y, a continuación, en la sección **Método de implementación** , elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación** y guárdelo en una unidad extraíble. También seleccione **Descargar paquete de instalación** y guárdelo en el dispositivo extraíble.

5. En un dispositivo macOS, guarde el paquete de instalación en un `wdav.pkg` directorio local.

6. Guarde el paquete de incorporación como `WindowsDefenderATPOnboardingPackage.zip` en el mismo directorio que usó para el paquete de instalación.

7. Use Finder para navegar hasta usted guardado y, a `wdav.pkg` continuación, abrirlo.

8. Seleccione **Continuar**, acepte los términos de licencia y escriba la contraseña cuando se le solicite.

9. Se le pedirá que permita instalar un controlador de Microsoft (ya sea "Extensión del sistema bloqueada" o "La instalación está en espera" o ambas. Se debe permitir que se instale el controlador. Para permitir la instalación, seleccione **Abrir preferencias de seguridad** o **Abrir preferencias** >  del **sistemaSeguridad & privacidad** y, a continuación, seleccione **Permitir**.

10. Use el siguiente comando de Python en Bash para ejecutar el paquete de incorporación: `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py`

11. Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Microsoft Defender para Empresas](mdb-create-edit-device-groups.md).

### <a name="endpoint-manager-for-macos"></a>Endpoint Manager para macOS

Si la suscripción incluye [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), puede incorporar dispositivos macOS en el centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)). Por ejemplo, si tiene [Microsoft 365 Empresa Premium](../../business/index.yml), tiene Endpoint Manager como parte de la suscripción. Endpoint Manager incluye [funcionalidades de Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [mobile Administración de dispositivos](/mem/intune/fundamentals/what-is-device-management). 

Hay varios métodos disponibles para inscribir dispositivos en Intune. Se recomienda empezar por uno de los métodos siguientes:

- [Elegir una opción para dispositivos macOS propiedad de la empresa](#options-for-company-owned-macos-devices)
- [Pida a los usuarios que inscriban sus propios dispositivos macOS en Intune](#ask-users-to-enroll-their-own-macos-devices-in-intune)

#### <a name="options-for-company-owned-macos-devices"></a>Opciones para dispositivos macOS propiedad de la empresa

Elija una de las opciones de la tabla siguiente para inscribir dispositivos macOS administrados por la empresa en Intune:

| Opción  | Descripción  |
|---------|---------|
| Inscripción de dispositivo automatizada de Apple |  Use este método para automatizar la experiencia de inscripción en los dispositivos comprados a través de Apple Business Manager o Apple School Manager. La inscripción de dispositivos automatizada implementa el perfil de inscripción por vía inalámbrica, por lo que no es necesario tener acceso físico a los dispositivos. <br/><br/>Consulta [Inscripción automática de dispositivos macOS con Apple Business Manager o Apple School Manager](/mem/intune/enrollment/device-enrollment-program-enroll-macos). |
| Administrador de inscripción de dispositivos (DEM)  |  Use este método para implementaciones a gran escala y cuando haya varias personas en la organización que puedan ayudar con la configuración de la inscripción. Alguien con permisos de administrador de inscripción de dispositivos (DEM) puede inscribir hasta 1 000 dispositivos con una sola cuenta de Azure Active Directory. Este método usa la aplicación Portal de empresa o la aplicación Microsoft Intune para inscribir dispositivos. No puede usar una cuenta de DEM para inscribir dispositivos a través de la inscripción de dispositivos automatizada.<br/><br/> Consulte [Inscripción de dispositivos en Intune mediante una cuenta de administrador de inscripción de dispositivos](/mem/intune/enrollment/device-enrollment-manager-enroll).  |
| Inscripción directa  | La inscripción directa inscribe dispositivos sin afinidad de usuario, por lo que este método es el mejor para los dispositivos que no están asociados a un solo usuario. Este método requiere que tenga acceso físico a los equipos Mac que está inscribiendo. <br/><br/>Consulte [Uso de la inscripción directa para dispositivos macOS](/mem/intune/enrollment/device-enrollment-direct-enroll-macos).      |

#### <a name="ask-users-to-enroll-their-own-macos-devices-in-intune"></a>Pida a los usuarios que inscriban sus propios dispositivos macOS en Intune

Si su empresa prefiere que las personas inscriban sus propios dispositivos en Intune, pida a los usuarios que sigan estos pasos:

1. Vaya al sitio web de Portal de empresa ([https://portal.manage.microsoft.com/](https://portal.manage.microsoft.com/)) e inicie sesión.

2. Siga las instrucciones del sitio web de Portal de empresa para agregar su dispositivo.

3. Instale la aplicación Portal de empresa en [https://aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac)y siga las instrucciones de la aplicación.

### <a name="confirm-that-a-macos-device-is-onboarded"></a>Confirmación de que un dispositivo macOS está incorporado

1. Para confirmar que el dispositivo está asociado a su empresa, use el siguiente comando de Python en Bash: `mdatp health --field org_id`.

2. Si usa macOS 10.15 (Catalina) o posterior, conceda a Defender for Business el consentimiento para proteger el dispositivo. Vaya a **Preferencias** >  del **sistemaSeguridad &** **PrivacidadPrivacidadAcceso** >  >  al **disco**. Seleccione el icono de bloqueo para realizar cambios (en la parte inferior del cuadro de diálogo) y, a continuación, seleccione **Microsoft Defender para Empresas** (o **Defender para punto de conexión**, si es lo que ve).

3. Para comprobar que el dispositivo está incorporado, use el siguiente comando en Bash: `mdatp health --field real_time_protection_enabled`

4. Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Microsoft Defender para Empresas](mdb-create-edit-device-groups.md).

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos que se incorporan a Defender for Business, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, en **Puntos de conexión**, elija **Inventario de dispositivos**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña correspondiente al sistema operativo de los dispositivos ([Windows clientes, Windows Server, macOS o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Microsoft Defender para Empresas](mdb-configure-security-settings.md)
- Consulte [Comenzar con Microsoft Defender para Empresas](mdb-get-started.md).

## <a name="mobile-devices"></a>[**dispositivos móviles**](#tab/mobiles)

## <a name="mobile-devices"></a>Dispositivos móviles

Necesitará Microsoft Intune para incorporar dispositivos móviles, como dispositivos Android e iOS/iPadOS. Si tiene [Microsoft 365 Empresa Premium](../../business/index.yml), tiene Endpoint Manager como parte de la suscripción. Endpoint Manager incluye [funcionalidades de Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [mobile Administración de dispositivos](/mem/intune/fundamentals/what-is-device-management). 

Consulte los siguientes recursos para obtener ayuda para inscribir estos dispositivos en Intune:

- [Inscribir dispositivos Android](/mem/intune/enrollment/android-enroll)
- [Inscripción de dispositivos iOS o iPadOS](/mem/intune/enrollment/ios-enroll)

Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Microsoft Defender para Empresas](mdb-create-edit-device-groups.md).

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña correspondiente al sistema operativo de los dispositivos ([Windows clientes, Windows Server, macOS o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Microsoft Defender para Empresas](mdb-configure-security-settings.md)
- Consulte [Comenzar con Microsoft Defender para Empresas](mdb-get-started.md).
