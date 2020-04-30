---
title: Crear registros DNS en Names.co.uk para Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Names.co.uk para Microsoft.
ms.openlocfilehash: 91c328877d583f415ffd2b8312ff1dc899a05bcc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939172"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="3d4d4-103">Crear registros DNS en Names.co.uk para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d4d4-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="3d4d4-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3d4d4-105">Si Names.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="3d4d4-106">Después de agregar estos registros a Names.co.uk, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="3d4d4-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3d4d4-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="3d4d4-110">Add a TXT record for verification</span></span>
<span data-ttu-id="3d4d4-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4d4-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3d4d4-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d4d4-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3d4d4-p104">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="3d4d4-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d4d4-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="3d4d4-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d4d4-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="3d4d4-124">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="3d4d4-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="3d4d4-126">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-126">**Host name**</span></span>|<span data-ttu-id="3d4d4-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-127">**Type**</span></span>|<span data-ttu-id="3d4d4-128">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d4d4-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d4d4-130">TXT</span><span class="sxs-lookup"><span data-stu-id="3d4d4-130">TXT</span></span>  <br/> |<span data-ttu-id="3d4d4-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3d4d4-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3d4d4-132">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-132">**Note:** This is an example.</span></span> <span data-ttu-id="3d4d4-133">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3d4d4-134">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="3d4d4-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="3d4d4-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-136">Select **Save**.</span></span>
    
    <span data-ttu-id="3d4d4-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="3d4d4-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3d4d4-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3d4d4-141">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3d4d4-142">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3d4d4-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3d4d4-144">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3d4d4-145">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3d4d4-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3d4d4-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d4d4-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3d4d4-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4d4-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3d4d4-p107">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="3d4d4-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d4d4-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="3d4d4-157">En la página **Agregar o modificar zona DNS**, en la sección **Registros Mail eXchange**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d4d4-158">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d4d4-159">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-159">**Host name**</span></span>|<span data-ttu-id="3d4d4-160">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-160">**Priority**</span></span>|<span data-ttu-id="3d4d4-161">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d4d4-162">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d4d4-163">1</span><span class="sxs-lookup"><span data-stu-id="3d4d4-163">1</span></span>  <br/> <span data-ttu-id="3d4d4-164">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="3d4d4-165">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="3d4d4-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3d4d4-166">> [!NOTE]> obtener la \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3d4d4-167">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="3d4d4-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="3d4d4-169">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-169">Select **Save**.</span></span>
    
    <span data-ttu-id="3d4d4-170">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="3d4d4-172">Si hay otros registros MX en la sección **Registros Mail eXchange**, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="3d4d4-174">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-174">Select **Save**.</span></span>
    
    <span data-ttu-id="3d4d4-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d4d4-177">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d4d4-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3d4d4-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4d4-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3d4d4-p109">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="3d4d4-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d4d4-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="3d4d4-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d4d4-186">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="3d4d4-187">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="3d4d4-188">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d4d4-189">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-189">**Host Name**</span></span>|<span data-ttu-id="3d4d4-190">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-190">**Type**</span></span>|<span data-ttu-id="3d4d4-191">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d4d4-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3d4d4-192">autodiscover</span></span>  <br/> |<span data-ttu-id="3d4d4-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d4d4-193">CNAME</span></span>  <br/> |<span data-ttu-id="3d4d4-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d4d4-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3d4d4-195">sip</span><span class="sxs-lookup"><span data-stu-id="3d4d4-195">sip</span></span>  <br/> |<span data-ttu-id="3d4d4-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d4d4-196">CNAME</span></span>  <br/> |<span data-ttu-id="3d4d4-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d4d4-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d4d4-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d4d4-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3d4d4-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d4d4-199">CNAME</span></span>  <br/> |<span data-ttu-id="3d4d4-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d4d4-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d4d4-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3d4d4-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3d4d4-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d4d4-202">CNAME</span></span>  <br/> |<span data-ttu-id="3d4d4-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3d4d4-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3d4d4-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3d4d4-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3d4d4-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d4d4-205">CNAME</span></span>  <br/> |<span data-ttu-id="3d4d4-206">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d4d4-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="3d4d4-208">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3d4d4-210">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3d4d4-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3d4d4-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4d4-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d4d4-212">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3d4d4-213">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3d4d4-214">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3d4d4-215">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="3d4d4-p111">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="3d4d4-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d4d4-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="3d4d4-222">En la página **zonas DNS en la cuenta** , en la columna **nombre de dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="3d4d4-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d4d4-225">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="3d4d4-226">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="3d4d4-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d4d4-228">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-228">**Host name**</span></span>|<span data-ttu-id="3d4d4-229">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-229">**Type**</span></span>|<span data-ttu-id="3d4d4-230">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d4d4-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d4d4-232">TXT</span><span class="sxs-lookup"><span data-stu-id="3d4d4-232">TXT</span></span>  <br/> |<span data-ttu-id="3d4d4-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3d4d4-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3d4d4-234">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="3d4d4-236">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-236">Select **Save**.</span></span>
    
    <span data-ttu-id="3d4d4-237">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d4d4-239">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d4d4-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3d4d4-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4d4-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3d4d4-p112">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="3d4d4-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d4d4-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="3d4d4-247">En la página **Agregar o modificar zona DNS**, en la sección **Registros de servicio**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d4d4-248">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d4d4-249">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-249">**Name**</span></span>|<span data-ttu-id="3d4d4-250">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-250">**Priority**</span></span>|<span data-ttu-id="3d4d4-251">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-251">**Weight**</span></span>|<span data-ttu-id="3d4d4-252">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-252">**Port**</span></span>|<span data-ttu-id="3d4d4-253">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="3d4d4-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d4d4-254">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="3d4d4-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="3d4d4-255">100</span><span class="sxs-lookup"><span data-stu-id="3d4d4-255">100</span></span>  <br/> |<span data-ttu-id="3d4d4-256">1</span><span class="sxs-lookup"><span data-stu-id="3d4d4-256">1</span></span>  <br/> |<span data-ttu-id="3d4d4-257">443</span><span class="sxs-lookup"><span data-stu-id="3d4d4-257">443</span></span>  <br/> |<span data-ttu-id="3d4d4-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d4d4-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d4d4-259">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="3d4d4-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3d4d4-260">100</span><span class="sxs-lookup"><span data-stu-id="3d4d4-260">100</span></span>  <br/> |<span data-ttu-id="3d4d4-261">1</span><span class="sxs-lookup"><span data-stu-id="3d4d4-261">1</span></span>  <br/> |<span data-ttu-id="3d4d4-262">5061</span><span class="sxs-lookup"><span data-stu-id="3d4d4-262">5061</span></span>  <br/> |<span data-ttu-id="3d4d4-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d4d4-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="3d4d4-265">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d4d4-265">Select **Save**.</span></span>
    
    <span data-ttu-id="3d4d4-266">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="3d4d4-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d4d4-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
