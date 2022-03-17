---
title: Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante JAMF Pro (versión preliminar)
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
description: Obtenga información sobre cómo incorporar y quitar dispositivos macOS en las soluciones de cumplimiento Microsoft 365 con JAMF Pro (versión preliminar)
ms.openlocfilehash: e66c9ba88e7c829af3695675a72e264da17e7dc4
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525255"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview"></a>Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante JAMF Pro (versión preliminar)

Puede usar jamf Pro para incorporar dispositivos macOS en soluciones de cumplimiento Microsoft 365 como la prevención de pérdida de datos de punto de conexión.

> [!IMPORTANT]
> Use este procedimiento si ***no tiene*** Microsoft Defender para endpoint (MDE) implementado en sus dispositivos macOS

**Se aplica a:**

- [Prevención de pérdida de datos en punto de conexión en Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que los [dispositivos macOS](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) se administran a través de JAMF pro y que están asociados con una identidad (Azure AD UPN unida) a través de JAMF Conectar o Intune.
- Instalar el explorador perimetral v95+ en los dispositivos macOS 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>Incorporar dispositivos a Microsoft 365 de cumplimiento con jamf Pro

1. Necesitará estos archivos para este procedimiento.

|Archivo necesario para |Origen |
|---------|---------|
|Paquete de incorporación    |Descargado del paquete de **incorporación del portal** de cumplimiento, nombre de archivo *DeviceComplianceOnboarding.plist* |
|accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso en disco completo     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Filtro de red| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|Extensiones del sistema |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|Preferencia de MDE     |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|Preferencia MAU|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|Paquete de instalación     |descargado del paquete de instalación del portal **de cumplimiento**, nombre de *\*archivo wdav.pkg*\* |

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o [en un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>Si alguno de estos archivos individuales se actualiza, deberá volver a descargar el archivo combinado o el archivo actualizado individualmente.

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso multifase.

### <a name="get-the-device-onboarding-package"></a>Obtener el paquete de incorporación de dispositivos

1. En **el Centro de** cumplimiento **, Configuración** >  **Incorporación de dispositivos y** elija **Incorporación**.
 
1. Para **Seleccionar sistema operativo para iniciar el proceso de incorporación** , elija **macOS**
 
1. Para **el método Deployment**, **elija Administración de dispositivos móviles/Microsoft Intune**
 
1. Elija **Descargar paquete de incorporación**
 
1. Extrae el contenido del paquete de incorporación de dispositivos. En la carpeta JAMF, debería ver el archivo *DeviceComplainceOnboarding.plist* .

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>Crear un perfil de configuración Pro JAMF para el paquete de incorporación

1. Cree un nuevo perfil de configuración en JAMF Pro. Consulte la guía [de administradores Pro JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP onboarding for macOS`
    - Descripción: `MDATP EDR onboarding for macOS`
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

2. En la consola Pro JAMF > **Configuración & personalizada**, elija **Cargar** y, a **continuación, agregar**. Use este valor:
    - Dominio de preferencia: `com.microsoft.wdav.atp`

3. Elija **cargar** y seleccionar el archivo de incorporación **DeviceComplianceOnboarding.plist**.

4. Elija la **pestaña ámbito** .

5. Elija los equipos de destino.

6. Seleccione **Guardar**.

7. Seleccione **Listo**.

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>Configurar el dominio de preferencia mediante la consola JAMF PRO

> [!IMPORTANT]
> Debe usar ***com.microsoft.wdav** _ como el valor dominio de preferencia. Microsoft Defender para endpoint usa este nombre y _ *_com.microsoft.wdav.ext_** para cargar su configuración administrada.

1. Cree un nuevo perfil de configuración en JAMF Pro. Consulte la guía [de administradores Pro JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP MDAV configuration settings`
    - Descripción: deje esto en blanco
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

1. En la **pestaña & personalizado Configuración**, elija **Aplicaciones** externas, elija **Agregar** y elija **Esquema** personalizado para el dominio de preferencia. Use este valor:
    - Dominio de preferencia: `com.microsoft.wdav`

1. Elija **Agregar esquema** **y Upload** para cargar el *archivo schema.json*.

1. Seleccione **Guardar**.

1. En **Propiedades de dominio de preferencia** , elija esta configuración
    - Características 
        - Use System Extensions: `enabled` - required for network extensions on Catalina
        - Usar prevención de pérdida de datos: `enabled`
    - El motor antivirus > modo pasivo: `true|false`. Se `true`usa si solo se implementa DLP. Use `false` o no asigne un valor si implementa DLP y Microsoft Defender para endpoint (MDE).

1. Elija la **pestaña** Ámbito.

1. Elija los grupos en los que desea implementar este perfil de configuración.

1. Seleccione **Guardar**. 


### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>Crear e implementar un perfil de configuración para Microsoft AutoUpdate (MAU)

1. Cree un archivo de configuración Pro JAMF con **com.microsoft.autoupdate2.plist**. Consulte la guía [de administradores Pro JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
    - Nombre: `MDATP MDAV MAU settings`
    - Descripción: `Microsoft AutoUPdate settings for MDATP for macOS`
    - Categoría: `none`
    - Método de distribución: `install automatically`
    - Nivel: `computer level`

1. En **Application & Custom Configuración** elija **Upload** y **Agregar**.

1. En **Preferencias,** escriba `com.microsoft.autoupdate2` Dominio y, **a continuación, elija Upload**.

1. Elija el **archivo com.microsoft.autoupdate2.plist** .

1. Seleccione **Guardar**.

1. Elija la **pestaña** Ámbito.

1. Elija los equipos de destino.

1. Seleccione **Guardar**.

1. Seleccione **Listo**.


### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>Crear e implementar un perfil de configuración para conceder acceso a disco completo

1. Use el **archivo fulldisk.mobileconfig** .

1. Upload el **archivo fulldisk.mobileconfig** a JAMF. Consulte [Deploying Custom Configuration Profiles using JAMF Pro](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html).

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>Crear e implementar un perfil de configuración para extensiones del sistema

1. Cree un archivo de configuración Pro JAMF mediante los procedimientos de la guía de [administradores Pro JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/). Use estos valores:
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

1. Elija la **pestaña** Ámbito.

1. Elija los equipos de destino.

1. Seleccione **Guardar**.

1. Seleccione **Listo**.

### <a name="configure-network-extension"></a>Configurar extensión de red

1.  Use el **archivo netfilter.mobileconfig** que descargó de GitHub.

2.  Upload a JAMF como se describe en [Implementar perfiles de configuración personalizados con Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

### <a name="grant-accessibility-access-to-dlp"></a>Conceder acceso de accesibilidad a DLP

1. Use el **archivo accessibility.mobileconfig** que descargó de GitHub.

2.  Upload a JAMF como se describe en [Implementar perfiles de configuración personalizados con Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

### <a name="get-the-installation-package"></a>Obtener el paquete de instalación

1. En **el Centro de** cumplimiento **, Configuración** >  **Incorporación de dispositivos y** elija **Incorporación**.
 
1. Para **Seleccionar sistema operativo para iniciar el proceso de incorporación** , elija **macOS**
 
1. Para **el método Deployment**, **elija Administración de dispositivos móviles/Microsoft Intune**
 
1. Elija **Descargar paquete de instalación**. Esto le dará el *archivo wdav.pkg* .


### <a name="deploy-the-installation-package"></a>Implementar el paquete de instalación

1. Navegue hasta donde guardó el `wdav.pkg` archivo.

1. Abra el panel de Pro JAMF.

1. Seleccione el equipo y haga clic en el engranaje de la parte superior y, a continuación, elija **Administración del equipo**.

1. En **Paquetes** , **elija +Nuevo**. Escriba estos detalles:
    - Nombre para mostrar: deje en blanco porque se restablecerá cuando elija el archivo .pkg.
    - Categoría: Ninguno (predeterminado)
    - Nombre de archivo: elija archivo, en este caso el `wdav.pkg` archivo.

1. Elija **Abrir**. Establecer:
    - **Nombre para mostrar**: `Microsoft Endpoint Technology`
    - **Archivo de manifiesto**: no obligatorio
    - **Ficha Opciones**: dejar los valores predeterminados
    - **Pestaña Limitaciones**: dejar los valores predeterminados

1. Seleccione **Guardar**. Esto carga el paquete en JAMF Pro.

1. Abra la **página Directivas** .

1. Elija **+Nuevo** para crear una nueva directiva.

1. Escriba estos valores
    - **Nombre para mostrar**: `MDATP Onboarding200329 v100.86.92 or later`

1. Elija **Check-in periódico**.

1. Seleccione **Guardar**.

1. Elija **PackagesConfigure** > .

1. Seleccione **Agregar**.

1. Seleccione **Guardar**. 

1. Elija la **pestaña** Ámbito.

1. Seleccione los equipos de destino.

1. Seleccione **Agregar**.

1. Elija **Autoservicio**.

1. Seleccione **Listo**.

### <a name="check-the-macos-device"></a>Comprobar el dispositivo macOS 

1. Reinicie el dispositivo macOS.

1. Abra **Preferencias** >  **del sistemaProfiles**.

1. Debería ver:
    - Accessiblity
    - Acceso en disco completo
    - MAU
    - Incorporación de MDATP
    - Preferencias de MDE
    - Perfil de administración
    - Filtro de red
    - Perfil de extensión del sistema

## <a name="offboard-macos-devices-using-jamf-pro"></a>Dispositivos macOS fuera de la pantalla con JAMF Pro

1. Desinstalar la aplicación (si no usa MDE)
    1. Consulte JAMF Pro Docs - Package Deployment - [JAMF Pro administrators guideJamf](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) Pro Administrator's Guide

1. Reiniciar el dispositivo macOS: algunas aplicaciones pueden perder la funcionalidad de impresión hasta que se reinician

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.
