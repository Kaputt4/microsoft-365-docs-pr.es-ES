---
title: Crear registros DNS en CloudFlare para Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en CloudFlare para Microsoft.
ms.openlocfilehash: f04e4b4a29085a3ddd9b388c7178c1cd638445ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629712"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="5c64c-103">Crear registros DNS en CloudFlare para Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c64c-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="5c64c-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="5c64c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5c64c-105">Si CloudFlare es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="5c64c-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5c64c-106">Después de agregar estos registros a CloudFlare, su dominio estará configurado para funcionar con los servicios de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c64c-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="5c64c-107">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c64c-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5c64c-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c64c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5c64c-111">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="5c64c-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="5c64c-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="5c64c-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c64c-113">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="5c64c-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="5c64c-114">Cuando se registró para CloudFlare, agregó un dominio mediante el proceso de **instalación** de CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="5c64c-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="5c64c-115">El dominio que agregó se compró en un registrador de dominios independiente; CloudFlare no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="5c64c-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="5c64c-116">Para comprobar y crear registros DNS para su dominio en Microsoft 365, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="5c64c-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="5c64c-117">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c64c-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="5c64c-118">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="5c64c-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="5c64c-119">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.</span><span class="sxs-lookup"><span data-stu-id="5c64c-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="5c64c-120">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="5c64c-120">First nameserver</span></span>  <br/> |<span data-ttu-id="5c64c-121">Usar el valor de nameserver proporcionado por CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="5c64c-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="5c64c-122">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="5c64c-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="5c64c-123">Usar el valor de nameserver proporcionado por CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="5c64c-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="5c64c-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="5c64c-124">You should use at least two name server records.</span></span> <span data-ttu-id="5c64c-125">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="5c64c-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="5c64c-126">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="5c64c-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5c64c-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5c64c-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5c64c-128">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="5c64c-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5c64c-129">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="5c64c-129">Add a TXT record for verification</span></span>
<span data-ttu-id="5c64c-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5c64c-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5c64c-131">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="5c64c-131">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="5c64c-132">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="5c64c-132">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c64c-p106">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="5c64c-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5c64c-135">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="5c64c-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="5c64c-136">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="5c64c-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="5c64c-137">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5c64c-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="5c64c-138">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="5c64c-139">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c64c-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="5c64c-140">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-140">**Type**</span></span>|<span data-ttu-id="5c64c-141">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5c64c-141">**Name**</span></span>|<span data-ttu-id="5c64c-142">**TTL automático**</span><span class="sxs-lookup"><span data-stu-id="5c64c-142">**Automatic TTL**</span></span>|<span data-ttu-id="5c64c-143">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="5c64c-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="5c64c-144">TXT</span><span class="sxs-lookup"><span data-stu-id="5c64c-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="5c64c-145">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-145">30 minutes</span></span>  <br/> |<span data-ttu-id="5c64c-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5c64c-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5c64c-147">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5c64c-147">**Note:** This is an example.</span></span> <span data-ttu-id="5c64c-148">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5c64c-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="5c64c-149">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="5c64c-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="5c64c-150">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="5c64c-151">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="5c64c-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5c64c-152">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y buscará el registro.</span><span class="sxs-lookup"><span data-stu-id="5c64c-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="5c64c-153">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="5c64c-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5c64c-154">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="5c64c-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5c64c-155">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="5c64c-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5c64c-156">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="5c64c-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5c64c-157">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5c64c-p109">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c64c-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5c64c-161">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c64c-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5c64c-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5c64c-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5c64c-163">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="5c64c-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="5c64c-164">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="5c64c-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="5c64c-165">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5c64c-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="5c64c-166">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="5c64c-167">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c64c-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="5c64c-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-168">**Type**</span></span>|<span data-ttu-id="5c64c-169">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5c64c-169">**Name**</span></span>|<span data-ttu-id="5c64c-170">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-170">**Mail server**</span></span>|<span data-ttu-id="5c64c-171">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="5c64c-171">**Priority**</span></span>|<span data-ttu-id="5c64c-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c64c-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c64c-173">MX</span><span class="sxs-lookup"><span data-stu-id="5c64c-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="5c64c-174">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="5c64c-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5c64c-175">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c64c-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="5c64c-176">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="5c64c-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="5c64c-177">1</span><span class="sxs-lookup"><span data-stu-id="5c64c-177">1</span></span>  <br/> <span data-ttu-id="5c64c-178">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5c64c-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="5c64c-179">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="5c64c-180">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="5c64c-181">Si hay otros registros MX enumerados en la sección **registros MX** , elimínelos seleccionando el icono **eliminar (X)** .</span><span class="sxs-lookup"><span data-stu-id="5c64c-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="5c64c-182">En el cuadro de diálogo de confirmación, seleccione **eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5c64c-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5c64c-183">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c64c-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5c64c-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5c64c-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5c64c-185">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="5c64c-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="5c64c-186">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="5c64c-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="5c64c-187">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5c64c-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="5c64c-188">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="5c64c-189">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c64c-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="5c64c-190">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c64c-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="5c64c-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-191">**Type**</span></span>|<span data-ttu-id="5c64c-192">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5c64c-192">**Name**</span></span>|<span data-ttu-id="5c64c-193">**Destino**</span><span class="sxs-lookup"><span data-stu-id="5c64c-193">**Target**</span></span>|<span data-ttu-id="5c64c-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c64c-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c64c-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="5c64c-195">CNAME</span></span>  <br/> |<span data-ttu-id="5c64c-196">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="5c64c-196">autodiscover</span></span>  <br/> |<span data-ttu-id="5c64c-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="5c64c-198">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="5c64c-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="5c64c-199">CNAME</span></span>  <br/> |<span data-ttu-id="5c64c-200">sip</span><span class="sxs-lookup"><span data-stu-id="5c64c-200">sip</span></span>  <br/> |<span data-ttu-id="5c64c-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5c64c-202">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="5c64c-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="5c64c-203">CNAME</span></span>  <br/> |<span data-ttu-id="5c64c-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5c64c-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5c64c-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5c64c-206">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="5c64c-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="5c64c-207">CNAME</span></span>  <br/> |<span data-ttu-id="5c64c-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5c64c-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5c64c-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5c64c-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="5c64c-210">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="5c64c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="5c64c-211">CNAME</span></span>  <br/> |<span data-ttu-id="5c64c-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5c64c-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5c64c-213">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="5c64c-214">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="5c64c-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="5c64c-215">CNAME</span></span>  <br/> |<span data-ttu-id="5c64c-216">msoid</span><span class="sxs-lookup"><span data-stu-id="5c64c-216">msoid</span></span>  <br/> |<span data-ttu-id="5c64c-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="5c64c-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="5c64c-218">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="5c64c-219">Seleccione el icono de **tráfico DNS** (nube naranja) para omitir los servidores de CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="5c64c-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="5c64c-220">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="5c64c-221">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c64c-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5c64c-222">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5c64c-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5c64c-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5c64c-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c64c-224">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="5c64c-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5c64c-225">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5c64c-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5c64c-226">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c64c-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="5c64c-227">En su lugar, agregue los valores necesarios de Microsoft 365 al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="5c64c-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5c64c-228">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="5c64c-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="5c64c-229">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="5c64c-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="5c64c-230">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5c64c-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="5c64c-231">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="5c64c-232">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c64c-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="5c64c-233">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-233">**Type**</span></span>|<span data-ttu-id="5c64c-234">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5c64c-234">**Name**</span></span>|<span data-ttu-id="5c64c-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c64c-235">**TTL**</span></span>|<span data-ttu-id="5c64c-236">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="5c64c-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c64c-237">TXT</span><span class="sxs-lookup"><span data-stu-id="5c64c-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="5c64c-238">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-238">30 minutes</span></span>  <br/> |<span data-ttu-id="5c64c-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5c64c-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5c64c-240">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="5c64c-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="5c64c-241">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5c64c-242">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c64c-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5c64c-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5c64c-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c64c-244">Tenga en cuenta que CloudFlare es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="5c64c-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="5c64c-245">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (GUI) CloudFlare actual, aproveche la [comunidad de CloudFlare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="5c64c-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="5c64c-246">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="5c64c-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="5c64c-247">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="5c64c-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="5c64c-248">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5c64c-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="5c64c-249">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="5c64c-250">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="5c64c-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="5c64c-251">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c64c-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="5c64c-252">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-252">**Type**</span></span>|<span data-ttu-id="5c64c-253">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="5c64c-253">**Service**</span></span>|<span data-ttu-id="5c64c-254">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="5c64c-254">**Protocol**</span></span>|<span data-ttu-id="5c64c-255">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5c64c-255">**Name**</span></span>|<span data-ttu-id="5c64c-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c64c-256">**TTL**</span></span>|<span data-ttu-id="5c64c-257">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="5c64c-257">**Priority**</span></span>|<span data-ttu-id="5c64c-258">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="5c64c-258">**Weight**</span></span>|<span data-ttu-id="5c64c-259">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="5c64c-259">**Port**</span></span>|<span data-ttu-id="5c64c-260">**Destino**</span><span class="sxs-lookup"><span data-stu-id="5c64c-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c64c-261">SRV</span><span class="sxs-lookup"><span data-stu-id="5c64c-261">SRV</span></span>|<span data-ttu-id="5c64c-262">_sip</span><span class="sxs-lookup"><span data-stu-id="5c64c-262">_sip</span></span> |<span data-ttu-id="5c64c-263">TLS</span><span class="sxs-lookup"><span data-stu-id="5c64c-263">TLS</span></span> |<span data-ttu-id="5c64c-264">Use su *domain_name*; por ejemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="5c64c-265">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-265">30 minutes</span></span> | <span data-ttu-id="5c64c-266">100</span><span class="sxs-lookup"><span data-stu-id="5c64c-266">100</span></span>|<span data-ttu-id="5c64c-267">1</span><span class="sxs-lookup"><span data-stu-id="5c64c-267">1</span></span> |<span data-ttu-id="5c64c-268">443</span><span class="sxs-lookup"><span data-stu-id="5c64c-268">443</span></span> |<span data-ttu-id="5c64c-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="5c64c-270">SRV</span><span class="sxs-lookup"><span data-stu-id="5c64c-270">SRV</span></span>|<span data-ttu-id="5c64c-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5c64c-271">_sipfederationtls</span></span> | <span data-ttu-id="5c64c-272">TCP</span><span class="sxs-lookup"><span data-stu-id="5c64c-272">TCP</span></span>|<span data-ttu-id="5c64c-273">Use su *domain_name*; por ejemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="5c64c-274">30 minutos</span><span class="sxs-lookup"><span data-stu-id="5c64c-274">30 minutes</span></span> |<span data-ttu-id="5c64c-275">100</span><span class="sxs-lookup"><span data-stu-id="5c64c-275">100</span></span> |<span data-ttu-id="5c64c-276">1</span><span class="sxs-lookup"><span data-stu-id="5c64c-276">1</span></span> |<span data-ttu-id="5c64c-277">5061</span><span class="sxs-lookup"><span data-stu-id="5c64c-277">5061</span></span> | <span data-ttu-id="5c64c-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c64c-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="5c64c-279">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c64c-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="5c64c-280">Agregue el otro registro SRV; para ello, elija los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5c64c-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="5c64c-p117">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c64c-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
