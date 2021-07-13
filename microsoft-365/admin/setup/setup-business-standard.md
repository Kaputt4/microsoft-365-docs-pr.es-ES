---
title: Configurar Microsoft 365 Empresa Estándar
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Cuando compre una suscripción a Microsoft 365 Empresa Estándar, tendrá la opción de usar un dominio de su propiedad o comprar uno durante el registro.
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393816"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="3e40f-103">Configurar Microsoft Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="3e40f-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="3e40f-104">Agregar su dominio para personalizar el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="3e40f-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="3e40f-105">Cuando compre una suscripción a Microsoft 365 Empresa Estándar, tendrá la opción de usar un dominio de su propiedad o comprar uno durante el registro.</span><span class="sxs-lookup"><span data-stu-id="3e40f-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="3e40f-106">Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="3e40f-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="3e40f-107">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="3e40f-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="3e40f-108">Para iniciar el asistente, seleccione **Ir a la configuración**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="3e40f-109">En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3e40f-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="3e40f-110">En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3e40f-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3e40f-p101">Si ha comprado un dominio durante el registro, no verá el paso **Agregar un dominio** aquí. En su lugar, vaya a [Agregar usuarios](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="3e40f-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="3e40f-113">Siga los pasos del asistente para [Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) a fin de verificar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3e40f-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="3e40f-114">Si conoce el host de dominio, consulte también [Agregar un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="3e40f-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="3e40f-115">Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.</span><span class="sxs-lookup"><span data-stu-id="3e40f-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="3e40f-117">Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="3e40f-117">Add users and assign licenses</span></span>

<span data-ttu-id="3e40f-118">Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../add-users/add-users.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="3e40f-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="3e40f-119">Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="3e40f-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="3e40f-120">Agregar usuarios en el asistente</span><span class="sxs-lookup"><span data-stu-id="3e40f-120">Add users in the wizard</span></span>

<span data-ttu-id="3e40f-121">Todos los usuarios que agregue en el asistente obtendrán automáticamente una licencia de Microsoft 365 Empresa Estándar.</span><span class="sxs-lookup"><span data-stu-id="3e40f-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="3e40f-p104">Si su suscripción a Microsoft 365 Empresa Estándar tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá la opción para asignarles licencias ahora. Aproveche de agregar las licencias para ellos también.</span><span class="sxs-lookup"><span data-stu-id="3e40f-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="3e40f-p105">Después de agregar a los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios agregados. Puede escoger entre imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="3e40f-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="3e40f-126">Conectar su dominio</span><span class="sxs-lookup"><span data-stu-id="3e40f-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="3e40f-127">Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="3e40f-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="3e40f-128">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="3e40f-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="3e40f-129">Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="3e40f-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="3e40f-130">Si no es así, consulte [Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="3e40f-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="3e40f-131">Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="3e40f-132">En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.</span><span class="sxs-lookup"><span data-stu-id="3e40f-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="3e40f-p108">Si tiene registros DNS existentes con otros hosts DNS (no habilitados para conexión de dominios), le conviene administrar sus propios registros DNS para asegurarse de que los servicios existentes siguen conectados. Consulte [conceptos básicos de dominio](/office365/admin/get-help-with-domains/dns-basics) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3e40f-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="3e40f-135">Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.</span><span class="sxs-lookup"><span data-stu-id="3e40f-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="3e40f-136">Cuando finalice el proceso de suscripción, se le dirigirá al Centro de administración, donde un asistente le indicará como instalar las aplicaciones de Office, agregar su dominio, agregar usuarios y asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="3e40f-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="3e40f-137">Una vez completada la configuración inicial, puede usar la página de **instalación** del Centro de administración para seguir instalando y configurando los servicios que se incluyen en las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="3e40f-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="3e40f-138">Para obtener más información sobre el Asistente para la instalación y la página de **Configuración** del Centro de administración, consulte [Diferencias entre el Asistente de configuración la página de Configuración](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="3e40f-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="3e40f-139">Finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="3e40f-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="3e40f-140">Configurar Outlook para el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3e40f-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="3e40f-141">En el menú Inicio de Windows, busque Outlook y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="3e40f-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="3e40f-142">(Si usa un equipo Mac, abra Outlook desde la barra de herramientas o búsquelo con el Buscador).</span><span class="sxs-lookup"><span data-stu-id="3e40f-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="3e40f-143">Si acaba de instalar Outlook, en la página principal, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="3e40f-144">Elija **Archivo** \> **Información** \> **Agregar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="3e40f-145">Escriba su dirección de correo electrónico de Microsoft y seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="3e40f-146">Ver: Configurar Outlook para el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3e40f-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="3e40f-147">Más información en [Configurar Outlook para el correo electrónico](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="3e40f-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="3e40f-148">Importar correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3e40f-148">Import email</span></span>

<span data-ttu-id="3e40f-149">Si usaba Outlook con otra dirección de correo electrónico, puede importar el correo electrónico anterior, el calendario y los contactos a la nueva cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3e40f-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="3e40f-150">**Exportar los mensajes antiguos**</span><span class="sxs-lookup"><span data-stu-id="3e40f-150">**Export your old email**</span></span>

    <span data-ttu-id="3e40f-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="3e40f-152">Elija **Exportar a un archivo** y, luego, siga los pasos para exportar el archivo de datos de Outlook (.pst) y las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="3e40f-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="3e40f-153">**Importar el correo electrónico antiguo**</span><span class="sxs-lookup"><span data-stu-id="3e40f-153">**Import your old email**</span></span>

    <span data-ttu-id="3e40f-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span><span class="sxs-lookup"><span data-stu-id="3e40f-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="3e40f-155">Esta vez, seleccione **Importar desde otro programa o archivo** y siga los pasos para importar el archivo de copia de seguridad que creó al exportar los mensajes antiguos.</span><span class="sxs-lookup"><span data-stu-id="3e40f-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="3e40f-156">Ver: Importar y redirigir correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3e40f-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="3e40f-157">Más información en [Importar correo electrónico con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="3e40f-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="3e40f-158">También puede usar el centro de administración de Exchange para importar el correo electrónico de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3e40f-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="3e40f-159">Para obtener más información, consulte [Migrar varias cuentas de correo electrónico](/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="3e40f-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="3e40f-160">Usar un sitio web público</span><span class="sxs-lookup"><span data-stu-id="3e40f-160">Use a public website</span></span>

<span data-ttu-id="3e40f-p111">Microsoft 365 no incluye un sitio web público para su empresa. Si desea configurar uno, puede usar un partner de Microsoft, como GoDaddy o WIX.</span><span class="sxs-lookup"><span data-stu-id="3e40f-p111">Microsoft 365 doesn't include a public website for your business. If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="3e40f-163">En el Centro de administración, vaya a **Recursos** y luego elija **sitio web público**.</span><span class="sxs-lookup"><span data-stu-id="3e40f-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="3e40f-164">Elija **Más información** en una de las opciones y, después, inicie sesión con un sitio web asociado y use sus herramientas para configurar y diseñar el sitio.</span><span class="sxs-lookup"><span data-stu-id="3e40f-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="3e40f-165">Ver: Crear un sitio web empresarial</span><span class="sxs-lookup"><span data-stu-id="3e40f-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="3e40f-166">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="3e40f-166">Related content</span></span>

<span data-ttu-id="3e40f-167">[Crear un sitio web](../../business-video/create-web-site.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="3e40f-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="3e40f-168">[Microsoft 365 para su empresa](../../business-video/index.yml) (página de vínculos)</span><span class="sxs-lookup"><span data-stu-id="3e40f-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
