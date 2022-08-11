---
title: Incorporación de dispositivos a Microsoft Defender para Empresas
description: Vea cómo incorporar dispositivos a Defender for Business para proteger los dispositivos desde el primer día.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/10/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: 3f69c82a6a401118d50372adec03b9cdbed0f502
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309403"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Incorporación de dispositivos a Microsoft Defender para Empresas

Con Defender para Empresas, tiene varias opciones entre las cuales elegir para incorporar los dispositivos de su empresa. En este artículo se le guiará por estas opciones y se proporciona información general sobre cómo funciona la incorporación.

## <a name="what-to-do"></a>Qué hacer

1. Seleccione una pestaña: 
   - **Windows 10 y 11**
   - **Mac**
   - **Servidores** (NUEVO! Windows Server o Linux Server)
   - **Móvil** (para dispositivos iOS/iPadOS o Android)
2. Vea las opciones de incorporación y siga las instrucciones de la pestaña seleccionada.
3. Continúe con los pasos siguientes.

## <a name="windows-10-and-11"></a>[**Windows 10 y 11**](#tab/Windows10and11)

## <a name="windows-10-and-11"></a>Windows 10 y 11

Elija una de las siguientes opciones para incorporar dispositivos cliente de Windows en Defender para Empresas:

- [Script local](#local-script-for-windows-10-and-11) (para la incorporación manual de dispositivos en el portal de Microsoft 365 Defender)
- [directiva de grupo](#group-policy-for-windows-10-and-11) (si ya usa directiva de grupo en su organización)
- [Microsoft Intune](#intune-for-windows-10-and-11)

### <a name="local-script-for-windows-10-and-11"></a>Script local para Windows 10 y 11

Puede usar un script local para incorporar dispositivos cliente Windows. Cuando se ejecuta el script de incorporación en un dispositivo, se crea una confianza con Azure Active Directory, si esa confianza aún no existe; inscribe el dispositivo en Microsoft Intune, si aún no está inscrito y, a continuación, incorpora el dispositivo a Defender for Business. El método de script local funciona incluso si actualmente no tiene Intune, y este es el método recomendado para los clientes de Defender para empresas.

> [!TIP]
> Se recomienda incorporar hasta 10 dispositivos a la vez cuando se usa el método de script local.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

3. Seleccione **Windows 10 y 11** y, a continuación, en la sección Método de **implementación**, elija **Script local**. 

4. Seleccione **Descargar el paquete de incorporación** Se recomienda guardar el paquete de incorporación en una unidad extraíble.

5. En un dispositivo Windows, extraiga el contenido del paquete de configuración en una ubicación, como la carpeta Escritorio. Debe tener un archivo denominado `WindowsDefenderATPLocalOnboardingScript.cmd`. 

6. Abra un símbolo del sistema como administrador.

7. Escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta Escritorio, escriba `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`y, a continuación, presione la tecla Entrar (o seleccione **Aceptar**).

8. Después de ejecutar el script, [ejecute una prueba de detección](#run-a-detection-test-on-a-windows-10-or-11-device).

### <a name="group-policy-for-windows-10-and-11"></a>directiva de grupo para Windows 10 y 11

Si prefieres usar directiva de grupo para incorporar clientes Windows, sigue las instrucciones de [Incorporación de dispositivos Windows mediante directiva de grupo](../defender-endpoint/configure-endpoints-gp.md). En este artículo se describen los pasos para la incorporación a Microsoft Defender para punto de conexión. Los pasos para la incorporación a Defender for Business son similares.

### <a name="intune-for-windows-10-and-11"></a>Intune para Windows 10 y 11

Puede incorporar clientes de Windows y otros dispositivos en Intune mediante el Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)). Hay varios métodos disponibles para inscribir dispositivos en Intune. Se recomienda usar uno de los métodos siguientes:

- [Habilitación de la inscripción automática de Windows para dispositivos administrados por la empresa o propiedad de la empresa](#enable-automatic-enrollment-for-windows-10-and-11)
- [Pida a los usuarios que inscriban sus propios dispositivos Windows 10/11 en Intune](#ask-users-enroll-their-own-windows-10-and-11-devices)

#### <a name="enable-automatic-enrollment-for-windows-10-and-11"></a>Habilitación de la inscripción automática para Windows 10 y 11

Al configurar la inscripción automática, los usuarios agregan su cuenta profesional al dispositivo. En segundo plano, el dispositivo se registra y se une a Azure Active Directory (Azure AD) y se inscribe en Intune.

1. Vaya a la Azure Portal ([https://portal.azure.com/](https://portal.azure.com/)) e inicie sesión.

2. Seleccione **Azure Active Directory** > **Mobility (MDM y MAM)** > **Microsoft Intune**.

3. Configure el **ámbito de usuario mdm** y el **ámbito de usuario mam**.

   :::image type="content" source="media/mem-mam-scope-azure-ad.png" alt-text="Captura de pantalla de la configuración del ámbito de usuario MDM y el ámbito de usuario MAM en Intune.":::

   - En ámbito de usuario de MDM, se recomienda seleccionar **Todo** para que todos los usuarios puedan inscribir automáticamente sus dispositivos Windows.
   - En la sección Ámbito de usuario de MAM, se recomiendan los siguientes valores predeterminados para las direcciones URL:

       - **URL de los términos de uso de MDM**
       - **URL de detección de MDM**
       - **URL de cumplimiento de MDM**

4. Seleccione **Guardar**.

5. Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos en Defender para empresas. [Obtenga más información sobre los grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

> [!TIP]
> Para obtener más información, consulta [Habilitar la inscripción automática de Windows](/mem/intune/enrollment/windows-enroll).

#### <a name="ask-users-enroll-their-own-windows-10-and-11-devices"></a>Pedir a los usuarios que inscriban sus propios dispositivos Windows 10 y 11

1. Vea el siguiente vídeo para ver cómo funciona la inscripción:<br/><br/>

   > [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]  

2. Comparta este artículo con los usuarios de su organización: [Inscriba dispositivos Windows 10/11 en Intune](/mem/intune/user-help/enroll-windows-10-device).

3. Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos en Defender para empresas. [Obtenga más información sobre los grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

### <a name="run-a-detection-test-on-a-windows-10-or-11-device"></a>Ejecución de una prueba de detección en un dispositivo Windows 10 o 11

Después de incorporar dispositivos Windows a Defender for Business, puede ejecutar una prueba de detección en el dispositivo para asegurarse de que todo funciona correctamente.

1. En el dispositivo Windows, cree una carpeta: `C:\test-MDATP-test`.

2. Abra un símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez que se ejecuta el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos incorporados a Defender for Business, vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En el panel de navegación, en **Puntos de conexión**, elija **Inventario de dispositivos**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña para esos dispositivos ([Windows 10 y 11, Mac, servidores o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Defender para empresas](mdb-configure-security-settings.md).
- Consulte [Introducción al uso de Defender para empresas](mdb-get-started.md).

## <a name="mac"></a>[**Mac**](#tab/mac)

## <a name="mac"></a>Mac

> [!NOTE]
> Se recomienda usar un [script local para incorporar Mac](#local-script-for-mac). Aunque puede [configurar la inscripción para Mac mediante Intune](/mem/intune/enrollment/macos-enroll), el script local es el método más sencillo para incorporar Mac a Defender for Business. 

Elija una de las siguientes opciones para incorporar Mac:

- [Script local para Mac](#local-script-for-mac) (*recomendado*)
- [Intune para Mac](#intune-for-mac)

### <a name="local-script-for-mac"></a>Script local para Mac

Cuando se ejecuta el script local en un Equipo Mac, se crea una confianza con Azure Active Directory, si esa confianza aún no existe; inscribe el Equipo Mac en Microsoft Intune, si aún no está inscrito y, a continuación, incorpora el Equipo Mac a Defender para empresas. Se recomienda incorporar hasta 10 dispositivos a la vez mediante este método.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

3. Seleccione **macOS**. En la sección **Método de implementación** , elija **Script local**. 

4. Seleccione **Descargar paquete de incorporación** y guárdelo en una unidad extraíble. También seleccione **Descargar paquete de instalación** y guárdelo en el dispositivo extraíble.

5. En un Equipo Mac, guarde el paquete de instalación en un `wdav.pkg` directorio local.

6. Guarde el paquete de incorporación como `WindowsDefenderATPOnboardingPackage.zip` en el mismo directorio que usó para el paquete de instalación.

7. Use Finder para navegar hasta usted guardado y, a `wdav.pkg` continuación, abrirlo.

8. Seleccione **Continuar**, acepte los términos de licencia y escriba la contraseña cuando se le solicite.

9. Se le pedirá que permita la instalación de un controlador desde Microsoft (ya sea "Extensión del sistema bloqueada" o "La instalación está en espera", o ambas). Debe permitir la instalación del controlador: seleccione **Abrir preferencias de seguridad** o **Abrir preferencias** >  del sistema **Seguridad & privacidad** y, a continuación, seleccione **Permitir**.

10. Use el siguiente comando de Python en Bash para ejecutar el paquete de incorporación: `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.sh`

Después de inscribir un Equipo Mac en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

### <a name="intune-for-mac"></a>Intune para Mac

Puede inscribir equipos Mac en Intune mediante el Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)). Hay varios métodos disponibles para inscribir Mac en Intune. Se recomienda uno de los métodos siguientes:

- [Elegir una opción para mac propiedad de la empresa](#options-for-company-owned-mac)
- [Pida a los usuarios que inscriban su propio Equipo Mac en Intune](#ask-users-to-enroll-their-own-mac-in-intune)

#### <a name="options-for-company-owned-mac"></a>Opciones para Mac propiedad de la empresa

Elija una de las siguientes opciones para inscribir dispositivos Mac administrados por la empresa en Intune:

| Opción  | Descripción  |
|---------|---------|
| Inscripción de dispositivo automatizada de Apple |  Use este método para automatizar la inscripción en dispositivos comprados a través de Apple Business Manager o Apple School Manager. La inscripción automatizada de dispositivos implementa el perfil de inscripción "por vía aérea", por lo que no es necesario tener acceso físico a los dispositivos. <br/><br/>Consulte [Inscripción automática de Mac con Apple Business Manager o Apple School Manager](/mem/intune/enrollment/device-enrollment-program-enroll-macos). |
| Administrador de inscripción de dispositivos (DEM)  |  Use este método para implementaciones a gran escala y cuando haya varias personas en la organización que puedan ayudar con la configuración de la inscripción. Alguien con permisos de administrador de inscripción de dispositivos (DEM) puede inscribir hasta 1 000 dispositivos con una sola cuenta de Azure Active Directory. Este método usa la aplicación Portal de empresa o la aplicación Microsoft Intune para inscribir dispositivos. No puede usar una cuenta de DEM para inscribir dispositivos a través de la inscripción de dispositivos automatizada.<br/><br/> Consulte [Inscripción de dispositivos en Intune mediante una cuenta de administrador de inscripción de dispositivos](/mem/intune/enrollment/device-enrollment-manager-enroll).  |
| Inscripción directa  | La inscripción directa inscribe dispositivos sin afinidad de usuario, por lo que este método es el mejor para los dispositivos que no están asociados a un solo usuario. Este método requiere que tenga acceso físico a los equipos Mac que está inscribiendo. <br/><br/>Consulte [Uso de la inscripción directa para Mac](/mem/intune/enrollment/device-enrollment-direct-enroll-macos).      |

#### <a name="ask-users-to-enroll-their-own-mac-in-intune"></a>Pida a los usuarios que inscriban su propio Equipo Mac en Intune

Si su empresa prefiere que las personas inscriban sus propios dispositivos en Intune, indique a los usuarios que sigan estos pasos:

1. Vaya al sitio web de Portal de empresa ([https://portal.manage.microsoft.com/](https://portal.manage.microsoft.com/)) e inicie sesión.

2. Siga las instrucciones del sitio web de Portal de empresa para agregar su dispositivo.

3. Instale la aplicación Portal de empresa en [https://aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac)y siga las instrucciones de la aplicación.

### <a name="confirm-that-a-mac-is-onboarded"></a>Confirmación de que un Equipo Mac está incorporado

1. Para confirmar que el dispositivo está asociado a su empresa, use el siguiente comando de Python en Bash:

   `mdatp health --field org_id`.

2. Si usa macOS 10.15 (Catalina) o una versión posterior, conceda a Defender for Business el consentimiento para proteger el dispositivo. Vaya a **Preferencias** >  del sistema **Seguridad &** > **Privacidad Acceso** > **total al disco**. Seleccione el icono de bloqueo en la parte inferior del cuadro de diálogo para realizar cambios y, a continuación, seleccione **Microsoft Defender para Empresas** (o **Defender para punto de conexión**, si es lo que ve).

3. Para comprobar que el dispositivo está incorporado, use el siguiente comando en Bash:

   `mdatp health --field real_time_protection_enabled`

Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos incorporados a Defender for Business, vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En el panel de navegación, en **Puntos de conexión**, elija **Inventario de dispositivos**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña para esos dispositivos ([Windows 10 y 11, Mac, servidores o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Defender para empresas](mdb-configure-security-settings.md).
- Consulte [Introducción al uso de Defender para empresas](mdb-get-started.md).

## <a name="servers"></a>[**Servidores**](#tab/Servers)

## <a name="servers"></a>Servidores

> [!NOTE]
> **La capacidad de incorporar un servidor está actualmente en versión preliminar**.

Elija el sistema operativo del servidor:

- [Windows Server](#windows-server)
- [Servidor Linux](#linux-server)

## <a name="windows-server"></a>Windows Server

> [!IMPORTANT]
> **La capacidad de incorporar puntos de conexión de Windows Server está actualmente en versión preliminar**. Asegúrese de cumplir los siguientes requisitos antes de incorporar un punto de conexión de Windows Server:
> - La opción **Características en versión preliminar** activada. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), vaya a **Configuración** > **Puntos de conexión** > **General** > **Características avanzadas** > **Características en versión preliminar**.
> - El ámbito de cumplimiento de Windows Server está activado. Vaya a **Configuración** > **Puntos de conexión** > **Administración de configuración** > **Ámbito de cumplimiento**. Seleccione **Usar MDE para aplicar la configuración de seguridad desde MEM**, seleccione  **Windows Server** y, luego, **Guardar**.

Puede incorporar una instancia de Windows Server a Defender para empresas mediante un script local.

### <a name="local-script-for-windows-server"></a>Script local para Windows Server

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Settings** > **Endpoints**, y, a continuación, en **Management**, elige **Incorporación**.

3. Seleccione un sistema operativo, como **Windows Server 1803, 2019 y 2022**, y, a continuación, en la sección **Método de implementación** , elija **Script local**. 

   Si selecciona **Windows Server 2012 R2 y 2016**, tendrá dos paquetes para descargar y ejecutar: un paquete de instalación y un paquete de incorporación. El paquete de instalación contiene un archivo MSI que instala el agente de Defender para empresas. El paquete de incorporación contiene el script para incorporar el punto de conexión de Windows Server a Defender para empresas.

4. Seleccione **Descargar el paquete de incorporación** Se recomienda guardar el paquete de incorporación en una unidad extraíble.

   Si seleccionó **Windows Server 2012 R2 y 2016**, seleccione también **Descargar paquete de instalación** y guarde el paquete en una unidad extraíble.

5. En el punto de conexión de Windows Server, extraiga el contenido del paquete de instalación o incorporación en una ubicación como la carpeta Escritorio. Debe tener un archivo denominado `WindowsDefenderATPLocalOnboardingScript.cmd`. 

   Si va a incorporar Windows Server 2012 R2 o Windows Server 2016, extraiga primero el paquete de instalación.

6. Abra un símbolo del sistema como administrador.

7. Si va a incorporar Windows Server 2012R2 o Windows Server 2016, ejecute el siguiente comando:

   `Msiexec /i md4ws.msi /quiet` 

   Si va a incorporar Windows Server 1803, 2019 o 2022, omita este paso y vaya al paso 8.

8. Escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta Escritorio, escriba `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`y, a continuación, presione Entrar (o seleccione **Aceptar**).

9. Vaya a [Ejecutar una prueba de detección en Windows Server](#run-a-detection-test-on-windows-server).

### <a name="run-a-detection-test-on-windows-server"></a>Ejecución de una prueba de detección en Windows Server

Después de incorporar el punto de conexión de Windows Server a Defender for Business, puede ejecutar una prueba de detección para asegurarse de que todo funciona correctamente:

1. En el dispositivo Windows Server, cree una carpeta: `C:\test-MDATP-test`.

2. Abra un símbolo del sistema como administrador.

3. En la ventana símbolo del sistema, ejecute el siguiente comando de PowerShell:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Una vez que se ejecuta el comando, la ventana del símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) para el dispositivo recién incorporado en unos 10 minutos.

## <a name="linux-server"></a>Servidor Linux

> [!IMPORTANT]
> **La capacidad de incorporar puntos de conexión de Servidor Linux está actualmente en versión preliminar**. Asegúrese de cumplir los siguientes requisitos antes de incorporar un punto de conexión de Servidor Linux:
> - La opción **Características en versión preliminar** activada. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), vaya a **Configuración** > **Puntos de conexión** > **General** > **Características avanzadas** > **Características en versión preliminar**.
> - Cumple los [requisitos previos para Microsoft Defender para punto de conexión en Linux](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites).

### <a name="onboard-linux-server-endpoints"></a>Incorporación de puntos de conexión del servidor Linux

Puede usar los métodos siguientes para incorporar una instancia de Linux Server a Defender for Business:

- **Script local:** Consulte [Implementación manual de Microsoft Defender para punto de conexión en Linux](../defender-endpoint/linux-install-manually.md).
- **Ansible:** Consulte [Implementación de Microsoft Defender para punto de conexión en Linux con Ansible](../defender-endpoint/linux-install-with-ansible.md).
- **Chef:** Consulte [Implementación de Defender para punto de conexión en Linux con Chef](../defender-endpoint/linux-deploy-defender-for-endpoint-with-chef.md).
- **Marioneta:** Consulte [Implementación de Microsoft Defender para punto de conexión en Linux con Puppet](../defender-endpoint/linux-install-with-puppet.md).

> [!NOTE]
> La incorporación de una instancia de Linux Server a Defender for Business es lo mismo que la incorporación a [Microsoft Defender para punto de conexión en Linux](../defender-endpoint/microsoft-defender-endpoint-linux.md).

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos incorporados a Defender for Business, vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En el panel de navegación, en **Puntos de conexión**, elija **Inventario de dispositivos**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña para esos dispositivos ([Windows 10 y 11, Mac, servidores o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Defender para empresas](mdb-configure-security-settings.md).
- Consulte [Introducción al uso de Defender para empresas](mdb-get-started.md).

## <a name="mobile-devices"></a>[**Dispositivos móviles**](#tab/mobiles)

## <a name="mobile-devices"></a>Dispositivos móviles

Puede usar Microsoft Intune para incorporar dispositivos móviles, como dispositivos Android e iOS/iPadOS. Consulte los siguientes recursos para obtener ayuda para inscribir estos dispositivos en Intune:

- [Inscribir dispositivos Android](/mem/intune/enrollment/android-enroll)
- [Inscribir dispositivos iOS o iPadOS](/mem/intune/enrollment/ios-enroll)

Después de inscribir un dispositivo en Intune, puede agregarlo a un grupo de dispositivos. [Obtenga más información sobre los grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

## <a name="view-a-list-of-onboarded-devices"></a>Ver una lista de dispositivos incorporados

Para ver la lista de dispositivos incorporados a Defender for Business, vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En el panel de navegación, en **Puntos de conexión**, elija **Inventario de dispositivos**.

## <a name="next-steps"></a>Siguientes pasos

- Si tiene otros dispositivos que incorporar, seleccione la pestaña para esos dispositivos ([Windows 10 y 11, Mac, servidores o dispositivos móviles](#what-to-do)) y siga las instrucciones de esa pestaña.
- Si ha terminado de incorporar dispositivos, vaya al [Paso 5: Configurar las directivas y las opciones de seguridad en Defender para empresas](mdb-configure-security-settings.md).
- Consulte [Introducción al uso de Defender para empresas](mdb-get-started.md).
