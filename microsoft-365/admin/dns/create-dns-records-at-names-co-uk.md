---
title: Crear registros DNS en Names.co.uk para Office 365
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
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Names.co.uk para Office 365.
ms.openlocfilehash: 8f8d76c1aebaa7fec80b264e0a9d2c8fffec9f41
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211672"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="d37a8-103">Crear registros DNS en Names.co.uk para Office 365</span><span class="sxs-lookup"><span data-stu-id="d37a8-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="d37a8-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="d37a8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d37a8-105">Si Names.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="d37a8-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="d37a8-106">Después de agregar estos registros a Names.co.uk, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d37a8-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="d37a8-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="d37a8-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d37a8-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d37a8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d37a8-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="d37a8-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d37a8-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d37a8-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d37a8-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d37a8-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d37a8-p104">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d37a8-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d37a8-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d37a8-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d37a8-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d37a8-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d37a8-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d37a8-125">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="d37a8-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d37a8-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="d37a8-127">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="d37a8-127">**Host name**</span></span>|<span data-ttu-id="d37a8-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d37a8-128">**Type**</span></span>|<span data-ttu-id="d37a8-129">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d37a8-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d37a8-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d37a8-131">TXT</span><span class="sxs-lookup"><span data-stu-id="d37a8-131">TXT</span></span>  <br/> |<span data-ttu-id="d37a8-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d37a8-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d37a8-133">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d37a8-133">**Note:** This is an example.</span></span> <span data-ttu-id="d37a8-134">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d37a8-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="d37a8-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="d37a8-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="d37a8-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-137">Select **Save**.</span></span>
    
    <span data-ttu-id="d37a8-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="d37a8-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="d37a8-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d37a8-141">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="d37a8-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="d37a8-142">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="d37a8-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d37a8-143">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="d37a8-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d37a8-144">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="d37a8-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d37a8-145">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="d37a8-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d37a8-146">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d37a8-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d37a8-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="d37a8-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="d37a8-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="d37a8-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d37a8-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d37a8-p107">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d37a8-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d37a8-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d37a8-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d37a8-158">En la página **Agregar o modificar zona DNS**, en la sección **Registros Mail eXchange**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d37a8-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d37a8-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d37a8-160">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="d37a8-160">**Host name**</span></span>|<span data-ttu-id="d37a8-161">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="d37a8-161">**Priority**</span></span>|<span data-ttu-id="d37a8-162">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d37a8-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d37a8-163">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="d37a8-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d37a8-164">1</span><span class="sxs-lookup"><span data-stu-id="d37a8-164">1</span></span>  <br/> <span data-ttu-id="d37a8-165">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="d37a8-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="d37a8-166">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="d37a8-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d37a8-167">> [!NOTE]> obtener la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d37a8-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="d37a8-168">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="d37a8-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="d37a8-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-170">Select **Save**.</span></span>
    
    <span data-ttu-id="d37a8-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="d37a8-173">Si hay otros registros MX en la sección **Registros Mail eXchange**, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="d37a8-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="d37a8-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-175">Select **Save**.</span></span>
    
    <span data-ttu-id="d37a8-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="d37a8-178">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="d37a8-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="d37a8-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d37a8-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d37a8-p109">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d37a8-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d37a8-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d37a8-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d37a8-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d37a8-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d37a8-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d37a8-188">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="d37a8-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d37a8-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d37a8-190">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="d37a8-190">**Host Name**</span></span>|<span data-ttu-id="d37a8-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d37a8-191">**Type**</span></span>|<span data-ttu-id="d37a8-192">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d37a8-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d37a8-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d37a8-193">autodiscover</span></span>  <br/> |<span data-ttu-id="d37a8-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="d37a8-194">CNAME</span></span>  <br/> |<span data-ttu-id="d37a8-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d37a8-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d37a8-196">sip</span><span class="sxs-lookup"><span data-stu-id="d37a8-196">sip</span></span>  <br/> |<span data-ttu-id="d37a8-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="d37a8-197">CNAME</span></span>  <br/> |<span data-ttu-id="d37a8-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d37a8-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d37a8-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d37a8-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d37a8-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="d37a8-200">CNAME</span></span>  <br/> |<span data-ttu-id="d37a8-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d37a8-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d37a8-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d37a8-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d37a8-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="d37a8-203">CNAME</span></span>  <br/> |<span data-ttu-id="d37a8-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d37a8-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d37a8-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d37a8-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d37a8-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="d37a8-206">CNAME</span></span>  <br/> |<span data-ttu-id="d37a8-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d37a8-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="d37a8-209">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d37a8-211">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="d37a8-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d37a8-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d37a8-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d37a8-213">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="d37a8-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d37a8-214">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="d37a8-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d37a8-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="d37a8-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="d37a8-216">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d37a8-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="d37a8-p111">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d37a8-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d37a8-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d37a8-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d37a8-223">En la página **zonas DNS en la cuenta** , en la columna **nombre de dominio** , seleccione el nombre del dominio que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="d37a8-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="d37a8-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d37a8-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d37a8-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d37a8-227">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="d37a8-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d37a8-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d37a8-229">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="d37a8-229">**Host name**</span></span>|<span data-ttu-id="d37a8-230">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d37a8-230">**Type**</span></span>|<span data-ttu-id="d37a8-231">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d37a8-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d37a8-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d37a8-233">TXT</span><span class="sxs-lookup"><span data-stu-id="d37a8-233">TXT</span></span>  <br/> |<span data-ttu-id="d37a8-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d37a8-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d37a8-235">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="d37a8-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="d37a8-237">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-237">Select **Save**.</span></span>
    
    <span data-ttu-id="d37a8-238">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="d37a8-240">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="d37a8-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="d37a8-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d37a8-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d37a8-p112">Para empezar, vaya a su página de dominios en Names.co.uk a través de [este vínculo](https://account.names.co.uk/dashboard#/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="d37a8-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d37a8-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d37a8-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d37a8-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d37a8-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d37a8-248">En la página **Agregar o modificar zona DNS**, en la sección **Registros de servicio**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d37a8-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d37a8-249">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="d37a8-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d37a8-250">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d37a8-250">**Name**</span></span>|<span data-ttu-id="d37a8-251">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="d37a8-251">**Priority**</span></span>|<span data-ttu-id="d37a8-252">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="d37a8-252">**Weight**</span></span>|<span data-ttu-id="d37a8-253">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="d37a8-253">**Port**</span></span>|<span data-ttu-id="d37a8-254">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d37a8-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d37a8-255">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="d37a8-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="d37a8-256">100</span><span class="sxs-lookup"><span data-stu-id="d37a8-256">100</span></span>  <br/> |<span data-ttu-id="d37a8-257">1</span><span class="sxs-lookup"><span data-stu-id="d37a8-257">1</span></span>  <br/> |<span data-ttu-id="d37a8-258">443</span><span class="sxs-lookup"><span data-stu-id="d37a8-258">443</span></span>  <br/> |<span data-ttu-id="d37a8-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d37a8-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d37a8-260">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="d37a8-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d37a8-261">100</span><span class="sxs-lookup"><span data-stu-id="d37a8-261">100</span></span>  <br/> |<span data-ttu-id="d37a8-262">1</span><span class="sxs-lookup"><span data-stu-id="d37a8-262">1</span></span>  <br/> |<span data-ttu-id="d37a8-263">5061</span><span class="sxs-lookup"><span data-stu-id="d37a8-263">5061</span></span>  <br/> |<span data-ttu-id="d37a8-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d37a8-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="d37a8-266">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d37a8-266">Select **Save**.</span></span>
    
    <span data-ttu-id="d37a8-267">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="d37a8-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="d37a8-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d37a8-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
