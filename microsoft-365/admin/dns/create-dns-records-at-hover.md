---
title: Crear registros DNS en hover para Microsoft
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios al pasar el mouse por Microsoft.
ms.openlocfilehash: 4779b8f6fadcd4b134d3954d2c6c133da40c19e6
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048992"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="2b069-103">Crear registros DNS en hover para Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b069-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="2b069-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="2b069-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2b069-105">Si Hover es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="2b069-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="2b069-106">Después de agregar estos registros al pasar el mouse, el dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b069-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="2b069-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b069-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2b069-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="2b069-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2b069-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2b069-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2b069-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="2b069-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b069-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="2b069-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="2b069-116">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2b069-116">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2b069-p104">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2b069-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2b069-120">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b069-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2b069-122">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2b069-122">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2b069-124">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2b069-124">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2b069-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2b069-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="2b069-127">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="2b069-127">Hostname</span></span>  <br/> |<span data-ttu-id="2b069-128">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="2b069-128">Record Type</span></span>  <br/> |<span data-ttu-id="2b069-129">Valor</span><span class="sxs-lookup"><span data-stu-id="2b069-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="2b069-130">TXT</span><span class="sxs-lookup"><span data-stu-id="2b069-130">TXT</span></span>  <br/> |<span data-ttu-id="2b069-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2b069-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2b069-132">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2b069-132">**Note:** This is an example.</span></span> <span data-ttu-id="2b069-133">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="2b069-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="2b069-134">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="2b069-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="2b069-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-136">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="2b069-138">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="2b069-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2b069-139">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="2b069-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="2b069-140">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="2b069-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2b069-141">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="2b069-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2b069-142">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="2b069-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2b069-143">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="2b069-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2b069-144">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2b069-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b069-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2b069-148">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b069-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2b069-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2b069-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2b069-150">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2b069-150">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2b069-p107">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2b069-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2b069-154">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b069-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2b069-156">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2b069-156">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2b069-158">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2b069-158">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2b069-160">En los cuadros para el nuevo registro, seleccione **MX** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b069-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2b069-161">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="2b069-161">**Hostname**</span></span>|<span data-ttu-id="2b069-162">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="2b069-162">**Record Type**</span></span>|<span data-ttu-id="2b069-163">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="2b069-163">**Priority**</span></span>|<span data-ttu-id="2b069-164">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="2b069-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2b069-165">MX</span><span class="sxs-lookup"><span data-stu-id="2b069-165">MX</span></span>  <br/> |<span data-ttu-id="2b069-166">comprendi</span><span class="sxs-lookup"><span data-stu-id="2b069-166">0</span></span>  <br/> <span data-ttu-id="2b069-167">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="2b069-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="2b069-168">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="2b069-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2b069-169">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b069-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2b069-170">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="2b069-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="2b069-172">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-172">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="2b069-174">Si existen otros registros MX, quite cada uno de ellos usando el procedimiento de dos pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b069-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="2b069-175">En primer lugar, mueva sobre un registro que quiera quitar, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Pase el mouse y seleccione eliminar](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="2b069-177">En segundo lugar, seleccione **sí** para confirmar cada eliminación.</span><span class="sxs-lookup"><span data-stu-id="2b069-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Seleccione Sí para confirmar la eliminación.](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="2b069-179">Repita este proceso hasta que haya eliminado todos los registros MX excepto el que haya agregado anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2b069-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2b069-180">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b069-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2b069-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2b069-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2b069-182">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2b069-182">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2b069-p109">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2b069-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2b069-186">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b069-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2b069-188">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2b069-188">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2b069-190">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b069-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="2b069-191">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2b069-191">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2b069-193">En los cuadros vacíos para el nuevo registro, seleccione **CNAME** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b069-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="2b069-194">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="2b069-194">**Hostname**</span></span>|<span data-ttu-id="2b069-195">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="2b069-195">**Record Type**</span></span>|<span data-ttu-id="2b069-196">**Host de destino**</span><span class="sxs-lookup"><span data-stu-id="2b069-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2b069-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2b069-197">autodiscover</span></span>  <br/> |<span data-ttu-id="2b069-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b069-198">CNAME</span></span>  <br/> |<span data-ttu-id="2b069-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2b069-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="2b069-200">sip</span><span class="sxs-lookup"><span data-stu-id="2b069-200">sip</span></span>  <br/> |<span data-ttu-id="2b069-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b069-201">CNAME</span></span>  <br/> |<span data-ttu-id="2b069-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2b069-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2b069-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2b069-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2b069-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b069-204">CNAME</span></span>  <br/> |<span data-ttu-id="2b069-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2b069-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2b069-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2b069-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2b069-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b069-207">CNAME</span></span>  <br/> |<span data-ttu-id="2b069-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2b069-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="2b069-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2b069-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2b069-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b069-210">CNAME</span></span>  <br/> |<span data-ttu-id="2b069-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2b069-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="2b069-213">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-213">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="2b069-215">Con los tres pasos anteriores y con los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b069-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2b069-216">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="2b069-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2b069-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2b069-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b069-218">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="2b069-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2b069-219">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="2b069-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2b069-220">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b069-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2b069-221">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="2b069-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="2b069-222">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2b069-222">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2b069-p111">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2b069-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2b069-226">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b069-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2b069-228">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2b069-228">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2b069-230">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2b069-230">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2b069-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2b069-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2b069-233">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="2b069-233">**Hostname**</span></span>|<span data-ttu-id="2b069-234">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="2b069-234">**Record Type**</span></span>|<span data-ttu-id="2b069-235">**Valor**</span><span class="sxs-lookup"><span data-stu-id="2b069-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2b069-236">TXT</span><span class="sxs-lookup"><span data-stu-id="2b069-236">TXT</span></span>  <br/> |<span data-ttu-id="2b069-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2b069-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="2b069-238">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="2b069-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="2b069-240">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-240">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2b069-242">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b069-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2b069-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2b069-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2b069-244">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2b069-244">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2b069-p112">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2b069-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2b069-248">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b069-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2b069-250">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2b069-250">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2b069-252">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="2b069-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="2b069-253">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2b069-253">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2b069-255">En los cuadros vacíos para el nuevo registro, seleccione **SRV** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b069-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="2b069-256">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="2b069-256">**Hostname**</span></span>|<span data-ttu-id="2b069-257">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="2b069-257">**Record Type**</span></span>|<span data-ttu-id="2b069-258">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="2b069-258">**Priority**</span></span>|<span data-ttu-id="2b069-259">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="2b069-259">**Weight**</span></span>|<span data-ttu-id="2b069-260">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="2b069-260">**Port**</span></span>|<span data-ttu-id="2b069-261">**Destino**</span><span class="sxs-lookup"><span data-stu-id="2b069-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2b069-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="2b069-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="2b069-263">SRV</span><span class="sxs-lookup"><span data-stu-id="2b069-263">SRV</span></span>  <br/> |<span data-ttu-id="2b069-264">100</span><span class="sxs-lookup"><span data-stu-id="2b069-264">100</span></span>  <br/> |<span data-ttu-id="2b069-265">1</span><span class="sxs-lookup"><span data-stu-id="2b069-265">1</span></span>  <br/> |<span data-ttu-id="2b069-266">443</span><span class="sxs-lookup"><span data-stu-id="2b069-266">443</span></span>  <br/> |<span data-ttu-id="2b069-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2b069-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2b069-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="2b069-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2b069-269">SRV</span><span class="sxs-lookup"><span data-stu-id="2b069-269">SRV</span></span>  <br/> |<span data-ttu-id="2b069-270">100</span><span class="sxs-lookup"><span data-stu-id="2b069-270">100</span></span>  <br/> |<span data-ttu-id="2b069-271">1</span><span class="sxs-lookup"><span data-stu-id="2b069-271">1</span></span>  <br/> |<span data-ttu-id="2b069-272">5061</span><span class="sxs-lookup"><span data-stu-id="2b069-272">5061</span></span>  <br/> |<span data-ttu-id="2b069-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2b069-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="2b069-275">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b069-275">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="2b069-277">Con los tres pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="2b069-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b069-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b069-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
