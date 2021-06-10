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
description: Use el Asistente para la instalación para agregar el dominio Microsoft 365 en el centro de administración de Microsoft 365 agregando un registro DNS en el host DNS.
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635683"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="9d8ac-103">Agregar un dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d8ac-103">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="9d8ac-104">**[Consulte Preguntas más frecuentes acerca de los dominios](domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-104">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="9d8ac-105">*Para agregar, modificar o quitar dominios, **debe ser** administrador **global** de un plan empresarial [o empresarial.](https://products.office.com/business/office) Estos cambios afectan a todo el inquilino, los administradores *personalizados* o los usuarios *normales* no podrán realizar estos cambios.*</span><span class="sxs-lookup"><span data-stu-id="9d8ac-105">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 ## <a name="add-a-domain"></a><span data-ttu-id="9d8ac-106">Agregar un dominio</span><span class="sxs-lookup"><span data-stu-id="9d8ac-106">Add a domain</span></span>

<span data-ttu-id="9d8ac-107">Siga estos pasos para agregar, configurar o seguir configurando un dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9d8ac-108">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="9d8ac-109">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9d8ac-110">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="9d8ac-111">Vaya a la **página Configuración**  >  **dominios.**</span><span class="sxs-lookup"><span data-stu-id="9d8ac-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="9d8ac-112">Seleccione **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="9d8ac-113">Escriba el nombre del dominio que desea agregar y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="9d8ac-114">Elija cómo desea comprobar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="9d8ac-115">Si el registrador de dominio usa [dominio Conectar,](#domain-connect-registrars-integrating-with-microsoft-365) [Microsoft](../get-help-with-domains/domain-connect.md) configurará los registros automáticamente al tener que iniciar sesión en el registrador y confirmar la conexión a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="9d8ac-116">Se te devolverá al Centro de administración y Microsoft comprobará automáticamente tu dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="9d8ac-117">Puede usar un registro TXT para comprobar su dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="9d8ac-118">Seleccione esto y **seleccione Siguiente** para ver instrucciones sobre cómo agregar este registro DNS al sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="9d8ac-119">Esto puede tardar hasta 30 minutos en comprobarse después de agregar el registro.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="9d8ac-120">Puede agregar un archivo de texto al sitio web de su dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="9d8ac-121">Seleccione y descargue el archivo .txt del asistente para la instalación y, a continuación, cargue el archivo en la carpeta de nivel superior del sitio web.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="9d8ac-122">La ruta de acceso al archivo debe ser similar a: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="9d8ac-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="9d8ac-123">Confirmaremos que es el propietario del dominio mediante la búsqueda del archivo en su sitio web.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="9d8ac-124">Elija cómo desea realizar los cambios DNS necesarios para que Microsoft use su dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="9d8ac-125">Elija **Agregar los** registros DNS para mí si su registrador admite dominio [Conectar](#domain-connect-registrars-integrating-with-microsoft-365)y [Microsoft](../get-help-with-domains/domain-connect.md) configurará los registros automáticamente si inicia sesión en su registrador y confirma la conexión a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="9d8ac-126">Elija **Agregaré los** registros DNS yo mismo si desea adjuntar solo servicios de Microsoft 365 específicos a su dominio o si desea omitir esto por ahora y hacerlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="9d8ac-127">**Elija esta opción si sabe exactamente lo que hace.**</span><span class="sxs-lookup"><span data-stu-id="9d8ac-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="9d8ac-128">Si decide agregar *registros DNS*  usted mismo, seleccione Siguiente y verá una página con todos los registros que necesita agregar al sitio web de registradores para configurar su dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="9d8ac-129">Si el portal no reconoce el registrador, puede [seguir estas instrucciones generales.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="9d8ac-130">Consulte nuestra lista de [instrucciones específicas del host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para buscar su host y siga los pasos para agregar todos los registros que necesite.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="9d8ac-131">Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ac-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="9d8ac-132">Si desea esperar más tarde, anule la selección de todos los servicios  y haga clic en Continuar **o,** en el paso de conexión de dominio anterior, elija Más opciones y seleccione **Omitir esto por ahora**.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="9d8ac-133">Selecciona **Finalizar:** ya has terminado.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="9d8ac-134">Agregar o editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="9d8ac-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="9d8ac-135">Siga los pasos siguientes para agregar un registro personalizado para un sitio web o un servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="9d8ac-136">Inicie sesión en el Centro de administración de Microsoft en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="9d8ac-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="9d8ac-137">Vaya a la **página Configuración**   >  **dominios.**</span><span class="sxs-lookup"><span data-stu-id="9d8ac-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="9d8ac-138">En la página **Dominios**, seleccione un dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="9d8ac-139">En **Configuración dns,** seleccione **Registros personalizados;** a **continuación, seleccione Nuevo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="9d8ac-140">Seleccione el tipo de registro DNS que desea agregar y escriba la información del nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="9d8ac-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="9d8ac-142">Registradores con dominio Conectar</span><span class="sxs-lookup"><span data-stu-id="9d8ac-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="9d8ac-143">[Los Conectar](https://www.domainconnect.org/) registradores habilitados permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="9d8ac-144">En el asistente, solo confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros de su dominio, de modo que el correo electrónico llegue a Microsoft 365 y otros servicios de Microsoft 365, como Teams, trabajen con su dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d8ac-145">Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="9d8ac-146">Registradores Conectar de dominio que se integran con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d8ac-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="9d8ac-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="9d8ac-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="9d8ac-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="9d8ac-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="9d8ac-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="9d8ac-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="9d8ac-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="9d8ac-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="9d8ac-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="9d8ac-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="9d8ac-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="9d8ac-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="9d8ac-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="9d8ac-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="9d8ac-154">SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="9d8ac-155">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9d8ac-155">Examples:</span></span>
        - [<span data-ttu-id="9d8ac-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="9d8ac-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="9d8ac-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="9d8ac-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="9d8ac-158">¿Qué sucede con mi correo electrónico y mi sitio web?</span><span class="sxs-lookup"><span data-stu-id="9d8ac-158">What happens to my email and website?</span></span>

<span data-ttu-id="9d8ac-159">Después de finalizar la instalación, el registro MX del dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a llegar a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="9d8ac-160">Asegúrese de que ha agregado usuarios y configurado buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en su dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="9d8ac-161">Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="9d8ac-162">Los pasos Conectar configuración del dominio no afectan al sitio web.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-content"></a><span data-ttu-id="9d8ac-163">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9d8ac-163">Related content</span></span>

<span data-ttu-id="9d8ac-164">[Preguntas más frecuentes sobre dominios](domains-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-164">[Domains FAQ](domains-faq.yml) (article)</span></span>\
[<span data-ttu-id="9d8ac-165">¿Qué es un dominio?</span><span class="sxs-lookup"><span data-stu-id="9d8ac-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md) <span data-ttu-id="9d8ac-166">(artículo)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-166">(article)</span></span>\
<span data-ttu-id="9d8ac-167">[Comprar un nombre de dominio en Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-167">[Buy a domain name in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (article)</span></span>\
<span data-ttu-id="9d8ac-168">[Configurar el dominio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-168">[Set up your domain](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (article)</span></span>