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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra los pasos de configuración para Microsoft 365 Business Premium, incluida la adición de un dominio y usuarios, la configuración de directivas de seguridad y mucho más.
ms.openlocfilehash: efa7934ece0dfeac3c4b20daa37da6f1160901e7
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079814"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="f57a7-103">Configuración de Microsoft 365 Business Premium en el Asistente para instalación</span><span class="sxs-lookup"><span data-stu-id="f57a7-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="f57a7-104">Vea este vídeo para obtener información general sobre la configuración de Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="f57a7-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="f57a7-105">Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="f57a7-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="f57a7-106">Agregar el dominio, usuarios y configurar directivas</span><span class="sxs-lookup"><span data-stu-id="f57a7-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="f57a7-107">Al adquirir Microsoft 365 Business Premium, tiene la opción de usar un dominio de su propiedad o comprar uno durante el [registro](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="f57a7-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="f57a7-108">Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="f57a7-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="f57a7-109">Agregar su dominio para personalizar el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="f57a7-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="f57a7-110">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="f57a7-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="f57a7-111">Para iniciar el asistente, seleccione **Ir a la configuración**.</span><span class="sxs-lookup"><span data-stu-id="f57a7-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Seleccione ir a la instalación.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="f57a7-113">En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f57a7-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="f57a7-114">En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f57a7-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f57a7-115">Si adquirió un dominio durante el inicio de sesión, no verá el paso**Agregar dominio** aquí.</span><span class="sxs-lookup"><span data-stu-id="f57a7-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="f57a7-116">Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f57a7-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Captura de pantalla de la página Personalice su inicio de sesión.](../media/adddomain.png)

    
4. <span data-ttu-id="f57a7-118">Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de host DNS para Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="f57a7-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="f57a7-119">Si ya sabe cuál es el host del dominio, consulte también las [ instrucciones específicas para los hosts](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="f57a7-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="f57a7-120">Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.</span><span class="sxs-lookup"><span data-stu-id="f57a7-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="f57a7-122">Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="f57a7-122">Add users and assign licenses</span></span>

<span data-ttu-id="f57a7-123">Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="f57a7-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="f57a7-124">Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="f57a7-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="f57a7-125">Agregar usuarios en el asistente</span><span class="sxs-lookup"><span data-stu-id="f57a7-125">Add users in the wizard</span></span>

<span data-ttu-id="f57a7-126">Cualquier usuario que agregue en el asistente obtiene automáticamente una licencia de Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="f57a7-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Captura de pantalla de la página agregar nuevos usuarios en el asistente](../media/addnewuserspage.png)

1. <span data-ttu-id="f57a7-128">Si su suscripción a Microsoft 365 Business Premium tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), tendrá una opción para asignar licencias a ellos en este momento.</span><span class="sxs-lookup"><span data-stu-id="f57a7-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="f57a7-129">Proceda y agrégueles licencias también.</span><span class="sxs-lookup"><span data-stu-id="f57a7-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="f57a7-130">Una vez que haya agregado los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="f57a7-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="f57a7-131">Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="f57a7-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="f57a7-132">Conectar su dominio</span><span class="sxs-lookup"><span data-stu-id="f57a7-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="f57a7-133">Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="f57a7-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="f57a7-134">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="f57a7-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="f57a7-135">Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="f57a7-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="f57a7-136">Si no es así, [cambie los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="f57a7-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="f57a7-137">Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**.</span><span class="sxs-lookup"><span data-stu-id="f57a7-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="f57a7-138">En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente**y elija **Autorizar** en la página del host DNS.</span><span class="sxs-lookup"><span data-stu-id="f57a7-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="f57a7-139">Si tiene registros DNS en otros hosts (que no están habilitados para usar la conexión de dominio), le recomendamos administrar sus propios registros DNS para asegurarse de que los servicios existentes permanezcan conectados.</span><span class="sxs-lookup"><span data-stu-id="f57a7-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="f57a7-140">Para obtener más información, consulte [Conceptos básicos sobre DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="f57a7-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Active la página de registros.](../media/activaterecords.png)

2. <span data-ttu-id="f57a7-142">Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.</span><span class="sxs-lookup"><span data-stu-id="f57a7-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="f57a7-143">Proteger la organización</span><span class="sxs-lookup"><span data-stu-id="f57a7-143">Protect your organization</span></span> 

<span data-ttu-id="f57a7-144">Las directivas que configure en el asistente se aplican automáticamente a un [grupo de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado *todos los usuarios*.</span><span class="sxs-lookup"><span data-stu-id="f57a7-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="f57a7-145">También puede crear grupos adicionales para asignar directivas en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="f57a7-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="f57a7-146">En el **aumento de la protección frente a las amenazas avanzadas de Cyber**, se recomienda que acepte los valores predeterminados para permitir que la [protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) examine los archivos y vínculos de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="f57a7-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Captura de pantalla de la página aumentar protección.](../media/increasetreatprotection.png)


2. <span data-ttu-id="f57a7-148">En la página **evitar pérdidas de datos confidenciales** , acepte los valores predeterminados para activar la prevención de pérdida de datos (DLP) de Office 365 para realizar un seguimiento de los datos confidenciales de las aplicaciones de Office y evitar el uso compartido accidental de estos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="f57a7-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="f57a7-149">En la página **proteger datos en Office para móviles** , deje administración de aplicaciones móviles en, expanda la configuración y revise y, a continuación, seleccione **crear Directiva de administración de aplicaciones móviles**.</span><span class="sxs-lookup"><span data-stu-id="f57a7-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Captura de pantalla de la página proteger datos en Office para móviles.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="f57a7-151">Proteger equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="f57a7-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="f57a7-152">En el panel de navegación izquierdo, seleccione **configuración** y, a continuación, en **Inicio de sesión y seguridad**, elija **proteger los equipos con Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="f57a7-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="f57a7-153">Elija **Ver** para empezar.</span><span class="sxs-lookup"><span data-stu-id="f57a7-153">Choose **View** to get started.</span></span> <span data-ttu-id="f57a7-154">Consulte [proteger los equipos con Windows 10](secure-win-10-pcs.md) para obtener instrucciones completas.</span><span class="sxs-lookup"><span data-stu-id="f57a7-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="f57a7-155">Implementación de aplicaciones cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="f57a7-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="f57a7-156">Si eligió instalar automáticamente las aplicaciones de Office durante la configuración, las aplicaciones se instalarán en los dispositivos con Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows, usando sus credenciales de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f57a7-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="f57a7-157">Para instalar Office en dispositivos móviles iOS o Android, consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 empresa Premium](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="f57a7-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="f57a7-158">También puede instalar Office de forma individual.</span><span class="sxs-lookup"><span data-stu-id="f57a7-158">You can also install Office individually.</span></span> <span data-ttu-id="f57a7-159">Consulte [instalar Office en un equipo PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f57a7-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f57a7-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="f57a7-160">See also</span></span>

[<span data-ttu-id="f57a7-161">Vídeos de aprendizaje de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f57a7-161">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
