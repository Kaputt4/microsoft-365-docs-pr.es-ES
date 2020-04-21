---
title: Crear registros DNS en dominios locos para Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Aprenda a comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en dominios locos para Microsoft.
ms.openlocfilehash: db8979d303e4749a2a04870d277b68e5aec2e52f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629700"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="a7051-103">Crear registros DNS en dominios locos para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7051-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="a7051-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="a7051-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7051-105">Si Crazy Domains es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="a7051-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a7051-106">Después de agregar estos registros a otros dominios, el dominio estará configurado para trabajar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7051-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="a7051-107">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a7051-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7051-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7051-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7051-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="a7051-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a7051-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a7051-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a7051-113">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="a7051-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a7051-114">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a7051-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7051-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="a7051-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a7051-p104">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a7051-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a7051-120">En la sección **mi cuenta** , seleccione **dominios**.</span><span class="sxs-lookup"><span data-stu-id="a7051-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a7051-122">En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7051-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a7051-124">En la sección **configuración DNS** , seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a7051-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a7051-126">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="a7051-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a7051-128">Elija **Registro TXT** en la lista desplegable **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="a7051-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="a7051-130">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="a7051-132">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7051-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a7051-133">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="a7051-133">**Sub Domain**</span></span>|<span data-ttu-id="a7051-134">**Registro de texto**</span><span class="sxs-lookup"><span data-stu-id="a7051-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a7051-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a7051-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a7051-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a7051-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a7051-137">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7051-137">**Note:** This is an example.</span></span> <span data-ttu-id="a7051-138">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a7051-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a7051-139">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="a7051-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="a7051-141">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="a7051-143">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="a7051-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7051-144">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.</span><span class="sxs-lookup"><span data-stu-id="a7051-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a7051-145">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="a7051-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7051-146">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="a7051-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a7051-147">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="a7051-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a7051-148">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="a7051-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a7051-149">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a7051-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7051-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a7051-153">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7051-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a7051-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a7051-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a7051-p107">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a7051-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a7051-158">En la sección **mi cuenta** , seleccione **dominios**.</span><span class="sxs-lookup"><span data-stu-id="a7051-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a7051-160">En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7051-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a7051-162">En la sección **configuración DNS** , seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a7051-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a7051-164">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="a7051-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a7051-166">Elija **Registro MX** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="a7051-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="a7051-168">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="a7051-170">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7051-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a7051-171">(Elija el valor **prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="a7051-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a7051-172">**Correo por zona**</span><span class="sxs-lookup"><span data-stu-id="a7051-172">**Mail For Zone**</span></span>|<span data-ttu-id="a7051-173">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a7051-173">**Priority**</span></span>|<span data-ttu-id="a7051-174">**Asignado a un servidor**</span><span class="sxs-lookup"><span data-stu-id="a7051-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a7051-175">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="a7051-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a7051-176">1</span><span class="sxs-lookup"><span data-stu-id="a7051-176">1</span></span>  <br/> <span data-ttu-id="a7051-177">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7051-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a7051-178">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="a7051-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a7051-179">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7051-179">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="a7051-180">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="a7051-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="a7051-182">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="a7051-184">Si hay otros registros MX enumerados en la sección **registro MX** , seleccione **modificar** para uno de esos registros.</span><span class="sxs-lookup"><span data-stu-id="a7051-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="a7051-186">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="a7051-188">Seleccione **Actualizar** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a7051-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="a7051-190">Use el mismo proceso para quitar cualquier otro registro MX de la lista, hasta que solo quede el que ha agregado anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a7051-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7051-191">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7051-191">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a7051-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a7051-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a7051-p109">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a7051-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a7051-196">En la sección **mi cuenta** , seleccione **dominios**.</span><span class="sxs-lookup"><span data-stu-id="a7051-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a7051-198">En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7051-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a7051-200">En la sección **configuración DNS** , seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a7051-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a7051-202">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="a7051-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a7051-204">Elija **Registro CNAME** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="a7051-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="a7051-206">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="a7051-208">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="a7051-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a7051-209">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7051-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="a7051-210">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="a7051-210">**Sub Domain**</span></span>|<span data-ttu-id="a7051-211">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="a7051-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a7051-212">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="a7051-212">autodiscover</span></span>  <br/> |<span data-ttu-id="a7051-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7051-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a7051-214">sip</span><span class="sxs-lookup"><span data-stu-id="a7051-214">sip</span></span>  <br/> |<span data-ttu-id="a7051-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7051-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7051-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a7051-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a7051-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7051-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7051-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a7051-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a7051-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a7051-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a7051-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a7051-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a7051-221">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7051-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="a7051-223">Seleccione **Agregar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="a7051-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="a7051-225">Agregue el segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="a7051-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="a7051-226">En los cuadros para el nuevo registro, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="a7051-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="a7051-227">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="a7051-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="a7051-228">Seleccione **Actualizar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a7051-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7051-230">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a7051-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7051-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a7051-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7051-232">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="a7051-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a7051-233">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a7051-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a7051-234">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7051-234">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a7051-235">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a7051-235">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a7051-p111">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a7051-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a7051-239">En la sección **mi cuenta** , seleccione **dominios**.</span><span class="sxs-lookup"><span data-stu-id="a7051-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a7051-241">En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7051-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a7051-243">En la sección **configuración DNS** , seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a7051-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a7051-245">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="a7051-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a7051-247">Elija **Registro TXT** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="a7051-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="a7051-249">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="a7051-251">En los cuadros para el nuevo registro, escriba o pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7051-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a7051-252">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="a7051-252">**Sub Domain**</span></span>|<span data-ttu-id="a7051-253">**Registro de texto**</span><span class="sxs-lookup"><span data-stu-id="a7051-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a7051-254">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="a7051-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a7051-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7051-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a7051-256">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="a7051-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="a7051-258">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7051-260">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7051-260">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a7051-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a7051-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a7051-p112">Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a7051-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a7051-265">En la sección **mi cuenta** , seleccione **dominios**.</span><span class="sxs-lookup"><span data-stu-id="a7051-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a7051-267">En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7051-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a7051-269">En la sección **configuración DNS** , seleccione el icono de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a7051-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a7051-271">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="a7051-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a7051-273">Elija **Registro SRV** en la lista desplegable **Agregar registro:**.</span><span class="sxs-lookup"><span data-stu-id="a7051-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="a7051-275">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="a7051-277">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="a7051-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a7051-278">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7051-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="a7051-279">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="a7051-279">**Record Type**</span></span>|<span data-ttu-id="a7051-280">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="a7051-280">**Sub Domain**</span></span>|<span data-ttu-id="a7051-281">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a7051-281">**Priority**</span></span>|<span data-ttu-id="a7051-282">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="a7051-282">**Weight**</span></span>|<span data-ttu-id="a7051-283">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="a7051-283">**Port**</span></span>|<span data-ttu-id="a7051-284">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a7051-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7051-285">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="a7051-285">SRV Record</span></span>  <br/> |<span data-ttu-id="a7051-286">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="a7051-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="a7051-287">100</span><span class="sxs-lookup"><span data-stu-id="a7051-287">100</span></span>  <br/> |<span data-ttu-id="a7051-288">1</span><span class="sxs-lookup"><span data-stu-id="a7051-288">1</span></span>  <br/> |<span data-ttu-id="a7051-289">443</span><span class="sxs-lookup"><span data-stu-id="a7051-289">443</span></span>  <br/> |<span data-ttu-id="a7051-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7051-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7051-291">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="a7051-291">SRV Record</span></span>  <br/> |<span data-ttu-id="a7051-292">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="a7051-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a7051-293">100</span><span class="sxs-lookup"><span data-stu-id="a7051-293">100</span></span>  <br/> |<span data-ttu-id="a7051-294">1</span><span class="sxs-lookup"><span data-stu-id="a7051-294">1</span></span>  <br/> |<span data-ttu-id="a7051-295">5061</span><span class="sxs-lookup"><span data-stu-id="a7051-295">5061</span></span>  <br/> |<span data-ttu-id="a7051-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7051-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="a7051-298">Seleccione **Agregar registro SRV**.</span><span class="sxs-lookup"><span data-stu-id="a7051-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="a7051-300">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="a7051-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a7051-301">En los cuadros del nuevo registro, use los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a7051-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="a7051-302">Seleccione **Actualizar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a7051-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="a7051-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7051-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
