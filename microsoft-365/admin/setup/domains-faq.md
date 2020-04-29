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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Obtenga más información sobre los dominios buscando respuestas a sus preguntas en preguntas más frecuentes.
ms.custom: okr_smb
ms.openlocfilehash: 81e67ee4b22ea0682d65ebc0e48a4b3564e79526
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919486"
---
# <a name="domains-faq"></a><span data-ttu-id="7e452-103">Preguntas más frecuentes de dominios</span><span class="sxs-lookup"><span data-stu-id="7e452-103">Domains FAQ</span></span>

<span data-ttu-id="7e452-104">Este artículo contiene respuestas a las preguntas más frecuentes acerca de los dominios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="7e452-105">Si no encuentra una respuesta a su pregunta, infórmenos de ello dejando un comentario y lo agregaremos a la lista.</span><span class="sxs-lookup"><span data-stu-id="7e452-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="7e452-106">¿Qué es una prioridad de MX?</span><span class="sxs-lookup"><span data-stu-id="7e452-106">What is MX priority?</span></span>

<span data-ttu-id="7e452-107">El correo se entrega al servidor de intercambio de correo con el número de preferencia más bajo (prioridad más alta), por lo que el registro MX que use para el enrutamiento de correo debe tener el número de preferencia más bajo, normalmente 0 o *alta* prioridad.</span><span class="sxs-lookup"><span data-stu-id="7e452-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="7e452-108">Al crear un registro MX, la mayoría de los proveedores de hospedaje DNS requieren que establezca el número de preferencia.</span><span class="sxs-lookup"><span data-stu-id="7e452-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="7e452-109">Algunas etiquetas son la *preferencia* de cuadro y alguna de ellas tiene *prioridad* .</span><span class="sxs-lookup"><span data-stu-id="7e452-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="7e452-110">Algunos requieren un número y algunos le piden que seleccione *bajo* , *medio* o *alto* .</span><span class="sxs-lookup"><span data-stu-id="7e452-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="7e452-111">Si solo tiene un registro MX, cualquier valor es correcto para prioridad o preferencia.</span><span class="sxs-lookup"><span data-stu-id="7e452-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="7e452-112">Si tiene más de uno, asegúrese de que el registro MX para el enrutamiento de correo tiene una prioridad mayor que la usada para validar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="7e452-113">¿Cómo puedo validar los registros de SPF para mi dominio?</span><span class="sxs-lookup"><span data-stu-id="7e452-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="7e452-114">Es importante que tenga o cree **un solo registro TXT para SPF**.</span><span class="sxs-lookup"><span data-stu-id="7e452-114">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="7e452-115">Si ya tiene un registro de SPF, debe anexar a él los nuevos valores de Office 365, en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="7e452-115">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="7e452-116">Una vez que haya agregado o actualizado el registro de SPF para el correo electrónico de Microsoft, debe asegurarse de que la sintaxis es correcta con una de estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="7e452-116">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="7e452-117">Herramientas de prueba de registros de SPF</span><span class="sxs-lookup"><span data-stu-id="7e452-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="7e452-118">Surveyor de SPF</span><span class="sxs-lookup"><span data-stu-id="7e452-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="7e452-119">Preparar la interfaz web</span><span class="sxs-lookup"><span data-stu-id="7e452-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="7e452-120">¿Cómo administra Office 365 los registros DNS?</span><span class="sxs-lookup"><span data-stu-id="7e452-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="7e452-121">Hay dos opciones para la administración de DNS con Office 365:</span><span class="sxs-lookup"><span data-stu-id="7e452-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="7e452-122">Puede cambiar los registros del servidor de nombres (NS) y, a continuación, Microsoft se encarga de todos los registros específicos del servicio, como la configuración de su registro MX para el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-122">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="7e452-123">**Recomenda**</span><span class="sxs-lookup"><span data-stu-id="7e452-123">**(Recommended)**</span></span>
    
2. <span data-ttu-id="7e452-124">Agregue los registros DNS para el correo electrónico y otros servicios de Office 365 en su host DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-124">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="7e452-125">**(Solo expertos)**</span><span class="sxs-lookup"><span data-stu-id="7e452-125">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="7e452-126">Office 365 crea y hospeda los registros DNS</span><span class="sxs-lookup"><span data-stu-id="7e452-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="7e452-127">**Ventajas**</span><span class="sxs-lookup"><span data-stu-id="7e452-127">**Advantages**</span></span> 
- <span data-ttu-id="7e452-128">No tiene que preocuparse por cometer errores en los valores que escribió para los registros DNS para los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="7e452-129">Tiene más flexibilidad en la elección del registrador de dominios y el host DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="7e452-130">Cualquier proveedor que le permita cambiar los registros del servidor de nombres funcionará, incluso si el proveedor no admite todos los tipos de registros necesarios.</span><span class="sxs-lookup"><span data-stu-id="7e452-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="7e452-131">Cuando Office 365 agrega nuevos registros DNS, no es necesario realizar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="7e452-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="7e452-132">Desventajas</span><span class="sxs-lookup"><span data-stu-id="7e452-132">Disadvantages</span></span> 
- <span data-ttu-id="7e452-133">No puede cambiar los registros DNS para hospedar correo electrónico fuera de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="7e452-134">Si ya usa un sitio web público con su dominio para su dirección, como www.fourthcoffee.com, debe redirigir a los usuarios a esa dirección desde Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="7e452-135">La configuración de la redirección requiere una dirección IP estática, que no siempre está disponible fácilmente para los sitios web públicos.</span><span class="sxs-lookup"><span data-stu-id="7e452-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="7e452-136">-Si su registrador de dominios actual no le permite cambiar los registros del servidor de nombres de su dominio, tiene que cambiar a otro registrador para usar esta opción de administración de DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="7e452-137">Los registros DNS se administran personalmente</span><span class="sxs-lookup"><span data-stu-id="7e452-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="7e452-138">Ventajas</span><span class="sxs-lookup"><span data-stu-id="7e452-138">Advantages</span></span>
- <span data-ttu-id="7e452-139">Puede controlar los registros DNS para los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="7e452-140">Si tiene un sitio web público con su dominio para su dirección, como www.fourthcoffee.com, no tiene que preocuparse por usar el redireccionamiento para asegurarse de que los usuarios aún puedan acceder a su sitio web después de configurar su dominio en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="7e452-141">Tiene la flexibilidad para hospedar correo electrónico en otro lugar, como con un servidor de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="7e452-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="7e452-142">Desventajas</span><span class="sxs-lookup"><span data-stu-id="7e452-142">Disadvantages</span></span>
<span data-ttu-id="7e452-143">Debe configurar los registros DNS para los servicios de Office 365 personalmente (a menos que tenga un dominio de GoDaddy).</span><span class="sxs-lookup"><span data-stu-id="7e452-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="7e452-144">Si su host DNS actual no es compatible con todos los tipos de registro necesarios para Microsoft 365, algunas características no estarán disponibles y es posible que deba cambiar a un host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="7e452-144">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="7e452-145">Cuando Office 365 cambia los requisitos para los registros DNS o agrega nuevos servicios, debe realizar las actualizaciones personalmente en el host DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="7e452-146">¿Qué es un nombre de dominio?</span><span class="sxs-lookup"><span data-stu-id="7e452-146">What is a domain name?</span></span>


<span data-ttu-id="7e452-147">Un dominio es un nombre único que aparece después del signo **@** en las direcciones de correo electrónico y después de **www.**</span><span class="sxs-lookup"><span data-stu-id="7e452-147">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="7e452-148">en las direcciones web.</span><span class="sxs-lookup"><span data-stu-id="7e452-148">in web addresses.</span></span> <span data-ttu-id="7e452-149">Normalmente, toma la forma del nombre de la organización y un sufijo de Internet estándar, como *yourbusiness.com* o *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="7e452-149">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="7e452-150">Usar un dominio personalizado como "**rob\@contoso.com**" con Office 365 puede ayudarle a crear credibilidad y un reconocimiento para su marca.</span><span class="sxs-lookup"><span data-stu-id="7e452-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="7e452-151">Puede [comprar un dominio en Office 365 y configurarlo automáticamente](../get-help-with-domains/buy-a-domain-name.md), o puede comprar o traer uno que ya es propietario de un registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="7e452-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="7e452-152">¿Puedo transferir un dominio que he comprado de Microsoft a otro proveedor?</span><span class="sxs-lookup"><span data-stu-id="7e452-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="7e452-153">Sí, pero no puede transferir un dominio de Office 365 a otro registrador hasta 60 días después de que lo haya comprado con Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="7e452-154">Tenga en cuenta que una consulta *Whois* mostrará un registrador de dominios de Office 365 comprado como dominios silvestres de Westn LLC.</span><span class="sxs-lookup"><span data-stu-id="7e452-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="7e452-155">Sin embargo, solo debe ponerse en contacto con Office 365 en relación con el dominio adquirido de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="7e452-156">Siga los pasos siguientes para obtener el código en Office 365 y, a continuación, vaya al sitio web del otro registrador de dominios para configurar la transferencia de su nombre de dominio a dicho registrador.</span><span class="sxs-lookup"><span data-stu-id="7e452-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7e452-157">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7e452-158">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7e452-159">En el centro de administración, vaya a la página de **configuración** > de <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">licencias</a> .</span><span class="sxs-lookup"><span data-stu-id="7e452-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7e452-160">En la página **dominios** , seleccione el dominio de Office 365 que desea transferir a otro registrador de dominios y, a continuación, seleccione **transferencia** > de dominio**Habilitar transferencia de dominio**.</span><span class="sxs-lookup"><span data-stu-id="7e452-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="7e452-161">Siga los pasos para preparar la transferencia del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="7e452-162">Una vez que obtenga el código, vaya al sitio web del registrador de dominios donde desea administrar su nombre de dominio hacia delante y siga sus instrucciones para transferir un dominio (busque ayuda en su sitio web).</span><span class="sxs-lookup"><span data-stu-id="7e452-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="7e452-163">Si necesita volver a ver el código, en la página **configuración del dominio** en Office 365, seleccione **Ver código de autorización para la transferencia del dominio**.</span><span class="sxs-lookup"><span data-stu-id="7e452-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="7e452-164">Una vez completada la transferencia, renovará su dominio en el nuevo registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="7e452-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="7e452-165">Para finalizar el proceso, vuelva a la página **dominios** del centro de administración y seleccione **transferencia de dominio completa**.</span><span class="sxs-lookup"><span data-stu-id="7e452-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="7e452-166">*Nota: tenga en cuenta que los dominios comprados de Office 365 no son válidos para los cambios en el servidor de nombres o la transferencia del dominio entre los inquilinos de Office 365.  Si alguno de ellos es necesario, el registro de dominio deberá transferirse a otro registrador.*</span><span class="sxs-lookup"><span data-stu-id="7e452-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="7e452-167">¿Cómo puedo cambiar el modo en que mis registros DNS se administran en Office 365?</span><span class="sxs-lookup"><span data-stu-id="7e452-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="7e452-168">Cambiar la administración de DNS a un host DNS fuera de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e452-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="7e452-169">Inicie sesión en el registrador de dominios de su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="7e452-170">Busque el área en el sitio web del registrador en la que se actualizan los registros del servidor de nombres y actualice los servidores de nombres para que apunten al host DNS de su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-170">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="7e452-171">(El host DNS suele ser el registrador de dominios).</span><span class="sxs-lookup"><span data-stu-id="7e452-171">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="7e452-172">Siga un vínculo para ir al Asistente para la configuración de dominios:</span><span class="sxs-lookup"><span data-stu-id="7e452-172">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="7e452-173">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="7e452-174">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-174">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="7e452-175">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-175">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="7e452-176">En la página **dominios** , seleccione el dominio que quiere cambiar y seleccione **Administración de DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e452-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="7e452-177">En el Asistente para la configuración de dominios, en la página **configurar los servicios en línea** , seleccione **Administraré mis propios registros DNS**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7e452-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="7e452-178">Agregue los registros DNS sugeridos por el asistente en la página **Actualizar configuración DNS** al sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="7e452-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="7e452-179">Una vez que haya agregado los registros, vuelva a Office 365 y seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="7e452-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="7e452-180">Cambiar la administración de DNS a Office 365</span><span class="sxs-lookup"><span data-stu-id="7e452-180">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7e452-181">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> ..</span><span class="sxs-lookup"><span data-stu-id="7e452-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7e452-182">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-182">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7e452-183">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-183">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7e452-184">En la página **dominios** , seleccione el dominio que quiere cambiar y seleccione **Administración de DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e452-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="7e452-185">En el Asistente para la configuración de dominios, en la página **configurar los servicios en línea** , seleccione **configurar mis servicios en línea para mí. (Recomendado)** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7e452-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="7e452-186">Si aún no ha comprobado el dominio, siga los pasos para hacerlo primero.</span><span class="sxs-lookup"><span data-stu-id="7e452-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="7e452-187">En la página **Actualizar configuración DNS** , se enumeran los servidores de nombres para Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-187">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="7e452-188">Vaya al registrador de dominios de su dominio y actualice los servidores de nombres a los servidores de nombres de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-188">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="7e452-189">Una vez que haya actualizado los servidores de nombres, **espere al menos una hora**.</span><span class="sxs-lookup"><span data-stu-id="7e452-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="7e452-190">A continuación, en el Asistente de Office 365, seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="7e452-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="7e452-191">¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?</span><span class="sxs-lookup"><span data-stu-id="7e452-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="7e452-192">Si administra sus propios registros DNS y su host DNS no admite todos los registros DNS que necesita Office 365, algunas características de Office 365 no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="7e452-192">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="7e452-193">Le recomendamos que transfiera su dominio a un registrador que admita todos los registros DNS necesarios.</span><span class="sxs-lookup"><span data-stu-id="7e452-193">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="7e452-194">Proveedores que admiten todos los registros DNS necesarios:</span><span class="sxs-lookup"><span data-stu-id="7e452-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="7e452-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="7e452-195">Dynadot</span></span>
    
- <span data-ttu-id="7e452-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="7e452-196">eNomCentral</span></span>
    
- <span data-ttu-id="7e452-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="7e452-197">Europe Registry</span></span>
    
- <span data-ttu-id="7e452-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="7e452-198">GoDaddy</span></span>
    
- <span data-ttu-id="7e452-199">Coloque</span><span class="sxs-lookup"><span data-stu-id="7e452-199">Hover</span></span>
    
- <span data-ttu-id="7e452-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="7e452-200">MyHosting.com</span></span>
    
- <span data-ttu-id="7e452-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="7e452-201">Name.com</span></span>
    
- <span data-ttu-id="7e452-202">Voz casi gratuita</span><span class="sxs-lookup"><span data-stu-id="7e452-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="7e452-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="7e452-203">Nettica</span></span>
    
- <span data-ttu-id="7e452-204">Centro de información de redes (NIC)</span><span class="sxs-lookup"><span data-stu-id="7e452-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="7e452-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="7e452-205">Network Solutions</span></span>
    
- <span data-ttu-id="7e452-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="7e452-206">Register.com</span></span>
    
 <span data-ttu-id="7e452-207">**Si no se admiten los registros SRV**, no estarán disponibles las siguientes características de Office 365:</span><span class="sxs-lookup"><span data-stu-id="7e452-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="7e452-208">Integración de presencia y mensajería instantánea de Skype empresarial online con Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="7e452-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="7e452-209">Comunicación externa (Federación) con usuarios de Skype empresarial online en otras organizaciones.</span><span class="sxs-lookup"><span data-stu-id="7e452-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="7e452-210">Conectividad pública a Internet (PIC) con usuarios de Skype empresarial online que han iniciado sesión con una cuenta de Microsoft (anteriormente conocida como Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="7e452-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="7e452-211">**Si no se admiten varios registros CNAME,** tiene que elegir entre las siguientes características de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="7e452-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="7e452-212">Los clientes de escritorio de correo electrónico y los clientes móviles pueden usar la detección automática para buscar automáticamente el servicio de Exchange Online para que los usuarios puedan iniciar sesión sin tener que escribir el nombre de un servidor.</span><span class="sxs-lookup"><span data-stu-id="7e452-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="7e452-213">Los clientes de escritorio de Skype empresarial online pueden usar la detección automática para buscar automáticamente el servicio de Skype empresarial online para que los usuarios puedan iniciar sesión sin tener que escribir el nombre de un servidor.</span><span class="sxs-lookup"><span data-stu-id="7e452-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="7e452-214">Los clientes móviles de Skype empresarial online pueden usar la detección automática para buscar automáticamente el servicio de Skype empresarial online para que los usuarios puedan iniciar sesión sin tener que escribir el nombre de un servidor.</span><span class="sxs-lookup"><span data-stu-id="7e452-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="7e452-215">**Si no se admiten los registros SPF/txt**, es posible que otras personas puedan usar su dominio para enviar correo no deseado u otro correo electrónico malintencionado.</span><span class="sxs-lookup"><span data-stu-id="7e452-215">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="7e452-216">Los registros de SPF funcionan mediante la identificación de los servidores autorizados para enviar correo electrónico desde su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-216">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="7e452-217">¿Cómo se configura o se cambia el dominio predeterminado en Office 365?</span><span class="sxs-lookup"><span data-stu-id="7e452-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="7e452-218">Debe tener al menos un dominio personalizado que haya agregado a Office 365 para poder elegir un dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7e452-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7e452-219">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7e452-220">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-220">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7e452-221">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e452-221">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7e452-222">En la página **dominios** , seleccione el dominio que desea establecer como predeterminado para las nuevas direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="7e452-223">Seleccione **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="7e452-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="7e452-224">No puede cambiar el nombre del dominio inicial *. onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="7e452-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="7e452-225">No puede cambiar el nombre del dominio inicial *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="7e452-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="7e452-226">No puede cambiar el nombre del dominio inicial *. Partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="7e452-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="7e452-227">¿Puedo agregar subdominios personalizados o varios dominios a Office 365?</span><span class="sxs-lookup"><span data-stu-id="7e452-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="7e452-228">Afirma!</span><span class="sxs-lookup"><span data-stu-id="7e452-228">Yes!</span></span> <span data-ttu-id="7e452-229">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="7e452-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="7e452-230">Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="7e452-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="7e452-231">Afirma!</span><span class="sxs-lookup"><span data-stu-id="7e452-231">Yes!</span></span> <span data-ttu-id="7e452-232">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="7e452-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="7e452-233">Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="7e452-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="7e452-234">Afirma!</span><span class="sxs-lookup"><span data-stu-id="7e452-234">Yes!</span></span> <span data-ttu-id="7e452-235">Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador.</span><span class="sxs-lookup"><span data-stu-id="7e452-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="7e452-236">Si permite que 21Vianet administre la configuración DNS con registros NS, no puede agregar subdominios.</span><span class="sxs-lookup"><span data-stu-id="7e452-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="7e452-237">Normalmente, puede Agregar hasta 900 dominios a su suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="7e452-238">Por ejemplo, puede Agregar los dominios contoso.com y contosomarketing.com y, a continuación, agregar los subdominios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, etc.</span><span class="sxs-lookup"><span data-stu-id="7e452-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="7e452-239">Cuando se agrega un subdominio, se comprueba automáticamente según el dominio primario que se está comprobando.</span><span class="sxs-lookup"><span data-stu-id="7e452-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="7e452-240">Cuando se agregan varios dominios a Office 365, puede hospedar cualquiera de los servicios (como correo electrónico) en cualquiera de los dominios que haya agregado.</span><span class="sxs-lookup"><span data-stu-id="7e452-240">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="7e452-241">*Al cambiar el correo electrónico a Office 365, al actualizar el registro MX de un dominio, todo el correo electrónico enviado a ese dominio empezará a llegar a Office 365.*</span><span class="sxs-lookup"><span data-stu-id="7e452-241">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="7e452-242">Si ya ha agregado un dominio contoso.com a un inquilino de Office 365, también puede Agregar el subdominio xyz.contoso.com a otro inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="7e452-243">Al agregar el subdominio, se le pedirá que agregue un registro TXT en el proveedor de host DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="7e452-244">¿Por qué tengo un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="7e452-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="7e452-245">Office 365 crea un dominio para usted, como *contoso.onmicrosoft.com*, cuando se registra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="7e452-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="7e452-246">El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="7e452-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="7e452-247">**Si quiere que su correo sea similar a *Alan\@contoso.com*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos que se indican en [Agregar usuarios y dominios a Office 365](add-domain.md) si es el propietario ya.</span><span class="sxs-lookup"><span data-stu-id="7e452-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="7e452-248">**No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.**</span><span class="sxs-lookup"><span data-stu-id="7e452-248">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="7e452-249">Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.com, no puede cambiarlo a fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7e452-249">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="7e452-250">Para usar un dominio onmicrosoft.com diferente, debe iniciar una nueva suscripción con Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-250">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="7e452-251">**No puede cambiar el nombre de la dirección URL del sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="7e452-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="7e452-252">La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7e452-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="7e452-253">Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="7e452-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="7e452-254">**No puede quitar el dominio de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="7e452-254">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="7e452-255">Office 365 debe mantenerlo ahí porque se usa en segundo plano para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="7e452-255">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="7e452-256">Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="7e452-256">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="7e452-257">Puede seguir usando el dominio de onmicrosoft.com inicial incluso después de agregar el dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-257">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="7e452-258">Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.</span><span class="sxs-lookup"><span data-stu-id="7e452-258">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="7e452-259">¿Por qué tengo un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="7e452-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="7e452-260">Office 365 crea un dominio para usted, como *contoso.onmicrosoft.de*, cuando se registra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="7e452-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="7e452-261">El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="7e452-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="7e452-262">**Si quiere que su correo sea similar a *Alan@contoso.de*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos indicados en [Agregar usuarios y dominios a Office 365](add-domain.md) si ya es el propietario.</span><span class="sxs-lookup"><span data-stu-id="7e452-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="7e452-263">**No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.**</span><span class="sxs-lookup"><span data-stu-id="7e452-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="7e452-264">Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.de, no puede cambiarlo a fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="7e452-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="7e452-265">Para usar un dominio onmicrosoft.de diferente, debe iniciar una nueva suscripción con Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="7e452-266">**No puede cambiar el nombre de la dirección URL del sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="7e452-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="7e452-267">La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.de. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="7e452-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="7e452-268">**No puede quitar el dominio de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="7e452-268">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="7e452-269">Office 365 debe mantenerlo ahí porque se usa en segundo plano para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="7e452-269">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="7e452-270">Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="7e452-270">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="7e452-271">Puede seguir usando el dominio de onmicrosoft.de inicial incluso después de agregar el dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="7e452-272">Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.</span><span class="sxs-lookup"><span data-stu-id="7e452-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="7e452-273">¿Cómo puedo comprobar mi estado para ONG o educación?</span><span class="sxs-lookup"><span data-stu-id="7e452-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="7e452-274">Seleccione **configurar** en el [centro de administración](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="7e452-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="7e452-275">(Asegúrese de iniciar sesión en Office 365 en primer lugar).</span><span class="sxs-lookup"><span data-stu-id="7e452-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="7e452-276">Para convertirse en el administrador de su centro educativo, seleccione la opción **convertirse en Administrador** en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="7e452-277">Se le pedirá que agregue un registro DNS TXT en el sitio web del host DNS de su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="7e452-278">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="7e452-278">Why?</span></span> <span data-ttu-id="7e452-279">Debido a que iniciando sesión en el host DNS y agrega un registro para su dominio, usted prueba a Office 365 que es el propietario del nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="7e452-280">Después de agregar el registro, volverá al portal de Office 365 y confirmará que lo ha agregado, por lo que Office 365 puede comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="7e452-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="7e452-281">¿Tiene una ONG y desea obtener Office 365?</span><span class="sxs-lookup"><span data-stu-id="7e452-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="7e452-282">Asegúrese de [que su organización sea cualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) y, a continuación, Regístrese para obtener el servicio.</span><span class="sxs-lookup"><span data-stu-id="7e452-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="7e452-283">¿Quiere saber más sobre cómo convertirse en el administrador de su centro educativo?</span><span class="sxs-lookup"><span data-stu-id="7e452-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="7e452-284">[Obtenga información sobre ti](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="7e452-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="7e452-285">¿Puedo realizar una prueba de Office 365 con unas pocas direcciones de correo electrónico de mi dominio personalizado?</span><span class="sxs-lookup"><span data-stu-id="7e452-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="7e452-286">Puede, pero hay limitaciones:</span><span class="sxs-lookup"><span data-stu-id="7e452-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="7e452-287">Su proveedor de correo electrónico actual debe proporcionar el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="7e452-288">Debe administrar los registros DNS relacionados con Office 365 en su proveedor de host DNS, en lugar de que Office 365 administre estos registros.</span><span class="sxs-lookup"><span data-stu-id="7e452-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="7e452-289">Para obtener más información, consulte Agregar un dominio a Office 365 cuando quiera administrar sus propios registros DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="7e452-290">Algunas características de Office 365 no estarán disponibles:</span><span class="sxs-lookup"><span data-stu-id="7e452-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="7e452-291">Los usuarios no podrán ver la información de disponibilidad de los usuarios que están en el otro proveedor de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="7e452-292">Los administradores no podrán administrar las cuentas de todos los usuarios desde un solo punto.</span><span class="sxs-lookup"><span data-stu-id="7e452-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="7e452-293">Es posible que los usuarios no puedan usar el filtrado de correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e452-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="7e452-294">Cómo configurar un piloto de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e452-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="7e452-295">Inicie sesión en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7e452-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="7e452-296">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="7e452-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="7e452-297">Vaya a **Settings** \> **dominios**de configuración.</span><span class="sxs-lookup"><span data-stu-id="7e452-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="7e452-298">Comprobar que es el propietario del dominio que desea usar</span><span class="sxs-lookup"><span data-stu-id="7e452-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="7e452-299">En la página **dominios** , seleccione **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="7e452-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="7e452-300">En el panel, escriba el dominio, en este ejemplo cohowinery.com y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7e452-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="7e452-301">En la página **comprobar** dominio, siga las instrucciones paso a paso.</span><span class="sxs-lookup"><span data-stu-id="7e452-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="7e452-302">En la lista desplegable, seleccione su proveedor de host DNS y siga las instrucciones para mostrar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e452-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="7e452-303">Seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="7e452-303">Select **Verify**.</span></span> <span data-ttu-id="7e452-304">Tarda entre unos minutos y 72 horas para que los cambios en el DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7e452-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="7e452-305">Cuando la comprobación se realice correctamente, se le pedirá que modifique los registros DNS.</span><span class="sxs-lookup"><span data-stu-id="7e452-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="7e452-306">Marcar el dominio como compartido en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7e452-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="7e452-307">Vaya al **centro de administración de Exchange** (EAC).</span><span class="sxs-lookup"><span data-stu-id="7e452-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="7e452-308">En la sección **flujo de correo** , seleccione **dominios aceptados**.</span><span class="sxs-lookup"><span data-stu-id="7e452-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="7e452-309">Haga doble clic en el dominio que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="7e452-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="7e452-310">En la ventana que se abre, seleccione **retransmisión interna**.</span><span class="sxs-lookup"><span data-stu-id="7e452-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="7e452-311">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e452-311">Select **Save**.</span></span> <span data-ttu-id="7e452-312">Esta configuración puede tardar unos minutos en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="7e452-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="7e452-313">Opcionalmente, desbloquear el servidor de correo electrónico existente</span><span class="sxs-lookup"><span data-stu-id="7e452-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="7e452-314">Office 365 usa Exchange Online Protection (EOP) para la protección contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7e452-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="7e452-315">Si EOP detecta un gran volumen de correo no deseado que ha reenviado su servidor de correo actual, puede bloquearlo, lo que impediría el reenvío en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="7e452-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="7e452-316">Si está seguro de que la protección contra correo no deseado de su proveedor de correo electrónico es la que usa, puede usar la lista blanca del servidor en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="7e452-317">Sin embargo, esto también permitirá que el correo no deseado que llegue a través del servidor original pase a los buzones de Office 365 y no podrá evaluar cómo Office 365 impide el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7e452-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="7e452-318">Vaya al centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="7e452-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="7e452-319">En EAC, seleccione **protección**y, a continuación, seleccione **filtro de conexión**.</span><span class="sxs-lookup"><span data-stu-id="7e452-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="7e452-320">En la lista de direcciones IP **permitidas**, seleccione **+** y agregue la dirección IP del servidor de correo que puede obtener de su proveedor de correo electrónico actual.</span><span class="sxs-lookup"><span data-stu-id="7e452-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="7e452-321">Crear cuentas de usuario y establecer la dirección principal (responder a)</span><span class="sxs-lookup"><span data-stu-id="7e452-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="7e452-322">Vaya al Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="7e452-323">En la barra de navegación izquierda, **Seleccione** \> usuarios **activos**.</span><span class="sxs-lookup"><span data-stu-id="7e452-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="7e452-324">Cree las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="7e452-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="7e452-325">Seleccione **+ (nuevo)** para cada cuenta y rellene la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="7e452-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="7e452-326">Para que el correo electrónico del usuario sea el mismo que el que está actualmente, el campo **nombre de usuario** debe ser exactamente igual a la dirección de correo electrónico existente del usuario.</span><span class="sxs-lookup"><span data-stu-id="7e452-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="7e452-327">Junto a nombre de usuario, seleccione su nombre de dominio personalizado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7e452-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="7e452-328">Seleccione **crear** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="7e452-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="7e452-329">Actualizar registros DNS en su proveedor de host DNS</span><span class="sxs-lookup"><span data-stu-id="7e452-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="7e452-330">Inicie sesión en el sitio web de su proveedor de host DNS y siga los [pasos de crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7e452-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="7e452-331">**Realice las siguientes excepciones:**</span><span class="sxs-lookup"><span data-stu-id="7e452-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="7e452-332">No cree un nuevo registro MX ni cambie el registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="7e452-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="7e452-333">Si ya tiene un registro de marco de directivas de remitente (SPF) para su proveedor de correo electrónico anterior, en lugar de crear un nuevo registro de SPF (TXT) para Exchange Online, solo tiene que agregar "include include SPF. Protection. Outlook. com" al registro TXT actual.</span><span class="sxs-lookup"><span data-stu-id="7e452-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="7e452-334">Por ejemplo, "v = spf1 mx include:adatum. com include include SPF. Protection. Outlook. com ~ All".</span><span class="sxs-lookup"><span data-stu-id="7e452-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="7e452-335">Si aún no tiene un registro de SPF, modifique el que se recomienda en Office 365 para incluir el dominio de su proveedor de correo electrónico actual, además de spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7e452-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="7e452-336">Esto autoriza los mensajes salientes desde ambos sistemas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="7e452-337">Configurar el reenvío de correo electrónico en su proveedor actual</span><span class="sxs-lookup"><span data-stu-id="7e452-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="7e452-338">En su proveedor de correo electrónico actual, configure el reenvío de las cuentas de correo electrónico de los usuarios a su dominio onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="7e452-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="7e452-339">El buzón del usuario A debe reenviar a usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e452-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="7e452-340">El buzón del usuario B debe reenviar a userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e452-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="7e452-341">Cuando haya completado este paso:</span><span class="sxs-lookup"><span data-stu-id="7e452-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="7e452-342">Todo el correo enviado a usera@yourcompany.com y userb@yourcompany.com estará disponible en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e452-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="7e452-343">Notas:</span><span class="sxs-lookup"><span data-stu-id="7e452-343">Notes:</span></span>
        
        - <span data-ttu-id="7e452-344">Póngase en contacto con su proveedor de correo electrónico actual para conocer los pasos exactos para configurar el reenvío.</span><span class="sxs-lookup"><span data-stu-id="7e452-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="7e452-345">No es necesario que conserve una copia de los mensajes en el proveedor de correo electrónico actual.</span><span class="sxs-lookup"><span data-stu-id="7e452-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="7e452-346">La mayoría de los proveedores reenvía correo electrónico que deja intacta la dirección de respuesta del remitente, de modo que las respuestas se envían al remitente original.</span><span class="sxs-lookup"><span data-stu-id="7e452-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="7e452-347">Prueba del flujo de correo</span><span class="sxs-lookup"><span data-stu-id="7e452-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="7e452-348">Inicie sesión en Outlook Web App con las credenciales del usuario A.</span><span class="sxs-lookup"><span data-stu-id="7e452-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="7e452-349">Realice las siguientes pruebas:</span><span class="sxs-lookup"><span data-stu-id="7e452-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="7e452-350">Pruebe el correo electrónico de Microsoft local.</span><span class="sxs-lookup"><span data-stu-id="7e452-350">Test local Microsoft email.</span></span> <span data-ttu-id="7e452-351">Por ejemplo, envíe un correo electrónico al usuario B. Este correo electrónico debe entregarse inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="7e452-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="7e452-352">En este escenario, el mensaje no se redirigirá al buzón del usuario B en el servidor original, ya que Office 365 Ve el buzón como local.</span><span class="sxs-lookup"><span data-stu-id="7e452-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="7e452-353">Pruebe el correo electrónico para alguien que se encuentra en el otro sistema de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="7e452-354">Por ejemplo, envíe un correo electrónico al usuario C. Este correo electrónico debe entregarse al buzón del usuario C en su servidor de correo original.</span><span class="sxs-lookup"><span data-stu-id="7e452-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="7e452-355">Desde una cuenta externa o de la cuenta de correo electrónico de un empleado en el otro sistema de correo electrónico, compruebe que el reenvío está configurado correctamente en el otro sistema de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e452-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="7e452-356">Por ejemplo, en la cuenta de servidor original del usuario C o en una cuenta de hotmail, envíe al usuario un correo electrónico y compruebe que llegue al buzón de Office 365 del usuario A.</span><span class="sxs-lookup"><span data-stu-id="7e452-356">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="7e452-357">Mover el contenido del buzón</span><span class="sxs-lookup"><span data-stu-id="7e452-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="7e452-358">Como solo hay dos usuarios que mover, y como el usuario A y el usuario B ya usan Outlook, el correo electrónico se puede mover abriendo el antiguo. PST en el nuevo perfil de Outlook y copiar los mensajes, los elementos del calendario, los contactos, etc. como se muestra en importar elementos de Outlook desde un archivo de datos de Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="7e452-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="7e452-359">Una vez organizadas en las ubicaciones adecuadas en el buzón de Office 365, se puede tener acceso a los elementos desde cualquier dispositivo en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="7e452-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="7e452-360">Cuando hay más buzones de correo implicados o si los empleados todavía no usan Outlook, puede usar las herramientas de migración disponibles en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7e452-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="7e452-361">Para empezar, vaya al centro de administración de Exchange y siga las instrucciones que se indican en migrar correo electrónico desde un servidor IMAP a buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7e452-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
