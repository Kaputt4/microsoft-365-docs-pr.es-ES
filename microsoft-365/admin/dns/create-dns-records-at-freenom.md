---
title: Crear registros DNS en Freenom para Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Freenom para Microsoft.
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629568"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="89b3b-103">Crear registros DNS en Freenom para Microsoft</span><span class="sxs-lookup"><span data-stu-id="89b3b-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="89b3b-104">[Consulte preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que está buscando.</span><span class="sxs-lookup"><span data-stu-id="89b3b-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="89b3b-105">El sitio web de Freenom no admite los registros SRV, lo que significa que no funcionarán varias características de Skype empresarial online y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="89b3b-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="89b3b-106">Independientemente del plan de Microsoft que use, hay importantes limitaciones de servicio y es posible que quiera cambiar a un proveedor de host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="89b3b-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="89b3b-107">Si a pesar de las limitaciones del servicio, elige administrar sus propios registros DNS de Microsoft en Freenom, siga los pasos descritos en este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico y otros servicios.</span><span class="sxs-lookup"><span data-stu-id="89b3b-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="89b3b-108">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="89b3b-108">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="89b3b-p102">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="89b3b-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="89b3b-112">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="89b3b-112">Add a TXT record for verification</span></span>
<span data-ttu-id="89b3b-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="89b3b-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="89b3b-114">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="89b3b-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="89b3b-115">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="89b3b-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89b3b-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="89b3b-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="89b3b-118">Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="89b3b-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="89b3b-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="89b3b-119">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="89b3b-121">Seleccione **servicios**y, a continuación, seleccione **mis dominios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom seleccionar servicios y mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="89b3b-123">En el dominio que quiera editar, seleccione **administrar dominio**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom seleccione administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="89b3b-125">Seleccione **administrar DNS de Freenom**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom administrar Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="89b3b-127">En **Agregar registro**, en la columna **tipo** , elija **txt** en el menú.</span><span class="sxs-lookup"><span data-stu-id="89b3b-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom agregar tipo de registro TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="89b3b-129">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="89b3b-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="89b3b-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="89b3b-130">**Name**</span></span>|<span data-ttu-id="89b3b-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="89b3b-131">**Type**</span></span>|<span data-ttu-id="89b3b-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="89b3b-132">**TTL**</span></span>|<span data-ttu-id="89b3b-133">**Destino**</span><span class="sxs-lookup"><span data-stu-id="89b3b-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="89b3b-134">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="89b3b-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="89b3b-135">TXT</span><span class="sxs-lookup"><span data-stu-id="89b3b-135">TXT</span></span>  <br/> |<span data-ttu-id="89b3b-136">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="89b3b-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="89b3b-138">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89b3b-138">**Note:** This is an example.</span></span> <span data-ttu-id="89b3b-139">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="89b3b-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="89b3b-140">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="89b3b-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Valores de Freenom TXT para verificación](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="89b3b-142">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-142">Select **Save Changes**.</span></span>
    
    ![Registro TXT Freenom guardar cambios](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="89b3b-144">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="89b3b-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="89b3b-145">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.</span><span class="sxs-lookup"><span data-stu-id="89b3b-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="89b3b-146">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="89b3b-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="89b3b-147">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="89b3b-147">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="89b3b-148">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="89b3b-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="89b3b-149">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="89b3b-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="89b3b-150">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="89b3b-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="89b3b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="89b3b-154">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="89b3b-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="89b3b-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="89b3b-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="89b3b-156">Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="89b3b-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="89b3b-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="89b3b-157">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="89b3b-159">Seleccione **servicios**y, a continuación, seleccione **mis dominios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom seleccionar servicios y mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="89b3b-161">En el dominio que quiera editar, seleccione **administrar dominio**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom seleccione administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="89b3b-163">Establezca el nombre para el dominio en los servidores de nombres Freenom predeterminados.</span><span class="sxs-lookup"><span data-stu-id="89b3b-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="89b3b-164">Seleccione **herramientas de administración**y, a continuación, seleccione **servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Configuración de los servidores de nombres Freenom](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="89b3b-166">Asegúrese de que la opción **usar servidores de nombres predeterminados** está seleccionada y, después, seleccione **Cambiar servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Cambiar los servidores de nombres de Freenom](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="89b3b-168">Seleccione **administrar DNS de Freenom**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom seleccionar administrar Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="89b3b-170">En **Agregar registro**, en la columna **tipo** , elija **mx** en el menú.</span><span class="sxs-lookup"><span data-stu-id="89b3b-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom agregar tipo de registro MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="89b3b-172">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="89b3b-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="89b3b-173">**Name**</span><span class="sxs-lookup"><span data-stu-id="89b3b-173">**Name**</span></span>|<span data-ttu-id="89b3b-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="89b3b-174">**Type**</span></span>|<span data-ttu-id="89b3b-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="89b3b-175">**TTL**</span></span>|<span data-ttu-id="89b3b-176">**Destino**</span><span class="sxs-lookup"><span data-stu-id="89b3b-176">**Target**</span></span>|<span data-ttu-id="89b3b-177">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="89b3b-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="89b3b-178">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="89b3b-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="89b3b-179">MX (intercambiador de correo)</span><span class="sxs-lookup"><span data-stu-id="89b3b-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="89b3b-180">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-181">\<Domain-Key\>. mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="89b3b-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="89b3b-182">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89b3b-182">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="89b3b-183">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="89b3b-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="89b3b-184">10 </span><span class="sxs-lookup"><span data-stu-id="89b3b-184">10</span></span>  <br/> <span data-ttu-id="89b3b-185">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="89b3b-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Registro MX de Freenom](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="89b3b-187">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-187">Select **Save Changes**.</span></span>
    
    ![Guardar cambios del registro MX de Freenom](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="89b3b-189">Si hay otros registros MX, elimínelos todos.</span><span class="sxs-lookup"><span data-stu-id="89b3b-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="89b3b-190">Para cada registro, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-190">For each record, select **Delete**.</span></span> <span data-ttu-id="89b3b-191">Si el mensaje **realmente desea quitar esta entrada** , seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="89b3b-192">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="89b3b-192">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="89b3b-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="89b3b-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="89b3b-194">Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="89b3b-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="89b3b-195">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="89b3b-195">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="89b3b-197">Seleccione **servicios**y, a continuación, seleccione **mis dominios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom seleccionar servicios y mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="89b3b-199">En el dominio que quiera editar, seleccione **administrar dominio**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom seleccione administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="89b3b-201">Seleccione **administrar DNS de Freenom**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom seleccionar administrar Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="89b3b-203">En **Agregar registro**, en la columna **tipo** , elija **CNAME** en el menú.</span><span class="sxs-lookup"><span data-stu-id="89b3b-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom agregar tipo de registro CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="89b3b-205">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="89b3b-205">Create the first CNAME record.</span></span> <span data-ttu-id="89b3b-206">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="89b3b-206">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="89b3b-207">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="89b3b-207">**Name**</span></span>|<span data-ttu-id="89b3b-208">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="89b3b-208">**Record type**</span></span>|<span data-ttu-id="89b3b-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="89b3b-209">**TTL**</span></span>|<span data-ttu-id="89b3b-210">**Destino**</span><span class="sxs-lookup"><span data-stu-id="89b3b-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="89b3b-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="89b3b-211">autodiscover</span></span>  <br/> |<span data-ttu-id="89b3b-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="89b3b-212">CNAME</span></span>  <br/> |<span data-ttu-id="89b3b-213">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="89b3b-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="89b3b-215">sip</span><span class="sxs-lookup"><span data-stu-id="89b3b-215">sip</span></span>  <br/> |<span data-ttu-id="89b3b-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="89b3b-216">CNAME</span></span>  <br/> |<span data-ttu-id="89b3b-217">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="89b3b-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="89b3b-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="89b3b-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="89b3b-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="89b3b-220">CNAME</span></span>  <br/> |<span data-ttu-id="89b3b-221">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="89b3b-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="89b3b-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="89b3b-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="89b3b-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="89b3b-224">CNAME</span></span>  <br/> |<span data-ttu-id="89b3b-225">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="89b3b-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="89b3b-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="89b3b-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="89b3b-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="89b3b-228">CNAME</span></span>  <br/> |<span data-ttu-id="89b3b-229">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-230">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="89b3b-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Valores CNAME de Freenom](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="89b3b-232">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-232">Select **Save Changes**.</span></span>
    
    ![Guardar los cambios de Freenom CNAME](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="89b3b-234">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="89b3b-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="89b3b-235">Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.</span><span class="sxs-lookup"><span data-stu-id="89b3b-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="89b3b-236">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="89b3b-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="89b3b-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="89b3b-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="89b3b-238">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="89b3b-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="89b3b-239">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="89b3b-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="89b3b-240">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89b3b-240">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="89b3b-241">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="89b3b-241">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="89b3b-242">Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="89b3b-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="89b3b-243">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="89b3b-243">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="89b3b-245">Seleccione **servicios**y, a continuación, seleccione **mis dominios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom seleccionar servicios y mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="89b3b-247">En el dominio que quiera editar, seleccione **administrar dominio**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom seleccione administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="89b3b-249">Seleccione **administrar DNS de Freenom**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom seleccionar administrar Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="89b3b-251">En **Agregar registro**, en la columna **tipo** , elija **txt** en el menú.</span><span class="sxs-lookup"><span data-stu-id="89b3b-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom agregar tipo de registro TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="89b3b-253">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="89b3b-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="89b3b-254">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="89b3b-254">**Name**</span></span>|<span data-ttu-id="89b3b-255">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="89b3b-255">**Record type**</span></span>|<span data-ttu-id="89b3b-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="89b3b-256">**TTL**</span></span>|<span data-ttu-id="89b3b-257">**Destino**</span><span class="sxs-lookup"><span data-stu-id="89b3b-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="89b3b-258">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="89b3b-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="89b3b-259">TXT</span><span class="sxs-lookup"><span data-stu-id="89b3b-259">TXT</span></span>  <br/> |<span data-ttu-id="89b3b-260">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="89b3b-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="89b3b-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="89b3b-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="89b3b-262">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="89b3b-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Valores de Freenom TXT para SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="89b3b-264">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89b3b-264">Select **Save Changes**.</span></span>
    
    ![Freenom registro TXT para cambios de guardado de SPF](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

