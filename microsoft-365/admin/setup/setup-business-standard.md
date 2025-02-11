---
title: Configurar Microsoft 365 Empresa Estándar con un dominio nuevo o existente
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier1
- scotvorg
- highpri
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
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid:
- MET150
- MOE150
- BEA160
description: Cuando compre una suscripción a Microsoft 365 Empresa Estándar, tendrá la opción de usar un dominio de su propiedad o comprar uno durante el registro.
ms.openlocfilehash: 14f97dad5aaf68b7bce415b8cb5862c514aa4b69
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731137"
---
# <a name="set-up-microsoft-365-business-standard-with-a-new-or-existing-domain"></a>Configurar Microsoft 365 Empresa Estándar con un dominio nuevo o existente

Cuando compre una suscripción a Microsoft 365 Empresa Estándar, tendrá la opción de añadir un dominio de su propiedad o comprar. Consulte [Registrarse para obtener una suscripción de Microsoft 365 Empresa Estándar](../simplified-signup/signup-business-standard.md).

En este artículo, le guiaremos por los pasos necesarios para agregar un dominio ya existente que ya posee o comprar uno nuevo. Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

> [!Tip]
> Si tiene una suscripción de Microsoft 365 Empresa Premium, consulte [Configurar Microsoft 365 Empresa Premium](../../business-premium/m365bp-setup.md).

## <a name="set-up-microsoft-365-for-business"></a>Configurar Microsoft 365 para empresas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE471FJ]

## <a name="before-you-begin"></a>Antes de empezar

Para agregar, modificar o quitar dominios, debe ser administrador global. Para obtener más información, consulte [Acerca de los roles de administrador.](../add-users/about-admin-roles.md)

> [!IMPORTANT]
> La persona que se suscribe a Microsoft 365 para empresas (normalmente el propietario de la empresa) se convierte automáticamente en el administrador técnico de la organización. Puede agregar a otras personas como administradores si desea obtener ayuda para administrar los servicios de Microsoft 365. Consulta [Asignar roles de administrador](../add-users/assign-admin-roles.md) para obtener más información.

## <a name="watch-add-an-existing-domain-to-your-microsoft-365-business-standard-subscription"></a>Vea: agregar un dominio existente a su suscripción de Microsoft 365 Empresa Estándar

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu]

## <a name="steps-add-an-existing-domain-to-your-microsoft-365-business-standard-subscription"></a>Pasos: agregar un dominio existente a la suscripción de Microsoft 365 Empresa Estándar

1. En la página **Cómo iniciará sesión** en el registro de Microsoft 365 Empresa Estándar elija **Crear una nueva cuenta de correo electrónico empresarial (avanzada)**.

2. En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.

3. En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).

    > [!IMPORTANT]
    > Si adquirió un dominio durante el inicio de sesión, no verá el paso **Agregar dominio** aquí. Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.

4. Siga los pasos para [Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio. Si conoce el host de dominio, consulte también [Agregar un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Ahora puede agregar usuarios, pero también puede [agregar usuarios más adelante](../add-users/add-users.md) en el centro de administración.

A los usuarios que agregue se les asignará automáticamente una licencia de Microsoft 365 Empresa Estándar.

1. If your Microsoft 365 Business Standard subscription has existing users you get an option to assign licenses to them now. Go ahead and add licenses to them as well.

2. After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.

## <a name="connect-your-domain"></a>Conectar su dominio
  
Para configurar servicios, es necesario actualizar registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, consulte [Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).

    - Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**. En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.
    - If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.

2. Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.

    Cuando finalice el proceso de suscripción, se le dirigirá al Centro de administración, donde un asistente le indicará como instalar las aplicaciones de Office, agregar su dominio, agregar usuarios y asignar licencias. Una vez completada la configuración inicial, puede usar la página de **instalación** del Centro de administración para seguir instalando y configurando los servicios que se incluyen en las suscripciones.

    Para obtener más información sobre el Asistente para la instalación y la página de **Configuración** del Centro de administración, consulte [Diferencias entre el Asistente de configuración la página de Configuración](o365-setup-wizard-and-setup-page.md).

## <a name="watch-set-up-business-email-with-a-new-domain"></a>Vea: configurar el correo electrónico empresarial con un nuevo dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA]

## <a name="steps-set-up-business-email-with-a-new-domain"></a>Pasos: configurar el correo electrónico empresarial con un nuevo dominio

1. En la página **Cómo iniciará sesión** en el registro de Microsoft 365 Empresa Estándar elija **Crear una nueva cuenta de correo electrónico empresarial (avanzada)**.

2. Siga los pasos para comprar un nuevo dominio y escriba el nombre de dominio que desea usar (por ejemplo, contoso.com). Una vez que haya terminado de comprar el dominio, puede [agregar usuarios y licencias](../add-users/add-users.md) e instalar las aplicaciones de Office en el centro de administración.

## <a name="finish-setting-up"></a>Finalizar la configuración

Siga los pasos que se indican a continuación para configurar Outlook, Teams, OneDrive y su sitio web.

### <a name="step-set-up-outlook-for-email"></a>Paso: configurar Outlook para correo electrónico

1. En el menú Inicio de Windows, busque Outlook y selecciónelo.

    (Si usa un equipo Mac, abra Outlook desde la barra de herramientas o búsquelo con el Buscador).

    Si acaba de instalar Outlook, en la página principal, elija **Siguiente**.

2. Elija **Archivo** \> **Información** \> **Agregar cuenta**.

3. Escriba su dirección de correo electrónico de Microsoft y seleccione **Conectar**.

## <a name="watch-set-up-outlook-for-email"></a>Ver: Configurar Outlook para el correo electrónico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Más información en [Configurar Outlook para el correo electrónico](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>Importar correo electrónico

Si usaba Outlook con otra dirección de correo electrónico, puede importar el correo electrónico anterior, el calendario y los contactos a la nueva cuenta de Microsoft.
  
1. **Exportar los mensajes antiguos**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.

    Elija **Exportar a un archivo** y, luego, siga los pasos para exportar el archivo de datos de Outlook (.pst) y las subcarpetas.

2. **Importar el correo electrónico antiguo**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.

    Esta vez, seleccione **Importar desde otro programa o archivo** y siga los pasos para importar el archivo de copia de seguridad que creó al exportar los mensajes antiguos.

## <a name="watch-import-and-redirect-email"></a>Ver: Importar y redirigir correo electrónico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Más información en [Importar correo electrónico con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

También puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a> para importar el correo electrónico de todos los usuarios. Para obtener más información, consulte [Migrar varias cuentas de correo electrónico](/Exchange/mailbox-migration/mailbox-migration).

## <a name="set-up-microsoft-teams-and-onedrive-for-business"></a>Configurar Microsoft Teams y OneDrive para la Empresa

Select the OneDrive cloud icon from your taskbar and follow the steps to move your files to your new OneDrive for Business folder. Select **Next** to set up Microsoft Teams.

1. Abra Microsoft Teams, seleccione el icono de perfil y, a continuación, **Agregar cuenta profesional o educativa**. Siga los pasos para agregar su nueva cuenta a Teams.

## <a name="use-a-public-website"></a>Usar un sitio web público

Microsoft 365 doesn't include a public website for your business. If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.
  
1. En el Centro de administración, vaya a **Recursos** y luego elija **sitio web público**.

2. Elija **Más información** en una de las opciones y, después, inicie sesión con un sitio web asociado y use sus herramientas para configurar y diseñar el sitio.

## <a name="watch-create-your-business-website"></a>Ver: Crear un sitio web empresarial

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="invite-users-to-join-your-subscription-and-organization"></a>Invitar a usuarios a unirse a su suscripción y organización

Una vez que haya configurado su organización, puede invitar a otros usuarios a unirse a su suscripción de Microsoft 365 Empresa. Obtendrán acceso a todas las características de la suscripción.

[Invitar a usuarios a mi suscripción](../simplified-signup/admin-invite-business-standard.md)

Informe a los usuarios de que pueden seguir los pasos de los artículos siguientes para unirse a su organización y suscripción.

- [Aceptar una invitación por correo electrónico](../simplified-signup/user-invite-business-standard.md)

- [Aceptar una invitación por correo electrónico utilizando una cuenta de Outlook, Yahoo, Gmail u otra (usuario)](../simplified-signup/user-invite-msa-nodomain-join.md)

## <a name="related-topics"></a>Temas relacionados

[Migrar datos a mi suscripción de Microsoft 365 Empresa Estándar](../simplified-signup/migrate-data-business-standard.md)
