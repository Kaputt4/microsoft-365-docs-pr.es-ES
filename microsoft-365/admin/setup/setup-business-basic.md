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
ms.openlocfilehash: 3de3dc618e164b1a330c700ed3ecaaee6395f60f
ms.sourcegitcommit: 173f696dc8f81259d852775572a6938ec39f6115
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67644189"
---
# <a name="set-up-microsoft-365-business-basic"></a>Configurar Microsoft 365 Empresa Básico

## <a name="watch-set-up-microsoft-365-business-basic"></a>Ver: Configurar Microsoft 365 Empresa Básico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="add-an-existing-domain-to-your-microsoft-365-business-basic-subscription"></a>Adición de un dominio existente a la suscripción de Microsoft 365 Empresa Básico

Cuando compre una suscripción a Microsoft 365 Empresa Básico, tendrá la opción de usar un dominio de su propiedad o comprar uno durante el registro.

- Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

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

Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../add-users/add-users.md) en el centro de administración.

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

Seleccione el icono de nube de OneDrive en la barra de tareas y siga los pasos para mover los archivos a la nueva carpeta OneDrive para la Empresa. Seleccione **Siguiente** para configurar Microsoft Teams.

1. Abra Microsoft Teams, seleccione el icono de perfil y, a continuación, **Agregar cuenta profesional o educativa**. Siga los pasos para agregar su nueva cuenta a Teams.

## <a name="use-a-public-website"></a>Usar un sitio web público

Microsoft 365 no incluye un sitio web público para su empresa. Si desea configurar uno, puede usar un partner de Microsoft, como GoDaddy o WIX.
  
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
