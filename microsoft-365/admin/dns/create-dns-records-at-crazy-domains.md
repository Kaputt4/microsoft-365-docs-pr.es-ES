---
title: Crear registros DNS en Crazy Domains para Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Crazy Domains for Microsoft.
ms.openlocfilehash: 4b39a51f96299879207b96d1e15d039905440b0a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658500"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="9ac6f-103">Crear registros DNS en Crazy Domains para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ac6f-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="9ac6f-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9ac6f-105">Si Crazy Domains es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9ac6f-106">Después de agregar estos registros a Crazy Domains, su dominio estará configurado para trabajar con los servicios Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="9ac6f-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9ac6f-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="9ac6f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="9ac6f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9ac6f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9ac6f-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ac6f-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9ac6f-p104">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9ac6f-119">En la **sección Mi cuenta,** seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9ac6f-121">En la **página Nombres de** dominio, en la sección **Dominio,** seleccione el nombre del dominio que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9ac6f-123">En la **sección Configuración** dns, seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9ac6f-125">Seleccione **Agregar registro.**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9ac6f-127">Elija **Registro TXT** en la lista desplegable **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="9ac6f-129">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="9ac6f-131">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9ac6f-132">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-132">**Sub Domain**</span></span>|<span data-ttu-id="9ac6f-133">**Registro de texto**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9ac6f-134">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9ac6f-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9ac6f-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9ac6f-136">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-136">**Note:** This is an example.</span></span> <span data-ttu-id="9ac6f-137">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9ac6f-138">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9ac6f-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="9ac6f-140">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="9ac6f-142">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9ac6f-143">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9ac6f-144">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9ac6f-145">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9ac6f-146">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9ac6f-147">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9ac6f-148">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9ac6f-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9ac6f-152">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ac6f-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9ac6f-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9ac6f-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9ac6f-p107">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9ac6f-157">En la **sección Mi cuenta,** seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9ac6f-159">En la **página Nombres de** dominio, en la sección **Dominio,** seleccione el nombre del dominio que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9ac6f-161">En la **sección Configuración** dns, seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9ac6f-163">Seleccione **Agregar registro.**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9ac6f-165">Elija **Registro MX** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="9ac6f-167">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="9ac6f-169">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="9ac6f-170">(Elija el **valor prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9ac6f-171">**Correo por zona**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-171">**Mail For Zone**</span></span>|<span data-ttu-id="9ac6f-172">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-172">**Priority**</span></span>|<span data-ttu-id="9ac6f-173">**Asignado a un servidor**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9ac6f-174">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9ac6f-175">1 </span><span class="sxs-lookup"><span data-stu-id="9ac6f-175">1</span></span>  <br/> <span data-ttu-id="9ac6f-176">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="9ac6f-176">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="9ac6f-177">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9ac6f-178">**Nota:** Obtenga su  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="9ac6f-179">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9ac6f-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="9ac6f-181">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="9ac6f-183">Si hay otros registros MX enumerados en la sección Registro **MX,** seleccione Modificar **para** uno de esos registros.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="9ac6f-185">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="9ac6f-187">Seleccione **Actualizar** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="9ac6f-189">Use el mismo proceso para quitar cualquier otro registro MX de la lista, hasta que solo quede el que ha agregado anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9ac6f-190">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ac6f-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9ac6f-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9ac6f-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9ac6f-p109">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9ac6f-195">En la **sección Mi cuenta,** seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9ac6f-197">En la **página Nombres de** dominio, en la sección **Dominio,** seleccione el nombre del dominio que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9ac6f-199">En la **sección Configuración** dns, seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9ac6f-201">Seleccione **Agregar registro.**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9ac6f-203">Elija **Registro CNAME** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="9ac6f-205">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="9ac6f-207">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9ac6f-208">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9ac6f-209">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-209">**Sub Domain**</span></span>|<span data-ttu-id="9ac6f-210">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9ac6f-211">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="9ac6f-211">autodiscover</span></span>  <br/> |<span data-ttu-id="9ac6f-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9ac6f-213">sip</span><span class="sxs-lookup"><span data-stu-id="9ac6f-213">sip</span></span>  <br/> |<span data-ttu-id="9ac6f-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9ac6f-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9ac6f-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9ac6f-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9ac6f-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9ac6f-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9ac6f-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9ac6f-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9ac6f-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9ac6f-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9ac6f-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="9ac6f-222">Seleccione **Agregar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="9ac6f-224">Agregue el segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="9ac6f-225">En los cuadros para el nuevo registro, use los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **Agregar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="9ac6f-226">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="9ac6f-227">Seleccione **Actualizar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9ac6f-229">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="9ac6f-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9ac6f-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9ac6f-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ac6f-231">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9ac6f-232">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9ac6f-233">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9ac6f-234">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *de*  SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9ac6f-p111">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9ac6f-238">En la **sección Mi cuenta,** seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9ac6f-240">En la **página Nombres de** dominio, en la sección **Dominio,** seleccione el nombre del dominio que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9ac6f-242">En la **sección Configuración** dns, seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9ac6f-244">Seleccione **Agregar registro.**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9ac6f-246">Elija **Registro TXT** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="9ac6f-248">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="9ac6f-250">En los cuadros para el nuevo registro, escriba o pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9ac6f-251">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-251">**Sub Domain**</span></span>|<span data-ttu-id="9ac6f-252">**Registro de texto**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9ac6f-253">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9ac6f-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9ac6f-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9ac6f-255">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="9ac6f-257">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9ac6f-259">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ac6f-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9ac6f-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9ac6f-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9ac6f-p112">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9ac6f-264">En la **sección Mi cuenta,** seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9ac6f-266">En la **página Nombres de** dominio, en la sección **Dominio,** seleccione el nombre del dominio que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9ac6f-268">En la **sección Configuración** dns, seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9ac6f-270">Seleccione **Agregar registro.**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9ac6f-272">Elija **Registro SRV** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="9ac6f-274">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="9ac6f-276">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9ac6f-277">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9ac6f-278">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-278">**Record Type**</span></span>|<span data-ttu-id="9ac6f-279">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-279">**Sub Domain**</span></span>|<span data-ttu-id="9ac6f-280">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-280">**Priority**</span></span>|<span data-ttu-id="9ac6f-281">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-281">**Weight**</span></span>|<span data-ttu-id="9ac6f-282">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-282">**Port**</span></span>|<span data-ttu-id="9ac6f-283">**Destino**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9ac6f-284">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="9ac6f-284">SRV Record</span></span>  <br/> |<span data-ttu-id="9ac6f-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9ac6f-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="9ac6f-286">100</span><span class="sxs-lookup"><span data-stu-id="9ac6f-286">100</span></span>  <br/> |<span data-ttu-id="9ac6f-287">1 </span><span class="sxs-lookup"><span data-stu-id="9ac6f-287">1</span></span>  <br/> |<span data-ttu-id="9ac6f-288">443</span><span class="sxs-lookup"><span data-stu-id="9ac6f-288">443</span></span>  <br/> |<span data-ttu-id="9ac6f-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9ac6f-290">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="9ac6f-290">SRV Record</span></span>  <br/> |<span data-ttu-id="9ac6f-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9ac6f-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9ac6f-292">100</span><span class="sxs-lookup"><span data-stu-id="9ac6f-292">100</span></span>  <br/> |<span data-ttu-id="9ac6f-293">1 </span><span class="sxs-lookup"><span data-stu-id="9ac6f-293">1</span></span>  <br/> |<span data-ttu-id="9ac6f-294">5061</span><span class="sxs-lookup"><span data-stu-id="9ac6f-294">5061</span></span>  <br/> |<span data-ttu-id="9ac6f-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9ac6f-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="9ac6f-297">Seleccione **Agregar registro SRV.**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="9ac6f-299">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="9ac6f-300">En los cuadros del nuevo registro, use los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="9ac6f-301">Seleccione **Actualizar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="9ac6f-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
