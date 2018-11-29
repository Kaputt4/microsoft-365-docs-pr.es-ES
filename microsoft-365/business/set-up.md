---
title: Configurar Microsoft 365 Business mediante el Asistente para configuración
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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre cómo configurar Microsoft 365 Business completando cuatro pasos.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871165"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="a1dd3-103">Configurar Microsoft 365 Business mediante el Asistente para configuración</span><span class="sxs-lookup"><span data-stu-id="a1dd3-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="a1dd3-104">Complete los pasos 1 a 4 que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="a1dd3-105">Configurar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a1dd3-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="a1dd3-106">Vea un vídeo sobre cómo configurar Microsoft 365 Business cuando no dispone de un local de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="a1dd3-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="a1dd3-p101">Los pasos de configuración incluyen información de configuraciones que incluya Active Directory local. Si desea seguir teniendo acceso a dispositivos unido a un dominio, lea los siguientes artículos para dos forma distinta de la habilitación y completar los pasos antes de ejecutar al Asistente para instalación:</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="a1dd3-109">Habilitar dispositivos de Windows 10 unido a un dominio administrado por Microsoft 365 empresarial</span><span class="sxs-lookup"><span data-stu-id="a1dd3-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="a1dd3-110">-Este es el método recomendado.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="a1dd3-111">Acceso a recursos desde un dispositivo unido a AD Azure en Microsoft 365 Business local</span><span class="sxs-lookup"><span data-stu-id="a1dd3-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="a1dd3-112">Paso 1: Personalizar Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="a1dd3-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="a1dd3-p102">Inicie sesión en [Microsoft 365 Business](https://portal.microsoft.com) usando las credenciales de administrador global. Elija el icono **Administrador** para ir al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="a1dd3-115">Elija **Iniciar instalación** (según su estado, es posible que vea **Continuar instalación** en su lugar) en el centro de administración para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="a1dd3-116">Escriba el nombre de dominio que desea utilizar (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="a1dd3-p103">Vamos a escribir su dominio aunque haya comprobado durante el uso de Azure AD conectar, por ejemplo. Los dos pasos siguientes no se aplican a usted si usa Azure Connect de AD para comprobar su dominio.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="a1dd3-119">Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje de DNS para Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) que comprueba el que propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="a1dd3-p104">Puede ver un vídeo de ejemplo de [vídeo: el programa de instalación de Office 365 en el centro de administración nuevo](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Tenga en cuenta que en este vídeo no incluye los pasos de protección de datos de negocio de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="a1dd3-123">Paso 2: Agregar usuarios y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="a1dd3-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="a1dd3-124">Puede agregar usuarios aquí, o puede [agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="a1dd3-125">Todos los usuarios que agregue tendrán una licencia de Microsoft 365 Business asignada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="a1dd3-p105">Si su suscripción a Microsoft 365 Business tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá una opción para asignarles licencias ahora. Siga y agrégueles licencias también.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="a1dd3-p106">También verá una opción para compartir las credenciales con los nuevos usuarios que ha agregado. Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="a1dd3-130">Omita la migración de mensajes de correo electrónico y elija **Siguiente** en la página **Migrar los mensajes de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="a1dd3-131">Si está migrando desde otro proveedor de correo electrónico y desea copiar los datos más adelante, se puede [migrar correo y contactos a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="a1dd3-133">Paso 3: Conectar su dominio</span><span class="sxs-lookup"><span data-stu-id="a1dd3-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="a1dd3-134">Si decidió usar el dominio .onmicrosoft, o utiliza Azure Connect de AD, no verá este paso.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="a1dd3-135">Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="a1dd3-p107">Normalmente, el Asistente para la instalación detecta a su registrador de y le proporciona un vínculo a instrucciones paso a paso para actualizar sus registros NS en el sitio Web de registrador. Si no es así, [servidores de cambio de nombres para configurar Office 365 con cualquier registrador de dominios](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="a1dd3-138">Se configurarán automáticamente el correo electrónico y otros servicios</span><span class="sxs-lookup"><span data-stu-id="a1dd3-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="a1dd3-139">Paso 4: Administración de dispositivos y archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a1dd3-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="a1dd3-p108">En el de **proteger los archivos de trabajo en los dispositivos móviles de** página establezca **proteger los archivos de trabajo cuando los dispositivos están perdidos o robados** y **cómo los usuarios tener acceso a los archivos de Office en dispositivos móviles de administrar** la configuración de **activado**. También puede tener acceso a cada configuración subcaracterísticas haciendo clic en las comillas angulares junto a cada opción.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="a1dd3-142">Todos los archivos de trabajo de los usuarios con licencia de ahora están protegidos en iOS y dispositivos Android, tan pronto como [instalar aplicaciones de Office](set-up-mobile-devices.md) (y autenticarse con sus credenciales de Microsoft 365 empresarial).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="a1dd3-144">En la página **configuración de dispositivo de establecer 10 de Windows** , establecer configuración de **Dispositivos de 10 Windows seguro** **activado**.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="a1dd3-145">También puede tener acceso a cada configuración subcaracterísticas haciendo clic en el botón de contenido adicional junto a ella.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="a1dd3-p109">Establecer la configuración de **Instalar Office en Windows 10 dispositivos** en **Sí** si todos los usuarios tienen equipos Windows 10, y no de Office instala o instalaciones de Office de click-to-run. Si no es el caso, configure esta opción en **No**. Una vez preparados los equipos de usuario se puede [instalar automáticamente Office](auto-install-or-uninstall-office.md) más adelante desde el centro de administración. Para obtener instrucciones, vea [preparación de la instalación de cliente de Office](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="a1dd3-150">Archivos de trabajo de los usuarios con licencia en los dispositivos de Windows 10 se deben proyectarse tan pronto como [unirse a su dispositivo Windows 10](set-up-windows-devices.md) a un dominio de negocio 365 Microsoft Azure AD o [instalar 10 de Windows en un equipo nuevo](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) mientras participa en el Microsoft 365 simultáneamente Dominio de negocio Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="a1dd3-151">Haga clic en **Siguiente** y ya ha terminado la configuración.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="a1dd3-152">Envíenos comentarios en este paso para ayudarnos a mejorar la experiencia.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="a1dd3-154">Opciones de configuración de seguridad adicionales</span><span class="sxs-lookup"><span data-stu-id="a1dd3-154">Additional security settings</span></span>

<span data-ttu-id="a1dd3-155">Además de la seguridad y la configuración de cumplimiento en el Asistente para la instalación, puede configurar también la siguiente configuración adicional:</span><span class="sxs-lookup"><span data-stu-id="a1dd3-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="a1dd3-p110">Configurar la protección frente a los datos adjuntos no seguros. **Una protección avanzada** (ATP) identifica contenido malintencionado y, a continuación, bloquea la entrega de los datos adjuntos no seguros, ayudar a proteger el equipo contra esquemas de suplantación de identidad y ransomware infección. Para activar la protección de datos adjuntos, vea [configurar las directivas de Office 365 ATP los datos adjuntos seguros](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="a1dd3-p111">Proteja el entorno cuando los usuarios, haga clic en vínculos malintencionados. ATP examina los vínculos en el correo electrónico en el momento en que un usuario hace clic en ellos. Si un vínculo no es seguro, el usuario se le advierte no para visitar el sitio o informado de que el sitio se ha bloqueado. Esto ayuda a proteger contra esquemas de suplantación de identidad. [Configurar las directivas de Office 365 ATP seguros vínculos](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [configurar las directivas de Office 365 ATP seguros vínculos](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="a1dd3-p112">Puede conservar todo el contenido buzón incluyendo los elementos eliminados colocando todo el buzón de un usuario en **suspensión de litigio**. Para obtener instrucciones, vea</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="a1dd3-166">[Configurar la retención de correo electrónico con Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="a1dd3-p113">Configurar personalizadas de **las directivas de retención**, por ejemplo, para conservar para un período de tiempo específico o eliminar permanentemente el contenido al final del período de retención. Puede habilitar las directivas de retención personalizada en el centro de cumplimiento, vaya a la **gobernanza de datos** y valores \> **retención**y, a continuación, siga los pasos descritos en el asistente. Para obtener más información, vea [información general de las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="a1dd3-170">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1dd3-170">Next steps</span></span>

<span data-ttu-id="a1dd3-171">En el caso de los usuarios que tienen licencia, el siguiente paso es configurar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="a1dd3-172">Consulte [Configurar dispositivos Windows para los usuarios de Microsoft 365 Business](set-up-windows-devices.md) y [Configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="a1dd3-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="a1dd3-173">Consulte [Administrar Microsoft 365 Business](manage.md) para ver vínculos relacionados con los temas sobre cómo configurar directivas de protección de aplicaciones y dispositivos y cómo eliminar datos de dispositivos de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1dd3-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


