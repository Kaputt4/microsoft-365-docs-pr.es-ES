---
title: Configurar Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre cómo configurar Microsoft 365 Business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660897"
---
# <a name="set-up-microsoft-365-business"></a>Configurar Microsoft 365 Business

Antes de empezar, vea [obtener Microsoft 365 Business](get-microsoft-365-business.md) para obtener información de suscripción.

Vea un [breve vídeo sobre cómo configurar Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) mediante el Asistente para la configuración y cuándo no dispone de Active Directory local.
  

## <a name="overview"></a>Información general

La mayoría de los pasos de configuración pueden realizarse en el Asistente de configuración, pero también se incluyen otras opciones.

1. [Agregar el dominio](#add-your-domain-to-personalize-sign-in) (si ha comprado su dominio durante el [Inicio de sesión](sign-up.md), este paso ya se ha realizado).
2. Agregar usuarios. Puede hacerlo de las tres maneras siguientes:
    - En el [Asistente para la instalación](#add-users-in-the-wizard).
    - Use la sincronización de directorios para [Agregar usuarios con Azure ad Connect](#add-users-by-using-azure-ad-connect) si tiene un Active Directory local.
    - También puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.
3. Configurar las directivas de seguridad y configurar dispositivos. Puede hacerlo de las tres maneras siguientes:
    - En el [Asistente para la instalación](#set-up-policies-in-the-wizard).  
    - En el [centro de administración](#modify-or-add-policies-in-the-admin-center).
    - En el [centro de administración](https://docs.microsoft.com/intune/what-is-device-management)de Intune.
4. Configurar y administrar dispositivos con Windows 10.

    Cuando se une a un dispositivo de WIndows 10 a Azure AD, se le aplican todas las directivas.
    - Configure las configuraciones de dispositivo de Windows 10 en el [Asistente de configuración](#set-up-policies-in-the-wizard).
    - Únase a un [nuevo dispositivo con Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) en Azure ad.
    - Unirse a un [dispositivo de Windows 10 existente](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) a Azure ad.
1. Instale Office 365 Business.
    - Puede instalar Office automáticamente en los dispositivos Windows mediante el Asistente de [configuración](#set-up-policies-in-the-wizard).
    - [Instalar Office](auto-install-or-uninstall-office.md) automáticamente desde el centro de administración.
    - Permita que los usuarios [instalen aplicaciones de Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows y dispositivos.
     
1. Configurar seguridad adicional.
    - El Asistente de configuración agrega directivas para proteger los dispositivos, pero también puede aprovechar las funciones de [seguridad adicionales](#additional-security-settings) para ayudarle a proteger sus datos, cuentas y mensajes de correo electrónico. 

## <a name="add-your-domain-users-and-set-up-policies"></a>Agregar el dominio, usuarios y configurar directivas

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Al adquirir Microsoft 365 Business, tiene la opción de usar un dominio de su propiedad o comprar uno durante el [registro](sign-up.md).

- Si compró un dominio nuevo cuando se registró, su dominio está todo configurado y puede moverse a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global. 

2. Elija **Agregar un dominio** para iniciar el asistente.

    ![Seleccione Agregar un dominio.](media/addadomainadmincenter.png)
    
3. En el asistente, escriba el nombre de dominio que desea usar (como contoso.com).


    ![Captura de pantalla de la página Personalice su inicio de sesión.](media/personalizesignin.png)

    
4. Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio. Si conoce el host del dominio, consulte también las [instrucciones específicas del host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Si su proveedor de hospedaje es GoDaddy, el proceso es sencillo y se le pedirá automáticamente que inicie sesión y deje que Microsoft se autentique en su nombre:

    ![En la página de confirmación de acceso a GoDaddy, seleccione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede Agregar usuarios en el asistente, pero también puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede Agregar usuarios con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

Cualquier usuario que agregue en el asistente obtiene automáticamente una licencia de Microsoft 365 Business.
Si tiene un controlador de dominio local y está usando Active Directory, consulte [Cómo usar el DDD usuarios con Azure ad Connect](#add-users-by-using-azure-ad-connect).

![Captura de pantalla de la página agregar nuevos usuarios en el asistente](media/addnewuserspage.png)

1. Si su suscripción a Microsoft 365 Business tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá una opción para asignarles licencias ahora. Siga y agrégueles licencias también.

3. Una vez que haya agregado los usuarios, también obtendrá una opción para compartir las credenciales con los nuevos usuarios que ha agregado. Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.

4. Omita la migración de mensajes de correo electrónico y elija **Siguiente** en la página **Migrar los mensajes de correo electrónico**. 

    Si va a cambiar de otro proveedor de correo electrónico y desea copiar los datos más adelante, puede migrar el [correo electrónico y los contactos a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).

#### <a name="add-users-by-using-azure-ad-connect"></a>Agregar usuarios con Azure AD Connect

 Si tiene un controlador de dominio local con Active Directory, debe sincronizar a los usuarios con Microsoft 365 Business mediante [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express). Complete esto antes de iniciar el Asistente para la instalación. Puede descargarla en el centro de administración:

- Vaya a **** \> usuarios **activos**, seleccione los puntos suspensivos en la parte superior de la página y, a continuación, seleccione **sincronización de directorios** para descargar Azure ad Connect.

    ![En la página usuarios activos, seleccione elipses > de directorio snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > Si crea usuarios de esta manera, aún tendrá que asignar licencias a ellos en el centro de administración.

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>Seguir accediendo a aplicaciones y dispositivos Unidos a un dominio

Si quiere seguir teniendo acceso a aplicaciones y dispositivos Unidos a un dominio, lea los artículos siguientes para dos formas diferentes de habilitarlo:
  
- [Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business](manage-windows-devices.md)
    - Esta es la forma recomendada.

- [Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md)

### <a name="connect-your-domain"></a>Conectar el dominio

> [!NOTE]
> Si eligió usar el dominio. en Microsoft o ha usado Azure AD Connect para configurar a los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, [cambie los servidores DNS para configurar Office 365 con cualquier registrador de dominios](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Si tiene registros DNS existentes, por ejemplo, un sitio web existente, querrá administrar sus propios registros DNS para asegurarse de que los servicios existentes permanecen conectados. Consulte [conceptos básicos de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obtener más información.

        ![Conecte la página del dominio con Administraré mis propios registros DNS.](media/connectyourdomainpage.png)

2. Siga los pasos del asistente y el correo electrónico y otros servicios se configurarán para usted.

### <a name="set-up-security-policies-and-device-configurations"></a>Configuración de directivas de seguridad y configuraciones de dispositivos 

Estas directivas se aplican a todos los usuarios a los que se le concede una licencia o a un grupo de usuarios si decide asignar directivas diferentes a un conjunto de usuarios.

#### <a name="set-up-policies-in-the-wizard"></a>Configurar directivas en el asistente

Las directivas que configure en el asistente se aplican automáticamente a un [grupo de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado *todos los usuarios*.

1. En **proteger los archivos de trabajo en dispositivos móviles** , la opción **proteger los archivos de trabajo cuando se pierdan o se roben dispositivos** se selecciona de forma predeterminada. Tiene una opción para activar **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y se recomienda hacerlo.

    ![Captura de pantalla de la página proteger archivos de trabajo en dispositivos móviles.](media/protectworkfilesondevices.png)

     - Si expande **proteger los archivos de trabajo cuando se pierden o se roban dispositivos**, los [valores](protect-work-files-on-lost-or-stolen-device.md) predeterminados se preseleccionan:

        ![Captura de pantalla de los valores predeterminados para proteger los archivos en dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - Si selecciona **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** y los amplían, se muestran los [valores](manage-user-access-on-mobile-devices.md) predeterminados. Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se apliquen a todos los usuarios. Podrá crear más directivas cuando se complete la configuración.

        ![Captura de pantalla de la configuración de protección para los archivos de Office en dispositivos móviles.](media/useraccessonmobile.png)

2. El último paso sobre la protección de datos y dispositivos le permite configurar directivas para proteger los dispositivos Windows 10. Esta configuración se aplica automáticamente cuando Windows 10 de un usuario se conecta a su organización. Puede ampliar la **seguridad de los dispositivos Windows 10** para ver y modificar los [valores](secure-windows-10-devices.md)predeterminados.
3. También puede optar por [instalar automáticamente Office](install-office-on-windows-10-during-setup.md) en dispositivos Windows 10.

    ![Captura de pantalla de la página establecer configuración de dispositivo de Windows 10.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>Modificar o agregar directivas en el centro de administración

Consulte [Manage Microsoft 365 Business](manage.md) para obtener vínculos a temas sobre cómo ver y modificar las directivas de protección de dispositivos y aplicaciones, y cómo quitar datos de los dispositivos de usuario o restablecerlos.

## <a name="deploy-and-manage-windows-10"></a>Implementar y administrar Windows 10
Consulte [configurar dispositivos Windows para que los usuarios de Microsoft 365 Business](set-up-windows-devices.md) se conecten manualmente a Azure ad, ya sea durante la instalación de nuevos equipos o cambiando el perfil de inicio de sesión de los equipos existentes. 

### <a name="use-autopilot-to-set-up-new-devices"></a>Usar AutoPilot para configurar nuevos dispositivos

Puede usar [Windows AutoPilot](add-autopilot-devices-and-profile.md) para preconfigurar automáticamente los **nuevos** dispositivos Windows 10 para un usuario, pero podría ser más fácil obtener un [asociado](https://www.microsoft.com/solution-providers/search) que lo haga por usted. También puede ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) y solicitar a un experto en la tecnología de la nube que configure los nuevos dispositivos que compre para usted.

### <a name="access-on-premises-resources"></a>Acceso a recursos locales

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 Business](manage-windows-devices.md) to Configure this. Este es el método preferido y los dispositivos en este estado se denominan dispositivos híbridos Unidos de Azure AD.

Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede dar acceso a estos recursos a los dispositivos de Azure AD siguiendo los pasos que se indican a continuación: [acceso a recursos locales desde un Dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md).

## <a name="deploy-office-365-client-apps"></a>Implementación de aplicaciones cliente de Office 365

Si eligió instalar automáticamente las aplicaciones de Office en durante la configuración, las aplicaciones se instalarán en los dispositivos con Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows con sus credenciales de trabajo.
Para instalar Office en dispositivos móviles iOS o Android, consulte [configurar dispositivos móviles para usuarios profesionales de Microsoft 365](set-up-mobile-devices.md).

También puede instalar Office de forma individual. Consulte [instalar Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) para obtener instrucciones.

## <a name="additional-security-settings"></a>Opciones de configuración de seguridad adicionales

Además de la configuración de seguridad y cumplimiento del Asistente para instalación, también puede configurar las siguientes opciones adicionales:
  
- **Protección contra malware de correo electrónico**
- **Datos adjuntos seguros de la protección contra amenazas avanzada (ATP)**
- **Vínculos seguros de ATP**
- **Protección contra suplantación de identidad (phishing)**
- **Archivado de Exchange Online**
- **Prevención de pérdida de datos (DLP)**
- **Azure Information Protection** (Plan 1)
- **Disponibilidad del portal de Intune**

Para empezar, vea [configurar las directivas de seguridad avanzada](set-up-advanced-security.md).

Consulte también [las 10 formas principales de proteger su empresa de Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener una guía de los procedimientos de seguridad recomendados.