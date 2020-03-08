---
title: Configurar Microsoft 365 Empresa
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
description: Descubra los pasos de configuración para Microsoft 365 Business, que incluye la adición de un dominio y usuarios, la configuración de directivas de seguridad y mucho más.
ms.openlocfilehash: 99994b6f1e9e817b4858aeafe4ce3ceaaf4c3c37
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561198"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="27e5f-103">Configurar Microsoft 365 empresa en el Asistente de configuración</span><span class="sxs-lookup"><span data-stu-id="27e5f-103">Set up Microsoft 365 Business in the setup wizard</span></span>

<span data-ttu-id="27e5f-104">Vea este vídeo para obtener información general sobre la configuración de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="27e5f-104">Watch this video for an overview of Microsoft 365 Business setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="27e5f-105">Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="27e5f-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="27e5f-106">Agregar el dominio, usuarios y configurar directivas</span><span class="sxs-lookup"><span data-stu-id="27e5f-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="27e5f-107">[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="27e5f-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="27e5f-108">Al adquirir Microsoft 365 Business, tiene la opción de usar un dominio de su propiedad o comprar uno durante el [registro](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="27e5f-108">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="27e5f-109">Si compró un dominio nuevo cuando se registró, su dominio está todo configurado y puede moverse a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="27e5f-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="27e5f-110">Agregar su dominio para personalizar el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="27e5f-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="27e5f-111">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="27e5f-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="27e5f-112">Elija **ir a la configuración** para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="27e5f-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Seleccione ir a la instalación.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="27e5f-114">En la página **instalar las aplicaciones de Office** , puede instalar de forma opcional las aplicaciones en su propio equipo.</span><span class="sxs-lookup"><span data-stu-id="27e5f-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="27e5f-115">En el paso **Agregar dominio** , escriba el nombre de dominio que desea usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="27e5f-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="27e5f-116">Si compró un dominio durante el registro, no verá aquí **el paso agregar un dominio** .</span><span class="sxs-lookup"><span data-stu-id="27e5f-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="27e5f-117">Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="27e5f-117">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Captura de pantalla de la página Personalice su inicio de sesión.](../media/adddomain.png)

    
4. <span data-ttu-id="27e5f-119">Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="27e5f-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="27e5f-120">Si conoce el host del dominio, consulte también las [instrucciones específicas del host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="27e5f-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="27e5f-121">Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y deje que Microsoft se autentique en su nombre.</span><span class="sxs-lookup"><span data-stu-id="27e5f-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![En la página de confirmación de acceso a GoDaddy, seleccione autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="27e5f-123">Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="27e5f-123">Add users and assign licenses</span></span>

<span data-ttu-id="27e5f-124">Puede Agregar usuarios en el asistente, pero también puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="27e5f-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="27e5f-125">Además, si tiene un controlador de dominio local, puede Agregar usuarios con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="27e5f-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="27e5f-126">Agregar usuarios en el asistente</span><span class="sxs-lookup"><span data-stu-id="27e5f-126">Add users in the wizard</span></span>

<span data-ttu-id="27e5f-127">Cualquier usuario que agregue en el asistente obtiene automáticamente una licencia de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="27e5f-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Captura de pantalla de la página agregar nuevos usuarios en el asistente](../media/addnewuserspage.png)

1. <span data-ttu-id="27e5f-129">Si su suscripción de Microsoft 365 Business tiene usuarios existentes (por ejemplo, si ha usado Azure AD Connect), tendrá una opción para asignar licencias a ellos en este momento.</span><span class="sxs-lookup"><span data-stu-id="27e5f-129">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="27e5f-130">Siga y agrégueles licencias también.</span><span class="sxs-lookup"><span data-stu-id="27e5f-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="27e5f-131">Una vez que haya agregado los usuarios, también obtendrá una opción para compartir las credenciales con los nuevos usuarios que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="27e5f-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="27e5f-132">Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="27e5f-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="27e5f-133">Conectar el dominio</span><span class="sxs-lookup"><span data-stu-id="27e5f-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="27e5f-134">Si eligió usar el dominio. en Microsoft o ha usado Azure AD Connect para configurar a los usuarios, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="27e5f-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="27e5f-135">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="27e5f-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="27e5f-136">Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="27e5f-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="27e5f-137">Si no es así, [cambie los servidores DNS para configurar Office 365 con cualquier registrador de dominios](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="27e5f-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="27e5f-138">Si tiene registros DNS existentes, por ejemplo, un sitio web existente, pero el host DNS está habilitado para la [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), elija **agregar registros**.</span><span class="sxs-lookup"><span data-stu-id="27e5f-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="27e5f-139">En la página **elegir los servicios en línea** , acepte los valores predeterminados y elija **siguiente**y elija **autorizar** en la página del host DNS.</span><span class="sxs-lookup"><span data-stu-id="27e5f-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="27e5f-140">Si tiene registros DNS con otros hosts DNS (no habilitados para la conexión de dominio), querrá administrar sus propios registros DNS para asegurarse de que los servicios existentes permanecen conectados.</span><span class="sxs-lookup"><span data-stu-id="27e5f-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="27e5f-141">Consulte [conceptos básicos de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="27e5f-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Active la página de registros.](../media/activaterecords.png)

2. <span data-ttu-id="27e5f-143">Siga los pasos del asistente y el correo electrónico y otros servicios se configurarán para usted.</span><span class="sxs-lookup"><span data-stu-id="27e5f-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="27e5f-144">Proteger la organización</span><span class="sxs-lookup"><span data-stu-id="27e5f-144">Protect your organization</span></span> 

<span data-ttu-id="27e5f-145">Las directivas que configure en el asistente se aplican automáticamente a un [grupo de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado *todos los usuarios*.</span><span class="sxs-lookup"><span data-stu-id="27e5f-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="27e5f-146">También puede crear grupos adicionales para asignar directivas en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="27e5f-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="27e5f-147">En el **aumento de la protección frente a las amenazas avanzadas de Cyber**, se recomienda que acepte los valores predeterminados para permitir que la [protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) examine los archivos y vínculos de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="27e5f-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Captura de pantalla de la página aumentar protección.](../media/increasetreatprotection.png)


2. <span data-ttu-id="27e5f-149">En la página **evitar pérdidas de datos confidenciales** , acepte los valores predeterminados para activar la prevención de pérdida de datos (DLP) de Office 365 para realizar un seguimiento de los datos confidenciales de las aplicaciones de Office y evitar el uso compartido accidental de estos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="27e5f-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="27e5f-150">En la página **proteger datos en Office para móviles** , deje administración de aplicaciones móviles en, expanda la configuración y revise y, a continuación, seleccione **crear Directiva de administración de aplicaciones móviles**.</span><span class="sxs-lookup"><span data-stu-id="27e5f-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Captura de pantalla de la página proteger datos en Office para móviles.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="27e5f-152">Proteger equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="27e5f-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="27e5f-153">En el panel de navegación izquierdo, seleccione **configuración** y, a continuación, en **Complementos y seguridad**, elija **proteger los equipos con Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="27e5f-153">On the left nav, select **Setup** and then, under **Sing-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="27e5f-154">Elija **Ver** para empezar.</span><span class="sxs-lookup"><span data-stu-id="27e5f-154">Choose **View** to get started.</span></span> <span data-ttu-id="27e5f-155">Consulte [proteger los equipos con Windows 10](secure-win-10-pcs.md) para obtener instrucciones completas.</span><span class="sxs-lookup"><span data-stu-id="27e5f-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="27e5f-156">Implementación de aplicaciones cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="27e5f-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="27e5f-157">Si eligió instalar automáticamente las aplicaciones de Office durante la configuración, las aplicaciones se instalarán en los dispositivos con Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows, usando sus credenciales de trabajo.</span><span class="sxs-lookup"><span data-stu-id="27e5f-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="27e5f-158">Para instalar Office en dispositivos móviles iOS o Android, consulte [configurar dispositivos móviles para usuarios profesionales de Microsoft 365](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="27e5f-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="27e5f-159">También puede instalar Office de forma individual.</span><span class="sxs-lookup"><span data-stu-id="27e5f-159">You can also install Office individually.</span></span> <span data-ttu-id="27e5f-160">Consulte [instalar Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="27e5f-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="27e5f-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="27e5f-161">See also</span></span>

[<span data-ttu-id="27e5f-162">Vídeos de aprendizaje de Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="27e5f-162">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
