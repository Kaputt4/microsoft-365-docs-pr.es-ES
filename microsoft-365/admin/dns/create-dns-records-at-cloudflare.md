---
title: Crear registros DNS en Cloudflare para Microsoft
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
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Cloudflare for Microsoft.
ms.openlocfilehash: 8d5dd7779f07fd42dd230ee33c40849da3519d26
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939277"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="e6739-103">Crear registros DNS en Cloudflare para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6739-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="e6739-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="e6739-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e6739-105">Si Cloudflare es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="e6739-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e6739-106">Después de agregar estos registros a Cloudflare, el dominio estará configurado para funcionar con los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6739-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="e6739-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6739-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e6739-110">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="e6739-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="e6739-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="e6739-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6739-112">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="e6739-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="e6739-113">Cuando te has registrado en Cloudflare, agregaste un  dominio mediante el proceso de configuración de Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e6739-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="e6739-114">El dominio que agregó se compró a Cloudflare o a un registrador de dominios independiente.</span><span class="sxs-lookup"><span data-stu-id="e6739-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="e6739-115">Para comprobar y crear registros DNS para su dominio en Microsoft 365, primero debe cambiar los servidores dns en el registrador de dominios para que usen los servidores dns de Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e6739-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="e6739-116">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6739-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="e6739-117">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="e6739-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="e6739-118">Cree dos registros de servidor dns con los valores de la tabla siguiente o edite los registros existentes del servidor dns para que coincidan con estos valores.</span><span class="sxs-lookup"><span data-stu-id="e6739-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="e6739-119">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="e6739-119">First nameserver</span></span>  <br/> |<span data-ttu-id="e6739-120">Use el valor de servidor de nombres proporcionado por Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e6739-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="e6739-121">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="e6739-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="e6739-122">Use el valor de servidor de nombres proporcionado por Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e6739-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="e6739-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="e6739-123">You should use at least two name server records.</span></span> <span data-ttu-id="e6739-124">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="e6739-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="e6739-125">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="e6739-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e6739-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="e6739-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e6739-127">A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="e6739-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e6739-128">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="e6739-128">Add a TXT record for verification</span></span>
<span data-ttu-id="e6739-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e6739-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e6739-p105">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="e6739-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6739-p106">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e6739-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e6739-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e6739-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e6739-135">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="e6739-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="e6739-136">En la **página** principal, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="e6739-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e6739-137">En la **página Información** general de su dominio, seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="e6739-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e6739-138">En la **página de administración de DNS,** haga clic en Agregar **registro** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6739-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="e6739-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6739-139">Type</span></span> | <span data-ttu-id="e6739-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6739-140">Name</span></span> | <span data-ttu-id="e6739-141">TTL automático</span><span class="sxs-lookup"><span data-stu-id="e6739-141">Automatic TTL</span></span> | <span data-ttu-id="e6739-142">Contenido</span><span class="sxs-lookup"><span data-stu-id="e6739-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="e6739-143">TXT</span><span class="sxs-lookup"><span data-stu-id="e6739-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e6739-144">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-144">30 minutes</span></span>  <br/> |<span data-ttu-id="e6739-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e6739-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e6739-146">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e6739-146">**Note:** This is an example.</span></span> <span data-ttu-id="e6739-147">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="e6739-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e6739-148">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e6739-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="e6739-149">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e6739-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="e6739-150">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="e6739-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e6739-151">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y buscará el registro.</span><span class="sxs-lookup"><span data-stu-id="e6739-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="e6739-152">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="e6739-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e6739-153">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="e6739-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e6739-154">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="e6739-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e6739-155">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e6739-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e6739-156">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="e6739-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e6739-p109">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6739-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e6739-160">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6739-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e6739-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e6739-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e6739-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e6739-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e6739-163">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="e6739-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="e6739-164">En la **página** principal, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="e6739-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e6739-165">En la **página Información** general de su dominio, seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="e6739-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e6739-166">En la **página de administración de DNS,** haga clic en Agregar **registro** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6739-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="e6739-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6739-167">Type</span></span> | <span data-ttu-id="e6739-168">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6739-168">Name</span></span> | <span data-ttu-id="e6739-169">Servidor de correo</span><span class="sxs-lookup"><span data-stu-id="e6739-169">Mail server</span></span> | <span data-ttu-id="e6739-170">Prioridad</span><span class="sxs-lookup"><span data-stu-id="e6739-170">Priority</span></span> | <span data-ttu-id="e6739-171">TTL</span><span class="sxs-lookup"><span data-stu-id="e6739-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e6739-172">MX</span><span class="sxs-lookup"><span data-stu-id="e6739-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="e6739-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e6739-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e6739-174">**Nota:** Obtenga la  *\<domain-key\>*  información de su cuenta de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6739-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="e6739-175">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="e6739-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="e6739-176">1 </span><span class="sxs-lookup"><span data-stu-id="e6739-176">1</span></span>  <br/> <span data-ttu-id="e6739-177">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e6739-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="e6739-178">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="e6739-179">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e6739-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="e6739-180">Si hay otros registros MX enumerados en la sección **Registros MX,** elimínelos seleccionando el icono **Eliminar (X).**</span><span class="sxs-lookup"><span data-stu-id="e6739-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="e6739-181">En el cuadro de diálogo de confirmación, **seleccione Eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e6739-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e6739-182">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6739-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e6739-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e6739-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e6739-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e6739-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e6739-185">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="e6739-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="e6739-186">En la **página** principal, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="e6739-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e6739-187">En la **página Información** general de su dominio, seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="e6739-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e6739-188">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e6739-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="e6739-189">En la **página de administración de DNS,** haga clic en Agregar **registro** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6739-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="e6739-190">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6739-190">Type</span></span> | <span data-ttu-id="e6739-191">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6739-191">Name</span></span> | <span data-ttu-id="e6739-192">Target</span><span class="sxs-lookup"><span data-stu-id="e6739-192">Target</span></span> | <span data-ttu-id="e6739-193">TTL</span><span class="sxs-lookup"><span data-stu-id="e6739-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e6739-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6739-194">CNAME</span></span>  <br/> |<span data-ttu-id="e6739-195">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="e6739-195">autodiscover</span></span>  <br/> |<span data-ttu-id="e6739-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e6739-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="e6739-197">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e6739-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6739-198">CNAME</span></span>  <br/> |<span data-ttu-id="e6739-199">sip</span><span class="sxs-lookup"><span data-stu-id="e6739-199">sip</span></span>  <br/> |<span data-ttu-id="e6739-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e6739-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e6739-201">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e6739-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6739-202">CNAME</span></span>  <br/> |<span data-ttu-id="e6739-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e6739-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e6739-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e6739-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e6739-205">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e6739-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6739-206">CNAME</span></span>  <br/> |<span data-ttu-id="e6739-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e6739-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e6739-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e6739-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="e6739-209">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e6739-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6739-210">CNAME</span></span>  <br/> |<span data-ttu-id="e6739-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e6739-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e6739-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e6739-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="e6739-213">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e6739-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6739-214">CNAME</span></span>  <br/> |<span data-ttu-id="e6739-215">msoid</span><span class="sxs-lookup"><span data-stu-id="e6739-215">msoid</span></span>  <br/> |<span data-ttu-id="e6739-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="e6739-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="e6739-217">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="e6739-218">Seleccione el **icono de tráfico DNS** (cambie la nube naranja a gris) para omitir los servidores de Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e6739-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="e6739-219">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e6739-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="e6739-220">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e6739-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e6739-221">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e6739-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e6739-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e6739-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6739-223">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="e6739-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e6739-224">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e6739-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e6739-225">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6739-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="e6739-226">En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e6739-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e6739-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e6739-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e6739-228">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="e6739-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="e6739-229">En la **página** principal, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="e6739-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e6739-230">En la **página Información** general de su dominio, seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="e6739-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e6739-231">En la **página de administración de DNS,** haga clic en Agregar **registro** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6739-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="e6739-232">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6739-232">Type</span></span> | <span data-ttu-id="e6739-233">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6739-233">Name</span></span> | <span data-ttu-id="e6739-234">TTL</span><span class="sxs-lookup"><span data-stu-id="e6739-234">TTL</span></span> | <span data-ttu-id="e6739-235">Contenido</span><span class="sxs-lookup"><span data-stu-id="e6739-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e6739-236">TXT</span><span class="sxs-lookup"><span data-stu-id="e6739-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e6739-237">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-237">30 minutes</span></span>  <br/> |<span data-ttu-id="e6739-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e6739-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e6739-239">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="e6739-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="e6739-240">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e6739-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e6739-241">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6739-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e6739-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e6739-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6739-243">Ten en cuenta que Cloudflare es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="e6739-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="e6739-244">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (Interfaz gráfica de usuario) de Cloudflare actual, aproveche [la comunidad de Cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="e6739-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="e6739-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e6739-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e6739-246">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="e6739-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="e6739-247">En la **página** principal, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="e6739-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e6739-248">En la **página Información** general de su dominio, seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="e6739-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="e6739-249">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="e6739-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="e6739-250">En la **página de administración de DNS,** haga clic en Agregar **registro** y, a continuación, seleccione los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6739-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="e6739-251">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6739-251">Type</span></span> | <span data-ttu-id="e6739-252">Servicio</span><span class="sxs-lookup"><span data-stu-id="e6739-252">Service</span></span> | <span data-ttu-id="e6739-253">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e6739-253">Protocol</span></span> | <span data-ttu-id="e6739-254">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6739-254">Name</span></span> | <span data-ttu-id="e6739-255">TTL</span><span class="sxs-lookup"><span data-stu-id="e6739-255">TTL</span></span> | <span data-ttu-id="e6739-256">Priority</span><span class="sxs-lookup"><span data-stu-id="e6739-256">Priority</span></span> | <span data-ttu-id="e6739-257">Peso</span><span class="sxs-lookup"><span data-stu-id="e6739-257">Weight</span></span> | <span data-ttu-id="e6739-258">Puerto</span><span class="sxs-lookup"><span data-stu-id="e6739-258">Port</span></span> | <span data-ttu-id="e6739-259">Target</span><span class="sxs-lookup"><span data-stu-id="e6739-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e6739-260">SRV</span><span class="sxs-lookup"><span data-stu-id="e6739-260">SRV</span></span>|<span data-ttu-id="e6739-261">_sip</span><span class="sxs-lookup"><span data-stu-id="e6739-261">_sip</span></span> |<span data-ttu-id="e6739-262">TLS</span><span class="sxs-lookup"><span data-stu-id="e6739-262">TLS</span></span> |<span data-ttu-id="e6739-263">Use su *domain_name*; por ejemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6739-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="e6739-264">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-264">30 minutes</span></span> | <span data-ttu-id="e6739-265">100</span><span class="sxs-lookup"><span data-stu-id="e6739-265">100</span></span>|<span data-ttu-id="e6739-266">1 </span><span class="sxs-lookup"><span data-stu-id="e6739-266">1</span></span> |<span data-ttu-id="e6739-267">443</span><span class="sxs-lookup"><span data-stu-id="e6739-267">443</span></span> |<span data-ttu-id="e6739-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e6739-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="e6739-269">SRV</span><span class="sxs-lookup"><span data-stu-id="e6739-269">SRV</span></span>|<span data-ttu-id="e6739-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e6739-270">_sipfederationtls</span></span> | <span data-ttu-id="e6739-271">TCP</span><span class="sxs-lookup"><span data-stu-id="e6739-271">TCP</span></span>|<span data-ttu-id="e6739-272">Use su *domain_name*; por ejemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6739-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="e6739-273">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e6739-273">30 minutes</span></span> |<span data-ttu-id="e6739-274">100</span><span class="sxs-lookup"><span data-stu-id="e6739-274">100</span></span> |<span data-ttu-id="e6739-275">1 </span><span class="sxs-lookup"><span data-stu-id="e6739-275">1</span></span> |<span data-ttu-id="e6739-276">5061</span><span class="sxs-lookup"><span data-stu-id="e6739-276">5061</span></span> | <span data-ttu-id="e6739-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e6739-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="e6739-278">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e6739-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="e6739-279">Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e6739-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="e6739-p117">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6739-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
