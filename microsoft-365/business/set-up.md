---
title: Configurar Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra los pasos de configuración para Microsoft 365 Business Premium, incluida la adición de un dominio y usuarios, la configuración de directivas de seguridad y mucho más.
ms.openlocfilehash: 03f446f790a664af85cc630048bc022d88b6e54f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165778"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configuración de Microsoft 365 Business Premium en el Asistente para instalación

Vea este vídeo para obtener información general sobre la configuración de Microsoft 365 empresa Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Agregar el dominio, usuarios y configurar directivas

[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Al adquirir Microsoft 365 Business Premium, tiene la opción de usar un dominio de su propiedad o comprar uno durante el [registro](sign-up.md).

- Si compró un dominio nuevo cuando se registró, su dominio está todo configurado y puede moverse a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global. 

2. Elija **ir a la configuración** para iniciar el asistente.

    ![Seleccione ir a la instalación.](../media/gotosetupinadmincenter.png)

3. En la página **instalar las aplicaciones de Office** , puede instalar de forma opcional las aplicaciones en su propio equipo.
    
4. En el paso **Agregar dominio** , escriba el nombre de dominio que desea usar (como contoso.com).

    > [!IMPORTANT]
    > Si compró un dominio durante el registro, no verá aquí **el paso agregar un dominio** . Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.

    ![Captura de pantalla de la página Personalice su inicio de sesión.](../media/adddomain.png)

    
4. Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio. Si conoce el host del dominio, consulte también las [instrucciones específicas del host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y deje que Microsoft se autentique en su nombre.

    ![En la página de confirmación de acceso a GoDaddy, seleccione autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede Agregar usuarios en el asistente, pero también puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede Agregar usuarios con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

Cualquier usuario que agregue en el asistente obtiene automáticamente una licencia de Microsoft 365 empresa Premium.

![Captura de pantalla de la página agregar nuevos usuarios en el asistente](../media/addnewuserspage.png)

1. Si su suscripción a Microsoft 365 Business Premium tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), tendrá una opción para asignar licencias a ellos en este momento. Siga y agrégueles licencias también.

2. Una vez que haya agregado los usuarios, también obtendrá una opción para compartir las credenciales con los nuevos usuarios que ha agregado. Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.

### <a name="connect-your-domain"></a>Conectar el dominio

> [!NOTE]
> Si eligió usar el dominio. en Microsoft o ha usado Azure AD Connect para configurar a los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, [cambie los servidores DNS para configurar Office 365 con cualquier registrador de dominios](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Si tiene registros DNS existentes, por ejemplo, un sitio web existente, pero el host DNS está habilitado para la [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), elija **agregar registros**. En la página **elegir los servicios en línea** , acepte los valores predeterminados y elija **siguiente**y elija **autorizar** en la página del host DNS.
    - Si tiene registros DNS con otros hosts DNS (no habilitados para la conexión de dominio), querrá administrar sus propios registros DNS para asegurarse de que los servicios existentes permanecen conectados. Consulte [conceptos básicos de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obtener más información.

        ![Active la página de registros.](../media/activaterecords.png)

2. Siga los pasos del asistente y el correo electrónico y otros servicios se configurarán para usted.

### <a name="protect-your-organization"></a>Proteger la organización 

Las directivas que configure en el asistente se aplican automáticamente a un [grupo de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado *todos los usuarios*. También puede crear grupos adicionales para asignar directivas en el centro de administración.

1. En el **aumento de la protección frente a las amenazas avanzadas de Cyber**, se recomienda que acepte los valores predeterminados para permitir que la [protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) examine los archivos y vínculos de las aplicaciones de Office.

    ![Captura de pantalla de la página aumentar protección.](../media/increasetreatprotection.png)


2. En la página **evitar pérdidas de datos confidenciales** , acepte los valores predeterminados para activar la prevención de pérdida de datos (DLP) de Office 365 para realizar un seguimiento de los datos confidenciales de las aplicaciones de Office y evitar el uso compartido accidental de estos fuera de la organización.

3. En la página **proteger datos en Office para móviles** , deje administración de aplicaciones móviles en, expanda la configuración y revise y, a continuación, seleccione **crear Directiva de administración de aplicaciones móviles**.

    ![Captura de pantalla de la página proteger datos en Office para móviles.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger equipos con Windows 10

En el panel de navegación izquierdo, seleccione **configuración** y, a continuación, en **Inicio de sesión y seguridad**, elija **proteger los equipos con Windows 10**. Elija **Ver** para empezar. Consulte [proteger los equipos con Windows 10](secure-win-10-pcs.md) para obtener instrucciones completas.

## <a name="deploy-office-365-client-apps"></a>Implementación de aplicaciones cliente de Office 365

Si eligió instalar automáticamente las aplicaciones de Office durante la configuración, las aplicaciones se instalarán en los dispositivos con Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows, usando sus credenciales de trabajo.

Para instalar Office en dispositivos móviles iOS o Android, consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 empresa Premium](set-up-mobile-devices.md).

También puede instalar Office de forma individual. Consulte [instalar Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.

## <a name="see-also"></a>Vea también

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
