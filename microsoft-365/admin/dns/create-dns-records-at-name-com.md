---
title: Crear registros DNS en name.com para Office 365
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en name.com para Office 365.
ms.openlocfilehash: f21a40f543ff3a9faffe6ffba98f4d541b2a7a7b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349986"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="34a1c-103">Crear registros DNS en name.com para Office 365</span><span class="sxs-lookup"><span data-stu-id="34a1c-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="34a1c-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="34a1c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="34a1c-105">Si name.com es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="34a1c-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="34a1c-106">Después de agregar estos registros a name.com, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34a1c-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="34a1c-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="34a1c-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="34a1c-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="34a1c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="34a1c-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="34a1c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="34a1c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="34a1c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="34a1c-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34a1c-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="34a1c-p104">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="34a1c-120">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="34a1c-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="34a1c-122">En la columna **detalles** , seleccione \* \* registros DNS \* \*.</span><span class="sxs-lookup"><span data-stu-id="34a1c-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="34a1c-124">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34a1c-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="34a1c-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="34a1c-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34a1c-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34a1c-126">**Type**</span></span> <br/> |<span data-ttu-id="34a1c-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="34a1c-127">**Host**</span></span> <br/> |<span data-ttu-id="34a1c-128">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="34a1c-128">**Answer**</span></span> <br/> |<span data-ttu-id="34a1c-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34a1c-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="34a1c-130">TXT</span><span class="sxs-lookup"><span data-stu-id="34a1c-130">TXT</span></span>  <br/> |<span data-ttu-id="34a1c-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="34a1c-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="34a1c-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="34a1c-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="34a1c-133">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="34a1c-133">**Note:** This is an example.</span></span> <span data-ttu-id="34a1c-134">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34a1c-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="34a1c-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="34a1c-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="34a1c-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-136">Use the default value (300).</span></span>  <br/> |
   
    ![Nombre-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="34a1c-138">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="34a1c-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="34a1c-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="34a1c-141">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="34a1c-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="34a1c-142">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="34a1c-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="34a1c-143">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="34a1c-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="34a1c-144">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="34a1c-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="34a1c-145">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="34a1c-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="34a1c-146">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="34a1c-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="34a1c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="34a1c-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="34a1c-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="34a1c-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="34a1c-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="34a1c-p107">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="34a1c-155">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="34a1c-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="34a1c-157">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="34a1c-159">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34a1c-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="34a1c-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="34a1c-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="34a1c-161">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34a1c-161">**Type**</span></span>|<span data-ttu-id="34a1c-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="34a1c-162">**Host**</span></span>|<span data-ttu-id="34a1c-163">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="34a1c-163">**Answer**</span></span>|<span data-ttu-id="34a1c-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34a1c-164">**TTL**</span></span>|<span data-ttu-id="34a1c-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="34a1c-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34a1c-166">MX</span><span class="sxs-lookup"><span data-stu-id="34a1c-166">MX</span></span>  <br/> |<span data-ttu-id="34a1c-167">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="34a1c-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="34a1c-168">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="34a1c-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="34a1c-169">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34a1c-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="34a1c-170">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="34a1c-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="34a1c-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="34a1c-172">comprendi</span><span class="sxs-lookup"><span data-stu-id="34a1c-172">0</span></span>  <br/> <span data-ttu-id="34a1c-173">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="34a1c-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Nombre-BP-configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="34a1c-175">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="34a1c-177">Si existen otros registros MX, elimine cada uno de ellos usando el procedimiento de dos pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="34a1c-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="34a1c-178">Por cada registro MX, seleccione **eliminar** en la columna **acciones** .</span><span class="sxs-lookup"><span data-stu-id="34a1c-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="34a1c-180">Para confirmar cada eliminación, seleccione **eliminar** en la columna **acciones** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="34a1c-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="34a1c-182">Repita este procedimiento de dos pasos hasta que haya eliminado cada uno de los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="34a1c-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="34a1c-183">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="34a1c-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="34a1c-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="34a1c-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="34a1c-p109">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="34a1c-188">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="34a1c-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="34a1c-190">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="34a1c-192">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="34a1c-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="34a1c-193">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34a1c-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="34a1c-194">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="34a1c-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="34a1c-195">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34a1c-195">**Type**</span></span>|<span data-ttu-id="34a1c-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="34a1c-196">**Host**</span></span>|<span data-ttu-id="34a1c-197">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="34a1c-197">**Answer**</span></span>|<span data-ttu-id="34a1c-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34a1c-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34a1c-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="34a1c-199">CNAME</span></span>  <br/> |<span data-ttu-id="34a1c-200">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="34a1c-200">autodiscover</span></span>  <br/> |<span data-ttu-id="34a1c-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="34a1c-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="34a1c-202">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="34a1c-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="34a1c-203">CNAME</span></span>  <br/> |<span data-ttu-id="34a1c-204">sip</span><span class="sxs-lookup"><span data-stu-id="34a1c-204">sip</span></span>  <br/> |<span data-ttu-id="34a1c-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34a1c-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="34a1c-206">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="34a1c-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="34a1c-207">CNAME</span></span>  <br/> |<span data-ttu-id="34a1c-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="34a1c-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="34a1c-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34a1c-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="34a1c-210">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="34a1c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="34a1c-211">CNAME</span></span>  <br/> |<span data-ttu-id="34a1c-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="34a1c-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="34a1c-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="34a1c-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="34a1c-214">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="34a1c-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="34a1c-215">CNAME</span></span>  <br/> |<span data-ttu-id="34a1c-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="34a1c-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="34a1c-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="34a1c-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="34a1c-218">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-218">Use the default value (300).</span></span>  <br/> |
   
   ![Nombre-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="34a1c-220">Seleccione **Agregar registro** para agregar el primer registro.</span><span class="sxs-lookup"><span data-stu-id="34a1c-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="34a1c-222">Agregue el segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="34a1c-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="34a1c-223">Use los valores de la segunda fila de la tabla anterior y, después, seleccione **Agregar registro** para agregar el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="34a1c-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="34a1c-224">Agregue los registros restantes de la misma manera, usando los valores de la tercera, la cuarta, la quinta y la sexta fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="34a1c-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="34a1c-225">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="34a1c-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="34a1c-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="34a1c-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="34a1c-227">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="34a1c-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="34a1c-228">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="34a1c-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="34a1c-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="34a1c-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="34a1c-230">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="34a1c-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="34a1c-p111">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="34a1c-234">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="34a1c-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="34a1c-236">En la columna **detalles** , seleccione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="34a1c-238">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34a1c-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="34a1c-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="34a1c-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="34a1c-240">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34a1c-240">**Type**</span></span>|<span data-ttu-id="34a1c-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="34a1c-241">**Host**</span></span>|<span data-ttu-id="34a1c-242">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="34a1c-242">**Answer**</span></span>|<span data-ttu-id="34a1c-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34a1c-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34a1c-244">TXT</span><span class="sxs-lookup"><span data-stu-id="34a1c-244">TXT</span></span>  <br/> |<span data-ttu-id="34a1c-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="34a1c-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="34a1c-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="34a1c-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="34a1c-247">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="34a1c-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="34a1c-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-248">Use the default value (300).</span></span>  <br/> |
   
   ![Nombre-BP-configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="34a1c-250">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="34a1c-252">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="34a1c-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="34a1c-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="34a1c-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="34a1c-p112">Para empezar, vaya a su página de dominios en name.com a través de [este vínculo](https://www.name.com/account/domain). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="34a1c-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="34a1c-257">En **mis dominios**, seleccione el nombre del dominio que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="34a1c-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="34a1c-259">En la columna **detalles** , seleccione **registros DNS +**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="34a1c-261">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="34a1c-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="34a1c-262">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34a1c-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="34a1c-263">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="34a1c-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="34a1c-264">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34a1c-264">**Type**</span></span>|<span data-ttu-id="34a1c-265">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="34a1c-265">**Service**</span></span>|<span data-ttu-id="34a1c-266">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="34a1c-266">**Weight**</span></span>|<span data-ttu-id="34a1c-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34a1c-267">**TTL**</span></span>|<span data-ttu-id="34a1c-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="34a1c-268">**Prio**</span></span>|<span data-ttu-id="34a1c-269">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="34a1c-269">**Protocol**</span></span>|<span data-ttu-id="34a1c-270">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="34a1c-270">**Port**</span></span>|<span data-ttu-id="34a1c-271">**Destino**</span><span class="sxs-lookup"><span data-stu-id="34a1c-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34a1c-272">SRV</span><span class="sxs-lookup"><span data-stu-id="34a1c-272">SRV</span></span>|<span data-ttu-id="34a1c-273">sip</span><span class="sxs-lookup"><span data-stu-id="34a1c-273">sip</span></span>|<span data-ttu-id="34a1c-274">1</span><span class="sxs-lookup"><span data-stu-id="34a1c-274">1</span></span>|<span data-ttu-id="34a1c-275">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-275">Use the default value (300).</span></span>|<span data-ttu-id="34a1c-276">100</span><span class="sxs-lookup"><span data-stu-id="34a1c-276">100</span></span>|<span data-ttu-id="34a1c-277">tls</span><span class="sxs-lookup"><span data-stu-id="34a1c-277">tls</span></span>|<span data-ttu-id="34a1c-278">443</span><span class="sxs-lookup"><span data-stu-id="34a1c-278">443</span></span>|<span data-ttu-id="34a1c-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34a1c-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="34a1c-280">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="34a1c-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="34a1c-281">SRV</span><span class="sxs-lookup"><span data-stu-id="34a1c-281">SRV</span></span>|<span data-ttu-id="34a1c-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="34a1c-282">sipfederationtls</span></span>|<span data-ttu-id="34a1c-283">1</span><span class="sxs-lookup"><span data-stu-id="34a1c-283">1</span></span>|<span data-ttu-id="34a1c-284">Use el valor predeterminado (300).</span><span class="sxs-lookup"><span data-stu-id="34a1c-284">Use the default value (300).</span></span>|<span data-ttu-id="34a1c-285">100</span><span class="sxs-lookup"><span data-stu-id="34a1c-285">100</span></span>|<span data-ttu-id="34a1c-286">tcp</span><span class="sxs-lookup"><span data-stu-id="34a1c-286">tcp</span></span>|<span data-ttu-id="34a1c-287">5061</span><span class="sxs-lookup"><span data-stu-id="34a1c-287">5061</span></span>|<span data-ttu-id="34a1c-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34a1c-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="34a1c-289">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="34a1c-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Nombre-BP-configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="34a1c-291">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="34a1c-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="34a1c-293">Agregue el segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="34a1c-293">Add the second SRV record:</span></span>

<span data-ttu-id="34a1c-294">Use los valores de la siguiente fila de la tabla anterior y, a continuación, seleccione **Agregar registro** para agregar el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="34a1c-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="34a1c-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="34a1c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
