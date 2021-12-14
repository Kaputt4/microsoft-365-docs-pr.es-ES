---
title: Configuración de Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
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
description: Descubra los pasos de configuración para Microsoft 365 Empresa Premium, como agregar un dominio y usuarios, configurar directivas de seguridad y mucho más.
ms.openlocfilehash: adfb65a5dcbba398ea398a17f605e12c17375c5c
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61422092"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configurar Microsoft 365 Empresa Premium en el Asistente para configuración

## <a name="watch-overview-of-microsoft-365-setup"></a>Watch: Overview of Microsoft 365 setup

Vea este vídeo para obtener información general sobre Microsoft 365 Empresa Premium configuración.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="watch-set-up-microsoft-365-business-premium"></a>Watch: Configure up Microsoft 365 Empresa Premium

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE471FJ?autoplay=false]

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>y seleccione **Ir al programa de instalación**. Se iniciará el asistente para la instalación.
1. Una vez completada la instalación, vuelva al Centro de administración de Microsoft. En el Centro de administración puede seguir configurando características como directivas de Windows 10, DLP, etc. en la página **De** instalación.

## <a name="add-your-domain-users-and-set-up-policies"></a>Agregar el dominio, los usuarios y configurar directivas

Al comprar Microsoft 365 Empresa Premium, tiene la opción de usar un dominio de su propiedad o de comprar uno durante [el registro.](../admin-overview/sign-up-for-office-365.md)

- Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global. 

2. Para iniciar el asistente, seleccione **Ir a la configuración**.

    ![Seleccione Ir al programa de instalación.](../../media/gotosetupinadmincenter.png)

3. En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.
    
4. En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).

    > [!IMPORTANT]
    > Si ha comprado un dominio durante el registro, no verá el paso **Agregar un dominio** aquí. En su lugar, vaya a [Agregar usuarios](#add-users-and-assign-licenses).

    ![Captura de pantalla de la página Personalizar el inicio de sesión.](../../media/adddomain.png)

    
4. Siga los pasos del asistente para Crear registros DNS en cualquier proveedor de [hospedaje DNS para](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Microsoft 365 que compruebe que es el propietario del dominio. Si conoce el host de dominio, consulte también [Agregar un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../add-users/add-users.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

A los usuarios que agregues en el asistente se les asignará automáticamente una Microsoft 365 Empresa Premium licencia.

![Captura de pantalla de la página Agregar nuevos usuarios en el asistente.](../../media/addnewuserspage.png)

1. Si la Microsoft 365 Empresa Premium cuenta con usuarios existentes (por ejemplo, si usó Azure AD Conectar), ahora tiene la opción de asignarles licencias. Proceda y agrégueles licencias también.

2. Después de agregar a los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios agregados. Puede escoger entre imprimirlas, enviarlas por correo electrónico o descargarlas.

### <a name="connect-your-domain"></a>Conectar su dominio

> [!NOTE]
> Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, cambie los servidores de nombres para configurar Microsoft 365 [con cualquier registrador de dominio](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**. En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.
    - Si tiene registros DNS existentes con otros hosts DNS (no habilitados para conexión de dominios), le conviene administrar sus propios registros DNS para asegurarse de que los servicios existentes siguen conectados. Consulte [conceptos básicos de dominio](/office365/admin/get-help-with-domains/dns-basics) para obtener más información.

        ![Página Activar registros.](../../media/activaterecords.png)

2. Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.

### <a name="protect-your-organization"></a>Proteger su organización 

Las directivas configuradas en el asistente se aplican automáticamente a un grupo [de seguridad](/office365/admin/create-groups/compare-groups#security-groups) denominado Todos *los usuarios*. También puede crear grupos adicionales a los que asignar directivas en el Centro de administración.

1. En **Aumentar** la protección contra amenazas cibernéticas avanzadas, se recomienda aceptar los valores predeterminados para permitir que [Office 365 Advance Threat Protection](../../security/office-365-security/defender-for-office-365.md) analice los archivos y vínculos de Office aplicaciones.

    ![Captura de pantalla de la página Aumentar la protección.](../../media/increasetreatprotection.png)


2. En la página Evitar **pérdidas** de datos confidenciales, acepte los valores predeterminados para activar la prevención de pérdida de datos (DLP) de Office 365 para realizar un seguimiento de los datos confidenciales en aplicaciones de Office y evitar el uso compartido accidental de estos fuera de la organización.

3. En la página Proteger datos **en Office** para dispositivos móviles, deje la administración de aplicaciones móviles en, expanda la configuración y repase los datos y, a continuación, seleccione Crear directiva de administración de **aplicaciones móviles.**

    ![Captura de pantalla de Proteger datos en Office para la página móvil.](../../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger equipos con Windows 10

En el panel de navegación izquierdo, seleccione **Configurar** y, a continuación, en Inicio de sesión y **seguridad,** elija Proteger los **Windows 10 equipos**. Elija **Ver** para empezar. Consulta [Proteger los Windows 10 equipos para](secure-win-10-pcs.md) obtener instrucciones completas.

## <a name="deploy-office-365-client-apps"></a>Implementar Office 365 cliente

Si decide instalar automáticamente aplicaciones Office durante la instalación, las aplicaciones se instalarán en los dispositivos de Windows 10 una vez que los usuarios han iniciado sesión en Azure AD desde sus dispositivos Windows, con sus credenciales de trabajo.

Para instalar Office dispositivos móviles iOS o Android, consulta Configurar dispositivos móviles [para Microsoft 365 Empresa Premium usuarios.](set-up-mobile-devices.md)

También puede instalar Office individualmente. Consulta [instalar Office en un EQUIPO o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.

## <a name="related-content"></a>Contenido relacionado

[Vídeos de aprendizaje de Microsoft 365 para empresas](../../business-video/index.yml) (página de vínculo)
