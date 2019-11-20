---
title: Configurar Microsoft 365 Empresa
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre cómo configurar Microsoft 365 Business.
ms.openlocfilehash: f29dbdb61636fdfe573a1a6920d0aed963b737ad
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721497"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="41d4e-103">Configurar Microsoft 365 empresa en el Asistente de configuración</span><span class="sxs-lookup"><span data-stu-id="41d4e-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="41d4e-104">Agregar el dominio, usuarios y configurar directivas</span><span class="sxs-lookup"><span data-stu-id="41d4e-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="41d4e-105">[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="41d4e-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="41d4e-106">Al adquirir Microsoft 365 Business, tiene la opción de usar un dominio de su propiedad o comprar uno durante el [registro](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="41d4e-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="41d4e-107">Si compró un dominio nuevo cuando se registró, su dominio está todo configurado y puede moverse a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="41d4e-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="41d4e-108">Agregar su dominio para personalizar el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="41d4e-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="41d4e-109">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="41d4e-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="41d4e-110">Elija **Agregar un dominio** o **Agregar usuarios** para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="41d4e-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="41d4e-111">Si compró un dominio durante el registro, no verá aquí **el paso agregar un dominio** .</span><span class="sxs-lookup"><span data-stu-id="41d4e-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="41d4e-112">Vaya a [Agregar usuarios](#add-users-and-assign-licenses) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="41d4e-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Seleccione ir a la instalación.](media/gotosetupinadmincenter.png)
    
3. <span data-ttu-id="41d4e-114">En el asistente, escriba el nombre de dominio que desea usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="41d4e-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Captura de pantalla de la página Personalice su inicio de sesión.](media/personalizesignin.png)

    
4. <span data-ttu-id="41d4e-116">Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="41d4e-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="41d4e-117">Si conoce el host del dominio, consulte también las [instrucciones específicas del host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="41d4e-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="41d4e-118">Si su proveedor de hospedaje es GoDaddy u otro host habilitado con [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), el proceso es sencillo y se le pedirá automáticamente que inicie sesión y deje que Microsoft se autentique en su nombre.</span><span class="sxs-lookup"><span data-stu-id="41d4e-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![En la página de confirmación de acceso a GoDaddy, seleccione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="41d4e-120">Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="41d4e-120">Add users and assign licenses</span></span>

<span data-ttu-id="41d4e-121">Puede Agregar usuarios en el asistente, pero también puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="41d4e-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="41d4e-122">Además, si tiene un controlador de dominio local, puede Agregar usuarios con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="41d4e-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="41d4e-123">Agregar usuarios en el asistente</span><span class="sxs-lookup"><span data-stu-id="41d4e-123">Add users in the wizard</span></span>

<span data-ttu-id="41d4e-124">Cualquier usuario que agregue en el asistente obtiene automáticamente una licencia de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="41d4e-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Captura de pantalla de la página agregar nuevos usuarios en el asistente](media/addnewuserspage.png)

1. <span data-ttu-id="41d4e-126">Si su suscripción de Microsoft 365 Business tiene usuarios existentes (por ejemplo, si ha usado Azure AD Connect), tendrá una opción para asignar licencias a ellos en este momento.</span><span class="sxs-lookup"><span data-stu-id="41d4e-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="41d4e-127">Siga y agrégueles licencias también.</span><span class="sxs-lookup"><span data-stu-id="41d4e-127">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="41d4e-128">Una vez que haya agregado los usuarios, también obtendrá una opción para compartir las credenciales con los nuevos usuarios que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="41d4e-128">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="41d4e-129">Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="41d4e-129">You can choose to print them out, email them, or download them.</span></span>

3. <span data-ttu-id="41d4e-130">En crear Microsoft Teams para su organización, puede elegir agregar Microsoft Teams y agregar usuarios a ellos.</span><span class="sxs-lookup"><span data-stu-id="41d4e-130">On the Create Teams for your organization, you can choose to add Teams and add users to them.</span></span> <span data-ttu-id="41d4e-131">También puede hacerlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="41d4e-131">You can also do this later.</span></span> <span data-ttu-id="41d4e-132">Para obtener más información, vea [crear un equipo de toda la empresa](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span><span class="sxs-lookup"><span data-stu-id="41d4e-132">For more information, see [create a company-wide Team](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>

4. <span data-ttu-id="41d4e-133">Omita la migración de mensajes de correo electrónico y elija **Siguiente** en la página **Migrar los mensajes de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="41d4e-133">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="41d4e-134">Si va a cambiar de otro proveedor de correo electrónico y desea copiar los datos más adelante, puede [migrar el correo electrónico y los contactos a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="41d4e-134">If you're moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="41d4e-135">Conectar el dominio</span><span class="sxs-lookup"><span data-stu-id="41d4e-135">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="41d4e-136">Si eligió usar el dominio. en Microsoft o ha usado Azure AD Connect para configurar a los usuarios, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="41d4e-136">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="41d4e-137">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="41d4e-137">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="41d4e-138">Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="41d4e-138">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="41d4e-139">Si no es así, [cambie los servidores DNS para configurar Office 365 con cualquier registrador de dominios](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="41d4e-139">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="41d4e-140">Si tiene registros DNS existentes, por ejemplo, un sitio web existente, pero el host DNS está habilitado para la [conexión de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), elija **agregar registros**.</span><span class="sxs-lookup"><span data-stu-id="41d4e-140">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="41d4e-141">En la página **elegir los servicios en línea** , acepte los valores predeterminados y elija **siguiente**y elija **autorizar** en la página del host DNS.</span><span class="sxs-lookup"><span data-stu-id="41d4e-141">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="41d4e-142">Si tiene registros DNS con otros hosts DNS (no habilitados para la conexión de dominio), querrá administrar sus propios registros DNS para asegurarse de que los servicios existentes permanecen conectados.</span><span class="sxs-lookup"><span data-stu-id="41d4e-142">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="41d4e-143">Consulte [conceptos básicos de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41d4e-143">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Conecte la página del dominio con Administraré mis propios registros DNS.](media/connectyourdomainpage.png)

2. <span data-ttu-id="41d4e-145">Siga los pasos del asistente y el correo electrónico y otros servicios se configurarán para usted.</span><span class="sxs-lookup"><span data-stu-id="41d4e-145">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-data-and-devices"></a><span data-ttu-id="41d4e-146">Proteger datos y dispositivos</span><span class="sxs-lookup"><span data-stu-id="41d4e-146">Protect data and devices</span></span> 

<span data-ttu-id="41d4e-147">Las directivas que configure en el asistente se aplican automáticamente a un [grupo de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado *todos los usuarios*.</span><span class="sxs-lookup"><span data-stu-id="41d4e-147">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="41d4e-148">También puede crear grupos adicionales para asignar directivas en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="41d4e-148">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="41d4e-149">En los **archivos de protección de su trabajo en dispositivos móviles**, la opción **proteger los archivos de trabajo cuando se pierdan o se roben dispositivos** se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41d4e-149">On the **Protect your work files on mobile devices**, the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="41d4e-150">Tiene una opción para activar **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y se recomienda hacerlo.</span><span class="sxs-lookup"><span data-stu-id="41d4e-150">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Captura de pantalla de la página proteger archivos de trabajo en dispositivos móviles.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="41d4e-152">Expanda **proteger archivos de trabajo cuando se pierdan o se roben dispositivos** para mostrar los [valores predeterminados](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="41d4e-152">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Captura de pantalla de los valores predeterminados para proteger los archivos en dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="41d4e-154">Seleccione **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** y expándalo para mostrar los [valores predeterminados](manage-user-access-on-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="41d4e-154">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="41d4e-155">Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se aplican a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="41d4e-155">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="41d4e-156">Podrá crear más directivas cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="41d4e-156">You can create more policies after setup completes.</span></span>

        ![Captura de pantalla de la configuración de protección para los archivos de Office en dispositivos móviles.](media/useraccessonmobile.png)

2. <span data-ttu-id="41d4e-158">El último paso sobre la protección de datos y dispositivos le permite configurar directivas para proteger los dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="41d4e-158">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="41d4e-159">Esta configuración se aplica automáticamente cuando Windows 10 de un usuario se conecta a su organización.</span><span class="sxs-lookup"><span data-stu-id="41d4e-159">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="41d4e-160">Puede ampliar la **seguridad de los dispositivos Windows 10** para ver y modificar los [valores predeterminados](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="41d4e-160">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="41d4e-161">También puede optar por [instalar automáticamente Office](install-office-on-windows-10-during-setup.md) en dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="41d4e-161">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Captura de pantalla de la página establecer configuración de dispositivo de Windows 10.](media/setwin10config.png)


## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="41d4e-163">Implementación de aplicaciones cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="41d4e-163">Deploy Office 365 client apps</span></span>

<span data-ttu-id="41d4e-164">Si eligió instalar automáticamente las aplicaciones de Office durante la configuración, las aplicaciones se instalarán en los dispositivos con Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows, usando sus credenciales de trabajo.</span><span class="sxs-lookup"><span data-stu-id="41d4e-164">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="41d4e-165">Para instalar Office en dispositivos móviles iOS o Android, consulte [configurar dispositivos móviles para usuarios profesionales de Microsoft 365](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="41d4e-165">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="41d4e-166">También puede instalar Office de forma individual.</span><span class="sxs-lookup"><span data-stu-id="41d4e-166">You can also install Office individually.</span></span> <span data-ttu-id="41d4e-167">Consulte [instalar Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="41d4e-167">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
