---
title: Crear registros DNS en web.com para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en web.com para Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249460"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="98ea0-103">Crear registros DNS en web.com para Office 365</span><span class="sxs-lookup"><span data-stu-id="98ea0-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="98ea0-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="98ea0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="98ea0-105">Si web.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="98ea0-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="98ea0-106">Después de agregar estos registros a web.com, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="98ea0-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="98ea0-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="98ea0-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="98ea0-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98ea0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="98ea0-111">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="98ea0-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="98ea0-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="98ea0-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="98ea0-113">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="98ea0-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="98ea0-114">Cuando se registró para web.com, agregó un dominio mediante el proceso de **instalación** de Web.com.</span><span class="sxs-lookup"><span data-stu-id="98ea0-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="98ea0-115">Para comprobar y crear registros DNS para su dominio en Office 365, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres Web. com.</span><span class="sxs-lookup"><span data-stu-id="98ea0-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="98ea0-116">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98ea0-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="98ea0-117">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="98ea0-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="98ea0-118">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.</span><span class="sxs-lookup"><span data-stu-id="98ea0-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="98ea0-119">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="98ea0-119">First nameserver</span></span>  <br/> |<span data-ttu-id="98ea0-120">Usar el valor de nameserver proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="98ea0-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="98ea0-121">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="98ea0-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="98ea0-122">Usar el valor de nameserver proporcionado por web.com.</span><span class="sxs-lookup"><span data-stu-id="98ea0-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="98ea0-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="98ea0-123">You should use at least two name server records.</span></span> <span data-ttu-id="98ea0-124">Si hay otros servidores de nombres enumerados, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="98ea0-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="98ea0-125">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="98ea0-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="98ea0-p103">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="98ea0-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="98ea0-128">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="98ea0-128">Add a TXT record for verification</span></span>
<span data-ttu-id="98ea0-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="98ea0-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="98ea0-p104">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="98ea0-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98ea0-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="98ea0-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="98ea0-134">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="98ea0-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="98ea0-135">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="98ea0-135">Log in first.</span></span>
  
2. <span data-ttu-id="98ea0-136">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="98ea0-137">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="98ea0-138">En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="98ea0-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="98ea0-139">**Host**</span></span>|<span data-ttu-id="98ea0-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="98ea0-140">**TTL**</span></span>|<span data-ttu-id="98ea0-141">**Texto**</span><span class="sxs-lookup"><span data-stu-id="98ea0-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="98ea0-142">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-142">3600</span></span>  <br/> |<span data-ttu-id="98ea0-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="98ea0-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="98ea0-144">**Nota:** Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="98ea0-144">**Note:** This is an example.</span></span> <span data-ttu-id="98ea0-145">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="98ea0-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="98ea0-146">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="98ea0-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="98ea0-147">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="98ea0-148">Espere unos minutos antes de comprobar el nuevo registro TXT, de modo que el registro que acaba de crear pueda actualizarse a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="98ea0-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="98ea0-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="98ea0-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="98ea0-150">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="98ea0-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="98ea0-151">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="98ea0-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="98ea0-152">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="98ea0-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="98ea0-153">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="98ea0-154">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="98ea0-p108">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98ea0-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="98ea0-158">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="98ea0-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="98ea0-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="98ea0-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="98ea0-160">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="98ea0-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="98ea0-161">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="98ea0-161">Log in first.</span></span>
  
2. <span data-ttu-id="98ea0-162">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="98ea0-163">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="98ea0-164">En **servidores de correo (registros MX)**, haga clic en **Editar registros MX**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="98ea0-165">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="98ea0-165">**Priority**</span></span>|<span data-ttu-id="98ea0-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="98ea0-166">**TTL**</span></span>|<span data-ttu-id="98ea0-167">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="98ea0-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="98ea0-168">1</span><span class="sxs-lookup"><span data-stu-id="98ea0-168">1</span></span>  <br/> <span data-ttu-id="98ea0-169">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="98ea0-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="98ea0-170">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-170">3600</span></span>  <br/> |<span data-ttu-id="98ea0-171">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="98ea0-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="98ea0-172">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="98ea0-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="98ea0-173">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="98ea0-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="98ea0-174">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="98ea0-175">Si hay otros registros MX enumerados en la sección **registros MX** , active la casilla situada junto al registro en **eliminar**y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="98ea0-176">En la pantalla de confirmación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="98ea0-177">Agregue los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="98ea0-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="98ea0-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="98ea0-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="98ea0-179">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="98ea0-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="98ea0-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="98ea0-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="98ea0-181">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="98ea0-182">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="98ea0-183">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="98ea0-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="98ea0-184">En **alias de host (registros CNAME)**, haga clic en **Editar registros CNAME**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="98ea0-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="98ea0-185">**Alias**</span></span>|<span data-ttu-id="98ea0-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="98ea0-186">**TTL**</span></span>|<span data-ttu-id="98ea0-187">**Referencia a nombre de host**</span><span class="sxs-lookup"><span data-stu-id="98ea0-187">**Refers to Host Name**</span></span>|<span data-ttu-id="98ea0-188">**Otro host**</span><span class="sxs-lookup"><span data-stu-id="98ea0-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="98ea0-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="98ea0-189">autodiscover</span></span>  <br/> |<span data-ttu-id="98ea0-190">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-190">3600</span></span>  <br/> |<span data-ttu-id="98ea0-191">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="98ea0-191">@ (none)</span></span>  <br/> |<span data-ttu-id="98ea0-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="98ea0-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="98ea0-193">sip</span><span class="sxs-lookup"><span data-stu-id="98ea0-193">sip</span></span>  <br/> |<span data-ttu-id="98ea0-194">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-194">3600</span></span>  <br/> |<span data-ttu-id="98ea0-195">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="98ea0-195">@ (none)</span></span>  <br/> |<span data-ttu-id="98ea0-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98ea0-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="98ea0-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="98ea0-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="98ea0-198">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-198">3600</span></span>  <br/> |<span data-ttu-id="98ea0-199">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="98ea0-199">@ (none)</span></span>  <br/> | <span data-ttu-id="98ea0-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98ea0-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="98ea0-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="98ea0-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="98ea0-202">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-202">3600</span></span>  <br/> |<span data-ttu-id="98ea0-203">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="98ea0-203">@ (none)</span></span>  <br/> |<span data-ttu-id="98ea0-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="98ea0-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="98ea0-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="98ea0-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="98ea0-206">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-206">3600</span></span>  <br/> |<span data-ttu-id="98ea0-207">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="98ea0-207">@ (none)</span></span>  <br/> |<span data-ttu-id="98ea0-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="98ea0-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="98ea0-209">msoid</span><span class="sxs-lookup"><span data-stu-id="98ea0-209">msoid</span></span>  <br/> |<span data-ttu-id="98ea0-210">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-210">3600</span></span>  <br/> |<span data-ttu-id="98ea0-211">@ (ninguno)</span><span class="sxs-lookup"><span data-stu-id="98ea0-211">@ (none)</span></span>  <br/> |<span data-ttu-id="98ea0-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="98ea0-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="98ea0-213">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="98ea0-214">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="98ea0-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="98ea0-215">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="98ea0-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="98ea0-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="98ea0-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="98ea0-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="98ea0-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="98ea0-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="98ea0-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="98ea0-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="98ea0-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="98ea0-220">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="98ea0-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="98ea0-221">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="98ea0-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="98ea0-222">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="98ea0-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="98ea0-223">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="98ea0-224">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="98ea0-225">En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="98ea0-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="98ea0-226">**Host**</span></span>|<span data-ttu-id="98ea0-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="98ea0-227">**TTL**</span></span>|<span data-ttu-id="98ea0-228">**Texto**</span><span class="sxs-lookup"><span data-stu-id="98ea0-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="98ea0-229">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-229">3600</span></span>  <br/> |<span data-ttu-id="98ea0-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="98ea0-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="98ea0-231">**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="98ea0-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="98ea0-232">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-232">Select **Continue**.</span></span>

6. <span data-ttu-id="98ea0-233">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="98ea0-234">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="98ea0-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="98ea0-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="98ea0-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="98ea0-236">Tenga en cuenta que web.com es responsable de hacer que esta funcionalidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="98ea0-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="98ea0-237">En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (GUI) web.com actual, aproveche la [comunidad de Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="98ea0-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="98ea0-238">Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="98ea0-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="98ea0-239">Inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="98ea0-239">Log in first.</span></span>
      
2. <span data-ttu-id="98ea0-240">En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="98ea0-241">En \* \* administrar \* mi dominio \* \* \*, seleccione **Editar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="98ea0-242">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="98ea0-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="98ea0-243">En **servicio (registros SRV)**, haga clic en **Editar registros SRV**y, a continuación, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="98ea0-244">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="98ea0-244">**Service**</span></span>|<span data-ttu-id="98ea0-245">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="98ea0-245">**Protocol**</span></span>|<span data-ttu-id="98ea0-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="98ea0-246">**TTL**</span></span>|<span data-ttu-id="98ea0-247">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="98ea0-247">**Priority**</span></span>|<span data-ttu-id="98ea0-248">**Peso**</span><span class="sxs-lookup"><span data-stu-id="98ea0-248">**Weight**</span></span>|<span data-ttu-id="98ea0-249">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="98ea0-249">**Port**</span></span>|<span data-ttu-id="98ea0-250">**Destino**</span><span class="sxs-lookup"><span data-stu-id="98ea0-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="98ea0-251">_sip</span><span class="sxs-lookup"><span data-stu-id="98ea0-251">_sip</span></span> |<span data-ttu-id="98ea0-252">_tls</span><span class="sxs-lookup"><span data-stu-id="98ea0-252">_tls</span></span> |<span data-ttu-id="98ea0-253">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-253">3600</span></span> | <span data-ttu-id="98ea0-254">100</span><span class="sxs-lookup"><span data-stu-id="98ea0-254">100</span></span>|<span data-ttu-id="98ea0-255">1</span><span class="sxs-lookup"><span data-stu-id="98ea0-255">1</span></span> |<span data-ttu-id="98ea0-256">443</span><span class="sxs-lookup"><span data-stu-id="98ea0-256">443</span></span> |<span data-ttu-id="98ea0-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98ea0-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="98ea0-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="98ea0-258">_sipfederationtls</span></span> |<span data-ttu-id="98ea0-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="98ea0-259">_tcp</span></span> |<span data-ttu-id="98ea0-260">3600</span><span class="sxs-lookup"><span data-stu-id="98ea0-260">3600</span></span> |<span data-ttu-id="98ea0-261">100</span><span class="sxs-lookup"><span data-stu-id="98ea0-261">100</span></span> |<span data-ttu-id="98ea0-262">1</span><span class="sxs-lookup"><span data-stu-id="98ea0-262">1</span></span> |<span data-ttu-id="98ea0-263">5061</span><span class="sxs-lookup"><span data-stu-id="98ea0-263">5061</span></span> | <span data-ttu-id="98ea0-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98ea0-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="98ea0-265">Agregue el otro registro SRV; para ello, elija los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="98ea0-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="98ea0-266">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-266">Select **Continue**.</span></span>

7. <span data-ttu-id="98ea0-267">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="98ea0-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="98ea0-p116">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98ea0-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
