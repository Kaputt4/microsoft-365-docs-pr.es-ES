---
title: Implementación basada en Intune para Microsoft Defender para punto de conexión en Mac
description: Instale Microsoft Defender para punto de conexión en Mac con Microsoft Intune.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4c2c1f7c11c57ca45411b74023807077f73ba8bf
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66044114"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Implementación basada en Intune para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En este tema se describe cómo implementar Microsoft Defender para punto de conexión en macOS a través de Intune. Una implementación correcta requiere la finalización de todos los pasos siguientes:

1. [Descarga del paquete de incorporación](#download-the-onboarding-package)
1. [Configuración del dispositivo cliente](#client-device-setup)
1. [Aprobación de extensiones del sistema](#approve-system-extensions)
1. [Creación de perfiles de configuración del sistema](#create-system-configuration-profiles)
1. [Publicar aplicación](#publish-application)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte [la Microsoft Defender para punto de conexión principal en macOS página](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

## <a name="overview"></a>Información general

En la tabla siguiente se resumen los pasos que tendría que seguir para implementar y administrar Microsoft Defender para punto de conexión en Mac, a través de Intune. Los pasos más detallados están disponibles a continuación.

<br>

****

|Paso|Nombres de archivo de ejemplo|BundleIdentifier|
|---|---|---|
|[Descarga del paquete de incorporación](#download-the-onboarding-package)|WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml|com.microsoft.wdav.atp|
|[Aprobación de la extensión del sistema para Microsoft Defender para punto de conexión](#approve-system-extensions)|MDATP_SysExt.xml|N/D|
|[Aprobación de la extensión del kernel para Microsoft Defender para punto de conexión](#download-the-onboarding-package)|MDATP_KExt.xml|N/D|
|[Conceder acceso completo al disco a Microsoft Defender para punto de conexión](#full-disk-access)|MDATP_tcc_Catalina_or_newer.xml|com.microsoft.wdav.tcc|
|[Directiva de extensión de red](#network-filter)|MDATP_NetExt.xml|N/D|
|[Configuración de Microsoft AutoUpdate (MAU)](mac-updates.md#intune)|MDATP_Microsoft_AutoUpdate.xml|com.microsoft.autoupdate2|
|[configuración de Microsoft Defender para punto de conexión](mac-preferences.md#intune-full-profile) <p> **Nota:** Si tiene previsto ejecutar un antivirus de terceros para macOS, establezca en `passiveMode` `true`.|MDATP_WDAV_and_exclusion_settings_Preferences.xml|com.microsoft.wdav|
|[Configuración de notificaciones Microsoft Defender para punto de conexión y MS AutoUpdate (MAU)](mac-updates.md)|MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig|com.microsoft.autoupdate2 o com.microsoft.wdav.tray|
|

## <a name="download-the-onboarding-package"></a>Descarga del paquete de incorporación

Descargue los paquetes de incorporación desde Microsoft 365 Defender portal:

1. En Microsoft 365 Defender portal, vaya a **Configuración** \> **Endpoints** \> **Device management** **Onboarding (Incorporación** de administración \> de dispositivos de puntos de conexión).

2. Establezca el sistema operativo en **macOS** y el método de implementación **en Mobile Administración de dispositivos/Microsoft Intune**.

   :::image type="content" source="images/macos-install-with-intune.png" alt-text="Página Configuración de incorporación" lightbox="images/macos-install-with-intune.png":::

3. Seleccione **Descargar el paquete de incorporación** Guárdelo como _WindowsDefenderATPOnboardingPackage.zip_ en el mismo directorio.

4. Extraiga el contenido del archivo .zip:

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```

    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a>Creación de perfiles de configuración del sistema

El siguiente paso consiste en crear perfiles de configuración del sistema que Microsoft Defender para punto de conexión necesidades.
En el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/), abra **Perfiles de configuración de dispositivos**\>.

### <a name="onboarding-blob"></a>Incorporación de blobs

Este perfil contiene información de licencia para Microsoft Defender para punto de conexión. Sin este perfil, Microsoft Defender para punto de conexión notificará que no tiene licencia.

1. Seleccione **Crear perfil** en **Perfiles de configuración**.
1. Seleccione **Plataforma**= **macOS**, **Plantillas de tipo**= de perfil **.** **Nombre**= de plantilla **Personalizado**. Haga clic en **Crear**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-1.png" alt-text="Página de creación del perfil de configuración personalizada" lightbox="images/mdatp-6-systemconfigurationprofiles-1.png":::

1. Elija un nombre para el perfil, por ejemplo, "Defender for Cloud o Incorporación de puntos de conexión para macOS". Haga clic en **Siguiente**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-2.png" alt-text="Campo Nombre del perfil de configuración personalizado" lightbox="images/mdatp-6-systemconfigurationprofiles-2.png":::

1. Elija un nombre para el nombre del perfil de configuración, por ejemplo, "Incorporación de Defender para punto de conexión para macOS".
1. Elija un [canal de implementación](/mem/intune/fundamentals/whats-new#new-deployment-channel-setting-for-custom-device-configuration-profiles-on-macos-devices).
1. Seleccione intune/WindowsDefenderATPOnboarding.xml que extrajo del paquete de incorporación anterior como archivo de perfil de configuración.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles.png" alt-text="Importación de una configuración desde un archivo para el perfil de configuración personalizado" lightbox="images/mdatp-6-systemconfigurationprofiles.png":::

1. Haga clic en **Siguiente**.
1. Asigne dispositivos en la pestaña **Asignación** . Haga clic en **Siguiente**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-2.png" alt-text="Perfil de configuración personalizado: asignación" lightbox="images/mdatp-6-systemconfigurationprofiles-2.png":::

1. Revisar y **crear**.
1. Abra Los **perfiles de configuración** de **dispositivos**\>, puede ver el perfil creado allí.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-3.png" alt-text="Finalización del perfil de configuración personalizado" lightbox="images/mdatp-6-systemconfigurationprofiles-3.png":::

### <a name="approve-system-extensions"></a>Aprobar extensiones del sistema

Este perfil es necesario para macOS 10.15 (Catalina) o posterior. Se omitirá en macOS anteriores.

1. Seleccione **Crear perfil** en **Perfiles de configuración**.
1. Seleccione **Plataforma**= **macOS**, **Plantillas de tipo**= de perfil **.** **Nombre**= de plantilla **Extensiones**. Haga clic en **Crear**.
1. En la pestaña **Aspectos básicos** , asigne un nombre a este nuevo perfil.
1. En la pestaña **Configuración** , expanda **Extensiones del sistema** y agregue las siguientes entradas en la sección **Extensiones de sistema permitidas** :

    |Identificador de agrupación|Identificador de equipo|
    |---|---|
    |com.microsoft.wdav.epsext|UBF8T346G9|
    |com.microsoft.wdav.netext|UBF8T346G9|

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mac-system-extension-intune2.png" alt-text="La configuración de la extensión del sistema" lightbox="images/mac-system-extension-intune2.png":::

1. En la pestaña **Asignaciones** , asigne este perfil a **Todos los usuarios & Todos los dispositivos**.
1. Revise y cree este perfil de configuración.

### <a name="kernel-extensions"></a>Extensiones de kernel

Este perfil es necesario para macOS 10.15 (Catalina) o posterior. Se omitirá en macOS más recientes.

> [!CAUTION]
> Los dispositivos Apple Silicon (M1) no admiten KEXT. Se producirá un error en la instalación de un perfil de configuración que consta de directivas KEXT en estos dispositivos.

1. Seleccione **Crear perfil** en **Perfiles de configuración**.
1. Seleccione **Plataforma**= **macOS**, **Plantillas de tipo**= de perfil **.** **Nombre**= de plantilla **Extensiones**. Haga clic en **Crear**.
1. En la pestaña **Aspectos básicos** , asigne un nombre a este nuevo perfil.
1. En la pestaña **Configuración** , expanda **Extensiones de kernel**.
1. Establezca **Identificador de equipo** en **UBF8T346G9** y haga clic en **Siguiente**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mac-kernel-extension-intune2.png" alt-text="Identificadores de equipo permitidos para las extensiones de kernel." lightbox="images/mac-kernel-extension-intune2.png":::

1. En la pestaña **Asignaciones** , asigne este perfil a **Todos los usuarios & Todos los dispositivos**.
1. Revise y cree este perfil de configuración.

### <a name="full-disk-access"></a>Acceso completo al disco

   > [!CAUTION]
   > macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como documentos, descargas, escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para punto de conexión no puede proteger completamente el dispositivo.
   >
   > Este perfil de configuración concede acceso total al disco a Microsoft Defender para punto de conexión. Si anteriormente configuró Microsoft Defender para punto de conexión a través de Intune, se recomienda actualizar la implementación con este perfil de configuración.

Descargue [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) desde [nuestro repositorio de GitHub](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).

Siga las instrucciones de [Incorporación de blobs](#onboarding-blob) desde arriba, con "Acceso a disco completo de Defender para punto de conexión" como nombre de perfil y ha descargado **fulldisk.mobileconfig** como nombre del perfil de configuración.

### <a name="network-filter"></a>Filtro de red

Como parte de las funcionalidades de detección y respuesta de puntos de conexión, Microsoft Defender para punto de conexión en macOS inspecciona el tráfico de socket e informa de esta información al portal de Microsoft 365 Defender. La siguiente directiva permite que la extensión de red realice esta funcionalidad.

Descargue [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) desde [nuestro repositorio de GitHub](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).

Siga las instrucciones de [Incorporación de blobs](#onboarding-blob) desde arriba, con "Filtro de red de Defender para punto de conexión" como nombre de perfil y **netfilter.mobileconfig** descargado como nombre del perfil de configuración.

### <a name="notifications"></a>Notificaciones

Este perfil se usa para permitir que Microsoft Defender para punto de conexión en macOS y Microsoft Auto Update muestren notificaciones en la interfaz de usuario en macOS 10.15 (Catalina) o versiones posteriores.

Descargue [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) desde [nuestro repositorio de GitHub](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).

Siga las instrucciones de [Incorporación del blob](#onboarding-blob) desde arriba, con "Notificaciones de Defender para punto de conexión" como nombre de perfil y **notif.mobileconfig** descargado como nombre del perfil de configuración.

### <a name="view-status"></a>Ver estado

Una vez que los cambios de Intune se propaguen a los dispositivos inscritos, puede verlos en Monitor Device status (**Supervisar** \> **estado del dispositivo**):

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/mdatp-7-devicestatusblade.png" alt-text="Vista del estado del dispositivo" lightbox="images/mdatp-7-devicestatusblade.png":::

## <a name="publish-application"></a>Publicar aplicación

Este paso permite implementar Microsoft Defender para punto de conexión en máquinas inscritas.

1. En el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/), abra **Aplicaciones**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-8-app-before.png" alt-text="Página de información general de la aplicación" lightbox="images/mdatp-8-app-before.png":::

1. Seleccione Por plataforma > macOS > Agregar.
1. Elija **Tipo**= de aplicación **macOS**, haga clic en **Seleccionar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-9-app-type.png" alt-text="El tipo de aplicación específico" lightbox="images/mdatp-9-app-type.png":::

1. Mantenga los valores predeterminados, haga clic en **Siguiente**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-10-properties.png" alt-text="Página de propiedades de la aplicación" lightbox="images/mdatp-10-properties.png":::

1. Agregue asignaciones y haga clic en **Siguiente**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-11-assignments.png" alt-text="Página de información de asignaciones de Intune" lightbox="images/mdatp-11-assignments.png":::

1. Revisar y **crear**.
1. Puede visitar **Aplicaciones** \> **por plataforma** \> **macOS** para verlo en la lista de todas las aplicaciones.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-12-applications.png" alt-text="Página de listas de aplicaciones" lightbox="images/mdatp-12-applications.png":::

Para obtener más información, vea [Agregar Microsoft Defender para punto de conexión a dispositivos macOS mediante Microsoft Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)).

   > [!CAUTION]
   > Debe crear todos los perfiles de configuración necesarios e insertarlos en todas las máquinas, como se explicó anteriormente.

## <a name="client-device-setup"></a>Configuración del dispositivo cliente

No necesita ningún aprovisionamiento especial para un dispositivo Mac más allá de una [instalación Portal de empresa](/intune-user-help/enroll-your-device-in-intune-macos-cp) estándar.

1. Confirme la administración de dispositivos.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-3-confirmdevicemgmt.png" alt-text="La página Confirmar administración de dispositivos" lightbox="images/mdatp-3-confirmdevicemgmt.png":::

    Seleccione **Abrir preferencias del sistema**, busque **Perfil de administración** en la lista y seleccione **Aprobar...**. El perfil de administración se mostraría como **Comprobado**:

    :::image type="content" source="images/mdatp-4-managementprofile.png" alt-text="Página Perfil de administración" lightbox="images/mdatp-4-managementprofile.png":::

2. Seleccione **Continuar** y complete la inscripción.

   Ahora puede inscribir más dispositivos. También puede inscribirlos más adelante, una vez que haya terminado de aprovisionar la configuración del sistema y los paquetes de aplicación.

3. En Intune, abra **Administrar** \> **dispositivos** \> **Todos los dispositivos**. Aquí puede ver el dispositivo entre los que aparecen:

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mdatp-5-alldevices.png" alt-text="Página Todos los dispositivos" lightbox="images/mdatp-5-alldevices.png":::

## <a name="verify-client-device-state"></a>Comprobación del estado del dispositivo cliente

1. Una vez implementados los perfiles de configuración en los dispositivos, abra **Perfiles** de **preferencias** \> del sistema en el dispositivo Mac.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-13-systempreferences.png" alt-text="Página Preferencias del sistema" lightbox="images/mdatp-13-systempreferences.png":::

   :::image type="content" source="images/mdatp-14-systempreferencesprofiles.png" alt-text="Página Perfiles de preferencias del sistema" lightbox="images/mdatp-14-systempreferencesprofiles.png":::

2. Compruebe que los siguientes perfiles de configuración están presentes e instalados. El **perfil de administración** debe ser el perfil del sistema Intune. _Wdav-config_ y _wdav-kext_ son perfiles de configuración del sistema que se agregaron en Intune:

   :::image type="content" source="images/mdatp-15-managementprofileconfig.png" alt-text="Página Perfiles" lightbox="images/mdatp-15-managementprofileconfig.png":::

3. También debería ver el icono de Microsoft Defender para punto de conexión en la esquina superior derecha:

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-icon-bar.png" alt-text="Icono de Microsoft Defender para punto de conexión en la barra de estado" lightbox="images/mdatp-icon-bar.png":::

## <a name="troubleshooting"></a>Solución de problemas

Problema: no se encontró ninguna licencia.

Solución: siga los pasos anteriores para crear un perfil de dispositivo mediante WindowsDefenderATPOnboarding.xml.

## <a name="logging-installation-issues"></a>Problemas de instalación de registro

Para obtener más información sobre cómo buscar el registro generado automáticamente que crea el instalador cuando se produce un error, consulte [Problemas de instalación de registro](mac-resources.md#logging-installation-issues).

## <a name="uninstallation"></a>Desinstalación

Consulte [Desinstalación](mac-resources.md#uninstalling) para obtener más información sobre cómo quitar Microsoft Defender para punto de conexión en macOS de dispositivos cliente.
