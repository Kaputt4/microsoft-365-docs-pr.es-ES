---
title: Crear registros DNS en Wix para Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Wix para Microsoft.
ms.openlocfilehash: 6f88cc65ae19f747a9fc3740ea1578f30d18b5e2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048860"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="a0ad5-103">Crear registros DNS en Wix para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0ad5-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="a0ad5-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a0ad5-105">Si Wix es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a0ad5-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="a0ad5-107">[Agregue un registro TXT para la comprobación](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="a0ad5-108">[Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="a0ad5-109">[Agregue los cinco registros CNAME necesarios para Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="a0ad5-110">[Agregue un registro TXT para SPF para ayudar a evitar el correo no deseado](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="a0ad5-111">[Agregue los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="a0ad5-112">Después de agregar estos registros a Wix, su dominio estará configurado para trabajar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a0ad5-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a0ad5-116">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="a0ad5-116">Add a TXT record for verification</span></span>
<span data-ttu-id="a0ad5-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="a0ad5-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="a0ad5-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0ad5-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a0ad5-122">Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a0ad5-123">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0ad5-124">En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a0ad5-125">Seleccione **+ Agregar otro** en la fila **txt (texto)** del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="a0ad5-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a0ad5-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-127">**Host Name**</span></span> <br/> |<span data-ttu-id="a0ad5-128">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="a0ad5-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="a0ad5-130">Se rellena automáticamente</span><span class="sxs-lookup"><span data-stu-id="a0ad5-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="a0ad5-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a0ad5-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a0ad5-132">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-132">**Note:** This is an example.</span></span> <span data-ttu-id="a0ad5-133">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="a0ad5-134">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="a0ad5-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="a0ad5-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="a0ad5-136">Seleccione el botón **Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a0ad5-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a0ad5-138">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a0ad5-139">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a0ad5-140">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a0ad5-141">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="a0ad5-142">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="a0ad5-143">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a0ad5-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a0ad5-147">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0ad5-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a0ad5-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="a0ad5-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="a0ad5-149">Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a0ad5-150">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0ad5-151">En la página **mis dominios** , en el área **buzones de correo** , seleccione el vínculo configurar los **registros MX** .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="a0ad5-152">Elija **otro** en la lista desplegable **proveedor de correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="a0ad5-153">Seleccione **+ Agregar otro**.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="a0ad5-154">En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0ad5-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a0ad5-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-155">**Host Name**</span></span>|<span data-ttu-id="a0ad5-156">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-156">**Points to**</span></span>|<span data-ttu-id="a0ad5-157">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-157">**Priority**</span></span>|<span data-ttu-id="a0ad5-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a0ad5-159">Se rellena automáticamente</span><span class="sxs-lookup"><span data-stu-id="a0ad5-159">Automatically populated</span></span> <br/> | <span data-ttu-id="a0ad5-160">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="a0ad5-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a0ad5-161">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="a0ad5-162">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="a0ad5-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="a0ad5-163">comprendi</span><span class="sxs-lookup"><span data-stu-id="a0ad5-163">0</span></span>  <br/> <span data-ttu-id="a0ad5-164">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a0ad5-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="a0ad5-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-165">1 Hour</span></span>|
   
6. <span data-ttu-id="a0ad5-166">Si hay otros registros MX enumerados, elimínelos.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="a0ad5-167">Seleccione **ACEPTAR**.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="a0ad5-168">En el cuadro de diálogo de confirmación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a0ad5-169">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0ad5-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a0ad5-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="a0ad5-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="a0ad5-171">Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a0ad5-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a0ad5-173">En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a0ad5-174">Seleccione **+ Agregar otro** en la fila **CNAME (aliases)** del editor DNS para cada registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="a0ad5-175">En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0ad5-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a0ad5-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-176">**Host Name**</span></span>|<span data-ttu-id="a0ad5-177">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-177">**Points to**</span></span>|<span data-ttu-id="a0ad5-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0ad5-179">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="a0ad5-179">autodiscover</span></span>  <br/> |<span data-ttu-id="a0ad5-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a0ad5-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a0ad5-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="a0ad5-182">sip</span><span class="sxs-lookup"><span data-stu-id="a0ad5-182">sip</span></span>  <br/> |<span data-ttu-id="a0ad5-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0ad5-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a0ad5-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="a0ad5-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a0ad5-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a0ad5-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0ad5-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="a0ad5-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="a0ad5-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a0ad5-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a0ad5-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a0ad5-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a0ad5-190">1 hora</span><span class="sxs-lookup"><span data-stu-id="a0ad5-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="a0ad5-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a0ad5-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a0ad5-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a0ad5-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a0ad5-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="a0ad5-194">Seleccione el botón **Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a0ad5-195">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a0ad5-196">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a0ad5-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a0ad5-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="a0ad5-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0ad5-198">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a0ad5-199">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a0ad5-200">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a0ad5-201">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="a0ad5-202">Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a0ad5-203">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0ad5-204">En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a0ad5-205">Seleccione **+ Agregar otro** en la fila **txt (texto)** del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="a0ad5-206">En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0ad5-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a0ad5-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-207">**Host Name**</span></span>|<span data-ttu-id="a0ad5-208">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-208">**TXT Value**</span></span>|<span data-ttu-id="a0ad5-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0ad5-210">[deje este cuadro en blanco]</span><span class="sxs-lookup"><span data-stu-id="a0ad5-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="a0ad5-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a0ad5-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a0ad5-212">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="a0ad5-213">TXT</span><span class="sxs-lookup"><span data-stu-id="a0ad5-213">TXT</span></span>  <br/> | <span data-ttu-id="a0ad5-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-214">1 Hour</span></span> |
   
5. <span data-ttu-id="a0ad5-215">Seleccione el botón **Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a0ad5-216">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a0ad5-217">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0ad5-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a0ad5-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="a0ad5-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="a0ad5-219">Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a0ad5-220">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0ad5-221">En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="a0ad5-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a0ad5-222">Seleccione **+ Agregar otro** en la fila **SRV** del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="a0ad5-223">En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0ad5-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a0ad5-224">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-224">**Service**</span></span>|<span data-ttu-id="a0ad5-225">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-225">**Protocol**</span></span>|<span data-ttu-id="a0ad5-226">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-226">**Name**</span></span>|<span data-ttu-id="a0ad5-227">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-227">**Weight**</span></span>|<span data-ttu-id="a0ad5-228">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-228">**Port**</span></span>|<span data-ttu-id="a0ad5-229">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-229">**Target**</span></span>|<span data-ttu-id="a0ad5-230">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-230">**Priority**</span></span>|<span data-ttu-id="a0ad5-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0ad5-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a0ad5-232">sip</span><span class="sxs-lookup"><span data-stu-id="a0ad5-232">sip</span></span>  |<span data-ttu-id="a0ad5-233">tls</span><span class="sxs-lookup"><span data-stu-id="a0ad5-233">tls</span></span>  |<span data-ttu-id="a0ad5-234">Se rellena automáticamente</span><span class="sxs-lookup"><span data-stu-id="a0ad5-234">Automatically populated</span></span> |<span data-ttu-id="a0ad5-235">1</span><span class="sxs-lookup"><span data-stu-id="a0ad5-235">1</span></span>  |<span data-ttu-id="a0ad5-236">443</span><span class="sxs-lookup"><span data-stu-id="a0ad5-236">443</span></span>   |<span data-ttu-id="a0ad5-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0ad5-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="a0ad5-238">100</span><span class="sxs-lookup"><span data-stu-id="a0ad5-238">100</span></span> |<span data-ttu-id="a0ad5-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-239">1 Hour</span></span> |
|<span data-ttu-id="a0ad5-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="a0ad5-240">sipfed</span></span>|<span data-ttu-id="a0ad5-241">tcp</span><span class="sxs-lookup"><span data-stu-id="a0ad5-241">tcp</span></span> |<span data-ttu-id="a0ad5-242">Se rellena automáticamente</span><span class="sxs-lookup"><span data-stu-id="a0ad5-242">Automatically populated</span></span>|<span data-ttu-id="a0ad5-243">1</span><span class="sxs-lookup"><span data-stu-id="a0ad5-243">1</span></span> |<span data-ttu-id="a0ad5-244">5061</span><span class="sxs-lookup"><span data-stu-id="a0ad5-244">5061</span></span> |<span data-ttu-id="a0ad5-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0ad5-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="a0ad5-246">100</span><span class="sxs-lookup"><span data-stu-id="a0ad5-246">100</span></span> | <span data-ttu-id="a0ad5-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a0ad5-247">1 Hour</span></span> |
   
5. <span data-ttu-id="a0ad5-248">Seleccione el botón **Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a0ad5-249">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="a0ad5-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="a0ad5-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a0ad5-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

