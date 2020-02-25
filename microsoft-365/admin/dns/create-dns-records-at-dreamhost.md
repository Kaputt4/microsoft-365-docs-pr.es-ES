---
title: Crear registros DNS en Dreamhost para Office 365
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Dreamhost para Office 365.
ms.openlocfilehash: f3f52e97fefece72dd96d9370e75e24fc4cebedf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248884"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="8c981-103">Crear registros DNS en Dreamhost para Office 365</span><span class="sxs-lookup"><span data-stu-id="8c981-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="8c981-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="8c981-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8c981-105">Si DreamHost es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.</span><span class="sxs-lookup"><span data-stu-id="8c981-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="8c981-106">Después de agregar estos registros a DreamHost, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c981-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="8c981-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c981-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c981-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c981-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8c981-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="8c981-111">Add a TXT record for verification</span></span>
<span data-ttu-id="8c981-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8c981-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8c981-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="8c981-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c981-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="8c981-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8c981-117">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="8c981-117">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="8c981-118">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8c981-118">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8c981-120">En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="8c981-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8c981-122">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="8c981-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8c981-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8c981-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8c981-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8c981-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8c981-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8c981-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8c981-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="8c981-127">**Name**</span></span>|<span data-ttu-id="8c981-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="8c981-128">**Type**</span></span>|<span data-ttu-id="8c981-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8c981-129">**Value**</span></span>|<span data-ttu-id="8c981-130">**Comment**</span><span class="sxs-lookup"><span data-stu-id="8c981-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8c981-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="8c981-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8c981-132">TXT</span><span class="sxs-lookup"><span data-stu-id="8c981-132">TXT</span></span>  <br/> |<span data-ttu-id="8c981-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8c981-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8c981-134">**Nota:** Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8c981-134">**Note:** This is an example.</span></span> <span data-ttu-id="8c981-135">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c981-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="8c981-136">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="8c981-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8c981-137">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="8c981-139">Seleccione **Agregar registro ahora.**</span><span class="sxs-lookup"><span data-stu-id="8c981-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="8c981-141">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="8c981-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8c981-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="8c981-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8c981-143">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="8c981-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8c981-144">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="8c981-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8c981-145">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="8c981-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8c981-146">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="8c981-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8c981-147">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="8c981-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8c981-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c981-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="8c981-151">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="8c981-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="8c981-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8c981-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8c981-153">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8c981-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8c981-154">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="8c981-154">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="8c981-155">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8c981-155">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8c981-157">En la página **Panel** , seleccione **correo**y, a continuación, **Custom mx**.</span><span class="sxs-lookup"><span data-stu-id="8c981-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-configure-2-1](../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="8c981-159">En la sección **administrar la entrega de correo** , en la columna **acciones** , seleccione **Editar** en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="8c981-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-2-2](../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="8c981-161">En la sección **registro MX personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores siguientes de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8c981-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="8c981-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8c981-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8c981-163">(Si hay otros registros MX, marque los registros que se van a eliminar).</span><span class="sxs-lookup"><span data-stu-id="8c981-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="8c981-164">**Registro MX (obligatorio)**</span><span class="sxs-lookup"><span data-stu-id="8c981-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="8c981-165">0  *\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8c981-166">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="8c981-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8c981-p108">El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="8c981-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="8c981-169">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c981-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="8c981-170">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="8c981-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-configure-2-3](../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="8c981-172">Seleccione **cambiar este dominio para usar registros MX personalizados ahora.**</span><span class="sxs-lookup"><span data-stu-id="8c981-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-configure-2-4](../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="8c981-174">Si hay otros registros MX, elimine cada uno de ellos seleccionando la entrada y, después, presionando la tecla **suprimir** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="8c981-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-configure-2-5](../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="8c981-176">Si ha eliminado algún registro, seleccione **actualizar los registros MX personalizados ahora.**</span><span class="sxs-lookup"><span data-stu-id="8c981-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-configure-2-6](../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="8c981-178">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="8c981-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="8c981-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8c981-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8c981-180">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8c981-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8c981-181">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="8c981-181">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="8c981-182">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8c981-182">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8c981-184">En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="8c981-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8c981-186">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="8c981-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8c981-188">En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8c981-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8c981-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8c981-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8c981-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8c981-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8c981-191">**Name**</span><span class="sxs-lookup"><span data-stu-id="8c981-191">**Name**</span></span>|<span data-ttu-id="8c981-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="8c981-192">**Type**</span></span>|<span data-ttu-id="8c981-193">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8c981-193">**Value**</span></span>|<span data-ttu-id="8c981-194">**Comment**</span><span class="sxs-lookup"><span data-stu-id="8c981-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8c981-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8c981-195">autodiscover</span></span>  <br/> |<span data-ttu-id="8c981-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c981-196">CNAME</span></span>  <br/> |<span data-ttu-id="8c981-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8c981-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8c981-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-199">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8c981-200">sip</span><span class="sxs-lookup"><span data-stu-id="8c981-200">sip</span></span>  <br/> |<span data-ttu-id="8c981-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c981-201">CNAME</span></span>  <br/> |<span data-ttu-id="8c981-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8c981-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8c981-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-204">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8c981-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8c981-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8c981-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c981-206">CNAME</span></span>  <br/> |<span data-ttu-id="8c981-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8c981-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8c981-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-209">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8c981-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8c981-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8c981-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c981-211">CNAME</span></span>  <br/> |<span data-ttu-id="8c981-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8c981-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="8c981-213">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8c981-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-214">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8c981-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8c981-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8c981-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c981-216">CNAME</span></span>  <br/> |<span data-ttu-id="8c981-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="8c981-218">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8c981-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-219">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-configure-3-1](../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="8c981-221">Seleccione **Agregar registro ahora.**</span><span class="sxs-lookup"><span data-stu-id="8c981-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-configure-3-2](../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="8c981-223">Con los dos pasos anteriores y los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8c981-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8c981-224">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="8c981-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8c981-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8c981-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c981-226">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="8c981-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8c981-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="8c981-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8c981-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c981-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="8c981-229">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8c981-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="8c981-230">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8c981-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8c981-231">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="8c981-231">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="8c981-232">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8c981-232">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8c981-234">En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="8c981-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8c981-236">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="8c981-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8c981-238">En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8c981-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8c981-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8c981-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8c981-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8c981-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8c981-241">**Name**</span><span class="sxs-lookup"><span data-stu-id="8c981-241">**Name**</span></span>|<span data-ttu-id="8c981-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="8c981-242">**Type**</span></span>|<span data-ttu-id="8c981-243">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8c981-243">**Value**</span></span>|<span data-ttu-id="8c981-244">**Comment**</span><span class="sxs-lookup"><span data-stu-id="8c981-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8c981-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="8c981-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8c981-246">TXT</span><span class="sxs-lookup"><span data-stu-id="8c981-246">TXT</span></span>  <br/> |<span data-ttu-id="8c981-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8c981-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8c981-248">**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="8c981-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="8c981-249">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-configure-4-1](../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="8c981-251">Seleccione **Agregar registro ahora.**</span><span class="sxs-lookup"><span data-stu-id="8c981-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-configure-4-2](../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="8c981-253">Con los dos pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="8c981-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="8c981-254">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="8c981-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="8c981-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8c981-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8c981-256">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8c981-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8c981-257">Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="8c981-257">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="8c981-258">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8c981-258">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8c981-260">En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="8c981-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8c981-262">En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="8c981-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8c981-264">En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8c981-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8c981-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8c981-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8c981-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8c981-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8c981-267">**Name**</span><span class="sxs-lookup"><span data-stu-id="8c981-267">**Name**</span></span>|<span data-ttu-id="8c981-268">**Type**</span><span class="sxs-lookup"><span data-stu-id="8c981-268">**Type**</span></span>|<span data-ttu-id="8c981-269">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8c981-269">**Value**</span></span>|<span data-ttu-id="8c981-270">**Comment**</span><span class="sxs-lookup"><span data-stu-id="8c981-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8c981-271">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="8c981-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="8c981-272">SRV</span><span class="sxs-lookup"><span data-stu-id="8c981-272">SRV</span></span>  <br/> |<span data-ttu-id="8c981-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="8c981-273">100 1 443</span></span>  <br/> <span data-ttu-id="8c981-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8c981-275">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8c981-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-276">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8c981-277">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="8c981-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8c981-278">SRV</span><span class="sxs-lookup"><span data-stu-id="8c981-278">SRV</span></span>  <br/> |<span data-ttu-id="8c981-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="8c981-279">100 1 5061</span></span>  <br/> <span data-ttu-id="8c981-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8c981-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="8c981-281">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="8c981-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8c981-282">(Este campo es opcional).</span><span class="sxs-lookup"><span data-stu-id="8c981-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-configure-5-1](../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="8c981-284">Seleccione **Agregar registro ahora**.</span><span class="sxs-lookup"><span data-stu-id="8c981-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-configure-5-2](../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="8c981-286">Con los dos pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="8c981-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="8c981-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c981-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
