---
title: Crear registros DNS en Hover para Office 365
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Aprenda a comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios al pasar el mouse para Office 365.
ms.openlocfilehash: 72df2d98f3446087a1e9796cd616293a91003ad9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350111"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="fe177-103">Crear registros DNS en Hover para Office 365</span><span class="sxs-lookup"><span data-stu-id="fe177-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="fe177-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="fe177-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fe177-105">Si Hover es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="fe177-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="fe177-106">Después de agregar estos registros a Hover, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe177-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="fe177-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="fe177-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="fe177-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fe177-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fe177-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="fe177-111">Add a TXT record for verification</span></span>
<span data-ttu-id="fe177-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fe177-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fe177-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="fe177-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe177-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="fe177-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="fe177-117">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fe177-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe177-p104">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fe177-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fe177-121">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fe177-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fe177-123">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="fe177-123">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fe177-125">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe177-125">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fe177-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fe177-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="fe177-128">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="fe177-128">Hostname</span></span>  <br/> |<span data-ttu-id="fe177-129">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="fe177-129">Record Type</span></span>  <br/> |<span data-ttu-id="fe177-130">Valor</span><span class="sxs-lookup"><span data-stu-id="fe177-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="fe177-131">TXT</span><span class="sxs-lookup"><span data-stu-id="fe177-131">TXT</span></span>  <br/> |<span data-ttu-id="fe177-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fe177-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fe177-133">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe177-133">**Note:** This is an example.</span></span> <span data-ttu-id="fe177-134">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe177-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="fe177-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="fe177-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="fe177-137">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-137">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="fe177-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="fe177-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fe177-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="fe177-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="fe177-141">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="fe177-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fe177-142">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="fe177-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fe177-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="fe177-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fe177-144">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="fe177-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fe177-145">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fe177-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fe177-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="fe177-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="fe177-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="fe177-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fe177-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="fe177-151">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fe177-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe177-p107">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fe177-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fe177-155">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fe177-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fe177-157">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="fe177-157">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fe177-159">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe177-159">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fe177-161">En los cuadros para el nuevo registro, seleccione **MX** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fe177-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fe177-162">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="fe177-162">**Hostname**</span></span>|<span data-ttu-id="fe177-163">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="fe177-163">**Record Type**</span></span>|<span data-ttu-id="fe177-164">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="fe177-164">**Priority**</span></span>|<span data-ttu-id="fe177-165">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="fe177-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fe177-166">MX</span><span class="sxs-lookup"><span data-stu-id="fe177-166">MX</span></span>  <br/> |<span data-ttu-id="fe177-167">comprendi</span><span class="sxs-lookup"><span data-stu-id="fe177-167">0</span></span>  <br/> <span data-ttu-id="fe177-168">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe177-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="fe177-169">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="fe177-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="fe177-170">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe177-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="fe177-171">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="fe177-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="fe177-173">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-173">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="fe177-175">Si existen otros registros MX, quite cada uno de ellos usando el procedimiento de dos pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe177-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="fe177-176">En primer lugar, mueva sobre un registro que quiera quitar, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Pase el mouse y seleccione eliminar](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="fe177-178">En segundo lugar, seleccione **sí** para confirmar cada eliminación.</span><span class="sxs-lookup"><span data-stu-id="fe177-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Seleccione Sí para confirmar la eliminación.](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="fe177-180">Repita este proceso hasta que haya eliminado todos los registros MX excepto el que haya agregado anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fe177-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="fe177-181">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="fe177-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="fe177-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fe177-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="fe177-183">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fe177-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe177-p109">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fe177-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fe177-187">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fe177-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fe177-189">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="fe177-189">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fe177-191">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="fe177-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="fe177-192">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe177-192">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fe177-194">En los cuadros vacíos para el nuevo registro, seleccione **CNAME** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fe177-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="fe177-195">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="fe177-195">**Hostname**</span></span>|<span data-ttu-id="fe177-196">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="fe177-196">**Record Type**</span></span>|<span data-ttu-id="fe177-197">**Host de destino**</span><span class="sxs-lookup"><span data-stu-id="fe177-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fe177-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fe177-198">autodiscover</span></span>  <br/> |<span data-ttu-id="fe177-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="fe177-199">CNAME</span></span>  <br/> |<span data-ttu-id="fe177-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fe177-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="fe177-201">sip</span><span class="sxs-lookup"><span data-stu-id="fe177-201">sip</span></span>  <br/> |<span data-ttu-id="fe177-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="fe177-202">CNAME</span></span>  <br/> |<span data-ttu-id="fe177-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fe177-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fe177-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fe177-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fe177-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="fe177-205">CNAME</span></span>  <br/> |<span data-ttu-id="fe177-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fe177-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fe177-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fe177-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fe177-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="fe177-208">CNAME</span></span>  <br/> |<span data-ttu-id="fe177-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fe177-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="fe177-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fe177-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fe177-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="fe177-211">CNAME</span></span>  <br/> |<span data-ttu-id="fe177-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fe177-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="fe177-214">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-214">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="fe177-216">Con los tres pasos anteriores y con los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="fe177-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fe177-217">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="fe177-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fe177-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fe177-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe177-219">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="fe177-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fe177-220">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="fe177-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fe177-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe177-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="fe177-222">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="fe177-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="fe177-223">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fe177-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe177-p111">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fe177-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fe177-227">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fe177-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fe177-229">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="fe177-229">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fe177-231">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe177-231">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fe177-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fe177-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fe177-234">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="fe177-234">**Hostname**</span></span>|<span data-ttu-id="fe177-235">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="fe177-235">**Record Type**</span></span>|<span data-ttu-id="fe177-236">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fe177-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fe177-237">TXT</span><span class="sxs-lookup"><span data-stu-id="fe177-237">TXT</span></span>  <br/> |<span data-ttu-id="fe177-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fe177-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="fe177-239">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="fe177-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="fe177-241">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-241">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="fe177-243">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="fe177-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="fe177-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fe177-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="fe177-245">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fe177-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe177-p112">Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fe177-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Iniciar sesión](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fe177-249">En **administre sus dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fe177-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Seleccionar un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fe177-251">Seleccione la pestaña **DNS** .</span><span class="sxs-lookup"><span data-stu-id="fe177-251">Select the **DNS** tab.</span></span> 
    
    ![Seleccione la pestaña DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fe177-253">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="fe177-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="fe177-254">Seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe177-254">Select **Add New**.</span></span>
    
    ![Seleccione Agregar nuevo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fe177-256">En los cuadros vacíos para el nuevo registro, seleccione **SRV** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fe177-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="fe177-257">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="fe177-257">**Hostname**</span></span>|<span data-ttu-id="fe177-258">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="fe177-258">**Record Type**</span></span>|<span data-ttu-id="fe177-259">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="fe177-259">**Priority**</span></span>|<span data-ttu-id="fe177-260">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="fe177-260">**Weight**</span></span>|<span data-ttu-id="fe177-261">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="fe177-261">**Port**</span></span>|<span data-ttu-id="fe177-262">**Destino**</span><span class="sxs-lookup"><span data-stu-id="fe177-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fe177-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="fe177-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="fe177-264">SRV</span><span class="sxs-lookup"><span data-stu-id="fe177-264">SRV</span></span>  <br/> |<span data-ttu-id="fe177-265">100</span><span class="sxs-lookup"><span data-stu-id="fe177-265">100</span></span>  <br/> |<span data-ttu-id="fe177-266">1</span><span class="sxs-lookup"><span data-stu-id="fe177-266">1</span></span>  <br/> |<span data-ttu-id="fe177-267">443</span><span class="sxs-lookup"><span data-stu-id="fe177-267">443</span></span>  <br/> |<span data-ttu-id="fe177-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fe177-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fe177-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="fe177-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="fe177-270">SRV</span><span class="sxs-lookup"><span data-stu-id="fe177-270">SRV</span></span>  <br/> |<span data-ttu-id="fe177-271">100</span><span class="sxs-lookup"><span data-stu-id="fe177-271">100</span></span>  <br/> |<span data-ttu-id="fe177-272">1</span><span class="sxs-lookup"><span data-stu-id="fe177-272">1</span></span>  <br/> |<span data-ttu-id="fe177-273">5061</span><span class="sxs-lookup"><span data-stu-id="fe177-273">5061</span></span>  <br/> |<span data-ttu-id="fe177-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fe177-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Escriba (o copie y pegue) los valores DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="fe177-276">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe177-276">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="fe177-278">Con los tres pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="fe177-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe177-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fe177-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
