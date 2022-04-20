---
title: Configuración de Microsoft 365 Empresa Premium
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1.keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra los pasos de configuración de Microsoft 365 Empresa Premium, incluidos la adición de un dominio y usuarios, la configuración de directivas de seguridad y mucho más.
ms.openlocfilehash: 69d158d7193a2f07c6b4c23557474f1458e2fb51
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64935903"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configuración de Microsoft 365 Empresa Premium en el Asistente para la instalación

## <a name="watch-overview-of-microsoft-365-setup"></a>Inspección: Introducción a la configuración de Microsoft 365

Vea este vídeo para obtener información general sobre Microsoft 365 Empresa Premium configuración.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="watch-set-up-microsoft-365-business-premium"></a>Inspección: Configuración de Microsoft 365 Empresa Premium

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE471FJ?autoplay=false]

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> y seleccione **Ir a la configuración**. Se iniciará el asistente para la instalación.
1. Una vez completada la instalación, vuelva al Centro de administración de Microsoft. En el Centro de administración, puede seguir configurando características como Windows 10 directivas, DLP, etc. en la página **Configuración**.

## <a name="add-your-domain-users-and-set-up-policies"></a>Agregar el dominio, los usuarios y configurar directivas

Al comprar Microsoft 365 Empresa Premium, tiene la opción de usar un dominio que posee o comprar uno durante el [registro](../admin-overview/sign-up-for-office-365.md).

- Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global. 

2. Para iniciar el asistente, seleccione **Ir a la configuración**.

    ![Seleccione Ir a la configuración.](../../media/gotosetupinadmincenter.png)

3. En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.
    
4. En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).

    > [!IMPORTANT]
    > Si ha comprado un dominio durante el registro, no verá el paso **Agregar un dominio** aquí. En su lugar, vaya a [Agregar usuarios](#add-users-and-assign-licenses).

    ![Captura de pantalla de la página Personalizar el inicio de sesión.](../../media/adddomain.png)

    
4. Siga los pasos del asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio. Si conoce el host de dominio, consulte también [Agregar un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../add-users/add-users.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

A los usuarios que agregue en el asistente se les asignará automáticamente una licencia de Microsoft 365 Empresa Premium.

![Captura de pantalla de la página Agregar nuevos usuarios en el asistente.](../../media/addnewuserspage.png)

1. Si la suscripción de Microsoft 365 Empresa Premium tiene usuarios existentes (por ejemplo, si usó Azure AD Conectar), obtendrá una opción para asignarles licencias ahora. Proceda y agrégueles licencias también.

2. Después de agregar a los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios agregados. Puede escoger entre imprimirlas, enviarlas por correo electrónico o descargarlas.

### <a name="connect-your-domain"></a>Conectar su dominio

> [!NOTE]
> Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, [cambie nameservers para configurar Microsoft 365 con cualquier registrador de dominios](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**. En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.
    - Si tiene registros DNS existentes con otros hosts DNS (no habilitados para conexión de dominios), le conviene administrar sus propios registros DNS para asegurarse de que los servicios existentes siguen conectados. Consulte [conceptos básicos de dominio](/office365/admin/get-help-with-domains/dns-basics) para obtener más información.

        ![Página Activar registros.](../../media/activaterecords.png)

2. Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.

### <a name="protect-your-organization"></a>Protección de la organización 

Las directivas que configuró en el asistente se aplican automáticamente a un [grupo de seguridad](/office365/admin/create-groups/compare-groups#security-groups) denominado *Todos los usuarios*. También puede crear grupos adicionales a los que asignar directivas en el centro de administración.

1. En **Aumento de la protección contra ciberamenazas avanzadas**, se recomienda aceptar los valores predeterminados para permitir que [Office 365 Advanced Threat Protection](../../security/office-365-security/defender-for-office-365.md) examine archivos y vínculos en Office aplicaciones.

    ![Captura de pantalla de la página Aumentar protección.](../../media/increasetreatprotection.png)


2. En la página **Evitar pérdidas de datos confidenciales**, acepte los valores predeterminados para activar Prevención de pérdida de datos de Microsoft Purview para realizar un seguimiento de la información confidencial en Office aplicaciones y evitar el uso compartido accidental de estos fuera de su organización.

3. En la página **Proteger datos en Office para dispositivos móviles**, deje activada la administración de aplicaciones móviles, expanda la configuración y revísela y, a continuación, seleccione **Crear directiva de administración de aplicaciones móviles**.

    ![Captura de pantalla de la página Proteger datos en Office para dispositivos móviles.](../../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger equipos con Windows 10

En el panel de navegación izquierdo, seleccione **Configurar** y, en **Inicio de sesión y seguridad**, elija **Proteger los equipos Windows 10**. Elija **Ver** para empezar. Consulte [Protección de los equipos Windows 10](secure-win-10-pcs.md) para obtener instrucciones completas.

## <a name="deploy-office-365-client-apps"></a>Implementación Office 365 aplicaciones cliente

Si decide instalar automáticamente Office aplicaciones durante la instalación, las aplicaciones se instalarán en los dispositivos Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows, con sus credenciales de trabajo.

Para instalar Office en dispositivos móviles iOS o Android, consulte Configuración de [dispositivos móviles para usuarios Microsoft 365 Empresa Premium](set-up-mobile-devices.md).

También puede instalar Office individualmente. Consulte [Instalar Office en un equipo o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.

## <a name="related-content"></a>Contenido relacionado

[Vídeos de aprendizaje de Microsoft 365 para empresas](../../business-video/index.yml) (página de vínculo)
