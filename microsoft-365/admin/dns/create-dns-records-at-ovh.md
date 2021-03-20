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
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en OVH para Microsoft.
ms.openlocfilehash: a43593af80d2f651e4407de64ed9aab51f1c1ecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910071"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="81ca2-103">Crear registros DNS en OVH para Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="81ca2-104">[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml) si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="81ca2-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="81ca2-105">Si OVH es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="81ca2-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="81ca2-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="81ca2-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="81ca2-107">Crear registros DNS en OVH para Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="81ca2-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="81ca2-109">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="81ca2-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="81ca2-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="81ca2-111">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="81ca2-112">Después de agregar estos registros en OVH, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81ca2-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="81ca2-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81ca2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="81ca2-116">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="81ca2-116">Add a TXT record for verification</span></span>
<span data-ttu-id="81ca2-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca2-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="81ca2-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="81ca2-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81ca2-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="81ca2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="81ca2-122">Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="81ca2-122">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="81ca2-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="81ca2-123">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="81ca2-125">En **Dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="81ca2-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="81ca2-127">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-127">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="81ca2-129">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-129">Select **Add an entry**.</span></span>
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="81ca2-131">Seleccionar **TXT**</span><span class="sxs-lookup"><span data-stu-id="81ca2-131">Select **TXT**</span></span>
    
    ![OVH seleccionar entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="81ca2-133">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="81ca2-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="81ca2-134">Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="81ca2-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="81ca2-135">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="81ca2-135">**Record type**</span></span>|<span data-ttu-id="81ca2-136">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="81ca2-136">**Sub-domain**</span></span>|<span data-ttu-id="81ca2-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="81ca2-137">**TTL**</span></span>|<span data-ttu-id="81ca2-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="81ca2-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81ca2-139">TXT</span><span class="sxs-lookup"><span data-stu-id="81ca2-139">TXT</span></span>  <br/> |<span data-ttu-id="81ca2-140">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="81ca2-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="81ca2-141">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="81ca2-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="81ca2-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="81ca2-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="81ca2-143">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81ca2-143">**Note:** This is an example.</span></span> <span data-ttu-id="81ca2-144">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="81ca2-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="81ca2-145">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="81ca2-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="81ca2-146">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-146">Select **Confirm**.</span></span> 
    
    ![OVH confirma TXT para verificación](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="81ca2-148">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="81ca2-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="81ca2-149">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="81ca2-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="81ca2-150">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="81ca2-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="81ca2-151">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="81ca2-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="81ca2-152">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="81ca2-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="81ca2-153">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="81ca2-154">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="81ca2-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81ca2-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="81ca2-158">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="81ca2-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca2-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="81ca2-160">Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="81ca2-160">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="81ca2-161">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="81ca2-161">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="81ca2-163">En **Dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="81ca2-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="81ca2-165">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-165">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="81ca2-167">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-167">Select **Add an entry**.</span></span>
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="81ca2-169">Seleccione **MX**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-169">Select **MX**.</span></span>
    
    ![Tipo de registro MX de OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="81ca2-171">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="81ca2-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="81ca2-172">Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="81ca2-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="81ca2-173">De forma predeterminada, OVH usa notación relativa para el destino, que agrega el nombre de dominio al final del registro de destino.</span><span class="sxs-lookup"><span data-stu-id="81ca2-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="81ca2-174">Para usar la notación absoluta en su lugar, agregue un punto al registro de destino como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="81ca2-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="81ca2-175">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="81ca2-175">**Record type**</span></span>|<span data-ttu-id="81ca2-176">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="81ca2-176">**Sub-domain**</span></span>|<span data-ttu-id="81ca2-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="81ca2-177">**TTL**</span></span>|<span data-ttu-id="81ca2-178">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="81ca2-178">**Priority**</span></span>|<span data-ttu-id="81ca2-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="81ca2-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81ca2-180">MX</span><span class="sxs-lookup"><span data-stu-id="81ca2-180">MX</span></span>  <br/> |<span data-ttu-id="81ca2-181">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="81ca2-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="81ca2-182">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="81ca2-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="81ca2-183">10  </span><span class="sxs-lookup"><span data-stu-id="81ca2-183">10</span></span>  <br/> <span data-ttu-id="81ca2-184">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="81ca2-184">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="81ca2-185">\<domain-key\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="81ca2-186">**Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81ca2-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="81ca2-187">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="81ca2-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Registro MX de OVH para correo](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="81ca2-189">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-189">Select **Next**.</span></span>
    
    ![Registro MX de OVH seleccionar Siguiente](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="81ca2-191">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-191">Select **Confirm**.</span></span>
    
    ![Registro MX de OVH seleccione Confirmar](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="81ca2-193">Si hay otros registros MX, elimínelos todos en la lista de la página **de zona DNS.**</span><span class="sxs-lookup"><span data-stu-id="81ca2-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="81ca2-194">Seleccione cada registro y, a continuación, en la **columna Acciones,** seleccione el icono **eliminar** de la papelera.</span><span class="sxs-lookup"><span data-stu-id="81ca2-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![Eliminar registro MX de OVH](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="81ca2-196">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="81ca2-197">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="81ca2-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca2-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="81ca2-199">Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="81ca2-199">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="81ca2-200">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="81ca2-200">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="81ca2-202">En **Dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="81ca2-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="81ca2-204">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-204">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="81ca2-206">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-206">Select **Add an entry**.</span></span>
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="81ca2-208">Seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-208">Select **CNAME**.</span></span>
    
    ![OVH agregar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="81ca2-210">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="81ca2-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="81ca2-211">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="81ca2-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="81ca2-212">Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="81ca2-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="81ca2-213">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="81ca2-213">**Record type**</span></span>|<span data-ttu-id="81ca2-214">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="81ca2-214">**Sub-domain**</span></span>|<span data-ttu-id="81ca2-215">**Destino**</span><span class="sxs-lookup"><span data-stu-id="81ca2-215">**Target**</span></span>|<span data-ttu-id="81ca2-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="81ca2-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81ca2-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="81ca2-217">CNAME</span></span>  <br/> |<span data-ttu-id="81ca2-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="81ca2-218">autodiscover</span></span>  <br/> |<span data-ttu-id="81ca2-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="81ca2-220">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="81ca2-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="81ca2-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="81ca2-221">CNAME</span></span>  <br/> |<span data-ttu-id="81ca2-222">sip</span><span class="sxs-lookup"><span data-stu-id="81ca2-222">sip</span></span>  <br/> |<span data-ttu-id="81ca2-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="81ca2-224">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="81ca2-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="81ca2-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="81ca2-225">CNAME</span></span>  <br/> |<span data-ttu-id="81ca2-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="81ca2-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="81ca2-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="81ca2-228">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="81ca2-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="81ca2-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="81ca2-229">CNAME</span></span>  <br/> |<span data-ttu-id="81ca2-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="81ca2-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="81ca2-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="81ca2-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="81ca2-232">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="81ca2-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="81ca2-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="81ca2-233">CNAME</span></span>  <br/> |<span data-ttu-id="81ca2-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="81ca2-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="81ca2-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="81ca2-236">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="81ca2-236">3600 seconds</span></span>  <br/> |
   
    ![Registro CNAME de OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="81ca2-238">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-238">Select **Next**.</span></span>
    
    ![OVH Agregar valores CNAME y seleccionar Siguiente](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="81ca2-240">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="81ca2-241">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="81ca2-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="81ca2-242">Para cada registro, escriba o copie y pegue los valores de la siguiente fila de la tabla anterior en los cuadros de ese registro.</span><span class="sxs-lookup"><span data-stu-id="81ca2-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="81ca2-243">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="81ca2-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="81ca2-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca2-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="81ca2-245">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="81ca2-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="81ca2-246">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="81ca2-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="81ca2-247">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81ca2-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="81ca2-248">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="81ca2-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="81ca2-249">Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="81ca2-249">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="81ca2-250">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="81ca2-250">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="81ca2-252">En **Dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="81ca2-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="81ca2-254">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-254">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="81ca2-256">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-256">Select **Add an entry**.</span></span>
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="81ca2-258">Seleccione **TXT**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="81ca2-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="81ca2-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="81ca2-260">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="81ca2-260">**Record type**</span></span>|<span data-ttu-id="81ca2-261">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="81ca2-261">**Sub-domain**</span></span>|<span data-ttu-id="81ca2-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="81ca2-262">**TTL**</span></span>|<span data-ttu-id="81ca2-263">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="81ca2-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81ca2-264">TXT</span><span class="sxs-lookup"><span data-stu-id="81ca2-264">TXT</span></span>  <br/> |<span data-ttu-id="81ca2-265">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="81ca2-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="81ca2-266">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="81ca2-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="81ca2-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="81ca2-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="81ca2-268">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="81ca2-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Agregar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="81ca2-270">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-270">Select **Next**.</span></span>
    
    ![OVH Agregar registro TXT para SPF y seleccionar Siguiente](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="81ca2-272">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-272">Select **Confirm**.</span></span>
    
    ![OVH Agregar registro TXT para SPF y Confirmar](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="81ca2-274">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="81ca2-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="81ca2-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca2-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="81ca2-276">Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="81ca2-276">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="81ca2-277">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="81ca2-277">You'll be prompted to log in.</span></span>
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="81ca2-279">En **Dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="81ca2-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="81ca2-281">Seleccione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-281">Select **DNS zone**.</span></span>
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="81ca2-283">Seleccione **Agregar una entrada**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-283">Select **Add an entry**.</span></span>
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="81ca2-285">Seleccione **SRV**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-285">Select **SRV**.</span></span>
    
    ![Tipo de registro SRV seleccionado por OVH](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="81ca2-287">Cree el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="81ca2-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="81ca2-288">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="81ca2-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="81ca2-289">Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="81ca2-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="81ca2-290">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="81ca2-290">**Record type**</span></span>|<span data-ttu-id="81ca2-291">**Subdominio**</span><span class="sxs-lookup"><span data-stu-id="81ca2-291">**Sub-domain**</span></span>|<span data-ttu-id="81ca2-292">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="81ca2-292">**Priority**</span></span>|<span data-ttu-id="81ca2-293">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="81ca2-293">**Weight**</span></span>|<span data-ttu-id="81ca2-294">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="81ca2-294">**Port**</span></span>|<span data-ttu-id="81ca2-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="81ca2-295">**TTL**</span></span>|<span data-ttu-id="81ca2-296">**Target**</span><span class="sxs-lookup"><span data-stu-id="81ca2-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81ca2-297">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="81ca2-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="81ca2-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="81ca2-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="81ca2-299">100</span><span class="sxs-lookup"><span data-stu-id="81ca2-299">100</span></span>  <br/> |<span data-ttu-id="81ca2-300">1</span><span class="sxs-lookup"><span data-stu-id="81ca2-300">1</span></span>  <br/> |<span data-ttu-id="81ca2-301">443</span><span class="sxs-lookup"><span data-stu-id="81ca2-301">443</span></span>  <br/> |<span data-ttu-id="81ca2-302">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="81ca2-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="81ca2-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="81ca2-304">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="81ca2-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="81ca2-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="81ca2-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="81ca2-306">100</span><span class="sxs-lookup"><span data-stu-id="81ca2-306">100</span></span>  <br/> |<span data-ttu-id="81ca2-307">1</span><span class="sxs-lookup"><span data-stu-id="81ca2-307">1</span></span>  <br/> |<span data-ttu-id="81ca2-308">5061</span><span class="sxs-lookup"><span data-stu-id="81ca2-308">5061</span></span>  <br/> |<span data-ttu-id="81ca2-309">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="81ca2-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="81ca2-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="81ca2-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Registro SRV de OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="81ca2-312">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-312">Select **Next**.</span></span>
    
    ![Registro SRV de OVH seleccione Siguiente](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="81ca2-314">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="81ca2-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="81ca2-315">Repita los pasos anteriores para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="81ca2-315">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="81ca2-316">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="81ca2-316">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="81ca2-p120">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81ca2-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
