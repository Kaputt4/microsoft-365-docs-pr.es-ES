---
title: Crear registros DNS en web.com microsoft
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
description: Obtenga información sobre cómo comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en web.com microsoft.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909987"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="68468-103">Crear registros DNS en web.com microsoft</span><span class="sxs-lookup"><span data-stu-id="68468-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="68468-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="68468-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="68468-105">Si web.com es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="68468-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="68468-106">Después de agregar estos registros en web.com, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68468-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="68468-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68468-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="68468-110">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="68468-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="68468-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="68468-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="68468-112">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="68468-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="68468-113">Cuando se inscribió en web.com, agregó un dominio mediante el web.com **de instalación.**</span><span class="sxs-lookup"><span data-stu-id="68468-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="68468-114">Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de web.com.</span><span class="sxs-lookup"><span data-stu-id="68468-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="68468-115">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="68468-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="68468-116">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="68468-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="68468-117">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros existentes del servidor de nombres para que coincidan con estos valores.</span><span class="sxs-lookup"><span data-stu-id="68468-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="68468-118">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="68468-118">First nameserver</span></span>  <br/> |<span data-ttu-id="68468-119">Use el valor de servidor de nombres proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="68468-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="68468-120">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="68468-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="68468-121">Use el valor de servidor de nombres proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="68468-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="68468-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="68468-122">You should use at least two name server records.</span></span> <span data-ttu-id="68468-123">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="68468-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="68468-124">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="68468-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="68468-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="68468-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="68468-126">A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="68468-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="68468-127">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="68468-127">Add a TXT record for verification</span></span>
<span data-ttu-id="68468-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="68468-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="68468-p104">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="68468-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68468-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="68468-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="68468-133">Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="68468-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="68468-134">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="68468-134">Log in first.</span></span>
  
2. <span data-ttu-id="68468-135">En la **página Administrador de** cuentas, seleccione Mis nombres de **dominio**.</span><span class="sxs-lookup"><span data-stu-id="68468-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="68468-136">En \*\*Administrar \*mi dominio\*\*\*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="68468-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="68468-137">En la **página Nombres de** dominio, en Texto **(registros TXT),** haga clic en Editar registros **TXT** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68468-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="68468-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="68468-138">**Host**</span></span>|<span data-ttu-id="68468-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="68468-139">**TTL**</span></span>|<span data-ttu-id="68468-140">**Texto**</span><span class="sxs-lookup"><span data-stu-id="68468-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="68468-141">3600</span><span class="sxs-lookup"><span data-stu-id="68468-141">3600</span></span>  <br/> |<span data-ttu-id="68468-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="68468-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="68468-143">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="68468-143">**Note:** This is an example.</span></span> <span data-ttu-id="68468-144">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="68468-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="68468-145">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="68468-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="68468-146">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="68468-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="68468-147">Espere unos minutos antes de comprobar el nuevo registro TXT, para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="68468-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="68468-148">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="68468-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="68468-149">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="68468-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="68468-150">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="68468-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="68468-151">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="68468-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="68468-152">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="68468-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="68468-153">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="68468-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="68468-p108">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68468-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="68468-157">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="68468-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="68468-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="68468-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="68468-159">Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="68468-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="68468-160">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="68468-160">Log in first.</span></span>
  
2. <span data-ttu-id="68468-161">En la **página Administrador de** cuentas, seleccione Mis nombres de **dominio**.</span><span class="sxs-lookup"><span data-stu-id="68468-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="68468-162">En \*\*Administrar \*mi dominio\*\*\*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="68468-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="68468-163">En **Servidores de correo (registros MX),** haga clic en Editar registros **MX** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68468-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="68468-164">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="68468-164">**Priority**</span></span>|<span data-ttu-id="68468-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="68468-165">**TTL**</span></span>|<span data-ttu-id="68468-166">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="68468-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="68468-167">1</span><span class="sxs-lookup"><span data-stu-id="68468-167">1</span></span>  <br/> <span data-ttu-id="68468-168">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="68468-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="68468-169">3600</span><span class="sxs-lookup"><span data-stu-id="68468-169">3600</span></span>  <br/> |<span data-ttu-id="68468-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="68468-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="68468-171">**Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68468-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="68468-172">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="68468-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="68468-173">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68468-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="68468-174">Si hay otros registros MX enumerados en la sección **Registros MX,** active la casilla situada junto al registro en **Eliminar** y **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68468-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="68468-175">En la pantalla de confirmación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="68468-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="68468-176">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="68468-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="68468-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="68468-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="68468-178">Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="68468-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="68468-179">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="68468-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="68468-180">En la **página Administrador de** cuentas, seleccione Mis nombres de **dominio**.</span><span class="sxs-lookup"><span data-stu-id="68468-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="68468-181">En \*\*Administrar \*mi dominio\*\*\*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="68468-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="68468-182">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="68468-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="68468-183">En **Alias de host (registros CNAME),** haga clic en Editar registros **CNAME** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68468-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="68468-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="68468-184">**Alias**</span></span>|<span data-ttu-id="68468-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="68468-185">**TTL**</span></span>|<span data-ttu-id="68468-186">**Referencia a nombre de host**</span><span class="sxs-lookup"><span data-stu-id="68468-186">**Refers to Host Name**</span></span>|<span data-ttu-id="68468-187">**Otro host**</span><span class="sxs-lookup"><span data-stu-id="68468-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="68468-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="68468-188">autodiscover</span></span>  <br/> |<span data-ttu-id="68468-189">3600</span><span class="sxs-lookup"><span data-stu-id="68468-189">3600</span></span>  <br/> |<span data-ttu-id="68468-190">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="68468-190">@ (none)</span></span>  <br/> |<span data-ttu-id="68468-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="68468-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="68468-192">sip</span><span class="sxs-lookup"><span data-stu-id="68468-192">sip</span></span>  <br/> |<span data-ttu-id="68468-193">3600</span><span class="sxs-lookup"><span data-stu-id="68468-193">3600</span></span>  <br/> |<span data-ttu-id="68468-194">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="68468-194">@ (none)</span></span>  <br/> |<span data-ttu-id="68468-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68468-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="68468-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="68468-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="68468-197">3600</span><span class="sxs-lookup"><span data-stu-id="68468-197">3600</span></span>  <br/> |<span data-ttu-id="68468-198">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="68468-198">@ (none)</span></span>  <br/> | <span data-ttu-id="68468-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68468-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="68468-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="68468-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="68468-201">3600</span><span class="sxs-lookup"><span data-stu-id="68468-201">3600</span></span>  <br/> |<span data-ttu-id="68468-202">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="68468-202">@ (none)</span></span>  <br/> |<span data-ttu-id="68468-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="68468-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="68468-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="68468-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="68468-205">3600</span><span class="sxs-lookup"><span data-stu-id="68468-205">3600</span></span>  <br/> |<span data-ttu-id="68468-206">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="68468-206">@ (none)</span></span>  <br/> |<span data-ttu-id="68468-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="68468-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="68468-208">msoid</span><span class="sxs-lookup"><span data-stu-id="68468-208">msoid</span></span>  <br/> |<span data-ttu-id="68468-209">3600</span><span class="sxs-lookup"><span data-stu-id="68468-209">3600</span></span>  <br/> |<span data-ttu-id="68468-210">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="68468-210">@ (none)</span></span>  <br/> |<span data-ttu-id="68468-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="68468-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="68468-212">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="68468-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="68468-213">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="68468-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="68468-214">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="68468-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="68468-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="68468-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="68468-216">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="68468-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="68468-217">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="68468-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="68468-218">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68468-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="68468-219">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="68468-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="68468-220">Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="68468-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="68468-221">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="68468-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="68468-222">En la **página Administrador de** cuentas, seleccione Mis nombres de **dominio**.</span><span class="sxs-lookup"><span data-stu-id="68468-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="68468-223">En \*\*Administrar \*mi dominio\*\*\*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="68468-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="68468-224">En la **página Nombres de** dominio, en Texto **(registros TXT),** haga clic en Editar registros **TXT** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68468-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="68468-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="68468-225">**Host**</span></span>|<span data-ttu-id="68468-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="68468-226">**TTL**</span></span>|<span data-ttu-id="68468-227">**Texto**</span><span class="sxs-lookup"><span data-stu-id="68468-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="68468-228">3600</span><span class="sxs-lookup"><span data-stu-id="68468-228">3600</span></span>  <br/> |<span data-ttu-id="68468-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="68468-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="68468-230">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="68468-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="68468-231">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="68468-231">Select **Continue**.</span></span>

6. <span data-ttu-id="68468-232">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="68468-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="68468-233">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="68468-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="68468-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="68468-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="68468-235">Tenga en cuenta que web.com es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="68468-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="68468-236">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario web.com actual, aproveche la [comunidad web.com .](https://community.web.com.com/)</span><span class="sxs-lookup"><span data-stu-id="68468-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="68468-237">Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="68468-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="68468-238">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="68468-238">Log in first.</span></span>
      
2. <span data-ttu-id="68468-239">En la **página Administrador de** cuentas, seleccione Mis nombres de **dominio**.</span><span class="sxs-lookup"><span data-stu-id="68468-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="68468-240">En \*\*Administrar \*mi dominio\*\*\*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="68468-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="68468-241">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="68468-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="68468-242">En **Servicio (registros SRV),** haga clic **en Editar registros SRV** y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68468-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="68468-243">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="68468-243">**Service**</span></span>|<span data-ttu-id="68468-244">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="68468-244">**Protocol**</span></span>|<span data-ttu-id="68468-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="68468-245">**TTL**</span></span>|<span data-ttu-id="68468-246">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="68468-246">**Priority**</span></span>|<span data-ttu-id="68468-247">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="68468-247">**Weight**</span></span>|<span data-ttu-id="68468-248">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="68468-248">**Port**</span></span>|<span data-ttu-id="68468-249">**Destino**</span><span class="sxs-lookup"><span data-stu-id="68468-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="68468-250">_sip</span><span class="sxs-lookup"><span data-stu-id="68468-250">_sip</span></span> |<span data-ttu-id="68468-251">_tls</span><span class="sxs-lookup"><span data-stu-id="68468-251">_tls</span></span> |<span data-ttu-id="68468-252">3600</span><span class="sxs-lookup"><span data-stu-id="68468-252">3600</span></span> | <span data-ttu-id="68468-253">100</span><span class="sxs-lookup"><span data-stu-id="68468-253">100</span></span>|<span data-ttu-id="68468-254">1</span><span class="sxs-lookup"><span data-stu-id="68468-254">1</span></span> |<span data-ttu-id="68468-255">443</span><span class="sxs-lookup"><span data-stu-id="68468-255">443</span></span> |<span data-ttu-id="68468-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68468-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="68468-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="68468-257">_sipfederationtls</span></span> |<span data-ttu-id="68468-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="68468-258">_tcp</span></span> |<span data-ttu-id="68468-259">3600</span><span class="sxs-lookup"><span data-stu-id="68468-259">3600</span></span> |<span data-ttu-id="68468-260">100</span><span class="sxs-lookup"><span data-stu-id="68468-260">100</span></span> |<span data-ttu-id="68468-261">1</span><span class="sxs-lookup"><span data-stu-id="68468-261">1</span></span> |<span data-ttu-id="68468-262">5061</span><span class="sxs-lookup"><span data-stu-id="68468-262">5061</span></span> | <span data-ttu-id="68468-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68468-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="68468-264">Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="68468-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="68468-265">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="68468-265">Select **Continue**.</span></span>

7. <span data-ttu-id="68468-266">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="68468-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="68468-p116">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68468-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
