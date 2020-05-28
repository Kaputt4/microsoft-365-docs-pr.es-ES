---
title: Crear registros DNS en web.com para Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en web.com para Microsoft.
ms.openlocfilehash: 2a9162c1ca6fc6a00e564e8f004768fac49bd3e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400309"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="728a6-103">Crear registros DNS en web.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="728a6-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="728a6-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="728a6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="728a6-105">Si web.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="728a6-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="728a6-106">Después de agregar estos registros a web.com, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="728a6-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="728a6-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="728a6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="728a6-110">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="728a6-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="728a6-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="728a6-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="728a6-112">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="728a6-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="728a6-113">Cuando se registró para web.com, agregó un dominio mediante el proceso de **instalación** de Web.com.</span><span class="sxs-lookup"><span data-stu-id="728a6-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="728a6-114">Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres Web. com.</span><span class="sxs-lookup"><span data-stu-id="728a6-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="728a6-115">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="728a6-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="728a6-116">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="728a6-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="728a6-117">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.</span><span class="sxs-lookup"><span data-stu-id="728a6-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="728a6-118">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="728a6-118">First nameserver</span></span>  <br/> |<span data-ttu-id="728a6-119">Usar el valor de nameserver proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="728a6-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="728a6-120">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="728a6-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="728a6-121">Usar el valor de nameserver proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="728a6-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="728a6-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="728a6-122">You should use at least two name server records.</span></span> <span data-ttu-id="728a6-123">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="728a6-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="728a6-124">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="728a6-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="728a6-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="728a6-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="728a6-126">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="728a6-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="728a6-127">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="728a6-127">Add a TXT record for verification</span></span>
<span data-ttu-id="728a6-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="728a6-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="728a6-p104">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="728a6-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="728a6-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="728a6-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="728a6-133">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="728a6-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="728a6-134">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="728a6-134">Log in first.</span></span>
  
2. <span data-ttu-id="728a6-135">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="728a6-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="728a6-136">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="728a6-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="728a6-137">En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="728a6-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="728a6-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="728a6-138">**Host**</span></span>|<span data-ttu-id="728a6-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="728a6-139">**TTL**</span></span>|<span data-ttu-id="728a6-140">**Texto**</span><span class="sxs-lookup"><span data-stu-id="728a6-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="728a6-141">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-141">3600</span></span>  <br/> |<span data-ttu-id="728a6-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="728a6-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="728a6-143">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="728a6-143">**Note:** This is an example.</span></span> <span data-ttu-id="728a6-144">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="728a6-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="728a6-145">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="728a6-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="728a6-146">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="728a6-147">Espere unos minutos antes de comprobar el nuevo registro TXT, de modo que el registro que acaba de crear pueda actualizarse a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="728a6-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="728a6-148">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="728a6-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="728a6-149">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="728a6-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="728a6-150">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="728a6-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="728a6-151">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="728a6-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="728a6-152">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="728a6-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="728a6-153">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="728a6-p108">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="728a6-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="728a6-157">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="728a6-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="728a6-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="728a6-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="728a6-159">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="728a6-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="728a6-160">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="728a6-160">Log in first.</span></span>
  
2. <span data-ttu-id="728a6-161">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="728a6-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="728a6-162">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="728a6-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="728a6-163">En **servidores de correo (registros MX)**, haga clic en **Editar registros MX**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="728a6-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="728a6-164">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="728a6-164">**Priority**</span></span>|<span data-ttu-id="728a6-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="728a6-165">**TTL**</span></span>|<span data-ttu-id="728a6-166">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="728a6-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="728a6-167">1 </span><span class="sxs-lookup"><span data-stu-id="728a6-167">1</span></span>  <br/> <span data-ttu-id="728a6-168">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="728a6-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="728a6-169">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-169">3600</span></span>  <br/> |<span data-ttu-id="728a6-170">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="728a6-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="728a6-171">**Nota:** Obtén tu *\<domain-key\>* cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="728a6-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="728a6-172">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="728a6-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="728a6-173">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="728a6-174">Si hay otros registros MX enumerados en la sección **registros MX** , active la casilla situada junto al registro en **eliminar**y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="728a6-175">En la pantalla de confirmación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="728a6-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="728a6-176">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="728a6-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="728a6-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="728a6-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="728a6-178">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="728a6-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="728a6-179">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="728a6-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="728a6-180">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="728a6-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="728a6-181">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="728a6-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="728a6-182">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="728a6-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="728a6-183">En **alias de host (registros CNAME)**, haga clic en **Editar registros CNAME**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="728a6-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="728a6-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="728a6-184">**Alias**</span></span>|<span data-ttu-id="728a6-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="728a6-185">**TTL**</span></span>|<span data-ttu-id="728a6-186">**Referencia a nombre de host**</span><span class="sxs-lookup"><span data-stu-id="728a6-186">**Refers to Host Name**</span></span>|<span data-ttu-id="728a6-187">**Otro host**</span><span class="sxs-lookup"><span data-stu-id="728a6-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="728a6-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="728a6-188">autodiscover</span></span>  <br/> |<span data-ttu-id="728a6-189">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-189">3600</span></span>  <br/> |<span data-ttu-id="728a6-190">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="728a6-190">@ (none)</span></span>  <br/> |<span data-ttu-id="728a6-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="728a6-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="728a6-192">sip</span><span class="sxs-lookup"><span data-stu-id="728a6-192">sip</span></span>  <br/> |<span data-ttu-id="728a6-193">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-193">3600</span></span>  <br/> |<span data-ttu-id="728a6-194">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="728a6-194">@ (none)</span></span>  <br/> |<span data-ttu-id="728a6-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="728a6-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="728a6-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="728a6-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="728a6-197">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-197">3600</span></span>  <br/> |<span data-ttu-id="728a6-198">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="728a6-198">@ (none)</span></span>  <br/> | <span data-ttu-id="728a6-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="728a6-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="728a6-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="728a6-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="728a6-201">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-201">3600</span></span>  <br/> |<span data-ttu-id="728a6-202">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="728a6-202">@ (none)</span></span>  <br/> |<span data-ttu-id="728a6-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="728a6-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="728a6-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="728a6-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="728a6-205">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-205">3600</span></span>  <br/> |<span data-ttu-id="728a6-206">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="728a6-206">@ (none)</span></span>  <br/> |<span data-ttu-id="728a6-207">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="728a6-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="728a6-208">msoid</span><span class="sxs-lookup"><span data-stu-id="728a6-208">msoid</span></span>  <br/> |<span data-ttu-id="728a6-209">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-209">3600</span></span>  <br/> |<span data-ttu-id="728a6-210">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="728a6-210">@ (none)</span></span>  <br/> |<span data-ttu-id="728a6-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="728a6-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="728a6-212">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="728a6-213">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="728a6-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="728a6-214">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="728a6-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="728a6-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="728a6-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="728a6-216">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="728a6-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="728a6-217">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="728a6-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="728a6-218">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="728a6-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="728a6-219">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="728a6-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="728a6-220">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="728a6-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="728a6-221">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="728a6-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="728a6-222">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="728a6-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="728a6-223">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="728a6-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="728a6-224">En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="728a6-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="728a6-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="728a6-225">**Host**</span></span>|<span data-ttu-id="728a6-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="728a6-226">**TTL**</span></span>|<span data-ttu-id="728a6-227">**Texto**</span><span class="sxs-lookup"><span data-stu-id="728a6-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="728a6-228">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-228">3600</span></span>  <br/> |<span data-ttu-id="728a6-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="728a6-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="728a6-230">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="728a6-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="728a6-231">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-231">Select **Continue**.</span></span>

6. <span data-ttu-id="728a6-232">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="728a6-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="728a6-233">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="728a6-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="728a6-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="728a6-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="728a6-235">Tenga en cuenta que web.com es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="728a6-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="728a6-236">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (GUI) web.com actual, aproveche la [comunidad de Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="728a6-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="728a6-237">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="728a6-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="728a6-238">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="728a6-238">Log in first.</span></span>
      
2. <span data-ttu-id="728a6-239">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="728a6-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="728a6-240">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="728a6-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="728a6-241">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="728a6-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="728a6-242">En **servicio (registros SRV)**, haga clic en **Editar registros SRV**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="728a6-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="728a6-243">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="728a6-243">**Service**</span></span>|<span data-ttu-id="728a6-244">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="728a6-244">**Protocol**</span></span>|<span data-ttu-id="728a6-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="728a6-245">**TTL**</span></span>|<span data-ttu-id="728a6-246">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="728a6-246">**Priority**</span></span>|<span data-ttu-id="728a6-247">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="728a6-247">**Weight**</span></span>|<span data-ttu-id="728a6-248">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="728a6-248">**Port**</span></span>|<span data-ttu-id="728a6-249">**Destino**</span><span class="sxs-lookup"><span data-stu-id="728a6-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="728a6-250">_sip</span><span class="sxs-lookup"><span data-stu-id="728a6-250">_sip</span></span> |<span data-ttu-id="728a6-251">_tls</span><span class="sxs-lookup"><span data-stu-id="728a6-251">_tls</span></span> |<span data-ttu-id="728a6-252">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-252">3600</span></span> | <span data-ttu-id="728a6-253">100</span><span class="sxs-lookup"><span data-stu-id="728a6-253">100</span></span>|<span data-ttu-id="728a6-254">1 </span><span class="sxs-lookup"><span data-stu-id="728a6-254">1</span></span> |<span data-ttu-id="728a6-255">443</span><span class="sxs-lookup"><span data-stu-id="728a6-255">443</span></span> |<span data-ttu-id="728a6-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="728a6-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="728a6-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="728a6-257">_sipfederationtls</span></span> |<span data-ttu-id="728a6-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="728a6-258">_tcp</span></span> |<span data-ttu-id="728a6-259">3600</span><span class="sxs-lookup"><span data-stu-id="728a6-259">3600</span></span> |<span data-ttu-id="728a6-260">100</span><span class="sxs-lookup"><span data-stu-id="728a6-260">100</span></span> |<span data-ttu-id="728a6-261">1 </span><span class="sxs-lookup"><span data-stu-id="728a6-261">1</span></span> |<span data-ttu-id="728a6-262">5061</span><span class="sxs-lookup"><span data-stu-id="728a6-262">5061</span></span> | <span data-ttu-id="728a6-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="728a6-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="728a6-264">Agregue el otro registro SRV; para ello, elija los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="728a6-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="728a6-265">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="728a6-265">Select **Continue**.</span></span>

7. <span data-ttu-id="728a6-266">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="728a6-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="728a6-p116">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="728a6-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
