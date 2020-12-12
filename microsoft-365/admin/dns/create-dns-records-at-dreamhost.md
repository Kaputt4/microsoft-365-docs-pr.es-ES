---
title: Crear registros DNS en Dreamhost para Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Dreamhost para Microsoft.
ms.openlocfilehash: 2faf7cae1fd9a0f9308e303c0588958e56b223e1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658128"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="cb912-103">Crear registros DNS en Dreamhost para Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb912-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="cb912-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="cb912-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cb912-105">Si DreamHost es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.</span><span class="sxs-lookup"><span data-stu-id="cb912-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="cb912-106">Después de agregar estos registros a DreamHost, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb912-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="cb912-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cb912-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cb912-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="cb912-110">Add a TXT record for verification</span></span>
<span data-ttu-id="cb912-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cb912-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cb912-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="cb912-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb912-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="cb912-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cb912-116">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="cb912-116">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb912-117">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cb912-117">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb912-119">En la página **Panel** , seleccione **dominios** y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="cb912-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb912-121">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="cb912-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb912-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cb912-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb912-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb912-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb912-125">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="cb912-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb912-126">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cb912-126">**Name**</span></span>|<span data-ttu-id="cb912-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="cb912-127">**Type**</span></span>|<span data-ttu-id="cb912-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cb912-128">**Value**</span></span>|<span data-ttu-id="cb912-129">**Comment**</span><span class="sxs-lookup"><span data-stu-id="cb912-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb912-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cb912-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb912-131">TXT</span><span class="sxs-lookup"><span data-stu-id="cb912-131">TXT</span></span>  <br/> |<span data-ttu-id="cb912-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cb912-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cb912-133">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cb912-133">**Note:** This is an example.</span></span> <span data-ttu-id="cb912-134">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="cb912-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="cb912-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="cb912-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cb912-136">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-136">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="cb912-138">Seleccione **Agregar registro ahora.**</span><span class="sxs-lookup"><span data-stu-id="cb912-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="cb912-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="cb912-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cb912-141">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="cb912-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cb912-142">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="cb912-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cb912-143">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="cb912-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cb912-144">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="cb912-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cb912-145">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="cb912-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cb912-146">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="cb912-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cb912-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cb912-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cb912-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb912-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cb912-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cb912-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cb912-152">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb912-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb912-153">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="cb912-153">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb912-154">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cb912-154">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb912-156">En la página **Panel** , seleccione **correo** y, a continuación, **Custom mx**.</span><span class="sxs-lookup"><span data-stu-id="cb912-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="cb912-158">En la sección **administrar la entrega de correo** , en la columna **acciones** , seleccione **Editar** en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="cb912-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="cb912-160">En la sección **registro MX personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores siguientes de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb912-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="cb912-161">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="cb912-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb912-162">(Si hay otros registros MX, marque los registros que se van a eliminar).</span><span class="sxs-lookup"><span data-stu-id="cb912-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="cb912-163">**Registro MX (obligatorio)**</span><span class="sxs-lookup"><span data-stu-id="cb912-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="cb912-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cb912-165">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="cb912-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cb912-p108">El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="cb912-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cb912-168">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb912-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="cb912-169">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="cb912-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="cb912-171">Seleccione **cambiar este dominio para usar registros MX personalizados ahora.**</span><span class="sxs-lookup"><span data-stu-id="cb912-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="cb912-173">Si hay otros registros MX, elimine cada uno de ellos seleccionando la entrada y, después, presionando la tecla **suprimir** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="cb912-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="cb912-175">Si ha eliminado algún registro, seleccione **actualizar los registros MX personalizados ahora.**</span><span class="sxs-lookup"><span data-stu-id="cb912-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cb912-177">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb912-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cb912-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cb912-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cb912-179">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb912-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb912-180">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="cb912-180">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb912-181">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cb912-181">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb912-183">En la página **Panel** , seleccione **dominios** y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="cb912-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb912-185">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="cb912-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb912-187">En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb912-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cb912-188">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="cb912-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb912-189">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="cb912-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb912-190">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cb912-190">**Name**</span></span>|<span data-ttu-id="cb912-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="cb912-191">**Type**</span></span>|<span data-ttu-id="cb912-192">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cb912-192">**Value**</span></span>|<span data-ttu-id="cb912-193">**Comment**</span><span class="sxs-lookup"><span data-stu-id="cb912-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb912-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cb912-194">autodiscover</span></span>  <br/> |<span data-ttu-id="cb912-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb912-195">CNAME</span></span>  <br/> |<span data-ttu-id="cb912-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cb912-197">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="cb912-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-198">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb912-199">sip</span><span class="sxs-lookup"><span data-stu-id="cb912-199">sip</span></span>  <br/> |<span data-ttu-id="cb912-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb912-200">CNAME</span></span>  <br/> |<span data-ttu-id="cb912-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb912-202">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="cb912-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-203">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb912-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cb912-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cb912-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb912-205">CNAME</span></span>  <br/> |<span data-ttu-id="cb912-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb912-207">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="cb912-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-208">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb912-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cb912-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cb912-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb912-210">CNAME</span></span>  <br/> |<span data-ttu-id="cb912-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="cb912-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cb912-212">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="cb912-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-213">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb912-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cb912-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cb912-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb912-215">CNAME</span></span>  <br/> |<span data-ttu-id="cb912-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cb912-217">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="cb912-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-218">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-218">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="cb912-220">Seleccione **Agregar registro ahora.**</span><span class="sxs-lookup"><span data-stu-id="cb912-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="cb912-222">Con los dos pasos anteriores y los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="cb912-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cb912-223">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cb912-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cb912-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cb912-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb912-225">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="cb912-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cb912-226">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="cb912-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cb912-227">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb912-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cb912-228">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="cb912-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="cb912-229">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb912-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb912-230">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="cb912-230">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb912-231">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cb912-231">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb912-233">En la página **Panel** , seleccione **dominios** y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="cb912-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb912-235">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="cb912-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb912-237">En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb912-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cb912-238">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="cb912-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb912-239">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="cb912-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb912-240">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cb912-240">**Name**</span></span>|<span data-ttu-id="cb912-241">**Type**</span><span class="sxs-lookup"><span data-stu-id="cb912-241">**Type**</span></span>|<span data-ttu-id="cb912-242">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cb912-242">**Value**</span></span>|<span data-ttu-id="cb912-243">**Comment**</span><span class="sxs-lookup"><span data-stu-id="cb912-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb912-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cb912-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb912-245">TXT</span><span class="sxs-lookup"><span data-stu-id="cb912-245">TXT</span></span>  <br/> |<span data-ttu-id="cb912-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cb912-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cb912-247">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="cb912-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cb912-248">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-248">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="cb912-250">Seleccione **Agregar registro ahora.**</span><span class="sxs-lookup"><span data-stu-id="cb912-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="cb912-252">Con los dos pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cb912-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cb912-253">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb912-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cb912-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cb912-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cb912-255">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb912-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb912-256">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="cb912-256">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb912-257">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cb912-257">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb912-259">En la página **Panel** , seleccione **dominios** y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="cb912-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb912-261">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="cb912-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb912-263">En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb912-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cb912-264">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="cb912-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb912-265">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="cb912-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb912-266">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cb912-266">**Name**</span></span>|<span data-ttu-id="cb912-267">**Type**</span><span class="sxs-lookup"><span data-stu-id="cb912-267">**Type**</span></span>|<span data-ttu-id="cb912-268">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cb912-268">**Value**</span></span>|<span data-ttu-id="cb912-269">**Comment**</span><span class="sxs-lookup"><span data-stu-id="cb912-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb912-270">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="cb912-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="cb912-271">SRV</span><span class="sxs-lookup"><span data-stu-id="cb912-271">SRV</span></span>  <br/> |<span data-ttu-id="cb912-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="cb912-272">100 1 443</span></span>  <br/> <span data-ttu-id="cb912-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb912-274">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="cb912-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-275">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb912-276">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="cb912-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cb912-277">SRV</span><span class="sxs-lookup"><span data-stu-id="cb912-277">SRV</span></span>  <br/> |<span data-ttu-id="cb912-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="cb912-278">100 1 5061</span></span>  <br/> <span data-ttu-id="cb912-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cb912-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb912-280">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="cb912-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb912-281">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="cb912-281">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="cb912-283">Seleccione **Agregar registro ahora**.</span><span class="sxs-lookup"><span data-stu-id="cb912-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="cb912-285">Con los dos pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cb912-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="cb912-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cb912-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
