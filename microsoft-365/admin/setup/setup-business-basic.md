---
title: Configurar Microsoft 365 Empresa Básico
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- VSBFY23
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Obtenga información acerca de cómo configurar su suscripción a Microsoft 365 Empresa Básico.
ms.openlocfilehash: 4ec614051eef61c51597da160b3030c6ba8aad07
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084859"
---
# <a name="set-up-microsoft-365-business-basic"></a>Configurar Microsoft 365 Empresa Básico

## <a name="watch-set-up-microsoft-365-business-basic"></a>Ver: Configurar Microsoft 365 Empresa Básico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

Cuando compre una suscripción a Microsoft 365 Empresa Básico, tendrá la opción de usar un dominio de su propiedad o comprar uno durante el registro.

- Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Para iniciar el asistente, seleccione **Ir a la configuración**.
    
3. En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).

    > [!IMPORTANT]
    > Si ha comprado un dominio durante el registro, no verá el paso **Agregar un dominio** aquí. En su lugar, vaya a [Agregar usuarios](#add-users-and-assign-licenses).

    
4. Siga los pasos del asistente para [Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) a fin de verificar que es el propietario del dominio. Si conoce el host de dominio, consulte también [Agregar un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../add-users/add-users.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

Todos los usuarios que agregue en el asistente obtendrán automáticamente una licencia de Microsoft 365 Empresa Básico.

1. Si su suscripción a Microsoft 365 Empresa Básico tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá la opción para asignarles licencias ahora. Aproveche de agregar las licencias para ellos también.

2. Después de agregar a los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios agregados. Puede escoger entre imprimirlas, enviarlas por correo electrónico o descargarlas.

## <a name="connect-your-domain"></a>Conectar su dominio

> [!NOTE]
> Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, consulte [Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**. En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.
    - Si tiene registros DNS existentes con otros hosts DNS (no habilitados para conexión de dominios), le conviene administrar sus propios registros DNS para asegurarse de que los servicios existentes siguen conectados. Consulte [conceptos básicos de dominio](/office365/admin/get-help-with-domains/dns-basics) para obtener más información.

2. Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.

    Cuando finalice el proceso de suscripción, se le dirigirá al centro de administración, donde podrá agregar usuarios y asignar licencias. Una vez completada la configuración inicial, puede usar la página de **instalación** del Centro de administración para seguir instalando y configurando los servicios que se incluyen en las suscripciones.

    Para obtener más información sobre el Asistente para la instalación y la página de **Configuración** del Centro de administración, consulte [Diferencias entre el Asistente de configuración la página de Configuración](o365-setup-wizard-and-setup-page.md).