---
title: Crear registros DNS en name.com para Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en name.com para Microsoft.
ms.openlocfilehash: ce465e06b3bc18c824d741ee4cba4b9f4f410d90
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645892"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="62997-103">Crear registros DNS en name.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="62997-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="62997-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="62997-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="62997-105">Si name.com es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="62997-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="62997-106">Después de agregar estos registros a name.com, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62997-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="62997-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62997-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="62997-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="62997-110">Add a TXT record for verification</span></span>
<span data-ttu-id="62997-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="62997-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="62997-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="62997-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62997-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="62997-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="62997-p104">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="62997-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="62997-119">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="62997-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="62997-121">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="62997-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="62997-123">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="62997-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="62997-124">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="62997-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62997-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="62997-125">**Type**</span></span> <br/> |<span data-ttu-id="62997-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="62997-126">**Host**</span></span> <br/> |<span data-ttu-id="62997-127">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="62997-127">**Answer**</span></span> <br/> |<span data-ttu-id="62997-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62997-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="62997-129">TXT</span><span class="sxs-lookup"><span data-stu-id="62997-129">TXT</span></span>  <br/> |<span data-ttu-id="62997-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="62997-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="62997-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="62997-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="62997-132">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="62997-132">**Note:** This is an example.</span></span> <span data-ttu-id="62997-133">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="62997-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="62997-134">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="62997-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="62997-135">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-135">Use the default value (300).</span></span>  <br/> |
   
    ![Nombre-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="62997-137">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="62997-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="62997-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="62997-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="62997-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="62997-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="62997-141">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="62997-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="62997-142">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="62997-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="62997-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="62997-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="62997-144">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="62997-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="62997-145">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="62997-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="62997-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62997-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="62997-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="62997-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="62997-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="62997-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="62997-p107">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="62997-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="62997-154">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="62997-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="62997-156">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="62997-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="62997-158">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="62997-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="62997-159">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="62997-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62997-160">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="62997-160">**Type**</span></span>|<span data-ttu-id="62997-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="62997-161">**Host**</span></span>|<span data-ttu-id="62997-162">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="62997-162">**Answer**</span></span>|<span data-ttu-id="62997-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62997-163">**TTL**</span></span>|<span data-ttu-id="62997-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="62997-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62997-165">MX</span><span class="sxs-lookup"><span data-stu-id="62997-165">MX</span></span>  <br/> |<span data-ttu-id="62997-166">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="62997-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="62997-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="62997-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="62997-168">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62997-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="62997-169">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="62997-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="62997-170">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="62997-171">comprendi</span><span class="sxs-lookup"><span data-stu-id="62997-171">0</span></span>  <br/> <span data-ttu-id="62997-172">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="62997-172">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Nombre-BP-configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="62997-174">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="62997-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="62997-176">Si existen otros registros MX, elimine cada uno de ellos usando el procedimiento de dos pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="62997-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="62997-177">Por cada registro MX, seleccione **eliminar** en la columna **acciones** .</span><span class="sxs-lookup"><span data-stu-id="62997-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="62997-179">Para confirmar cada eliminación, seleccione **eliminar** en la columna **acciones** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="62997-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="62997-181">Repita este procedimiento de dos pasos hasta que haya eliminado cada uno de los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="62997-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="62997-182">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="62997-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="62997-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="62997-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="62997-p109">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="62997-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="62997-187">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="62997-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="62997-189">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="62997-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="62997-191">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="62997-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="62997-192">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="62997-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="62997-193">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="62997-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62997-194">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="62997-194">**Type**</span></span>|<span data-ttu-id="62997-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="62997-195">**Host**</span></span>|<span data-ttu-id="62997-196">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="62997-196">**Answer**</span></span>|<span data-ttu-id="62997-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62997-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62997-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="62997-198">CNAME</span></span>  <br/> |<span data-ttu-id="62997-199">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="62997-199">autodiscover</span></span>  <br/> |<span data-ttu-id="62997-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="62997-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="62997-201">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="62997-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="62997-202">CNAME</span></span>  <br/> |<span data-ttu-id="62997-203">sip</span><span class="sxs-lookup"><span data-stu-id="62997-203">sip</span></span>  <br/> |<span data-ttu-id="62997-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="62997-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="62997-205">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="62997-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="62997-206">CNAME</span></span>  <br/> |<span data-ttu-id="62997-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="62997-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="62997-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="62997-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="62997-209">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="62997-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="62997-210">CNAME</span></span>  <br/> |<span data-ttu-id="62997-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="62997-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="62997-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="62997-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="62997-213">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="62997-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="62997-214">CNAME</span></span>  <br/> |<span data-ttu-id="62997-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="62997-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="62997-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="62997-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="62997-217">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-217">Use the default value (300).</span></span>  <br/> |
   
   ![Nombre-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="62997-219">Seleccione **Agregar registro** para agregar el primer registro.</span><span class="sxs-lookup"><span data-stu-id="62997-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="62997-221">Agregue el segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="62997-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="62997-222">Use los valores de la segunda fila de la tabla anterior y, después, seleccione **Agregar registro** para agregar el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="62997-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="62997-223">Agregue los registros restantes de la misma manera, usando los valores de la tercera, la cuarta, la quinta y la sexta fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="62997-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="62997-224">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="62997-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="62997-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="62997-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="62997-226">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="62997-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="62997-227">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="62997-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="62997-228">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62997-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="62997-229">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="62997-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="62997-p111">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="62997-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="62997-233">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="62997-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="62997-235">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="62997-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="62997-237">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="62997-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="62997-238">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="62997-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62997-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="62997-239">**Type**</span></span>|<span data-ttu-id="62997-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="62997-240">**Host**</span></span>|<span data-ttu-id="62997-241">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="62997-241">**Answer**</span></span>|<span data-ttu-id="62997-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62997-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62997-243">TXT</span><span class="sxs-lookup"><span data-stu-id="62997-243">TXT</span></span>  <br/> |<span data-ttu-id="62997-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="62997-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="62997-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="62997-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="62997-246">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="62997-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="62997-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="62997-247">Use the default value (300).</span></span>  <br/> |
   
   ![Nombre-BP-configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="62997-249">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="62997-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="62997-251">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="62997-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="62997-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="62997-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="62997-p112">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="62997-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="62997-256">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="62997-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="62997-258">En la columna **detalles** , seleccione **registros DNS +**.</span><span class="sxs-lookup"><span data-stu-id="62997-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="62997-260">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="62997-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="62997-261">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="62997-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="62997-262">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="62997-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62997-263">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="62997-263">**Type**</span></span>|<span data-ttu-id="62997-264">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="62997-264">**Service**</span></span>|<span data-ttu-id="62997-265">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="62997-265">**Weight**</span></span>|<span data-ttu-id="62997-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62997-266">**TTL**</span></span>|<span data-ttu-id="62997-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="62997-267">**Prio**</span></span>|<span data-ttu-id="62997-268">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="62997-268">**Protocol**</span></span>|<span data-ttu-id="62997-269">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="62997-269">**Port**</span></span>|<span data-ttu-id="62997-270">**Destino**</span><span class="sxs-lookup"><span data-stu-id="62997-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62997-271">SRV</span><span class="sxs-lookup"><span data-stu-id="62997-271">SRV</span></span>|<span data-ttu-id="62997-272">sip</span><span class="sxs-lookup"><span data-stu-id="62997-272">sip</span></span>|<span data-ttu-id="62997-273">1</span><span class="sxs-lookup"><span data-stu-id="62997-273">1</span></span>|<span data-ttu-id="62997-274">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-274">Use the default value (300).</span></span>|<span data-ttu-id="62997-275">100</span><span class="sxs-lookup"><span data-stu-id="62997-275">100</span></span>|<span data-ttu-id="62997-276">tls</span><span class="sxs-lookup"><span data-stu-id="62997-276">tls</span></span>|<span data-ttu-id="62997-277">443</span><span class="sxs-lookup"><span data-stu-id="62997-277">443</span></span>|<span data-ttu-id="62997-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="62997-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="62997-279">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="62997-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="62997-280">SRV</span><span class="sxs-lookup"><span data-stu-id="62997-280">SRV</span></span>|<span data-ttu-id="62997-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="62997-281">sipfederationtls</span></span>|<span data-ttu-id="62997-282">1</span><span class="sxs-lookup"><span data-stu-id="62997-282">1</span></span>|<span data-ttu-id="62997-283">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="62997-283">Use the default value (300).</span></span>|<span data-ttu-id="62997-284">100</span><span class="sxs-lookup"><span data-stu-id="62997-284">100</span></span>|<span data-ttu-id="62997-285">tcp</span><span class="sxs-lookup"><span data-stu-id="62997-285">tcp</span></span>|<span data-ttu-id="62997-286">5061</span><span class="sxs-lookup"><span data-stu-id="62997-286">5061</span></span>|<span data-ttu-id="62997-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="62997-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="62997-288">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="62997-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Nombre-BP-configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="62997-290">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="62997-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="62997-292">Agregue el segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="62997-292">Add the second SRV record:</span></span>

<span data-ttu-id="62997-293">Use los valores de la siguiente fila de la tabla anterior y, a continuación, seleccione **Agregar registro** para agregar el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="62997-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="62997-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62997-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
