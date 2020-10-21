---
title: Agregar un dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Agregue su dominio a Microsoft 365 en el centro de administración de Microsoft 365 agregando un registro DNS en su host DNS. El Asistente para la instalación le guiará por el proceso.
ms.openlocfilehash: 3a4cd31a37eb01570f58e9cdb83940640768a273
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644620"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="a65e7-104">Agregar un dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a65e7-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a65e7-105">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="a65e7-105">The admin center is changing.</span></span> <span data-ttu-id="a65e7-106">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a65e7-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="a65e7-107">**[Consulte Preguntas más frecuentes acerca de los dominios](domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="a65e7-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="a65e7-108">*Para agregar, modificar o quitar dominios, **debe** ser **administrador global** de un [plan empresarial o](https://products.office.com/business/office)empresarial. Estos cambios afectan a todo el espacio empresarial, los *administradores personalizados* o *los usuarios normales* no podrán realizar estos cambios.*</span><span class="sxs-lookup"><span data-stu-id="a65e7-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="a65e7-109">Siga estos pasos para agregar, configurar o seguir configurando un dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a65e7-110">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="a65e7-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="a65e7-111">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="a65e7-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a65e7-112">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="a65e7-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a65e7-113">Vaya a la página **configuración**de  >  **dominios** .</span><span class="sxs-lookup"><span data-stu-id="a65e7-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="a65e7-114">Seleccione **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="a65e7-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="a65e7-115">Escriba el nombre del dominio que desea agregar y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a65e7-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="a65e7-116">Elija cómo desea comprobar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="a65e7-117">Si el registrador de dominios usa [conexión de dominio](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [configurará los registros automáticamente](../get-help-with-domains/domain-connect.md) al tener que iniciar sesión en su registrador y confirmar la conexión a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a65e7-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="a65e7-118">Se le devolverá al centro de administración y Microsoft, a continuación, comprobará el dominio automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a65e7-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="a65e7-119">Puede usar un registro TXT para comprobar su dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="a65e7-120">Seleccione esta y seleccione **siguiente** para ver instrucciones sobre cómo agregar este registro DNS al sitio web de su registrador.</span><span class="sxs-lookup"><span data-stu-id="a65e7-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="a65e7-121">Esto puede tardar hasta 30 minutos en comprobarse después de agregar el registro.</span><span class="sxs-lookup"><span data-stu-id="a65e7-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="a65e7-122">Puede Agregar un archivo de texto al sitio web del dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="a65e7-123">Seleccione y descargue el archivo. txt desde el Asistente de configuración y, después, cargue el archivo en la carpeta de nivel superior del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="a65e7-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="a65e7-124">La ruta de acceso al archivo debe tener un aspecto similar a: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="a65e7-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="a65e7-125">Le confirmaremos que es el propietario del dominio buscando el archivo en el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="a65e7-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="a65e7-126">Elija cómo desea que los cambios de DNS sean necesarios para que Microsoft use su dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="a65e7-127">Elija **Agregar los registros DNS para mí** si su registrador admite la [conexión de dominio](#domain-connect-registrars-integrating-with-microsoft-365)y Microsoft [configurará los registros automáticamente](../get-help-with-domains/domain-connect.md) al tener que iniciar sesión en su registrador y confirmar la conexión a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a65e7-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="a65e7-128">Elija **voy a agregar los registros DNS yo mismo** si solo quiere adjuntar los servicios específicos de Microsoft 365 a su dominio o si desea omitir este por ahora y hacerlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="a65e7-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="a65e7-129">**Elija esta opción si sabe exactamente lo que hace.**</span><span class="sxs-lookup"><span data-stu-id="a65e7-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="a65e7-130">Si eligió *Agregar los registros DNS*  , seleccione **siguiente** y verá una página con todos los registros que necesita agregar al sitio web de sus registradores para configurar el dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="a65e7-131">Si el portal no reconoce el registrador, puede [seguir estas instrucciones generales.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="a65e7-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="a65e7-132">Consulte nuestra lista de [instrucciones específicas del host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para buscar su host y siga los pasos para agregar todos los registros que necesite.</span><span class="sxs-lookup"><span data-stu-id="a65e7-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="a65e7-133">Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="a65e7-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="a65e7-134">Si desea esperar más adelante, anule la selección de todos los servicios y haga clic en **continuar**o bien, en el paso anterior de la conexión de dominio, elija **más opciones** y seleccione **omitir esta por ahora**.</span><span class="sxs-lookup"><span data-stu-id="a65e7-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="a65e7-135">Haga clic en **Finalizar** (ya está listo).</span><span class="sxs-lookup"><span data-stu-id="a65e7-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="a65e7-136">Agregar o editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="a65e7-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="a65e7-137">Siga los pasos a continuación para agregar un registro personalizado para un sitio web o un servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="a65e7-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="a65e7-138">Inicie sesión en el centro de administración de Microsoft en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="a65e7-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a65e7-139">Vaya a la página **configuración**de   >  **dominios** .</span><span class="sxs-lookup"><span data-stu-id="a65e7-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="a65e7-140">En la página **Dominios**, seleccione un dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="a65e7-141">En **configuración DNS**, seleccione **registros personalizados**; a continuación, seleccione **nuevo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="a65e7-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="a65e7-142">Seleccione el tipo de registro DNS que desea agregar y escriba la información del nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="a65e7-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="a65e7-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a65e7-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="a65e7-144">Registradores con conexión de dominio</span><span class="sxs-lookup"><span data-stu-id="a65e7-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="a65e7-145">Los registradores habilitados para la [conexión de dominio](https://www.domainconnect.org/) le permiten agregar su dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.</span><span class="sxs-lookup"><span data-stu-id="a65e7-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="a65e7-146">En el asistente, simplemente confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros del dominio, por lo que el correo electrónico se entrega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcionan con su dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a65e7-147">Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="a65e7-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="a65e7-148">Registradores de conexión de dominio que se integran con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a65e7-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="a65e7-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="a65e7-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="a65e7-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="a65e7-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="a65e7-151">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="a65e7-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="a65e7-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a65e7-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="a65e7-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="a65e7-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="a65e7-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="a65e7-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="a65e7-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="a65e7-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="a65e7-156">SecureServer o WildWestDomains (revendedores de GoDaddy que usen el hospedaje de SecureServer DNS)</span><span class="sxs-lookup"><span data-stu-id="a65e7-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="a65e7-157">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a65e7-157">Examples:</span></span>
        - [<span data-ttu-id="a65e7-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="a65e7-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="a65e7-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="a65e7-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="a65e7-160">¿Qué ocurre con mi correo electrónico y el sitio web?</span><span class="sxs-lookup"><span data-stu-id="a65e7-160">What happens to my email and website?</span></span>

<span data-ttu-id="a65e7-161">Una vez finalizada la instalación, el registro MX de su dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a ser de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a65e7-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a65e7-162">Asegúrese de que ha agregado usuarios y configurado los buzones en Microsoft 365 para todos los usuarios que obtienen correo electrónico en su dominio.</span><span class="sxs-lookup"><span data-stu-id="a65e7-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="a65e7-163">Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="a65e7-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="a65e7-164">Los pasos de configuración de conexión de dominio no afectan a su sitio Web.</span><span class="sxs-lookup"><span data-stu-id="a65e7-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a65e7-165">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a65e7-165">Related articles</span></span>

[<span data-ttu-id="a65e7-166">Preguntas más frecuentes de dominios</span><span class="sxs-lookup"><span data-stu-id="a65e7-166">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="a65e7-167">¿Qué es un dominio?</span><span class="sxs-lookup"><span data-stu-id="a65e7-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="a65e7-168">Comprar un nombre de dominio en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a65e7-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="a65e7-169">Configurar su dominio (instrucciones específicas del host)</span><span class="sxs-lookup"><span data-stu-id="a65e7-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
