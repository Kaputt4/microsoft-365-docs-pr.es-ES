---
title: Configurar Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre cómo configurar Microsoft 365 Business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660897"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="96d6c-103">Configurar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="96d6c-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="96d6c-104">Antes de empezar, vea [obtener Microsoft 365 Business](get-microsoft-365-business.md) para obtener información de suscripción.</span><span class="sxs-lookup"><span data-stu-id="96d6c-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="96d6c-105">Vea un [breve vídeo sobre cómo configurar Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) mediante el Asistente para la configuración y cuándo no dispone de Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="96d6c-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="96d6c-106">Información general</span><span class="sxs-lookup"><span data-stu-id="96d6c-106">Overview</span></span>

<span data-ttu-id="96d6c-107">La mayoría de los pasos de configuración pueden realizarse en el Asistente de configuración, pero también se incluyen otras opciones.</span><span class="sxs-lookup"><span data-stu-id="96d6c-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="96d6c-108">[Agregar el dominio](#add-your-domain-to-personalize-sign-in) (si ha comprado su dominio durante el [Inicio de sesión](sign-up.md), este paso ya se ha realizado).</span><span class="sxs-lookup"><span data-stu-id="96d6c-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="96d6c-109">Agregar usuarios.</span><span class="sxs-lookup"><span data-stu-id="96d6c-109">Add users.</span></span> <span data-ttu-id="96d6c-110">Puede hacerlo de las tres maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="96d6c-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="96d6c-111">En el [Asistente para la instalación](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="96d6c-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="96d6c-112">Use la sincronización de directorios para [Agregar usuarios con Azure ad Connect](#add-users-by-using-azure-ad-connect) si tiene un Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="96d6c-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="96d6c-113">También puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="96d6c-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="96d6c-114">Configurar las directivas de seguridad y configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="96d6c-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="96d6c-115">Puede hacerlo de las tres maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="96d6c-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="96d6c-116">En el [Asistente para la instalación](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="96d6c-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="96d6c-117">En el [centro de administración](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="96d6c-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="96d6c-118">En el [centro de administración](https://docs.microsoft.com/intune/what-is-device-management)de Intune.</span><span class="sxs-lookup"><span data-stu-id="96d6c-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="96d6c-119">Configurar y administrar dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="96d6c-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="96d6c-120">Cuando se une a un dispositivo de WIndows 10 a Azure AD, se le aplican todas las directivas.</span><span class="sxs-lookup"><span data-stu-id="96d6c-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="96d6c-121">Configure las configuraciones de dispositivo de Windows 10 en el [Asistente de configuración](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="96d6c-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="96d6c-122">Únase a un [nuevo dispositivo con Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) en Azure ad.</span><span class="sxs-lookup"><span data-stu-id="96d6c-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="96d6c-123">Unirse a un [dispositivo de Windows 10 existente](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) a Azure ad.</span><span class="sxs-lookup"><span data-stu-id="96d6c-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="96d6c-124">Instale Office 365 Business.</span><span class="sxs-lookup"><span data-stu-id="96d6c-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="96d6c-125">Puede instalar Office automáticamente en los dispositivos Windows mediante el Asistente de [configuración](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="96d6c-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="96d6c-126">[Instalar Office](auto-install-or-uninstall-office.md) automáticamente desde el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="96d6c-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="96d6c-127">Permita que los usuarios [instalen aplicaciones de Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="96d6c-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="96d6c-128">Configurar seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="96d6c-128">Set up additional security.</span></span>
    - <span data-ttu-id="96d6c-129">El Asistente de configuración agrega directivas para proteger los dispositivos, pero también puede aprovechar las funciones de [seguridad adicionales](#additional-security-settings) para ayudarle a proteger sus datos, cuentas y mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="96d6c-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="96d6c-130">Agregar el dominio, usuarios y configurar directivas</span><span class="sxs-lookup"><span data-stu-id="96d6c-130">Add your domain, users and set up policies</span></span>

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="96d6c-132">Al adquirir Microsoft 365 Business, tiene la opción de usar un dominio de su propiedad o comprar uno durante el [registro](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="96d6c-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="96d6c-133">Si compró un dominio nuevo cuando se registró, su dominio está todo configurado y puede moverse a [Agregar usuarios y asignar licencias](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="96d6c-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="96d6c-134">Agregar su dominio para personalizar el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="96d6c-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="96d6c-135">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="96d6c-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="96d6c-136">Elija **Agregar un dominio** para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="96d6c-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Seleccione Agregar un dominio.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="96d6c-138">En el asistente, escriba el nombre de dominio que desea usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="96d6c-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Captura de pantalla de la página Personalice su inicio de sesión.](media/personalizesignin.png)

    
4. <span data-ttu-id="96d6c-140">Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que compruebe que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="96d6c-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="96d6c-141">Si conoce el host del dominio, consulte también las [instrucciones específicas del host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="96d6c-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="96d6c-142">Si su proveedor de hospedaje es GoDaddy, el proceso es sencillo y se le pedirá automáticamente que inicie sesión y deje que Microsoft se autentique en su nombre:</span><span class="sxs-lookup"><span data-stu-id="96d6c-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![En la página de confirmación de acceso a GoDaddy, seleccione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="96d6c-144">Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="96d6c-144">Add users and assign licenses</span></span>

<span data-ttu-id="96d6c-145">Puede Agregar usuarios en el asistente, pero también puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="96d6c-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="96d6c-146">Además, si tiene un controlador de dominio local, puede Agregar usuarios con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="96d6c-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="96d6c-147">Agregar usuarios en el asistente</span><span class="sxs-lookup"><span data-stu-id="96d6c-147">Add users in the wizard</span></span>

<span data-ttu-id="96d6c-148">Cualquier usuario que agregue en el asistente obtiene automáticamente una licencia de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="96d6c-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="96d6c-149">Si tiene un controlador de dominio local y está usando Active Directory, consulte [Cómo usar el DDD usuarios con Azure ad Connect](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="96d6c-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Captura de pantalla de la página agregar nuevos usuarios en el asistente](media/addnewuserspage.png)

1. <span data-ttu-id="96d6c-p106">Si su suscripción a Microsoft 365 Business tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá una opción para asignarles licencias ahora. Siga y agrégueles licencias también.</span><span class="sxs-lookup"><span data-stu-id="96d6c-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="96d6c-153">Una vez que haya agregado los usuarios, también obtendrá una opción para compartir las credenciales con los nuevos usuarios que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="96d6c-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="96d6c-154">Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="96d6c-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="96d6c-155">Omita la migración de mensajes de correo electrónico y elija **Siguiente** en la página **Migrar los mensajes de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="96d6c-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="96d6c-156">Si va a cambiar de otro proveedor de correo electrónico y desea copiar los datos más adelante, puede migrar el [correo electrónico y los contactos a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="96d6c-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="96d6c-157">Agregar usuarios con Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="96d6c-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="96d6c-158">Si tiene un controlador de dominio local con Active Directory, debe sincronizar a los usuarios con Microsoft 365 Business mediante [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="96d6c-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="96d6c-159">Complete esto antes de iniciar el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="96d6c-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="96d6c-160">Puede descargarla en el centro de administración:</span><span class="sxs-lookup"><span data-stu-id="96d6c-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="96d6c-161">Vaya a \*\*\*\* \> usuarios **activos**, seleccione los puntos suspensivos en la parte superior de la página y, a continuación, seleccione **sincronización de directorios** para descargar Azure ad Connect.</span><span class="sxs-lookup"><span data-stu-id="96d6c-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![En la página usuarios activos, seleccione elipses > de directorio snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="96d6c-163">Si crea usuarios de esta manera, aún tendrá que asignar licencias a ellos en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="96d6c-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="96d6c-164">Seguir accediendo a aplicaciones y dispositivos Unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="96d6c-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="96d6c-165">Si quiere seguir teniendo acceso a aplicaciones y dispositivos Unidos a un dominio, lea los artículos siguientes para dos formas diferentes de habilitarlo:</span><span class="sxs-lookup"><span data-stu-id="96d6c-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="96d6c-166">Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="96d6c-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="96d6c-167">Esta es la forma recomendada.</span><span class="sxs-lookup"><span data-stu-id="96d6c-167">This is the recommended way.</span></span>

- [<span data-ttu-id="96d6c-168">Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="96d6c-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="96d6c-169">Conectar el dominio</span><span class="sxs-lookup"><span data-stu-id="96d6c-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="96d6c-170">Si eligió usar el dominio. en Microsoft o ha usado Azure AD Connect para configurar a los usuarios, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="96d6c-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="96d6c-171">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="96d6c-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="96d6c-172">Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="96d6c-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="96d6c-173">Si no es así, [cambie los servidores DNS para configurar Office 365 con cualquier registrador de dominios](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="96d6c-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="96d6c-174">Si tiene registros DNS existentes, por ejemplo, un sitio web existente, querrá administrar sus propios registros DNS para asegurarse de que los servicios existentes permanecen conectados.</span><span class="sxs-lookup"><span data-stu-id="96d6c-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="96d6c-175">Consulte [conceptos básicos de dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="96d6c-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Conecte la página del dominio con Administraré mis propios registros DNS.](media/connectyourdomainpage.png)

2. <span data-ttu-id="96d6c-177">Siga los pasos del asistente y el correo electrónico y otros servicios se configurarán para usted.</span><span class="sxs-lookup"><span data-stu-id="96d6c-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="96d6c-178">Configuración de directivas de seguridad y configuraciones de dispositivos</span><span class="sxs-lookup"><span data-stu-id="96d6c-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="96d6c-179">Estas directivas se aplican a todos los usuarios a los que se le concede una licencia o a un grupo de usuarios si decide asignar directivas diferentes a un conjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="96d6c-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="96d6c-180">Configurar directivas en el asistente</span><span class="sxs-lookup"><span data-stu-id="96d6c-180">Set up policies in the wizard</span></span>

<span data-ttu-id="96d6c-181">Las directivas que configure en el asistente se aplican automáticamente a un [grupo de seguridad](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominado *todos los usuarios*.</span><span class="sxs-lookup"><span data-stu-id="96d6c-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="96d6c-182">En **proteger los archivos de trabajo en dispositivos móviles** , la opción **proteger los archivos de trabajo cuando se pierdan o se roben dispositivos** se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="96d6c-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="96d6c-183">Tiene una opción para activar **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y se recomienda hacerlo.</span><span class="sxs-lookup"><span data-stu-id="96d6c-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Captura de pantalla de la página proteger archivos de trabajo en dispositivos móviles.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="96d6c-185">Si expande **proteger los archivos de trabajo cuando se pierden o se roban dispositivos**, los [valores](protect-work-files-on-lost-or-stolen-device.md) predeterminados se preseleccionan:</span><span class="sxs-lookup"><span data-stu-id="96d6c-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Captura de pantalla de los valores predeterminados para proteger los archivos en dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="96d6c-187">Si selecciona **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** y los amplían, se muestran los [valores](manage-user-access-on-mobile-devices.md) predeterminados.</span><span class="sxs-lookup"><span data-stu-id="96d6c-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="96d6c-188">Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se apliquen a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="96d6c-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="96d6c-189">Podrá crear más directivas cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="96d6c-189">You can create more policies after setup completes.</span></span>

        ![Captura de pantalla de la configuración de protección para los archivos de Office en dispositivos móviles.](media/useraccessonmobile.png)

2. <span data-ttu-id="96d6c-191">El último paso sobre la protección de datos y dispositivos le permite configurar directivas para proteger los dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="96d6c-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="96d6c-192">Esta configuración se aplica automáticamente cuando Windows 10 de un usuario se conecta a su organización.</span><span class="sxs-lookup"><span data-stu-id="96d6c-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="96d6c-193">Puede ampliar la **seguridad de los dispositivos Windows 10** para ver y modificar los [valores](secure-windows-10-devices.md)predeterminados.</span><span class="sxs-lookup"><span data-stu-id="96d6c-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="96d6c-194">También puede optar por [instalar automáticamente Office](install-office-on-windows-10-during-setup.md) en dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="96d6c-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Captura de pantalla de la página establecer configuración de dispositivo de Windows 10.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="96d6c-196">Modificar o agregar directivas en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="96d6c-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="96d6c-197">Consulte [Manage Microsoft 365 Business](manage.md) para obtener vínculos a temas sobre cómo ver y modificar las directivas de protección de dispositivos y aplicaciones, y cómo quitar datos de los dispositivos de usuario o restablecerlos.</span><span class="sxs-lookup"><span data-stu-id="96d6c-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="96d6c-198">Implementar y administrar Windows 10</span><span class="sxs-lookup"><span data-stu-id="96d6c-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="96d6c-199">Consulte [configurar dispositivos Windows para que los usuarios de Microsoft 365 Business](set-up-windows-devices.md) se conecten manualmente a Azure ad, ya sea durante la instalación de nuevos equipos o cambiando el perfil de inicio de sesión de los equipos existentes.</span><span class="sxs-lookup"><span data-stu-id="96d6c-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="96d6c-200">Usar AutoPilot para configurar nuevos dispositivos</span><span class="sxs-lookup"><span data-stu-id="96d6c-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="96d6c-201">Puede usar [Windows AutoPilot](add-autopilot-devices-and-profile.md) para preconfigurar automáticamente los **nuevos** dispositivos Windows 10 para un usuario, pero podría ser más fácil obtener un [asociado](https://www.microsoft.com/solution-providers/search) que lo haga por usted.</span><span class="sxs-lookup"><span data-stu-id="96d6c-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="96d6c-202">También puede ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) y solicitar a un experto en la tecnología de la nube que configure los nuevos dispositivos que compre para usted.</span><span class="sxs-lookup"><span data-stu-id="96d6c-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="96d6c-203">Acceso a recursos locales</span><span class="sxs-lookup"><span data-stu-id="96d6c-203">Access on-premises resources</span></span>

<span data-ttu-id="96d6c-204">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="96d6c-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="96d6c-205">Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 Business](manage-windows-devices.md) to Configure this.</span><span class="sxs-lookup"><span data-stu-id="96d6c-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="96d6c-206">Este es el método preferido y los dispositivos en este estado se denominan dispositivos híbridos Unidos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96d6c-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="96d6c-207">Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede dar acceso a estos recursos a los dispositivos de Azure AD siguiendo los pasos que se indican a continuación: [acceso a recursos locales desde un Dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="96d6c-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="96d6c-208">Implementación de aplicaciones cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="96d6c-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="96d6c-209">Si eligió instalar automáticamente las aplicaciones de Office en durante la configuración, las aplicaciones se instalarán en los dispositivos con Windows 10 una vez que los usuarios hayan iniciado sesión en Azure AD desde sus dispositivos Windows con sus credenciales de trabajo.</span><span class="sxs-lookup"><span data-stu-id="96d6c-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="96d6c-210">Para instalar Office en dispositivos móviles iOS o Android, consulte [configurar dispositivos móviles para usuarios profesionales de Microsoft 365](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="96d6c-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="96d6c-211">También puede instalar Office de forma individual.</span><span class="sxs-lookup"><span data-stu-id="96d6c-211">You can also install Office individually.</span></span> <span data-ttu-id="96d6c-212">Consulte [instalar Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="96d6c-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="96d6c-213">Opciones de configuración de seguridad adicionales</span><span class="sxs-lookup"><span data-stu-id="96d6c-213">Additional security settings</span></span>

<span data-ttu-id="96d6c-214">Además de la configuración de seguridad y cumplimiento del Asistente para instalación, también puede configurar las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="96d6c-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="96d6c-215">**Protección contra malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="96d6c-215">**Email malware protection**</span></span>
- <span data-ttu-id="96d6c-216">**Datos adjuntos seguros de la protección contra amenazas avanzada (ATP)**</span><span class="sxs-lookup"><span data-stu-id="96d6c-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="96d6c-217">**Vínculos seguros de ATP**</span><span class="sxs-lookup"><span data-stu-id="96d6c-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="96d6c-218">**Protección contra suplantación de identidad (phishing)**</span><span class="sxs-lookup"><span data-stu-id="96d6c-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="96d6c-219">**Archivado de Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="96d6c-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="96d6c-220">**Prevención de pérdida de datos (DLP)**</span><span class="sxs-lookup"><span data-stu-id="96d6c-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="96d6c-221">**Azure Information Protection** (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="96d6c-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="96d6c-222">**Disponibilidad del portal de Intune**</span><span class="sxs-lookup"><span data-stu-id="96d6c-222">**Intune portal availability**</span></span>

<span data-ttu-id="96d6c-223">Para empezar, vea [configurar las directivas de seguridad avanzada](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="96d6c-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="96d6c-224">Consulte también [las 10 formas principales de proteger su empresa de Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener una guía de los procedimientos de seguridad recomendados.</span><span class="sxs-lookup"><span data-stu-id="96d6c-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>