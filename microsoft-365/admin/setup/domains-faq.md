---
title: Preguntas más frecuentes de dominios
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Obtenga más información acerca de los dominios buscando respuestas a las preguntas más frecuentes.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068108"
---
# <a name="domains-faq"></a><span data-ttu-id="0edb2-103">Preguntas más frecuentes de dominios</span><span class="sxs-lookup"><span data-stu-id="0edb2-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0edb2-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="0edb2-104">The admin center is changing.</span></span> <span data-ttu-id="0edb2-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0edb2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="0edb2-106">Este artículo contiene respuestas a las preguntas más frecuentes acerca de los dominios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0edb2-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="0edb2-107">Si no encuentra una respuesta a su pregunta, infórmenos de ello dejando un comentario y lo agregaremos a la lista.</span><span class="sxs-lookup"><span data-stu-id="0edb2-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="0edb2-108">En este artículo</span><span class="sxs-lookup"><span data-stu-id="0edb2-108">In this article</span></span>

- [<span data-ttu-id="0edb2-109">¿Qué es una prioridad de MX?</span><span class="sxs-lookup"><span data-stu-id="0edb2-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="0edb2-110">¿Cómo puedo validar los registros de SPF para mi dominio?</span><span class="sxs-lookup"><span data-stu-id="0edb2-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="0edb2-111">¿Qué es un nombre de dominio?</span><span class="sxs-lookup"><span data-stu-id="0edb2-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="0edb2-112">¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?</span><span class="sxs-lookup"><span data-stu-id="0edb2-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="0edb2-113">¿Cómo se configura o se cambia el dominio predeterminado en Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0edb2-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="0edb2-114">¿Puedo agregar subdominios personalizados o varios dominios a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0edb2-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="0edb2-115">¿Por qué tengo un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="0edb2-115">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="0edb2-116">¿Por qué tengo un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="0edb2-116">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="0edb2-117">¿Cómo puedo comprobar mi estado para ONG o educación?</span><span class="sxs-lookup"><span data-stu-id="0edb2-117">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="0edb2-118">¿Qué es una prioridad de MX?</span><span class="sxs-lookup"><span data-stu-id="0edb2-118">What is MX priority?</span></span>

<span data-ttu-id="0edb2-119">El correo se entrega al servidor de intercambio de correo con el número de preferencia más bajo (prioridad más alta), por lo que el registro MX que use para el enrutamiento de correo debe tener el número de preferencia más bajo, normalmente 0 o *alta* prioridad.</span><span class="sxs-lookup"><span data-stu-id="0edb2-119">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="0edb2-120">Al crear un registro MX, la mayoría de los proveedores de hospedaje DNS requieren que establezca el número de preferencia.</span><span class="sxs-lookup"><span data-stu-id="0edb2-120">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="0edb2-121">Algunas etiquetas son la *preferencia* de cuadro y alguna de ellas tiene *prioridad* .</span><span class="sxs-lookup"><span data-stu-id="0edb2-121">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="0edb2-122">Algunos requieren un número y algunos le piden que seleccione *bajo* , *medio* o *alto* .</span><span class="sxs-lookup"><span data-stu-id="0edb2-122">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="0edb2-123">Si solo tiene un registro MX, cualquier valor es correcto para prioridad o preferencia.</span><span class="sxs-lookup"><span data-stu-id="0edb2-123">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="0edb2-124">Si tiene más de uno, asegúrese de que el registro MX para el enrutamiento de correo tiene una prioridad mayor que la usada para validar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-124">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="0edb2-125">¿Cómo puedo validar los registros de SPF para mi dominio?</span><span class="sxs-lookup"><span data-stu-id="0edb2-125">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="0edb2-126">Es importante que tenga o cree **un solo registro TXT para SPF**.</span><span class="sxs-lookup"><span data-stu-id="0edb2-126">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="0edb2-127">Si ya tiene un registro de SPF, debe anexar a él los nuevos valores de Microsoft 365, en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="0edb2-127">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="0edb2-128">Una vez que haya agregado o actualizado el registro de SPF para el correo electrónico de Microsoft, debe asegurarse de que la sintaxis es correcta con una de estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="0edb2-128">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="0edb2-129">Herramientas de prueba de registros de SPF</span><span class="sxs-lookup"><span data-stu-id="0edb2-129">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="0edb2-130">Surveyor de SPF</span><span class="sxs-lookup"><span data-stu-id="0edb2-130">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="0edb2-131">Preparar la interfaz web</span><span class="sxs-lookup"><span data-stu-id="0edb2-131">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="0edb2-132">¿Qué es un nombre de dominio?</span><span class="sxs-lookup"><span data-stu-id="0edb2-132">What is a domain name?</span></span>

<span data-ttu-id="0edb2-133">Un dominio es un nombre único que aparece después del signo **@** en las direcciones de correo electrónico y después de **www.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-133">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="0edb2-134">en las direcciones web.</span><span class="sxs-lookup"><span data-stu-id="0edb2-134">in web addresses.</span></span> <span data-ttu-id="0edb2-135">Normalmente, toma la forma del nombre de la organización y un sufijo de Internet estándar, como *yourbusiness.com* o *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="0edb2-135">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="0edb2-136">Usar un dominio personalizado como "**rob \@ contoso.com**" con Microsoft 365 puede ayudarle a crear credibilidad y un reconocimiento para su marca.</span><span class="sxs-lookup"><span data-stu-id="0edb2-136">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="0edb2-137">Puede [comprar un dominio en Microsoft 365 y configurarlo automáticamente](../get-help-with-domains/buy-a-domain-name.md), o puede comprar o traer uno que ya es propietario de un registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="0edb2-137">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="0edb2-138">¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?</span><span class="sxs-lookup"><span data-stu-id="0edb2-138">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="0edb2-139">Si administra sus propios registros DNS y su host DNS no admite todos los registros DNS que Microsoft 365 necesita, algunas características de Microsoft 365 no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="0edb2-139">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="0edb2-140">Le recomendamos que transfiera su dominio a un registrador que admita todos los registros DNS necesarios.</span><span class="sxs-lookup"><span data-stu-id="0edb2-140">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="0edb2-141">Proveedores que admiten todos los registros DNS necesarios:</span><span class="sxs-lookup"><span data-stu-id="0edb2-141">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="0edb2-142">Dynadot</span><span class="sxs-lookup"><span data-stu-id="0edb2-142">Dynadot</span></span>
    
- <span data-ttu-id="0edb2-143">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="0edb2-143">eNomCentral</span></span>
    
- <span data-ttu-id="0edb2-144">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="0edb2-144">Europe Registry</span></span>
    
- <span data-ttu-id="0edb2-145">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="0edb2-145">GoDaddy</span></span>
    
- <span data-ttu-id="0edb2-146">Coloque</span><span class="sxs-lookup"><span data-stu-id="0edb2-146">Hover</span></span>
    
- <span data-ttu-id="0edb2-147">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="0edb2-147">MyHosting.com</span></span>
    
- <span data-ttu-id="0edb2-148">Name.com</span><span class="sxs-lookup"><span data-stu-id="0edb2-148">Name.com</span></span>
    
- <span data-ttu-id="0edb2-149">Voz casi gratuita</span><span class="sxs-lookup"><span data-stu-id="0edb2-149">Nearly Free Speech</span></span>
    
- <span data-ttu-id="0edb2-150">Nettica</span><span class="sxs-lookup"><span data-stu-id="0edb2-150">Nettica</span></span>
    
- <span data-ttu-id="0edb2-151">Centro de información de redes (NIC)</span><span class="sxs-lookup"><span data-stu-id="0edb2-151">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="0edb2-152">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="0edb2-152">Network Solutions</span></span>
    
- <span data-ttu-id="0edb2-153">Register.com</span><span class="sxs-lookup"><span data-stu-id="0edb2-153">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="0edb2-154">¿Cómo se configura o se cambia el dominio predeterminado en Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0edb2-154">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="0edb2-155">Debe tener al menos un dominio personalizado que haya agregado a Microsoft 365 para poder elegir un dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0edb2-155">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0edb2-156">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="0edb2-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0edb2-157">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="0edb2-157">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0edb2-158">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="0edb2-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0edb2-159">En la página **dominios** , seleccione el dominio que desea establecer como predeterminado para las nuevas direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0edb2-159">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="0edb2-160">Seleccione **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="0edb2-160">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="0edb2-161">No puede cambiar el nombre del dominio inicial *. onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="0edb2-161">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="0edb2-162">No puede cambiar el nombre del dominio inicial *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="0edb2-162">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="0edb2-163">No puede cambiar el nombre del dominio inicial *. Partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="0edb2-163">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="0edb2-164">¿Puedo agregar subdominios personalizados o varios dominios a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0edb2-164">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="0edb2-165">Sí.</span><span class="sxs-lookup"><span data-stu-id="0edb2-165">Yes.</span></span> <span data-ttu-id="0edb2-166">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="0edb2-166">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="0edb2-167">Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="0edb2-167">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="0edb2-168">Afirma!</span><span class="sxs-lookup"><span data-stu-id="0edb2-168">Yes!</span></span> <span data-ttu-id="0edb2-169">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="0edb2-169">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="0edb2-170">Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="0edb2-170">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="0edb2-171">Afirma!</span><span class="sxs-lookup"><span data-stu-id="0edb2-171">Yes!</span></span> <span data-ttu-id="0edb2-172">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="0edb2-172">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="0edb2-173">Si permite que 21Vianet administre la configuración DNS con registros NS, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="0edb2-173">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="0edb2-174">Normalmente, puede Agregar hasta 900 dominios a su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0edb2-174">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="0edb2-175">Por ejemplo, puede Agregar los dominios contoso.com y contosomarketing.com y, a continuación, agregar los subdominios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, etc.</span><span class="sxs-lookup"><span data-stu-id="0edb2-175">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="0edb2-176">Cuando se agrega un subdominio, se comprueba automáticamente según el dominio primario que se está comprobando.</span><span class="sxs-lookup"><span data-stu-id="0edb2-176">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="0edb2-177">Cuando se agregan varios dominios a Microsoft 365, puede hospedar cualquiera de los servicios (como correo electrónico) en cualquiera de los dominios que haya agregado.</span><span class="sxs-lookup"><span data-stu-id="0edb2-177">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="0edb2-178">*Al cambiar el correo electrónico a Microsoft 365, al actualizar el registro MX de un dominio, todo el correo electrónico enviado a ese dominio empezará a ser de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="0edb2-178">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0edb2-179">Si agregó un dominio contoso.com a una suscripción de Microsoft 365, también puede Agregar el subdominio xyz.contoso.com a otra organización 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0edb2-179">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="0edb2-180">Al agregar el subdominio, se le pedirá que agregue un registro TXT en el proveedor de host DNS.</span><span class="sxs-lookup"><span data-stu-id="0edb2-180">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="0edb2-181">¿Por qué tengo un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="0edb2-181">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="0edb2-182">Microsoft 365 crea un dominio para usted, como *contoso.onmicrosoft.com*, cuando se registra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-182">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="0edb2-183">El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="0edb2-183">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="0edb2-184">**Si quiere que su correo sea similar a *Alan \@ contoso.com*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos que se indican en [Agregar usuarios y dominios a Microsoft 365](add-domain.md) si es el propietario ya.</span><span class="sxs-lookup"><span data-stu-id="0edb2-184">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="0edb2-185">**No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-185">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="0edb2-186">Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.com, no puede cambiarlo a fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0edb2-186">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="0edb2-187">Para usar un dominio de onmicrosoft.com diferente, debe iniciar una nueva suscripción con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0edb2-187">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="0edb2-188">**No puede cambiar el nombre de la dirección URL del sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-188">**You can't rename your team site URL.**</span></span> <span data-ttu-id="0edb2-189">La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0edb2-189">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="0edb2-190">Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="0edb2-190">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="0edb2-191">**No puede quitar el dominio de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-191">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="0edb2-192">Microsoft 365 necesita mantenerlo bien porque se usa en segundo plano para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="0edb2-192">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="0edb2-193">Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="0edb2-193">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="0edb2-194">Puede seguir usando el dominio de onmicrosoft.com inicial incluso después de agregar el dominio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-194">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="0edb2-195">Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.</span><span class="sxs-lookup"><span data-stu-id="0edb2-195">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="0edb2-196">¿Por qué tengo un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="0edb2-196">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="0edb2-197">Microsoft 365 crea un dominio para usted, como *contoso.onmicrosoft.de*, cuando se registra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-197">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="0edb2-198">El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="0edb2-198">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="0edb2-199">**Si quiere que su correo sea similar a *Alan@contoso.de*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos descritos en [Agregar los usuarios y el dominio a Microsoft 365](add-domain.md) si ya es el propietario.</span><span class="sxs-lookup"><span data-stu-id="0edb2-199">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="0edb2-200">**No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-200">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="0edb2-201">Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.de, no puede cambiarlo a fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="0edb2-201">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="0edb2-202">Para usar un dominio de onmicrosoft.de diferente, debe iniciar una nueva suscripción con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0edb2-202">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="0edb2-203">**No puede cambiar el nombre de la dirección URL del sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-203">**You can't rename your team site URL.**</span></span> <span data-ttu-id="0edb2-204">La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.de. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="0edb2-204">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="0edb2-205">**No puede quitar el dominio de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="0edb2-205">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="0edb2-206">Microsoft 365 necesita mantenerlo bien porque se usa en segundo plano para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="0edb2-206">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="0edb2-207">Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="0edb2-207">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="0edb2-208">Puede seguir usando el dominio de onmicrosoft.de inicial incluso después de agregar el dominio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-208">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="0edb2-209">Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.</span><span class="sxs-lookup"><span data-stu-id="0edb2-209">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="0edb2-210">¿Cómo puedo comprobar mi estado para ONG o educación?</span><span class="sxs-lookup"><span data-stu-id="0edb2-210">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="0edb2-211">Seleccione **configurar** en el [centro de administración](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="0edb2-211">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="0edb2-212">(Asegúrese de iniciar sesión primero en Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="0edb2-212">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="0edb2-213">Para convertirse en el administrador de su centro educativo, seleccione la opción **convertirse en Administrador** en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0edb2-213">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="0edb2-214">Se le pedirá que agregue un registro DNS TXT en el sitio web del host DNS de su dominio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-214">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="0edb2-215">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="0edb2-215">Why?</span></span> <span data-ttu-id="0edb2-216">Debido a que inicia sesión en el host DNS y agrega un registro para su dominio, usted prueba a Microsoft 365 que es el propietario del nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-216">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="0edb2-217">Después de agregar el registro, volverá al portal de 365 de Microsoft y confirmará que lo ha agregado, por lo que Microsoft 365 puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="0edb2-217">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="0edb2-218">¿Tiene una ONG y desea obtener Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0edb2-218">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="0edb2-219">Asegúrese de [que su organización sea cualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) y, a continuación, Regístrese para obtener el servicio.</span><span class="sxs-lookup"><span data-stu-id="0edb2-219">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="0edb2-220">¿Quiere saber más sobre cómo convertirse en el administrador de su centro educativo?</span><span class="sxs-lookup"><span data-stu-id="0edb2-220">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="0edb2-221">[Obtenga información sobre ti](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="0edb2-221">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>