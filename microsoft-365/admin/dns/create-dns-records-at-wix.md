---
title: Crear registros DNS en Wix para Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Wix para Microsoft.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916111"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="581e6-103">Crear registros DNS en Wix para Microsoft</span><span class="sxs-lookup"><span data-stu-id="581e6-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="581e6-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="581e6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="581e6-105">Si Wix es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="581e6-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="581e6-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="581e6-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="581e6-107">[Agregue un registro TXT para la comprobación](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="581e6-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="581e6-108">[Agregue un registro MX para que el correo electrónico de su dominio se envíe a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="581e6-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="581e6-109">[Agregue los cinco registros CNAME necesarios para Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="581e6-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="581e6-110">[Agregue un registro TXT para SPF para ayudar a evitar el correo no deseado de correo electrónico](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="581e6-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="581e6-111">[Agregue los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="581e6-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="581e6-112">Después de agregar estos registros en Wix, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="581e6-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="581e6-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="581e6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="581e6-116">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="581e6-116">Add a TXT record for verification</span></span>
<span data-ttu-id="581e6-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="581e6-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="581e6-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="581e6-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="581e6-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="581e6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="581e6-122">WIX no admite entradas DNS para subdominios.</span><span class="sxs-lookup"><span data-stu-id="581e6-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="581e6-123">Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="581e6-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="581e6-124">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="581e6-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="581e6-125">En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.**</span><span class="sxs-lookup"><span data-stu-id="581e6-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="581e6-126">Seleccione **+ Agregar otro en** la fila TXT **(Texto)** del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="581e6-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="581e6-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="581e6-128">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="581e6-128">Host Name</span></span> <br/> | <span data-ttu-id="581e6-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="581e6-129">TXT Value</span></span> <br/> | <span data-ttu-id="581e6-130">TTL</span><span class="sxs-lookup"><span data-stu-id="581e6-130">TTL</span></span> <br/> |
   |<span data-ttu-id="581e6-131">Rellenado automáticamente</span><span class="sxs-lookup"><span data-stu-id="581e6-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="581e6-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="581e6-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="581e6-133">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="581e6-133">**Note:** This is an example.</span></span> <span data-ttu-id="581e6-134">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="581e6-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="581e6-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="581e6-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="581e6-136">1 hora</span><span class="sxs-lookup"><span data-stu-id="581e6-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="581e6-137">Seleccione el **botón Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="581e6-138">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="581e6-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="581e6-139">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="581e6-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="581e6-140">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="581e6-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="581e6-141">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="581e6-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="581e6-142">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="581e6-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="581e6-143">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="581e6-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="581e6-144">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="581e6-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="581e6-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="581e6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="581e6-148">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="581e6-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="581e6-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="581e6-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="581e6-150">Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="581e6-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="581e6-151">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="581e6-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="581e6-152">En la **página Mis dominios,** en el área **Buzones,** seleccione el vínculo Configurar los **registros MX.**</span><span class="sxs-lookup"><span data-stu-id="581e6-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="581e6-153">Elija **Otro** en **la lista desplegable** Su proveedor de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="581e6-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="581e6-154">Seleccione **+ Agregar otro**.</span><span class="sxs-lookup"><span data-stu-id="581e6-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="581e6-155">En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="581e6-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="581e6-156">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="581e6-156">Host Name</span></span> | <span data-ttu-id="581e6-157">Points to </span><span class="sxs-lookup"><span data-stu-id="581e6-157">Points to</span></span> | <span data-ttu-id="581e6-158">Prioridad</span><span class="sxs-lookup"><span data-stu-id="581e6-158">Priority</span></span> | <span data-ttu-id="581e6-159">TTL</span><span class="sxs-lookup"><span data-stu-id="581e6-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="581e6-160">Rellenado automáticamente</span><span class="sxs-lookup"><span data-stu-id="581e6-160">Automatically populated</span></span> <br/> | <span data-ttu-id="581e6-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="581e6-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="581e6-162">**Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="581e6-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="581e6-163">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="581e6-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="581e6-164">0</span><span class="sxs-lookup"><span data-stu-id="581e6-164">0</span></span>  <br/> <span data-ttu-id="581e6-165">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="581e6-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> | <span data-ttu-id="581e6-166">1 hora</span><span class="sxs-lookup"><span data-stu-id="581e6-166">1 Hour</span></span>|
   
6. <span data-ttu-id="581e6-167">Si hay otros registros MX enumerados, elimine cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="581e6-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="581e6-168">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="581e6-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="581e6-169">En el cuadro de diálogo de confirmación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="581e6-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="581e6-170">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="581e6-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="581e6-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="581e6-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="581e6-172">Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="581e6-172">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="581e6-173">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="581e6-173">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="581e6-174">En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.**</span><span class="sxs-lookup"><span data-stu-id="581e6-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="581e6-175">Seleccione **+ Agregar otro en** la fila **CNAME (Alias)** del editor DNS para cada registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="581e6-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="581e6-176">En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="581e6-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="581e6-177">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="581e6-177">Host Name</span></span> | <span data-ttu-id="581e6-178">Points to </span><span class="sxs-lookup"><span data-stu-id="581e6-178">Points to</span></span> | <span data-ttu-id="581e6-179">TTL</span><span class="sxs-lookup"><span data-stu-id="581e6-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="581e6-180">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="581e6-180">autodiscover</span></span>  <br/> |<span data-ttu-id="581e6-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="581e6-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="581e6-182">1 hora</span><span class="sxs-lookup"><span data-stu-id="581e6-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="581e6-183">sip</span><span class="sxs-lookup"><span data-stu-id="581e6-183">sip</span></span>  <br/> |<span data-ttu-id="581e6-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="581e6-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="581e6-185">1 hora</span><span class="sxs-lookup"><span data-stu-id="581e6-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="581e6-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="581e6-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="581e6-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="581e6-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="581e6-188">1 hora</span><span class="sxs-lookup"><span data-stu-id="581e6-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="581e6-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="581e6-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="581e6-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="581e6-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="581e6-191">1 hora</span><span class="sxs-lookup"><span data-stu-id="581e6-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="581e6-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="581e6-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="581e6-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="581e6-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="581e6-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="581e6-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="581e6-195">Seleccione el **botón Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="581e6-196">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="581e6-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="581e6-197">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="581e6-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="581e6-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="581e6-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="581e6-199">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="581e6-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="581e6-200">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="581e6-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="581e6-201">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="581e6-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="581e6-202">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="581e6-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="581e6-203">Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="581e6-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="581e6-204">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="581e6-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="581e6-205">En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.**</span><span class="sxs-lookup"><span data-stu-id="581e6-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="581e6-206">Seleccione **+ Agregar otro en** la fila TXT **(Texto)** del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="581e6-207">En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="581e6-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="581e6-208">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="581e6-208">Host Name</span></span> | <span data-ttu-id="581e6-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="581e6-209">TXT Value</span></span> | <span data-ttu-id="581e6-210">TTL</span><span class="sxs-lookup"><span data-stu-id="581e6-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="581e6-211">[Deje esto en blanco]</span><span class="sxs-lookup"><span data-stu-id="581e6-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="581e6-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="581e6-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="581e6-213">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="581e6-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="581e6-214">TXT</span><span class="sxs-lookup"><span data-stu-id="581e6-214">TXT</span></span>  <br/> | <span data-ttu-id="581e6-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="581e6-215">1 Hour</span></span> |
   
5. <span data-ttu-id="581e6-216">Seleccione el **botón Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="581e6-217">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="581e6-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="581e6-218">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="581e6-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="581e6-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="581e6-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="581e6-220">Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="581e6-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="581e6-221">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="581e6-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="581e6-222">En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.**</span><span class="sxs-lookup"><span data-stu-id="581e6-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="581e6-223">Seleccione **+ Agregar otro** en la fila **SRV** del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="581e6-224">En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="581e6-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="581e6-225">Servicio</span><span class="sxs-lookup"><span data-stu-id="581e6-225">Service</span></span> | <span data-ttu-id="581e6-226">Protocolo</span><span class="sxs-lookup"><span data-stu-id="581e6-226">Protocol</span></span> | <span data-ttu-id="581e6-227">Nombre</span><span class="sxs-lookup"><span data-stu-id="581e6-227">Name</span></span> | <span data-ttu-id="581e6-228">Peso</span><span class="sxs-lookup"><span data-stu-id="581e6-228">Weight</span></span> | <span data-ttu-id="581e6-229">Puerto</span><span class="sxs-lookup"><span data-stu-id="581e6-229">Port</span></span> | <span data-ttu-id="581e6-230">Target</span><span class="sxs-lookup"><span data-stu-id="581e6-230">Target</span></span> | <span data-ttu-id="581e6-231">Prioridad</span><span class="sxs-lookup"><span data-stu-id="581e6-231">Priority</span></span> | <span data-ttu-id="581e6-232">TTL</span><span class="sxs-lookup"><span data-stu-id="581e6-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="581e6-233">sip</span><span class="sxs-lookup"><span data-stu-id="581e6-233">sip</span></span>  |<span data-ttu-id="581e6-234">tls</span><span class="sxs-lookup"><span data-stu-id="581e6-234">tls</span></span>  |<span data-ttu-id="581e6-235">Rellenado automáticamente</span><span class="sxs-lookup"><span data-stu-id="581e6-235">Automatically populated</span></span> |<span data-ttu-id="581e6-236">1</span><span class="sxs-lookup"><span data-stu-id="581e6-236">1</span></span>  |<span data-ttu-id="581e6-237">443</span><span class="sxs-lookup"><span data-stu-id="581e6-237">443</span></span>   |<span data-ttu-id="581e6-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="581e6-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="581e6-239">100</span><span class="sxs-lookup"><span data-stu-id="581e6-239">100</span></span> |<span data-ttu-id="581e6-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="581e6-240">1 Hour</span></span> |
   |<span data-ttu-id="581e6-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="581e6-241">sipfed</span></span>|<span data-ttu-id="581e6-242">tcp</span><span class="sxs-lookup"><span data-stu-id="581e6-242">tcp</span></span> |<span data-ttu-id="581e6-243">Rellenado automáticamente</span><span class="sxs-lookup"><span data-stu-id="581e6-243">Automatically populated</span></span>|<span data-ttu-id="581e6-244">1</span><span class="sxs-lookup"><span data-stu-id="581e6-244">1</span></span> |<span data-ttu-id="581e6-245">5061</span><span class="sxs-lookup"><span data-stu-id="581e6-245">5061</span></span> |<span data-ttu-id="581e6-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="581e6-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="581e6-247">100</span><span class="sxs-lookup"><span data-stu-id="581e6-247">100</span></span> | <span data-ttu-id="581e6-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="581e6-248">1 Hour</span></span> |
   
5. <span data-ttu-id="581e6-249">Seleccione el **botón Guardar DNS** en la parte superior del editor DNS.</span><span class="sxs-lookup"><span data-stu-id="581e6-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="581e6-250">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="581e6-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="581e6-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="581e6-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
