---
title: Configurar Microsoft 365 Empresa Estándar
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Obtenga información acerca de cómo configurar su suscripción a Microsoft 365 Empresa Estándar.
ms.openlocfilehash: b42dd0779c708410614ea2ab0d134aa3dcf0c7e9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778930"
---
# <a name="set-up-microsoft-business-standard"></a>Configurar Microsoft Empresa Estándar
  
 *Estos pasos están dirigidos a empresas y [organizaciones sin ánimo de lucro](https://go.microsoft.com/fwlink/p/?LinkId=627221) que tengan el **[Plan de Microsoft 365 Empresa Estándar.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***

Vea un vídeo breve sobre cómo configurar Microsoft 365 Empresa Estándar (anteriormente denominada Office 365 Empresa Premium).<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Agregar su dominio para personalizar el inicio de sesión

Cuando compre una suscripción a Microsoft 365 Empresa Estándar, tendrá la opción de usar un dominio de su propiedad o comprar uno durante el registro.

- Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global. 

2. Para iniciar el asistente, seleccione **Ir a la configuración**.

3. En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.
    
4. En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).

    > [!IMPORTANT]
    > Si adquirió un dominio durante el inicio de sesión, no verá el paso**Agregar dominio** aquí. Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.

    
4. Siga los pasos del asistente para [Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) a fin de verificar que es el propietario del dominio. Si ya sabe cuál es el host del dominio, consulte también las [ instrucciones específicas para los hosts](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../add-users/add-users.md) en el centro de administración. Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Agregar usuarios en el asistente

Todos los usuarios que agregue en el asistente obtendrán automáticamente una licencia de Microsoft 365 Empresa Estándar.

1. Si su suscripción a Microsoft 365 Empresa Estándar tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá una opción para asignarles licencias ahora. Proceda y agrégueles licencias también.

2. Una vez que haya agregado los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios que ha agregado. Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.

## <a name="connect-your-domain"></a>Conectar su dominio

> [!NOTE]
> Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, consulte [Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**. En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente**y elija **Autorizar** en la página del host DNS.
    - Si tiene registros DNS en otros hosts (que no están habilitados para usar la conexión de dominio), le recomendamos administrar sus propios registros DNS para asegurarse de que los servicios existentes permanezcan conectados. Para obtener más información, consulte [Conceptos básicos sobre DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

2. Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.

    Cuando finalice el proceso de suscripción, se le dirigirá al Centro de administración, donde un asistente le indicará como instalar las aplicaciones de Office, agregar su dominio, agregar usuarios y asignar licencias. Una vez completada la configuración inicial, puede usar la página de **instalación** del Centro de administración para seguir instalando y configurando los servicios que se incluyen en las suscripciones.

    Para obtener más información sobre el Asistente para la instalación y la página de **Configuración** del Centro de administración, consulte [Diferencias entre el Asistente de configuración la página de Configuración](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Finalizar la configuración

### <a name="set-up-outlook-for-email"></a>Configurar Outlook para el correo electrónico

1. En el menú Inicio de Windows, busque Outlook y selecciónelo.

    (Si usa un equipo Mac, abra Outlook desde la barra de herramientas o búsquelo con el Buscador).

    Si acaba de instalar Outlook, en la página principal, elija **Siguiente**.

2. Elija **Archivo** \> **Información** \> **Agregar cuenta**.

3. Escriba su dirección de correo electrónico de Microsoft y seleccione **Conectar**.

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

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Más información en [Importar correo electrónico con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

También puede usar el centro de administración de Exchange para importar el correo electrónico de todos los usuarios. Para obtener más información, consulte [Migrar varias cuentas de correo electrónico](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Usar un sitio web público

Microsoft 365 no incluye un sitio web público para su empresa. Si desea configurar uno, puede usar un partner de Microsoft, como GoDaddy o WIX.
  
1. En el Centro de administración, vaya a **Recursos** y luego elija **sitio web público**.

2. Elija **Más información** en una de las opciones y, después, inicie sesión con un sitio web asociado y use sus herramientas para configurar y diseñar el sitio.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

Más información en [Utilizar un sitio Web público](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).