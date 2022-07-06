---
title: Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Aprenda a incorporar y desconectar dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro
ms.openlocfilehash: a4f6928098525cf04c2e752b8c6d467800f270da
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635631"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-purview-solutions-using-jamf-pro"></a>Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro

Puede usar JAMF Pro para incorporar dispositivos macOS a soluciones de Microsoft Purview, como la prevención de pérdida de datos de punto de conexión.

> [!IMPORTANT]
> Use este procedimiento si ***no*** tiene Microsoft Defender para punto de conexión (MDE) implementados en los dispositivos macOS.

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que [los dispositivos macOS se administran a través de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) y están asociados a una identidad (UPN unido a Azure AD) a través de JAMF Connect o Intune.
- Instalar el explorador v95+ Edge en los dispositivos macOS

## <a name="onboard-devices-into-microsoft-purview-solutions-using-jamf-pro"></a>Incorporación de dispositivos a soluciones de Microsoft Purview mediante JAMF Pro

1. Necesitará estos archivos para este procedimiento.

|Archivo necesario para|Origen|
|---|---|
|Paquete de incorporación|Descargado del **paquete de incorporación** del portal de cumplimiento, nombre de archivo *DeviceComplianceOnboarding.plist*|
|Accesibilidad|[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso completo al disco|[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Filtro de red| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|Extensiones del sistema|[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|Preferencia de MDE|[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|Preferencias de MAU|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|Paquete de instalación|descargado desde el **paquete de instalación** del portal de cumplimiento, nombre *\*de archivo wdav.pkg*\*|

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o en [un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
>
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>Si alguno de estos archivos individuales se actualiza, deberá descargar el archivo combinado de nuevo o el archivo actualizado individualmente.

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso de varias fases.

### <a name="get-the-device-onboarding-package"></a>Obtención del paquete de incorporación de dispositivos

1. En **el Centro de cumplimiento** , abra **Configuración** > **Incorporación de** dispositivos y elija **Incorporación**.

1. En **Seleccionar sistema operativo para iniciar el proceso de incorporación**, elija **macOS**.

1. En **Método de implementación**, elija **Mobile Administración de dispositivos/Microsoft Intune**

1. Elija **Descargar paquete de incorporación**

1. Extraiga el contenido del paquete de incorporación de dispositivos. En la carpeta JAMF, debería ver el archivo *DeviceComplainceOnboarding.plist* .

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>Creación de un perfil de configuración de JAMF Pro para el paquete de incorporación

1. Cree un nuevo perfil de configuración en JAMF Pro. Consulte la [guía de administradores de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP onboarding for macOS`
    - Descripción: `MDATP EDR onboarding for macOS`
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

2. En la consola de JAMF Pro > **Aplicación & Configuración personalizada**, elija **Cargar** y, a continuación, **agregar**. Use este valor:
    - Dominio de preferencia: `com.microsoft.wdav.atp`

3. Elija **Cargar** y seleccione el archivo de incorporación **DeviceComplianceOnboarding.plist**.

4. Elija la pestaña **ámbito** .

5. Elija los equipos de destino.

6. Elija **Guardar**.

7. Seleccione **Listo**.

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>Configuración del dominio de preferencias mediante la consola de JAMF PRO

> [!IMPORTANT]
> Debe usar ***com.microsoft.wdav** _ como valor de dominio de preferencia. Microsoft Defender para punto de conexión usa este nombre y _ *_com.microsoft.wdav.ext_** para cargar su configuración administrada.

1. Cree un nuevo perfil de configuración en JAMF Pro. Consulte la [guía de administradores de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP MDAV configuration settings`
    - Descripción: deje esto en blanco.
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

1. En la pestaña **Application & Custom Settings (Configuración personalizada de la aplicación** ), elija **External Applications (Aplicaciones externas**), **Add (Agregar** ) y **Custom Schema (Esquema personalizado** ) para el dominio de preferencias. Use este valor:
    - Dominio de preferencia: `com.microsoft.wdav`

1. Elija **Agregar esquema** y **Cargar** para cargar el archivo *schema.json* .

1. Elija **Guardar**.

1. En **Propiedades de dominio de preferencia,** elija esta configuración.
    - Características
        - Uso de extensiones del sistema: `enabled` necesario para las extensiones de red en Catalina
        - Usar la prevención de pérdida de datos: `enabled`
    - El motor antivirus > modo pasivo: `true|false`. Use `true`si solo implementa DLP. Use `false` o no asigne un valor si implementa DLP y Microsoft Defender para punto de conexión (MDE).

1. Elija la pestaña **Ámbito** .

1. Elija los grupos en los que implementar este perfil de configuración.

1. Elija **Guardar**.

### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>Creación e implementación de un perfil de configuración para Microsoft AutoUpdate (MAU)

1. Cree un archivo de configuración JAMF Pro mediante **com.microsoft.autoupdate2.plist**. Consulte la [guía de administradores de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP MDAV MAU settings`
    - Descripción: `Microsoft AutoUPdate settings for MDATP for macOS`
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

1. En **Application & Custom Settings (Configuración personalizada)** elija **Upload and Add (Cargar** y **agregar).**

1. En **Preferencias dominio** escriba `com.microsoft.autoupdate2` y, a continuación, elija **Cargar**.

1. Elija el archivo **com.microsoft.autoupdate2.plist** .

1. Elija **Guardar**.

1. Elija la pestaña **Ámbito** .

1. Elija los equipos de destino.

1. Elija **Guardar**.

1. Seleccione **Listo**.

### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>Creación e implementación de un perfil de configuración para conceder acceso completo al disco

1. Use el archivo **fulldisk.mobileconfig** .

1. Cargue el archivo **fulldisk.mobileconfig** en JAMF. Consulte [Implementación de perfiles de configuración personalizados mediante JAMF Pro](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html).

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>Creación e implementación de un perfil de configuración para extensiones del sistema

1. Cree un archivo de configuración de JAMF Pro mediante los procedimientos descritos en la [guía de administradores de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP MDAV System Extensions`
    - Descripción: `MDATP system extensions`
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

1. En **Perfil de extensiones del sistema** , escriba estos valores:
    - Nombre para mostrar: `Microsoft Corp. System Extensions`
    - Tipos de extensión del sistema: `Allowed System Extensions`
    - Identificador de equipo: `UBF8T346G9`
    - Extensiones de sistema permitidas: `com.microsoft.wdav.epsext`, y `com.microsoft.wdav.netext`

1. Elija la pestaña **Ámbito** .

1. Elija los equipos de destino.

1. Elija **Guardar**.

1. Seleccione **Listo**.

### <a name="configure-network-extension"></a>Configuración de la extensión de red

1. Use el archivo **netfilter.mobileconfig**  que descargó de GitHub.

2. Cargue en JAMF como se describe en [Implementación de perfiles de configuración personalizados mediante Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

### <a name="grant-accessibility-access-to-dlp"></a>Concesión de acceso de accesibilidad a DLP

1. Use el archivo **accessibility.mobileconfig** que descargó de GitHub.

2. Cargue en JAMF como se describe en [Implementación de perfiles de configuración personalizados mediante Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

### <a name="get-the-installation-package"></a>Obtención del paquete de instalación

1. En **el Centro de cumplimiento** , abra **Configuración** > **Incorporación de** dispositivos y elija **Incorporación**.

1. En **Seleccionar sistema operativo para iniciar el proceso de incorporación**, elija **macOS**.

1. En **Método de implementación**, elija **Mobile Administración de dispositivos/Microsoft Intune**

1. Elija **Descargar paquete de instalación**. Esto le proporcionará el archivo *wdav.pkg* .

### <a name="deploy-the-installation-package"></a>Implementación del paquete de instalación

1. Vaya al lugar donde guardó el `wdav.pkg` archivo.

1. Abra el panel de JAMF Pro.

1. Seleccione el equipo y haga clic en el engranaje de la parte superior y, a continuación, elija **Administración de equipos**.

1. En **Paquetes** , elija **+Nuevo**. Escriba estos detalles:
    - Nombre para mostrar: deje en blanco porque se restablecerá al elegir el archivo .pkg.
    - Categoría: Ninguno (valor predeterminado)
    - Nombre de archivo: elija el archivo, en este caso el `wdav.pkg` archivo.

1. Elija **Abrir**. Establecer:
    - **Nombre para mostrar**: `Microsoft Endpoint Technology`
    - **Archivo de manifiesto**: no necesario
    - **Pestaña Opciones**: deje los valores predeterminados
    - **Pestaña Limitaciones**: deje los valores predeterminados

1. Elija **Guardar**. Esto carga el paquete en JAMF Pro.

1. Abra la página **Directivas** .

1. Elija **+Nuevo** para crear una nueva directiva.

1. Escriba estos valores.
    - **Nombre para mostrar**: `MDATP Onboarding200329 v100.86.92 or later`

1. Elija **Registro periódico**.

1. Elija **Guardar**.

1. Elija **Configuración de paquetes** > **.**

1. Seleccione **Agregar**.

1. Elija **Guardar**.

1. Elija la pestaña **Ámbito** .

1. Seleccione los equipos de destino.

1. Seleccione **Agregar**.

1. Elija **Autoservicio**.

1. Seleccione **Listo**.

### <a name="check-the-macos-device"></a>Comprobación del dispositivo macOS

1. Reinicie el dispositivo macOS.

1. Abra **Perfiles de preferencias del** >  sistema.

1. Debería ver lo siguiente:
    - Accesibilidad
    - Acceso completo al disco
    - MAU
    - Incorporación de MDATP
    - Preferencias de MDE
    - Perfil de administración
    - Filtro de red
    - Perfil de extensión del sistema

## <a name="offboard-macos-devices-using-jamf-pro"></a>Dispositivos macOS fuera del panel con JAMF Pro

1. Desinstale la aplicación (si no usa MDE)
    1. Consulte JAMF Pro Docs - Package Deployment - [JAMF Pro administrators guide](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)Jamf Pro Administrator's Guide

1. Reinicio del dispositivo macOS: algunas aplicaciones pueden perder la funcionalidad de impresión hasta que se reinician

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.
