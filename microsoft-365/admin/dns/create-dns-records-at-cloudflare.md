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
ms.openlocfilehash: 36578d8eed2c5630a9ce5abfb355983a26028888
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049076"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="093e1-103">Crear registros DNS en CloudFlare para Microsoft</span><span class="sxs-lookup"><span data-stu-id="093e1-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="093e1-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="093e1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="093e1-105">Si CloudFlare es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="093e1-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="093e1-106">Después de agregar estos registros a CloudFlare, su dominio estará configurado para funcionar con los servicios de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="093e1-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="093e1-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="093e1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="093e1-110">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="093e1-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="093e1-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="093e1-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="093e1-112">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="093e1-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="093e1-113">Cuando se registró para CloudFlare, agregó un dominio mediante el proceso de **instalación** de CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="093e1-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="093e1-114">El dominio que agregó se compró en CloudFlare o un registrador de dominios independiente.</span><span class="sxs-lookup"><span data-stu-id="093e1-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="093e1-115">Para comprobar y crear registros DNS para su dominio en Microsoft 365, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="093e1-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="093e1-116">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="093e1-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="093e1-117">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="093e1-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="093e1-118">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.</span><span class="sxs-lookup"><span data-stu-id="093e1-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="093e1-119">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="093e1-119">First nameserver</span></span>  <br/> |<span data-ttu-id="093e1-120">Usar el valor de nameserver proporcionado por CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="093e1-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="093e1-121">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="093e1-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="093e1-122">Usar el valor de nameserver proporcionado por CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="093e1-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="093e1-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="093e1-123">You should use at least two name server records.</span></span> <span data-ttu-id="093e1-124">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="093e1-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="093e1-125">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="093e1-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="093e1-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="093e1-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="093e1-127">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="093e1-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="093e1-128">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="093e1-128">Add a TXT record for verification</span></span>
<span data-ttu-id="093e1-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="093e1-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="093e1-p105">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="093e1-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="093e1-p106">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="093e1-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="093e1-134">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="093e1-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="093e1-135">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="093e1-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="093e1-136">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="093e1-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="093e1-137">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="093e1-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="093e1-138">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="093e1-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="093e1-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="093e1-139">**Type**</span></span>|<span data-ttu-id="093e1-140">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="093e1-140">**Name**</span></span>|<span data-ttu-id="093e1-141">**TTL automático**</span><span class="sxs-lookup"><span data-stu-id="093e1-141">**Automatic TTL**</span></span>|<span data-ttu-id="093e1-142">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="093e1-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="093e1-143">TXT</span><span class="sxs-lookup"><span data-stu-id="093e1-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="093e1-144">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-144">30 minutes</span></span>  <br/> |<span data-ttu-id="093e1-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="093e1-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="093e1-146">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="093e1-146">**Note:** This is an example.</span></span> <span data-ttu-id="093e1-147">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="093e1-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="093e1-148">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="093e1-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="093e1-149">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="093e1-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="093e1-150">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="093e1-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="093e1-151">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y buscará el registro.</span><span class="sxs-lookup"><span data-stu-id="093e1-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="093e1-152">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="093e1-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="093e1-153">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="093e1-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="093e1-154">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="093e1-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="093e1-155">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="093e1-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="093e1-156">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="093e1-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="093e1-p109">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="093e1-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="093e1-160">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="093e1-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="093e1-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="093e1-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="093e1-162">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="093e1-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="093e1-163">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="093e1-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="093e1-164">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="093e1-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="093e1-165">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="093e1-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="093e1-166">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="093e1-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="093e1-167">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="093e1-167">**Type**</span></span>|<span data-ttu-id="093e1-168">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="093e1-168">**Name**</span></span>|<span data-ttu-id="093e1-169">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="093e1-169">**Mail server**</span></span>|<span data-ttu-id="093e1-170">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="093e1-170">**Priority**</span></span>|<span data-ttu-id="093e1-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="093e1-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="093e1-172">MX</span><span class="sxs-lookup"><span data-stu-id="093e1-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="093e1-173">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="093e1-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="093e1-174">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="093e1-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="093e1-175">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="093e1-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="093e1-176">1</span><span class="sxs-lookup"><span data-stu-id="093e1-176">1</span></span>  <br/> <span data-ttu-id="093e1-177">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="093e1-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="093e1-178">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="093e1-179">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="093e1-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="093e1-180">Si hay otros registros MX enumerados en la sección **registros MX** , elimínelos seleccionando el icono **eliminar (X)** .</span><span class="sxs-lookup"><span data-stu-id="093e1-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="093e1-181">En el cuadro de diálogo de confirmación, seleccione **eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="093e1-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="093e1-182">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="093e1-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="093e1-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="093e1-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="093e1-184">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="093e1-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="093e1-185">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="093e1-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="093e1-186">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="093e1-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="093e1-187">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="093e1-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="093e1-188">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="093e1-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="093e1-189">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="093e1-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="093e1-190">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="093e1-190">**Type**</span></span>|<span data-ttu-id="093e1-191">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="093e1-191">**Name**</span></span>|<span data-ttu-id="093e1-192">**Destino**</span><span class="sxs-lookup"><span data-stu-id="093e1-192">**Target**</span></span>|<span data-ttu-id="093e1-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="093e1-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="093e1-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="093e1-194">CNAME</span></span>  <br/> |<span data-ttu-id="093e1-195">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="093e1-195">autodiscover</span></span>  <br/> |<span data-ttu-id="093e1-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="093e1-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="093e1-197">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="093e1-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="093e1-198">CNAME</span></span>  <br/> |<span data-ttu-id="093e1-199">sip</span><span class="sxs-lookup"><span data-stu-id="093e1-199">sip</span></span>  <br/> |<span data-ttu-id="093e1-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="093e1-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="093e1-201">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="093e1-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="093e1-202">CNAME</span></span>  <br/> |<span data-ttu-id="093e1-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="093e1-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="093e1-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="093e1-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="093e1-205">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="093e1-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="093e1-206">CNAME</span></span>  <br/> |<span data-ttu-id="093e1-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="093e1-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="093e1-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="093e1-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="093e1-209">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="093e1-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="093e1-210">CNAME</span></span>  <br/> |<span data-ttu-id="093e1-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="093e1-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="093e1-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="093e1-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="093e1-213">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="093e1-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="093e1-214">CNAME</span></span>  <br/> |<span data-ttu-id="093e1-215">msoid</span><span class="sxs-lookup"><span data-stu-id="093e1-215">msoid</span></span>  <br/> |<span data-ttu-id="093e1-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="093e1-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="093e1-217">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="093e1-218">Seleccione el icono de **tráfico DNS** (nube naranja) para omitir los servidores de CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="093e1-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="093e1-219">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="093e1-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="093e1-220">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="093e1-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="093e1-221">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="093e1-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="093e1-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="093e1-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="093e1-223">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="093e1-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="093e1-224">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="093e1-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="093e1-225">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="093e1-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="093e1-226">En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="093e1-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="093e1-227">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="093e1-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="093e1-228">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="093e1-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="093e1-229">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="093e1-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="093e1-230">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="093e1-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="093e1-231">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="093e1-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="093e1-232">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="093e1-232">**Type**</span></span>|<span data-ttu-id="093e1-233">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="093e1-233">**Name**</span></span>|<span data-ttu-id="093e1-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="093e1-234">**TTL**</span></span>|<span data-ttu-id="093e1-235">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="093e1-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="093e1-236">TXT</span><span class="sxs-lookup"><span data-stu-id="093e1-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="093e1-237">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-237">30 minutes</span></span>  <br/> |<span data-ttu-id="093e1-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="093e1-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="093e1-239">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="093e1-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="093e1-240">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="093e1-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="093e1-241">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="093e1-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="093e1-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="093e1-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="093e1-243">Tenga en cuenta que CloudFlare es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="093e1-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="093e1-244">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (GUI) CloudFlare actual, aproveche la [comunidad de CloudFlare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="093e1-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="093e1-245">Para empezar, vaya a su página de dominios en CloudFlare a través de [este vínculo](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="093e1-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="093e1-246">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="093e1-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="093e1-247">En la página **principal** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="093e1-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="093e1-248">En la página **información general** del dominio, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="093e1-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="093e1-249">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="093e1-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="093e1-250">En la página **Administración de DNS** , haga clic en **Agregar registro**y, a continuación, seleccione los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="093e1-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="093e1-251">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="093e1-251">**Type**</span></span>|<span data-ttu-id="093e1-252">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="093e1-252">**Service**</span></span>|<span data-ttu-id="093e1-253">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="093e1-253">**Protocol**</span></span>|<span data-ttu-id="093e1-254">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="093e1-254">**Name**</span></span>|<span data-ttu-id="093e1-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="093e1-255">**TTL**</span></span>|<span data-ttu-id="093e1-256">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="093e1-256">**Priority**</span></span>|<span data-ttu-id="093e1-257">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="093e1-257">**Weight**</span></span>|<span data-ttu-id="093e1-258">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="093e1-258">**Port**</span></span>|<span data-ttu-id="093e1-259">**Destino**</span><span class="sxs-lookup"><span data-stu-id="093e1-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="093e1-260">SRV</span><span class="sxs-lookup"><span data-stu-id="093e1-260">SRV</span></span>|<span data-ttu-id="093e1-261">_sip</span><span class="sxs-lookup"><span data-stu-id="093e1-261">_sip</span></span> |<span data-ttu-id="093e1-262">TLS</span><span class="sxs-lookup"><span data-stu-id="093e1-262">TLS</span></span> |<span data-ttu-id="093e1-263">Use su *domain_name*; por ejemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="093e1-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="093e1-264">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-264">30 minutes</span></span> | <span data-ttu-id="093e1-265">100</span><span class="sxs-lookup"><span data-stu-id="093e1-265">100</span></span>|<span data-ttu-id="093e1-266">1</span><span class="sxs-lookup"><span data-stu-id="093e1-266">1</span></span> |<span data-ttu-id="093e1-267">443</span><span class="sxs-lookup"><span data-stu-id="093e1-267">443</span></span> |<span data-ttu-id="093e1-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="093e1-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="093e1-269">SRV</span><span class="sxs-lookup"><span data-stu-id="093e1-269">SRV</span></span>|<span data-ttu-id="093e1-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="093e1-270">_sipfederationtls</span></span> | <span data-ttu-id="093e1-271">TCP</span><span class="sxs-lookup"><span data-stu-id="093e1-271">TCP</span></span>|<span data-ttu-id="093e1-272">Use su *domain_name*; por ejemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="093e1-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="093e1-273">30 minutos</span><span class="sxs-lookup"><span data-stu-id="093e1-273">30 minutes</span></span> |<span data-ttu-id="093e1-274">100</span><span class="sxs-lookup"><span data-stu-id="093e1-274">100</span></span> |<span data-ttu-id="093e1-275">1</span><span class="sxs-lookup"><span data-stu-id="093e1-275">1</span></span> |<span data-ttu-id="093e1-276">5061</span><span class="sxs-lookup"><span data-stu-id="093e1-276">5061</span></span> | <span data-ttu-id="093e1-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="093e1-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="093e1-278">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="093e1-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="093e1-279">Agregue el otro registro SRV; para ello, elija los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="093e1-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="093e1-p117">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="093e1-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
