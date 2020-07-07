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
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049741"
---
# <a name="domains-faq"></a><span data-ttu-id="b5f44-103">Preguntas más frecuentes de dominios</span><span class="sxs-lookup"><span data-stu-id="b5f44-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b5f44-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="b5f44-104">The admin center is changing.</span></span> <span data-ttu-id="b5f44-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b5f44-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b5f44-106">Este artículo contiene respuestas a las preguntas más frecuentes acerca de los dominios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5f44-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="b5f44-107">Si no encuentra una respuesta a su pregunta, infórmenos de ello dejando un comentario y lo agregaremos a la lista.</span><span class="sxs-lookup"><span data-stu-id="b5f44-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="b5f44-108">En este artículo</span><span class="sxs-lookup"><span data-stu-id="b5f44-108">In this article</span></span>

<span data-ttu-id="b5f44-109">[¿Qué es la prioridad mx?](#what-is-mx-priority) 
 [¿Cómo puedo validar los registros de SPF para mi dominio?](#how-can-i-validate-spf-records-for-my-domain) 
 [¿Qué es un nombre de dominio?](#what-is-a-domain-name) 
 [¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [¿Cómo se configura o se cambia el dominio predeterminado en Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 [¿Puedo agregar subdominios personalizados o varios dominios a Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [¿Por qué tengo un dominio "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [¿Por qué tengo un dominio "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [¿Cómo puedo comprobar mi estado para ONG o educación?](#how-do-i-verify-my-nonprofit-or-education-status)</span><span class="sxs-lookup"><span data-stu-id="b5f44-109">[What is MX priority?](#what-is-mx-priority)
[How can I validate SPF records for my domain?](#how-can-i-validate-spf-records-for-my-domain)
[What is a domain name?](#what-is-a-domain-name)
[What happens if my DNS provider doesn't support certain record types?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
[How do I set or change the default domain in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
[Can I add custom subdomains or multiple domains to Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
[Why do I have an "onmicrosoft.com" domain?](#why-do-i-have-an-onmicrosoftcom-domain)
[Why do I have an "onmicrosoft.de" domain?](#why-do-i-have-an-onmicrosoftde-domain)
[How do I verify my nonprofit or education status?](#how-do-i-verify-my-nonprofit-or-education-status)</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="b5f44-110">¿Qué es una prioridad de MX?</span><span class="sxs-lookup"><span data-stu-id="b5f44-110">What is MX priority?</span></span>

<span data-ttu-id="b5f44-111">El correo se entrega al servidor de intercambio de correo con el número de preferencia más bajo (prioridad más alta), por lo que el registro MX que use para el enrutamiento de correo debe tener el número de preferencia más bajo, normalmente 0 o *alta* prioridad.</span><span class="sxs-lookup"><span data-stu-id="b5f44-111">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="b5f44-112">Al crear un registro MX, la mayoría de los proveedores de hospedaje DNS requieren que establezca el número de preferencia.</span><span class="sxs-lookup"><span data-stu-id="b5f44-112">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="b5f44-113">Algunas etiquetas son la *preferencia* de cuadro y alguna de ellas tiene *prioridad* .</span><span class="sxs-lookup"><span data-stu-id="b5f44-113">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="b5f44-114">Algunos requieren un número y algunos le piden que seleccione *bajo* , *medio* o *alto* .</span><span class="sxs-lookup"><span data-stu-id="b5f44-114">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="b5f44-115">Si solo tiene un registro MX, cualquier valor es correcto para prioridad o preferencia.</span><span class="sxs-lookup"><span data-stu-id="b5f44-115">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="b5f44-116">Si tiene más de uno, asegúrese de que el registro MX para el enrutamiento de correo tiene una prioridad mayor que la usada para validar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-116">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="b5f44-117">¿Cómo puedo validar los registros de SPF para mi dominio?</span><span class="sxs-lookup"><span data-stu-id="b5f44-117">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="b5f44-118">Es importante que tenga o cree **un solo registro TXT para SPF**.</span><span class="sxs-lookup"><span data-stu-id="b5f44-118">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="b5f44-119">Si ya tiene un registro de SPF, debe anexar a él los nuevos valores de Microsoft 365, en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="b5f44-119">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="b5f44-120">Una vez que haya agregado o actualizado el registro de SPF para el correo electrónico de Microsoft, debe asegurarse de que la sintaxis es correcta con una de estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="b5f44-120">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="b5f44-121">Herramientas de prueba de registros de SPF</span><span class="sxs-lookup"><span data-stu-id="b5f44-121">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="b5f44-122">Surveyor de SPF</span><span class="sxs-lookup"><span data-stu-id="b5f44-122">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="b5f44-123">Preparar la interfaz web</span><span class="sxs-lookup"><span data-stu-id="b5f44-123">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="b5f44-124">¿Qué es un nombre de dominio?</span><span class="sxs-lookup"><span data-stu-id="b5f44-124">What is a domain name?</span></span>

<span data-ttu-id="b5f44-125">Un dominio es un nombre único que aparece después del signo **@** en las direcciones de correo electrónico y después de **www.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="b5f44-126">en las direcciones web.</span><span class="sxs-lookup"><span data-stu-id="b5f44-126">in web addresses.</span></span> <span data-ttu-id="b5f44-127">Normalmente, toma la forma del nombre de la organización y un sufijo de Internet estándar, como *yourbusiness.com* o *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="b5f44-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="b5f44-128">Usar un dominio personalizado como "**rob \@ contoso.com**" con Microsoft 365 puede ayudarle a crear credibilidad y un reconocimiento para su marca.</span><span class="sxs-lookup"><span data-stu-id="b5f44-128">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="b5f44-129">Puede [comprar un dominio en Microsoft 365 y configurarlo automáticamente](../get-help-with-domains/buy-a-domain-name.md), o puede comprar o traer uno que ya es propietario de un registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="b5f44-129">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="b5f44-130">¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?</span><span class="sxs-lookup"><span data-stu-id="b5f44-130">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="b5f44-131">Si administra sus propios registros DNS y su host DNS no admite todos los registros DNS que Microsoft 365 necesita, algunas características de Microsoft 365 no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="b5f44-131">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="b5f44-132">Le recomendamos que transfiera su dominio a un registrador que admita todos los registros DNS necesarios.</span><span class="sxs-lookup"><span data-stu-id="b5f44-132">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="b5f44-133">Proveedores que admiten todos los registros DNS necesarios:</span><span class="sxs-lookup"><span data-stu-id="b5f44-133">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="b5f44-134">Dynadot</span><span class="sxs-lookup"><span data-stu-id="b5f44-134">Dynadot</span></span>
    
- <span data-ttu-id="b5f44-135">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="b5f44-135">eNomCentral</span></span>
    
- <span data-ttu-id="b5f44-136">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="b5f44-136">Europe Registry</span></span>
    
- <span data-ttu-id="b5f44-137">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="b5f44-137">GoDaddy</span></span>
    
- <span data-ttu-id="b5f44-138">Coloque</span><span class="sxs-lookup"><span data-stu-id="b5f44-138">Hover</span></span>
    
- <span data-ttu-id="b5f44-139">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="b5f44-139">MyHosting.com</span></span>
    
- <span data-ttu-id="b5f44-140">Name.com</span><span class="sxs-lookup"><span data-stu-id="b5f44-140">Name.com</span></span>
    
- <span data-ttu-id="b5f44-141">Voz casi gratuita</span><span class="sxs-lookup"><span data-stu-id="b5f44-141">Nearly Free Speech</span></span>
    
- <span data-ttu-id="b5f44-142">Nettica</span><span class="sxs-lookup"><span data-stu-id="b5f44-142">Nettica</span></span>
    
- <span data-ttu-id="b5f44-143">Centro de información de redes (NIC)</span><span class="sxs-lookup"><span data-stu-id="b5f44-143">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="b5f44-144">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="b5f44-144">Network Solutions</span></span>
    
- <span data-ttu-id="b5f44-145">Register.com</span><span class="sxs-lookup"><span data-stu-id="b5f44-145">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="b5f44-146">¿Cómo se configura o se cambia el dominio predeterminado en Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b5f44-146">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="b5f44-147">Debe tener al menos un dominio personalizado que haya agregado a Microsoft 365 para poder elegir un dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b5f44-147">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b5f44-148">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="b5f44-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b5f44-149">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="b5f44-149">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b5f44-150">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="b5f44-150">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="b5f44-151">En la página **dominios** , seleccione el dominio que desea establecer como predeterminado para las nuevas direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b5f44-151">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="b5f44-152">Seleccione **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="b5f44-152">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="b5f44-153">No puede cambiar el nombre del dominio inicial *. onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="b5f44-153">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="b5f44-154">No puede cambiar el nombre del dominio inicial *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="b5f44-154">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="b5f44-155">No puede cambiar el nombre del dominio inicial *. Partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="b5f44-155">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="b5f44-156">¿Puedo agregar subdominios personalizados o varios dominios a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b5f44-156">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="b5f44-157">Sí.</span><span class="sxs-lookup"><span data-stu-id="b5f44-157">Yes.</span></span> <span data-ttu-id="b5f44-158">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="b5f44-158">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="b5f44-159">Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="b5f44-159">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="b5f44-160">Afirma!</span><span class="sxs-lookup"><span data-stu-id="b5f44-160">Yes!</span></span> <span data-ttu-id="b5f44-161">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="b5f44-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="b5f44-162">Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="b5f44-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="b5f44-163">Afirma!</span><span class="sxs-lookup"><span data-stu-id="b5f44-163">Yes!</span></span> <span data-ttu-id="b5f44-164">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="b5f44-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="b5f44-165">Si permite que 21Vianet administre la configuración DNS con registros NS, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="b5f44-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="b5f44-166">Normalmente, puede Agregar hasta 900 dominios a su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5f44-166">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="b5f44-167">Por ejemplo, puede Agregar los dominios contoso.com y contosomarketing.com y, a continuación, agregar los subdominios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, etc.</span><span class="sxs-lookup"><span data-stu-id="b5f44-167">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="b5f44-168">Cuando se agrega un subdominio, se comprueba automáticamente según el dominio primario que se está comprobando.</span><span class="sxs-lookup"><span data-stu-id="b5f44-168">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="b5f44-169">Cuando se agregan varios dominios a Microsoft 365, puede hospedar cualquiera de los servicios (como correo electrónico) en cualquiera de los dominios que haya agregado.</span><span class="sxs-lookup"><span data-stu-id="b5f44-169">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="b5f44-170">*Al cambiar el correo electrónico a Microsoft 365, al actualizar el registro MX de un dominio, todo el correo electrónico enviado a ese dominio empezará a ser de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="b5f44-170">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b5f44-171">Si agregó un dominio contoso.com a una suscripción de Microsoft 365, también puede Agregar el subdominio xyz.contoso.com a otra organización 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5f44-171">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="b5f44-172">Al agregar el subdominio, se le pedirá que agregue un registro TXT en el proveedor de host DNS.</span><span class="sxs-lookup"><span data-stu-id="b5f44-172">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="b5f44-173">¿Por qué tengo un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="b5f44-173">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="b5f44-174">Microsoft 365 crea un dominio para usted, como *contoso.onmicrosoft.com*, cuando se registra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-174">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="b5f44-175">El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="b5f44-175">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="b5f44-176">**Si quiere que su correo sea similar a *Alan \@ contoso.com*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos que se indican en [Agregar usuarios y dominios a Microsoft 365](add-domain.md) si es el propietario ya.</span><span class="sxs-lookup"><span data-stu-id="b5f44-176">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="b5f44-177">**No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-177">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="b5f44-178">Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.com, no puede cambiarlo a fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b5f44-178">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="b5f44-179">Para usar un dominio de onmicrosoft.com diferente, debe iniciar una nueva suscripción con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5f44-179">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="b5f44-180">**No puede cambiar el nombre de la dirección URL del sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-180">**You can't rename your team site URL.**</span></span> <span data-ttu-id="b5f44-181">La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b5f44-181">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="b5f44-182">Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="b5f44-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="b5f44-183">**No puede quitar el dominio de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-183">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="b5f44-184">Microsoft 365 necesita mantenerlo bien porque se usa en segundo plano para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b5f44-184">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="b5f44-185">Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="b5f44-185">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="b5f44-186">Puede seguir usando el dominio de onmicrosoft.com inicial incluso después de agregar el dominio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="b5f44-187">Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.</span><span class="sxs-lookup"><span data-stu-id="b5f44-187">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="b5f44-188">¿Por qué tengo un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="b5f44-188">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="b5f44-189">Microsoft 365 crea un dominio para usted, como *contoso.onmicrosoft.de*, cuando se registra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-189">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="b5f44-190">El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="b5f44-190">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="b5f44-191">**Si quiere que su correo sea similar a *Alan@contoso.de*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos descritos en [Agregar los usuarios y el dominio a Microsoft 365](add-domain.md) si ya es el propietario.</span><span class="sxs-lookup"><span data-stu-id="b5f44-191">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="b5f44-192">**No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-192">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="b5f44-193">Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.de, no puede cambiarlo a fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="b5f44-193">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="b5f44-194">Para usar un dominio de onmicrosoft.de diferente, debe iniciar una nueva suscripción con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5f44-194">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="b5f44-195">**No puede cambiar el nombre de la dirección URL del sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-195">**You can't rename your team site URL.**</span></span> <span data-ttu-id="b5f44-196">La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.de. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="b5f44-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="b5f44-197">**No puede quitar el dominio de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="b5f44-197">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="b5f44-198">Microsoft 365 necesita mantenerlo bien porque se usa en segundo plano para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b5f44-198">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="b5f44-199">Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="b5f44-199">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="b5f44-200">Puede seguir usando el dominio de onmicrosoft.de inicial incluso después de agregar el dominio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="b5f44-201">Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.</span><span class="sxs-lookup"><span data-stu-id="b5f44-201">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="b5f44-202">¿Cómo puedo comprobar mi estado para ONG o educación?</span><span class="sxs-lookup"><span data-stu-id="b5f44-202">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="b5f44-203">Seleccione **configurar** en el [centro de administración](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="b5f44-203">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="b5f44-204">(Asegúrese de iniciar sesión primero en Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="b5f44-204">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="b5f44-205">Para convertirse en el administrador de su centro educativo, seleccione la opción **convertirse en Administrador** en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5f44-205">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="b5f44-206">Se le pedirá que agregue un registro DNS TXT en el sitio web del host DNS de su dominio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-206">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="b5f44-207">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="b5f44-207">Why?</span></span> <span data-ttu-id="b5f44-208">Debido a que inicia sesión en el host DNS y agrega un registro para su dominio, usted prueba a Microsoft 365 que es el propietario del nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-208">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="b5f44-209">Después de agregar el registro, volverá al portal de 365 de Microsoft y confirmará que lo ha agregado, por lo que Microsoft 365 puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="b5f44-209">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="b5f44-210">¿Tiene una ONG y desea obtener Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b5f44-210">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="b5f44-211">Asegúrese de [que su organización sea cualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) y, a continuación, Regístrese para obtener el servicio.</span><span class="sxs-lookup"><span data-stu-id="b5f44-211">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="b5f44-212">¿Quiere saber más sobre cómo convertirse en el administrador de su centro educativo?</span><span class="sxs-lookup"><span data-stu-id="b5f44-212">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="b5f44-213">[Obtenga información sobre ti](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="b5f44-213">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>