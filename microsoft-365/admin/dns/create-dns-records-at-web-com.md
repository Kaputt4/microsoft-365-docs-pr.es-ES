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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en web.com para Microsoft.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629256"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="afc9d-103">Crear registros DNS en web.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="afc9d-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="afc9d-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="afc9d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="afc9d-105">Si web.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="afc9d-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="afc9d-106">Después de agregar estos registros a web.com, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afc9d-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="afc9d-107">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="afc9d-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="afc9d-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afc9d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="afc9d-111">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="afc9d-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="afc9d-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="afc9d-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc9d-113">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="afc9d-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="afc9d-114">Cuando se registró para web.com, agregó un dominio mediante el proceso de **instalación** de Web.com.</span><span class="sxs-lookup"><span data-stu-id="afc9d-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="afc9d-115">Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres Web. com.</span><span class="sxs-lookup"><span data-stu-id="afc9d-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="afc9d-116">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="afc9d-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="afc9d-117">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="afc9d-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="afc9d-118">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.</span><span class="sxs-lookup"><span data-stu-id="afc9d-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="afc9d-119">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="afc9d-119">First nameserver</span></span>  <br/> |<span data-ttu-id="afc9d-120">Usar el valor de nameserver proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="afc9d-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="afc9d-121">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="afc9d-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="afc9d-122">Usar el valor de nameserver proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="afc9d-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="afc9d-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="afc9d-123">You should use at least two name server records.</span></span> <span data-ttu-id="afc9d-124">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="afc9d-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="afc9d-125">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="afc9d-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="afc9d-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="afc9d-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="afc9d-127">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="afc9d-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="afc9d-128">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="afc9d-128">Add a TXT record for verification</span></span>
<span data-ttu-id="afc9d-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="afc9d-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="afc9d-130">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="afc9d-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="afc9d-131">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="afc9d-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afc9d-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="afc9d-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="afc9d-134">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afc9d-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afc9d-135">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="afc9d-135">Log in first.</span></span>
  
2. <span data-ttu-id="afc9d-136">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afc9d-137">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="afc9d-138">En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc9d-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="afc9d-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="afc9d-139">**Host**</span></span>|<span data-ttu-id="afc9d-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afc9d-140">**TTL**</span></span>|<span data-ttu-id="afc9d-141">**Texto**</span><span class="sxs-lookup"><span data-stu-id="afc9d-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="afc9d-142">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-142">3600</span></span>  <br/> |<span data-ttu-id="afc9d-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="afc9d-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="afc9d-144">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="afc9d-144">**Note:** This is an example.</span></span> <span data-ttu-id="afc9d-145">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="afc9d-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="afc9d-146">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="afc9d-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="afc9d-147">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="afc9d-148">Espere unos minutos antes de comprobar el nuevo registro TXT, de modo que el registro que acaba de crear pueda actualizarse a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="afc9d-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="afc9d-149">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.</span><span class="sxs-lookup"><span data-stu-id="afc9d-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="afc9d-150">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="afc9d-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="afc9d-151">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="afc9d-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="afc9d-152">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="afc9d-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="afc9d-153">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="afc9d-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="afc9d-154">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="afc9d-p108">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afc9d-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="afc9d-158">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="afc9d-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="afc9d-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="afc9d-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="afc9d-160">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afc9d-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afc9d-161">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="afc9d-161">Log in first.</span></span>
  
2. <span data-ttu-id="afc9d-162">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afc9d-163">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="afc9d-164">En **servidores de correo (registros MX)**, haga clic en **Editar registros MX**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc9d-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="afc9d-165">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="afc9d-165">**Priority**</span></span>|<span data-ttu-id="afc9d-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afc9d-166">**TTL**</span></span>|<span data-ttu-id="afc9d-167">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="afc9d-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="afc9d-168">1</span><span class="sxs-lookup"><span data-stu-id="afc9d-168">1</span></span>  <br/> <span data-ttu-id="afc9d-169">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="afc9d-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="afc9d-170">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-170">3600</span></span>  <br/> |<span data-ttu-id="afc9d-171">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="afc9d-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="afc9d-172">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afc9d-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="afc9d-173">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="afc9d-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="afc9d-174">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="afc9d-175">Si hay otros registros MX enumerados en la sección **registros MX** , active la casilla situada junto al registro en **eliminar**y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="afc9d-176">En la pantalla de confirmación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="afc9d-177">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="afc9d-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="afc9d-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="afc9d-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="afc9d-179">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afc9d-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afc9d-180">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="afc9d-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="afc9d-181">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afc9d-182">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="afc9d-183">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="afc9d-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="afc9d-184">En **alias de host (registros CNAME)**, haga clic en **Editar registros CNAME**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc9d-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="afc9d-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="afc9d-185">**Alias**</span></span>|<span data-ttu-id="afc9d-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afc9d-186">**TTL**</span></span>|<span data-ttu-id="afc9d-187">**Referencia a nombre de host**</span><span class="sxs-lookup"><span data-stu-id="afc9d-187">**Refers to Host Name**</span></span>|<span data-ttu-id="afc9d-188">**Otro host**</span><span class="sxs-lookup"><span data-stu-id="afc9d-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afc9d-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="afc9d-189">autodiscover</span></span>  <br/> |<span data-ttu-id="afc9d-190">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-190">3600</span></span>  <br/> |<span data-ttu-id="afc9d-191">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="afc9d-191">@ (none)</span></span>  <br/> |<span data-ttu-id="afc9d-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="afc9d-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="afc9d-193">sip</span><span class="sxs-lookup"><span data-stu-id="afc9d-193">sip</span></span>  <br/> |<span data-ttu-id="afc9d-194">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-194">3600</span></span>  <br/> |<span data-ttu-id="afc9d-195">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="afc9d-195">@ (none)</span></span>  <br/> |<span data-ttu-id="afc9d-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afc9d-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="afc9d-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="afc9d-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="afc9d-198">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-198">3600</span></span>  <br/> |<span data-ttu-id="afc9d-199">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="afc9d-199">@ (none)</span></span>  <br/> | <span data-ttu-id="afc9d-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afc9d-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="afc9d-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="afc9d-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="afc9d-202">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-202">3600</span></span>  <br/> |<span data-ttu-id="afc9d-203">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="afc9d-203">@ (none)</span></span>  <br/> |<span data-ttu-id="afc9d-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="afc9d-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="afc9d-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="afc9d-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="afc9d-206">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-206">3600</span></span>  <br/> |<span data-ttu-id="afc9d-207">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="afc9d-207">@ (none)</span></span>  <br/> |<span data-ttu-id="afc9d-208">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="afc9d-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="afc9d-209">msoid</span><span class="sxs-lookup"><span data-stu-id="afc9d-209">msoid</span></span>  <br/> |<span data-ttu-id="afc9d-210">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-210">3600</span></span>  <br/> |<span data-ttu-id="afc9d-211">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="afc9d-211">@ (none)</span></span>  <br/> |<span data-ttu-id="afc9d-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="afc9d-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="afc9d-213">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="afc9d-214">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="afc9d-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="afc9d-215">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="afc9d-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="afc9d-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="afc9d-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc9d-217">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="afc9d-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="afc9d-218">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="afc9d-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="afc9d-219">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afc9d-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="afc9d-220">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="afc9d-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="afc9d-221">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afc9d-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afc9d-222">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="afc9d-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="afc9d-223">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afc9d-224">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="afc9d-225">En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc9d-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="afc9d-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="afc9d-226">**Host**</span></span>|<span data-ttu-id="afc9d-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afc9d-227">**TTL**</span></span>|<span data-ttu-id="afc9d-228">**Texto**</span><span class="sxs-lookup"><span data-stu-id="afc9d-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="afc9d-229">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-229">3600</span></span>  <br/> |<span data-ttu-id="afc9d-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="afc9d-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="afc9d-231">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="afc9d-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="afc9d-232">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-232">Select **Continue**.</span></span>

6. <span data-ttu-id="afc9d-233">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="afc9d-234">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="afc9d-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="afc9d-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="afc9d-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc9d-236">Tenga en cuenta que web.com es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="afc9d-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="afc9d-237">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (GUI) web.com actual, aproveche la [comunidad de Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="afc9d-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="afc9d-238">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afc9d-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afc9d-239">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="afc9d-239">Log in first.</span></span>
      
2. <span data-ttu-id="afc9d-240">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afc9d-241">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="afc9d-242">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="afc9d-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="afc9d-243">En **servicio (registros SRV)**, haga clic en **Editar registros SRV**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc9d-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="afc9d-244">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="afc9d-244">**Service**</span></span>|<span data-ttu-id="afc9d-245">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="afc9d-245">**Protocol**</span></span>|<span data-ttu-id="afc9d-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afc9d-246">**TTL**</span></span>|<span data-ttu-id="afc9d-247">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="afc9d-247">**Priority**</span></span>|<span data-ttu-id="afc9d-248">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="afc9d-248">**Weight**</span></span>|<span data-ttu-id="afc9d-249">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="afc9d-249">**Port**</span></span>|<span data-ttu-id="afc9d-250">**Destino**</span><span class="sxs-lookup"><span data-stu-id="afc9d-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afc9d-251">_sip</span><span class="sxs-lookup"><span data-stu-id="afc9d-251">_sip</span></span> |<span data-ttu-id="afc9d-252">_tls</span><span class="sxs-lookup"><span data-stu-id="afc9d-252">_tls</span></span> |<span data-ttu-id="afc9d-253">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-253">3600</span></span> | <span data-ttu-id="afc9d-254">100</span><span class="sxs-lookup"><span data-stu-id="afc9d-254">100</span></span>|<span data-ttu-id="afc9d-255">1</span><span class="sxs-lookup"><span data-stu-id="afc9d-255">1</span></span> |<span data-ttu-id="afc9d-256">443</span><span class="sxs-lookup"><span data-stu-id="afc9d-256">443</span></span> |<span data-ttu-id="afc9d-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afc9d-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="afc9d-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="afc9d-258">_sipfederationtls</span></span> |<span data-ttu-id="afc9d-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="afc9d-259">_tcp</span></span> |<span data-ttu-id="afc9d-260">3600</span><span class="sxs-lookup"><span data-stu-id="afc9d-260">3600</span></span> |<span data-ttu-id="afc9d-261">100</span><span class="sxs-lookup"><span data-stu-id="afc9d-261">100</span></span> |<span data-ttu-id="afc9d-262">1</span><span class="sxs-lookup"><span data-stu-id="afc9d-262">1</span></span> |<span data-ttu-id="afc9d-263">5061</span><span class="sxs-lookup"><span data-stu-id="afc9d-263">5061</span></span> | <span data-ttu-id="afc9d-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afc9d-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="afc9d-265">Agregue el otro registro SRV; para ello, elija los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="afc9d-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="afc9d-266">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-266">Select **Continue**.</span></span>

7. <span data-ttu-id="afc9d-267">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="afc9d-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="afc9d-p116">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afc9d-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
