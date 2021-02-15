---
title: Configuración de Microsoft 365 Empresa Premium
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra los pasos de configuración de Microsoft 365 Empresa Premium, como agregar un dominio y usuarios, configurar directivas de seguridad y mucho más.
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044738"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configurar Microsoft 365 Empresa Premium en el asistente de configuración

Vea este vídeo para obtener información general sobre la configuración de Microsoft 365 Empresa Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Agregar el dominio, los usuarios y configurar directivas

Al comprar Microsoft 365 Empresa Premium, tiene la opción de usar un dominio de su propiedad o de comprar uno durante [el registro.](sign-up.md)

- Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global. 

2. Para iniciar el asistente, seleccione **Ir a la configuración**.

    ![Seleccione Ir a la configuración.](../media/gotosetupinadmincenter.png)

3. En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.
    
4. En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).

    > [!IMPORTANT]
    > Si adquirió un dominio durante el inicio de sesión, no verá el paso **Agregar dominio** aquí. Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.

    ![Captura de pantalla de la página Personalizar el inicio de sesión.](../media/adddomain.png)

    
4. Siga los pasos del asistente para crear registros DNS en cualquier proveedor de host DNS para [Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio. Si ya sabe cuál es el host del dominio, consulte también las [ instrucciones específicas para los hosts](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](add-users-m365b.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

A los usuarios que agregues en el asistente se les asignará automáticamente una licencia de Microsoft 365 Empresa Premium.

![Captura de pantalla de la página Agregar nuevos usuarios en el asistente](../media/addnewuserspage.png)

1. Si su suscripción a Microsoft 365 Empresa Premium tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), ahora obtiene una opción para asignarles licencias. Proceda y agrégueles licencias también.

2. Una vez que haya agregado los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios que ha agregado. Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.

### <a name="connect-your-domain"></a>Conectar su dominio

> [!NOTE]
> Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, [cambie los servidores dns para configurar Microsoft 365 con cualquier registrador de dominios.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) 

    - Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**. En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.
    - Si tiene registros DNS en otros hosts (que no están habilitados para usar la conexión de dominio), le recomendamos administrar sus propios registros DNS para asegurarse de que los servicios existentes permanezcan conectados. Para obtener más información, consulte [Conceptos básicos sobre DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

        ![Activar página de registros.](../media/activaterecords.png)

2. Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.

### <a name="protect-your-organization"></a>Proteger la organización 

Las directivas configuradas en el asistente se aplican automáticamente a un grupo [de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado Todos *los usuarios.* También puede crear grupos adicionales a los que asignar directivas en el centro de administración.

1. En Aumentar **la protección** contra ciberamenazas avanzadas, se recomienda que acepte los valores predeterminados para permitir que la Protección contra amenazas avanzada de [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) analice los archivos y vínculos en las aplicaciones de Office.

    ![Captura de pantalla de la página Aumentar protección.](../media/increasetreatprotection.png)


2. En la página Evitar **pérdidas** de datos confidenciales, acepte los valores predeterminados para activar la Prevención de pérdida de datos (DLP) de Office 365 para realizar un seguimiento de los datos confidenciales en las aplicaciones de Office y evitar el uso compartido accidental de estos fuera de su organización.

3. En la **página Proteger datos en Office** para dispositivos móviles, deje la administración de aplicaciones móviles, expanda la configuración y repase y, a continuación, seleccione Crear directiva de administración de aplicaciones **móviles.**

    ![Captura de pantalla de la página Proteger datos en Office para móviles.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger equipos con Windows 10

En el panel de navegación izquierdo, seleccione **Configurar** y, a continuación, en Inicio de sesión y **seguridad,** elija Proteger los equipos con **Windows 10.** Elija **Ver** para empezar. Consulta [proteger los equipos con Windows 10](secure-win-10-pcs.md) para obtener instrucciones completas.

## <a name="deploy-office-365-client-apps"></a>Implementar aplicaciones cliente de Office 365

Si decidió instalar automáticamente las aplicaciones de Office durante la instalación, las aplicaciones se instalarán en los dispositivos Windows 10 una vez que los usuarios iniciaron sesión en Azure AD desde sus dispositivos Windows con sus credenciales de trabajo.

Para instalar Office en dispositivos móviles iOS o Android, consulte Configurar dispositivos móviles para usuarios [de Microsoft 365 Empresa Premium.](set-up-mobile-devices.md)

También puede instalar Office individualmente. Consulte [instalar Office en un equipo PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.

## <a name="see-also"></a>Vea también

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
