---
title: Crear registros DNS en OVH para Office 365
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en OVH para Office 365.
ms.openlocfilehash: 4857addd7dfd096c1ddd6e59f1f17ace76b75a9e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354351"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="e1803-103">Crear registros DNS en OVH para Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="e1803-104">[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="e1803-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e1803-105">Si OVH es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="e1803-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e1803-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="e1803-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="e1803-107">Crear registros DNS en OVH para Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="e1803-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="e1803-109">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="e1803-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e1803-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e1803-111">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="e1803-112">Después de agregar estos registros a OVH, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1803-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="e1803-113">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1803-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e1803-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1803-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e1803-117">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="e1803-117">Add a TXT record for verification</span></span>
<span data-ttu-id="e1803-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e1803-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="e1803-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="e1803-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1803-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e1803-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e1803-123">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="e1803-123">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="e1803-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1803-124">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e1803-126">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e1803-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e1803-128">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="e1803-128">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e1803-130">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="e1803-130">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e1803-132">Seleccionar **txt**</span><span class="sxs-lookup"><span data-stu-id="e1803-132">Select **TXT**</span></span>
    
    ![OVH seleccione la entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="e1803-134">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1803-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="e1803-135">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e1803-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e1803-136">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="e1803-136">**Record type**</span></span>|<span data-ttu-id="e1803-137">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="e1803-137">**Sub-domain**</span></span>|<span data-ttu-id="e1803-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1803-138">**TTL**</span></span>|<span data-ttu-id="e1803-139">**Valor**</span><span class="sxs-lookup"><span data-stu-id="e1803-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1803-140">TXT</span><span class="sxs-lookup"><span data-stu-id="e1803-140">TXT</span></span>  <br/> |<span data-ttu-id="e1803-141">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="e1803-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="e1803-142">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e1803-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e1803-143">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="e1803-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="e1803-144">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1803-144">**Note:** This is an example.</span></span> <span data-ttu-id="e1803-145">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1803-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="e1803-146">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e1803-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="e1803-147">Seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-147">Select **Confirm**.</span></span> 
    
    ![OVH confirmar TXT para verificación](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="e1803-149">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="e1803-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e1803-150">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="e1803-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e1803-151">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="e1803-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e1803-152">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="e1803-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e1803-153">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="e1803-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e1803-154">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="e1803-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e1803-155">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e1803-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1803-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="e1803-159">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="e1803-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e1803-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="e1803-161">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="e1803-161">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="e1803-162">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1803-162">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e1803-164">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e1803-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e1803-166">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="e1803-166">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e1803-168">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="e1803-168">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e1803-170">Seleccione **mx**.</span><span class="sxs-lookup"><span data-stu-id="e1803-170">Select **MX**.</span></span>
    
    ![Tipo de registro MX de OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="e1803-172">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1803-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="e1803-173">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e1803-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e1803-174">De forma predeterminada OVH usa la notación relativa para el destino, que agrega el nombre de dominio al final del registro de destino.</span><span class="sxs-lookup"><span data-stu-id="e1803-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="e1803-175">Para usar la notación absoluta en su lugar, agregue un punto al registro de destino, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e1803-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="e1803-176">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="e1803-176">**Record type**</span></span>|<span data-ttu-id="e1803-177">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="e1803-177">**Sub-domain**</span></span>|<span data-ttu-id="e1803-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1803-178">**TTL**</span></span>|<span data-ttu-id="e1803-179">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="e1803-179">**Priority**</span></span>|<span data-ttu-id="e1803-180">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e1803-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1803-181">MX</span><span class="sxs-lookup"><span data-stu-id="e1803-181">MX</span></span>  <br/> |<span data-ttu-id="e1803-182">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="e1803-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="e1803-183">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e1803-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e1803-184">10 </span><span class="sxs-lookup"><span data-stu-id="e1803-184">10</span></span>  <br/> <span data-ttu-id="e1803-185">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1803-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="e1803-186">\<Domain-Key\>. mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e1803-187">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1803-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="e1803-188">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e1803-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH registro MX para correo](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="e1803-190">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1803-190">Select **Next**.</span></span>
    
    ![OVH registro MX Seleccione siguiente](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="e1803-192">Seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-192">Select **Confirm**.</span></span>
    
    ![OVH seleccionar confirmar registro MX](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="e1803-194">Si hay otros registros MX, elimínelos en la lista de la página **zona DNS** .</span><span class="sxs-lookup"><span data-stu-id="e1803-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="e1803-195">Seleccione cada registro y, a continuación, en la columna **acciones** , seleccione el icono de papelera de **eliminación** .</span><span class="sxs-lookup"><span data-stu-id="e1803-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![Eliminar registro MX de OVH](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="e1803-197">Seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="e1803-198">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="e1803-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e1803-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="e1803-200">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="e1803-200">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="e1803-201">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1803-201">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e1803-203">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e1803-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e1803-205">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="e1803-205">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e1803-207">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="e1803-207">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e1803-209">Seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e1803-209">Select **CNAME**.</span></span>
    
    ![OVH agregar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="e1803-211">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="e1803-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="e1803-212">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1803-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="e1803-213">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e1803-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e1803-214">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="e1803-214">**Record type**</span></span>|<span data-ttu-id="e1803-215">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="e1803-215">**Sub-domain**</span></span>|<span data-ttu-id="e1803-216">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e1803-216">**Target**</span></span>|<span data-ttu-id="e1803-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1803-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1803-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1803-218">CNAME</span></span>  <br/> |<span data-ttu-id="e1803-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1803-219">autodiscover</span></span>  <br/> |<span data-ttu-id="e1803-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="e1803-221">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="e1803-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e1803-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1803-222">CNAME</span></span>  <br/> |<span data-ttu-id="e1803-223">sip</span><span class="sxs-lookup"><span data-stu-id="e1803-223">sip</span></span>  <br/> |<span data-ttu-id="e1803-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="e1803-225">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="e1803-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e1803-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1803-226">CNAME</span></span>  <br/> |<span data-ttu-id="e1803-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1803-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e1803-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="e1803-229">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="e1803-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e1803-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1803-230">CNAME</span></span>  <br/> |<span data-ttu-id="e1803-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e1803-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e1803-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e1803-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="e1803-233">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="e1803-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e1803-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1803-234">CNAME</span></span>  <br/> |<span data-ttu-id="e1803-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e1803-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e1803-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="e1803-237">de 3600 segundos</span><span class="sxs-lookup"><span data-stu-id="e1803-237">3600 seconds</span></span>  <br/> |
   
    ![Registro CNAME de OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="e1803-239">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1803-239">Select **Next**.</span></span>
    
    ![OVH agregar valores CNAME y seleccionar siguiente](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="e1803-241">Seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="e1803-242">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e1803-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="e1803-243">Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.</span><span class="sxs-lookup"><span data-stu-id="e1803-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e1803-244">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e1803-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e1803-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e1803-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1803-246">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="e1803-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e1803-247">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e1803-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e1803-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1803-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="e1803-249">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e1803-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e1803-250">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="e1803-250">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="e1803-251">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1803-251">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e1803-253">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e1803-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e1803-255">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="e1803-255">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e1803-257">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="e1803-257">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e1803-259">Seleccione **txt**.</span><span class="sxs-lookup"><span data-stu-id="e1803-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="e1803-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="e1803-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="e1803-261">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="e1803-261">**Record type**</span></span>|<span data-ttu-id="e1803-262">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="e1803-262">**Sub-domain**</span></span>|<span data-ttu-id="e1803-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1803-263">**TTL**</span></span>|<span data-ttu-id="e1803-264">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="e1803-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1803-265">TXT</span><span class="sxs-lookup"><span data-stu-id="e1803-265">TXT</span></span>  <br/> |<span data-ttu-id="e1803-266">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="e1803-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="e1803-267">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e1803-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e1803-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e1803-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e1803-269">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="e1803-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH agregar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="e1803-271">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1803-271">Select **Next**.</span></span>
    
    ![OVH agregar registro TXT para SPF y seleccionar siguiente](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="e1803-273">Seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-273">Select **Confirm**.</span></span>
    
    ![OVH agregar registro TXT para SPF y confirmar](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="e1803-275">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e1803-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="e1803-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="e1803-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="e1803-277">Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="e1803-277">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="e1803-278">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1803-278">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e1803-280">En **dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e1803-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e1803-282">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="e1803-282">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e1803-284">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="e1803-284">Select **Add an entry**.</span></span>
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e1803-286">Seleccione **SRV**.</span><span class="sxs-lookup"><span data-stu-id="e1803-286">Select **SRV**.</span></span>
    
    ![OVH Seleccione el tipo de registro SRV](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="e1803-288">Cree el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="e1803-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="e1803-289">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1803-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="e1803-290">Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e1803-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e1803-291">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="e1803-291">**Record type**</span></span>|<span data-ttu-id="e1803-292">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="e1803-292">**Sub-domain**</span></span>|<span data-ttu-id="e1803-293">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="e1803-293">**Priority**</span></span>|<span data-ttu-id="e1803-294">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="e1803-294">**Weight**</span></span>|<span data-ttu-id="e1803-295">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="e1803-295">**Port**</span></span>|<span data-ttu-id="e1803-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1803-296">**TTL**</span></span>|<span data-ttu-id="e1803-297">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e1803-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1803-298">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="e1803-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="e1803-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="e1803-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="e1803-300">100</span><span class="sxs-lookup"><span data-stu-id="e1803-300">100</span></span>  <br/> |<span data-ttu-id="e1803-301">1</span><span class="sxs-lookup"><span data-stu-id="e1803-301">1</span></span>  <br/> |<span data-ttu-id="e1803-302">443</span><span class="sxs-lookup"><span data-stu-id="e1803-302">443</span></span>  <br/> |<span data-ttu-id="e1803-303">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e1803-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e1803-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="e1803-305">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="e1803-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="e1803-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="e1803-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e1803-307">100</span><span class="sxs-lookup"><span data-stu-id="e1803-307">100</span></span>  <br/> |<span data-ttu-id="e1803-308">1</span><span class="sxs-lookup"><span data-stu-id="e1803-308">1</span></span>  <br/> |<span data-ttu-id="e1803-309">5061</span><span class="sxs-lookup"><span data-stu-id="e1803-309">5061</span></span>  <br/> |<span data-ttu-id="e1803-310">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e1803-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e1803-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1803-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Registro SRV de OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="e1803-313">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1803-313">Select **Next**.</span></span>
    
    ![OVH de la selección de registro SRV siguiente](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="e1803-315">Seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1803-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="e1803-316">Repita los pasos anteriores para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="e1803-316">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="e1803-317">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="e1803-317">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e1803-p120">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1803-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
