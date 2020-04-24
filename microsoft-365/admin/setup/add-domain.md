---
title: Agregar un dominio a Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Agregue su dominio a Office 365 en el centro de administración de Microsoft 365 agregando un registro DNS en su host DNS. El Asistente para la instalación le guiará por el proceso.
ms.openlocfilehash: a77526efc526073e17b535612213202ad22d5657
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800028"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="d10ed-104">Agregar un dominio a Office 365</span><span class="sxs-lookup"><span data-stu-id="d10ed-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="d10ed-105">**[Consulte Preguntas más frecuentes acerca de los dominios](domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="d10ed-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="d10ed-106">*Para agregar, modificar o quitar dominios, **debe** ser **administrador global** de un [plan empresarial o](https://products.office.com/business/office)empresarial. Estos cambios afectan a todo el espacio empresarial, los *administradores personalizados* o *los usuarios normales* no podrán realizar estos cambios.*</span><span class="sxs-lookup"><span data-stu-id="d10ed-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="d10ed-107">Siga estos pasos para agregar, configurar o seguir configurando un dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d10ed-108">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="d10ed-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="d10ed-109">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="d10ed-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d10ed-110">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="d10ed-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="d10ed-111">Vaya a la página de **configuración** > de**dominios** .</span><span class="sxs-lookup"><span data-stu-id="d10ed-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="d10ed-112">Seleccione **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="d10ed-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="d10ed-113">Escriba el nombre del dominio que desea agregar y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d10ed-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="d10ed-114">Elija cómo desea comprobar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="d10ed-115">Si su dominio está registrado en Godaddy o 1&amp;1, seleccione **iniciar sesión** > a**continuación** y Microsoft[configurará los registros automáticamente](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="d10ed-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft[will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="d10ed-116">Puede hacer que le envíen un correo electrónico al contacto registrado para el dominio con un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d10ed-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="d10ed-117">Si no reconoce o tiene acceso al correo electrónico en el registro, puede usar la tercera opción.</span><span class="sxs-lookup"><span data-stu-id="d10ed-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="d10ed-118">Puede usar un registro TXT para comprobar su dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="d10ed-119">Seleccione esta y seleccione **siguiente** para ver instrucciones sobre cómo agregar este registro DNS al sitio web de su registrador.</span><span class="sxs-lookup"><span data-stu-id="d10ed-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="d10ed-120">Esto puede tardar hasta 30 minutos en comprobarse después de agregar el registro.</span><span class="sxs-lookup"><span data-stu-id="d10ed-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="d10ed-121">Elija cómo desea realizar los cambios de DNS necesarios para que Office use su dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="d10ed-122">Elija **Agregar los registros DNS para mí** si desea que Office configure el DNS de forma automática.</span><span class="sxs-lookup"><span data-stu-id="d10ed-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="d10ed-123">Elija **voy a agregar los registros DNS yo mismo** si solo quiere adjuntar servicios específicos de Office 365 a su dominio o si desea omitir este por ahora y hacerlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="d10ed-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="d10ed-124">**Elija esta opción si sabe exactamente lo que hace.**</span><span class="sxs-lookup"><span data-stu-id="d10ed-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="d10ed-125">Si eligió *Agregar los registros DNS* , seleccione **siguiente** y verá una página con todos los registros que necesita agregar al sitio web de sus registradores para configurar el dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="d10ed-126">Si el portal no reconoce el registrador, puede [seguir estas instrucciones generales.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="d10ed-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="d10ed-127">Consulte nuestra lista de [instrucciones específicas del host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) para buscar su host y siga los pasos para agregar todos los registros que necesite.</span><span class="sxs-lookup"><span data-stu-id="d10ed-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="d10ed-128">Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="d10ed-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="d10ed-129">Si desea esperar más tarde, desplácese hasta la parte inferior y seleccione **omitir este paso**.</span><span class="sxs-lookup"><span data-stu-id="d10ed-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="d10ed-130">Haga clic en **Finalizar** (ya está listo).</span><span class="sxs-lookup"><span data-stu-id="d10ed-130">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="d10ed-131">Agregar o editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="d10ed-131">Add or edit custom DNS records</span></span>

<span data-ttu-id="d10ed-132">Siga los pasos a continuación para agregar un registro personalizado para un sitio web o un servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="d10ed-132">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="d10ed-133">Inicie sesión en el centro de administración de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="d10ed-133">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="d10ed-134">Vaya a la página **configuración**  > de**dominios** .</span><span class="sxs-lookup"><span data-stu-id="d10ed-134">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="d10ed-135">En la página **Dominios**, seleccione un dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-135">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="d10ed-136">En **configuración DNS**, seleccione **registros personalizados**; a continuación, seleccione **nuevo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="d10ed-136">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="d10ed-137">Seleccione el tipo de registro DNS que desea agregar y escriba la información del nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="d10ed-137">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="d10ed-138">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d10ed-138">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="d10ed-139">Registradores con conexión de dominio</span><span class="sxs-lookup"><span data-stu-id="d10ed-139">Registrars with Domain Connect</span></span>

<span data-ttu-id="d10ed-140">Los registradores habilitados para la [conexión de dominio](https://www.domainconnect.org/) le permiten agregar su dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.</span><span class="sxs-lookup"><span data-stu-id="d10ed-140">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="d10ed-141">En el asistente, simplemente confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros del dominio, por lo que el correo electrónico se entrega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcionan con su dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-141">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d10ed-142">Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="d10ed-142">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="d10ed-143">Registradores de conexión de dominio que se integran con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d10ed-143">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="d10ed-144">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="d10ed-144">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="d10ed-145">123Reg</span><span class="sxs-lookup"><span data-stu-id="d10ed-145">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="d10ed-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="d10ed-146">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="d10ed-147">WordPress</span><span class="sxs-lookup"><span data-stu-id="d10ed-147">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="d10ed-148">Plesk</span><span class="sxs-lookup"><span data-stu-id="d10ed-148">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="d10ed-149">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="d10ed-149">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="d10ed-150">SecureServer o WildWestDomains (revendedores de GoDaddy que usen el hospedaje de SecureServer DNS)</span><span class="sxs-lookup"><span data-stu-id="d10ed-150">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="d10ed-151">Dominios de MadDog</span><span class="sxs-lookup"><span data-stu-id="d10ed-151">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="d10ed-152">CheapNames</span><span class="sxs-lookup"><span data-stu-id="d10ed-152">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="d10ed-153">¿Qué ocurre con mi correo electrónico y el sitio web?</span><span class="sxs-lookup"><span data-stu-id="d10ed-153">What happens to my email and website?</span></span>

<span data-ttu-id="d10ed-154">Una vez finalizada la instalación, el registro MX de su dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a ser de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d10ed-154">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="d10ed-155">Asegúrese de que agregó usuarios y configuró los buzones en Office 365 para todos los usuarios que reciban correo electrónico en el dominio.</span><span class="sxs-lookup"><span data-stu-id="d10ed-155">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="d10ed-156">Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="d10ed-156">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="d10ed-157">Los pasos de configuración de conexión de dominio no afectan a su sitio Web.</span><span class="sxs-lookup"><span data-stu-id="d10ed-157">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d10ed-158">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="d10ed-158">Related articles</span></span>

[<span data-ttu-id="d10ed-159">Preguntas más frecuentes de dominios</span><span class="sxs-lookup"><span data-stu-id="d10ed-159">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="d10ed-160">¿Qué es un dominio?</span><span class="sxs-lookup"><span data-stu-id="d10ed-160">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="d10ed-161">Comprar un nombre de dominio en Office 365</span><span class="sxs-lookup"><span data-stu-id="d10ed-161">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="d10ed-162">Configurar su dominio (instrucciones específicas del host)</span><span class="sxs-lookup"><span data-stu-id="d10ed-162">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="d10ed-163">Obtener ayuda con los dominios</span><span class="sxs-lookup"><span data-stu-id="d10ed-163">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
