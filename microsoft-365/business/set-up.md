---
title: Configuración de Microsoft 365 Empresa Premium
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
description: Descubra los pasos de configuración para Microsoft 365 Empresa Premium, como agregar un dominio y usuarios, configurar directivas de seguridad y mucho más.
ms.openlocfilehash: 37607b483686fc12ac6253ae9f693ec86c073c4e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245052"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="6b0c3-103">Configurar Microsoft 365 Empresa Premium en el Asistente para configuración</span><span class="sxs-lookup"><span data-stu-id="6b0c3-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="6b0c3-104">Vea este vídeo para obtener información general sobre Microsoft 365 Empresa Premium configuración.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="6b0c3-105">Agregar el dominio, los usuarios y configurar directivas</span><span class="sxs-lookup"><span data-stu-id="6b0c3-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="6b0c3-106">Al comprar Microsoft 365 Empresa Premium, tiene la opción de usar un dominio de su propiedad o de comprar uno durante [el registro.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="6b0c3-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="6b0c3-107">Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="6b0c3-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="6b0c3-108">Agregar su dominio para personalizar el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="6b0c3-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="6b0c3-109">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="6b0c3-110">Para iniciar el asistente, seleccione **Ir a la configuración**.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-110">Choose **Go to setup** to start the wizard.</span></span>

    ![Seleccione Ir al programa de instalación.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="6b0c3-112">En la página **Instalar sus aplicaciones de Office**, tendrá la opción de instalar las aplicaciones en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="6b0c3-113">En el paso **Agregar dominio**, escriba el nombre de dominio que desee usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6b0c3-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6b0c3-114">Si adquirió un dominio durante el inicio de sesión, no verá el paso **Agregar dominio** aquí.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="6b0c3-115">Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Captura de pantalla de la página Personalizar el inicio de sesión.](../media/adddomain.png)

    
4. <span data-ttu-id="6b0c3-117">Siga los pasos del asistente para Crear registros DNS en cualquier proveedor de [hospedaje DNS para](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Microsoft 365 que compruebe que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="6b0c3-118">Si ya sabe cuál es el host del dominio, consulte también las [ instrucciones específicas para los hosts](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="6b0c3-118">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="6b0c3-119">Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![En la página Confirmar acceso de GoDaddy, seleccione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="6b0c3-121">Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="6b0c3-121">Add users and assign licenses</span></span>

<span data-ttu-id="6b0c3-122">Puede agregar usuarios en el asistente, pero también puede [agregarlos más adelante](../admin/add-users/add-users.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-122">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="6b0c3-123">Además, si tiene un controlador de dominio local, puede agregar usuarios con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="6b0c3-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="6b0c3-124">Agregar usuarios en el asistente</span><span class="sxs-lookup"><span data-stu-id="6b0c3-124">Add users in the wizard</span></span>

<span data-ttu-id="6b0c3-125">A los usuarios que agregues en el asistente se les asignará automáticamente una Microsoft 365 Empresa Premium licencia.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Captura de pantalla de la página Agregar nuevos usuarios en el asistente](../media/addnewuserspage.png)

1. <span data-ttu-id="6b0c3-127">Si la Microsoft 365 Empresa Premium cuenta con usuarios existentes (por ejemplo, si usó Azure AD Conectar), ahora obtiene una opción para asignarles licencias.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="6b0c3-128">Proceda y agrégueles licencias también.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="6b0c3-129">Una vez que haya agregado los usuarios, también verá una opción para compartir las credenciales con los nuevos usuarios que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="6b0c3-130">Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="6b0c3-131">Conectar su dominio</span><span class="sxs-lookup"><span data-stu-id="6b0c3-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="6b0c3-132">Si ha elegido usar el dominio .onmicrosoft, o ha usado Azure AD Connect para configurar los usuarios, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="6b0c3-133">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="6b0c3-134">Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="6b0c3-135">Si no es así, cambie los servidores de nombres para configurar Microsoft 365 [con cualquier registrador de dominio](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="6b0c3-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="6b0c3-136">Si tiene registros DNS existentes (por ejemplo, un sitio web existente), pero el host DNS está habilitado para usar la [conexión de dominio](/office365/admin/get-help-with-domains/domain-connect), elija **Agregar registros para mí**.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="6b0c3-137">En la página **Seleccione sus servicios en línea**, acepte todos los valores predeterminados, haga clic en **Siguiente** y elija **Autorizar** en la página del host DNS.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="6b0c3-138">Si tiene registros DNS en otros hosts (que no están habilitados para usar la conexión de dominio), le recomendamos administrar sus propios registros DNS para asegurarse de que los servicios existentes permanezcan conectados.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="6b0c3-139">Para obtener más información, consulte [Conceptos básicos sobre DNS](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="6b0c3-139">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Página Activar registros.](../media/activaterecords.png)

2. <span data-ttu-id="6b0c3-141">Siga los pasos del asistente y se configurarán el correo electrónico y otros servicios.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="6b0c3-142">Proteger su organización</span><span class="sxs-lookup"><span data-stu-id="6b0c3-142">Protect your organization</span></span> 

<span data-ttu-id="6b0c3-143">Las directivas configuradas en el asistente se aplican automáticamente a un grupo [de seguridad](/office365/admin/create-groups/compare-groups#security-groups) denominado Todos *los usuarios*.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-143">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="6b0c3-144">También puede crear grupos adicionales a los que asignar directivas en el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="6b0c3-145">En **Aumentar** la protección contra amenazas cibernéticas avanzadas, se recomienda aceptar los valores predeterminados para permitir que [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) analice los archivos y vínculos de Office aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Captura de pantalla de la página Aumentar la protección.](../media/increasetreatprotection.png)


2. <span data-ttu-id="6b0c3-147">En la página Evitar **pérdidas** de datos confidenciales, acepte los valores predeterminados para activar la prevención de pérdida de datos (DLP) de Office 365 para realizar un seguimiento de los datos confidenciales en aplicaciones de Office y evitar el uso compartido accidental de estos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="6b0c3-148">En la página Proteger datos **en Office** para dispositivos móviles, deje la administración de aplicaciones móviles en, expanda la configuración y repase los datos y, a continuación, seleccione Crear directiva de administración de **aplicaciones móviles.**</span><span class="sxs-lookup"><span data-stu-id="6b0c3-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Captura de pantalla de Proteger datos en Office para la página móvil.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="6b0c3-150">Proteger equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="6b0c3-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="6b0c3-151">En el panel de navegación izquierdo, seleccione **Configurar** y, a continuación, en Inicio de sesión y **seguridad,** elija Proteger los **Windows 10 equipos**.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="6b0c3-152">Elija **Ver** para empezar.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-152">Choose **View** to get started.</span></span> <span data-ttu-id="6b0c3-153">Consulta [Proteger los Windows 10 equipos para](secure-win-10-pcs.md) obtener instrucciones completas.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="6b0c3-154">Implementar Office 365 cliente</span><span class="sxs-lookup"><span data-stu-id="6b0c3-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="6b0c3-155">Si optó por instalar automáticamente aplicaciones Office durante la instalación, las aplicaciones se instalarán en los dispositivos de Windows 10 una vez que los usuarios han iniciado sesión en Azure AD desde sus dispositivos Windows, con sus credenciales de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="6b0c3-156">Para instalar Office dispositivos móviles iOS o Android, consulta Configurar dispositivos móviles [para Microsoft 365 Empresa Premium usuarios.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="6b0c3-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="6b0c3-157">También puede instalar Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-157">You can also install Office individually.</span></span> <span data-ttu-id="6b0c3-158">Consulta [instalar Office en un EQUIPO o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6b0c3-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b0c3-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b0c3-159">See also</span></span>

[<span data-ttu-id="6b0c3-160">Vídeos de aprendizaje de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6b0c3-160">Microsoft 365 for business training videos</span></span>](../business-video/index.yml)
