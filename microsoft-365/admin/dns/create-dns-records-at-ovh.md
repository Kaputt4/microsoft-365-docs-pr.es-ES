---
title: Crear registros DNS en OVH para Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en OVH para Microsoft.
ms.openlocfilehash: 14c3796ff6686ae0d98ec32ec6ddf6afc004a3c3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657784"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="ef813-103">Crear registros DNS en OVH para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="ef813-104">[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml) si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="ef813-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ef813-105">Si OVH es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="ef813-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ef813-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="ef813-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="ef813-107">Crear registros DNS en OVH para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="ef813-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="ef813-109">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ef813-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="ef813-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ef813-111">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ef813-112">Después de agregar estos registros a OVH, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef813-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="ef813-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef813-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ef813-116">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="ef813-116">Add a TXT record for verification</span></span>
<span data-ttu-id="ef813-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ef813-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="ef813-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="ef813-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef813-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="ef813-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ef813-122">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ef813-122">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ef813-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ef813-123">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ef813-125">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="ef813-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ef813-127">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef813-127">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ef813-129">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="ef813-129">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ef813-131">Seleccionar **txt**</span><span class="sxs-lookup"><span data-stu-id="ef813-131">Select **TXT**</span></span>
    
    ![OVH seleccione la entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="ef813-133">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef813-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="ef813-134">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ef813-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ef813-135">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ef813-135">**Record type**</span></span>|<span data-ttu-id="ef813-136">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="ef813-136">**Sub-domain**</span></span>|<span data-ttu-id="ef813-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef813-137">**TTL**</span></span>|<span data-ttu-id="ef813-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ef813-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef813-139">TXT</span><span class="sxs-lookup"><span data-stu-id="ef813-139">TXT</span></span>  <br/> |<span data-ttu-id="ef813-140">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="ef813-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="ef813-141">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ef813-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef813-142">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="ef813-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="ef813-143">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef813-143">**Note:** This is an example.</span></span> <span data-ttu-id="ef813-144">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="ef813-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="ef813-145">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="ef813-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ef813-146">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-146">Select **Confirm**.</span></span> 
    
    ![OVH confirmar TXT para verificación](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="ef813-148">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="ef813-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ef813-149">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="ef813-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ef813-150">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="ef813-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ef813-151">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="ef813-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ef813-152">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="ef813-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ef813-153">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="ef813-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ef813-154">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ef813-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef813-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ef813-158">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ef813-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ef813-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="ef813-160">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ef813-160">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ef813-161">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ef813-161">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ef813-163">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="ef813-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ef813-165">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef813-165">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ef813-167">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="ef813-167">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ef813-169">Seleccione **mx**.</span><span class="sxs-lookup"><span data-stu-id="ef813-169">Select **MX**.</span></span>
    
    ![Tipo de registro MX de OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="ef813-171">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef813-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="ef813-172">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ef813-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ef813-173">De forma predeterminada OVH usa la notación relativa para el destino, que agrega el nombre de dominio al final del registro de destino.</span><span class="sxs-lookup"><span data-stu-id="ef813-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="ef813-174">Para usar la notación absoluta en su lugar, agregue un punto al registro de destino, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="ef813-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="ef813-175">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ef813-175">**Record type**</span></span>|<span data-ttu-id="ef813-176">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="ef813-176">**Sub-domain**</span></span>|<span data-ttu-id="ef813-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef813-177">**TTL**</span></span>|<span data-ttu-id="ef813-178">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="ef813-178">**Priority**</span></span>|<span data-ttu-id="ef813-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="ef813-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef813-180">MX</span><span class="sxs-lookup"><span data-stu-id="ef813-180">MX</span></span>  <br/> |<span data-ttu-id="ef813-181">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="ef813-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="ef813-182">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ef813-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef813-183">10 </span><span class="sxs-lookup"><span data-stu-id="ef813-183">10</span></span>  <br/> <span data-ttu-id="ef813-184">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="ef813-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="ef813-185">\<domain-key\>. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ef813-186">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef813-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="ef813-187">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="ef813-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH registro MX para correo](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="ef813-189">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ef813-189">Select **Next**.</span></span>
    
    ![OVH registro MX Seleccione siguiente](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="ef813-191">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-191">Select **Confirm**.</span></span>
    
    ![OVH seleccionar confirmar registro MX](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="ef813-193">Si hay otros registros MX, elimínelos en la lista de la página **zona DNS** .</span><span class="sxs-lookup"><span data-stu-id="ef813-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="ef813-194">Seleccione cada registro y, a continuación, en la columna **acciones** , seleccione el icono de papelera de **eliminación** .</span><span class="sxs-lookup"><span data-stu-id="ef813-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![Eliminar registro MX de OVH](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="ef813-196">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef813-197">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ef813-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ef813-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="ef813-199">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ef813-199">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ef813-200">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ef813-200">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ef813-202">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="ef813-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ef813-204">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef813-204">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ef813-206">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="ef813-206">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ef813-208">Seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ef813-208">Select **CNAME**.</span></span>
    
    ![OVH agregar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="ef813-210">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="ef813-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="ef813-211">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef813-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="ef813-212">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ef813-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ef813-213">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ef813-213">**Record type**</span></span>|<span data-ttu-id="ef813-214">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="ef813-214">**Sub-domain**</span></span>|<span data-ttu-id="ef813-215">**Destino**</span><span class="sxs-lookup"><span data-stu-id="ef813-215">**Target**</span></span>|<span data-ttu-id="ef813-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef813-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef813-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef813-217">CNAME</span></span>  <br/> |<span data-ttu-id="ef813-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ef813-218">autodiscover</span></span>  <br/> |<span data-ttu-id="ef813-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="ef813-220">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ef813-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ef813-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef813-221">CNAME</span></span>  <br/> |<span data-ttu-id="ef813-222">sip</span><span class="sxs-lookup"><span data-stu-id="ef813-222">sip</span></span>  <br/> |<span data-ttu-id="ef813-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ef813-224">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ef813-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ef813-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef813-225">CNAME</span></span>  <br/> |<span data-ttu-id="ef813-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ef813-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ef813-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ef813-228">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ef813-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ef813-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef813-229">CNAME</span></span>  <br/> |<span data-ttu-id="ef813-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ef813-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ef813-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="ef813-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="ef813-232">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ef813-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ef813-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef813-233">CNAME</span></span>  <br/> |<span data-ttu-id="ef813-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ef813-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ef813-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="ef813-236">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ef813-236">3600 seconds</span></span>  <br/> |
   
    ![Registro CNAME de OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="ef813-238">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ef813-238">Select **Next**.</span></span>
    
    ![OVH agregar valores CNAME y seleccionar siguiente](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="ef813-240">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="ef813-241">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="ef813-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="ef813-242">Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.</span><span class="sxs-lookup"><span data-stu-id="ef813-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ef813-243">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="ef813-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ef813-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ef813-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef813-245">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="ef813-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ef813-246">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="ef813-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ef813-247">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef813-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ef813-248">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ef813-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="ef813-249">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ef813-249">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ef813-250">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ef813-250">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ef813-252">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="ef813-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ef813-254">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef813-254">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ef813-256">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="ef813-256">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ef813-258">Seleccione **txt**.</span><span class="sxs-lookup"><span data-stu-id="ef813-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="ef813-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="ef813-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="ef813-260">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ef813-260">**Record type**</span></span>|<span data-ttu-id="ef813-261">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="ef813-261">**Sub-domain**</span></span>|<span data-ttu-id="ef813-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef813-262">**TTL**</span></span>|<span data-ttu-id="ef813-263">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="ef813-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef813-264">TXT</span><span class="sxs-lookup"><span data-stu-id="ef813-264">TXT</span></span>  <br/> |<span data-ttu-id="ef813-265">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="ef813-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="ef813-266">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ef813-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef813-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ef813-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ef813-268">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="ef813-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH agregar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="ef813-270">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ef813-270">Select **Next**.</span></span>
    
    ![OVH agregar registro TXT para SPF y seleccionar siguiente](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="ef813-272">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-272">Select **Confirm**.</span></span>
    
    ![OVH agregar registro TXT para SPF y confirmar](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef813-274">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef813-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ef813-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ef813-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="ef813-276">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ef813-276">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ef813-277">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ef813-277">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ef813-279">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="ef813-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ef813-281">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef813-281">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ef813-283">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="ef813-283">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ef813-285">Seleccione **SRV**.</span><span class="sxs-lookup"><span data-stu-id="ef813-285">Select **SRV**.</span></span>
    
    ![OVH Seleccione el tipo de registro SRV](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="ef813-287">Cree el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ef813-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="ef813-288">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef813-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="ef813-289">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ef813-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ef813-290">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ef813-290">**Record type**</span></span>|<span data-ttu-id="ef813-291">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="ef813-291">**Sub-domain**</span></span>|<span data-ttu-id="ef813-292">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="ef813-292">**Priority**</span></span>|<span data-ttu-id="ef813-293">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="ef813-293">**Weight**</span></span>|<span data-ttu-id="ef813-294">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="ef813-294">**Port**</span></span>|<span data-ttu-id="ef813-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef813-295">**TTL**</span></span>|<span data-ttu-id="ef813-296">**Target**</span><span class="sxs-lookup"><span data-stu-id="ef813-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef813-297">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="ef813-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="ef813-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ef813-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="ef813-299">100</span><span class="sxs-lookup"><span data-stu-id="ef813-299">100</span></span>  <br/> |<span data-ttu-id="ef813-300">1 </span><span class="sxs-lookup"><span data-stu-id="ef813-300">1</span></span>  <br/> |<span data-ttu-id="ef813-301">443</span><span class="sxs-lookup"><span data-stu-id="ef813-301">443</span></span>  <br/> |<span data-ttu-id="ef813-302">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ef813-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef813-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="ef813-304">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="ef813-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="ef813-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ef813-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ef813-306">100</span><span class="sxs-lookup"><span data-stu-id="ef813-306">100</span></span>  <br/> |<span data-ttu-id="ef813-307">1 </span><span class="sxs-lookup"><span data-stu-id="ef813-307">1</span></span>  <br/> |<span data-ttu-id="ef813-308">5061</span><span class="sxs-lookup"><span data-stu-id="ef813-308">5061</span></span>  <br/> |<span data-ttu-id="ef813-309">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ef813-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef813-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ef813-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Registro SRV de OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="ef813-312">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ef813-312">Select **Next**.</span></span>
    
    ![OVH de la selección de registro SRV siguiente](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="ef813-314">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef813-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="ef813-315">Repita los pasos anteriores para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ef813-315">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="ef813-316">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="ef813-316">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="ef813-p120">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef813-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
