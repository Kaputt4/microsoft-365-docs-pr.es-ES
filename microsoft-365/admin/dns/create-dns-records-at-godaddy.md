---
title: Crear registros DNS en GoDaddy para Microsoft
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en GoDaddy para Microsoft.
ms.openlocfilehash: 995e579e21a185084d9ee64a7ee462930d845844
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646132"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="abbce-103">Crear registros DNS en GoDaddy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="abbce-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="abbce-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="abbce-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="abbce-105">Si GoDaddy es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="abbce-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="abbce-106">Después de agregar estos registros a GoDaddy, el dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abbce-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="abbce-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="abbce-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="abbce-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="abbce-110">Add a TXT record for verification</span></span>
<span data-ttu-id="abbce-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="abbce-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="abbce-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="abbce-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="abbce-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="abbce-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="abbce-116">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abbce-116">Follow the steps below.</span></span>

1. <span data-ttu-id="abbce-p104">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="abbce-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="abbce-120">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="abbce-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="abbce-122">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-122">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="abbce-124">Elija **TXT (texto)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="abbce-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="abbce-125">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="abbce-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="abbce-126">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="abbce-126">**Record type**</span></span> |<span data-ttu-id="abbce-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="abbce-127">**Host**</span></span>|<span data-ttu-id="abbce-128">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="abbce-128">**TXT Value**</span></span>|<span data-ttu-id="abbce-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="abbce-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="abbce-130">TXT (texto)</span><span class="sxs-lookup"><span data-stu-id="abbce-130">TXT (Text)</span></span>|@|<span data-ttu-id="abbce-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="abbce-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="abbce-132">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="abbce-132">**Note**: This is an example.</span></span> <span data-ttu-id="abbce-133">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="abbce-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="abbce-134">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="abbce-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="abbce-135">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-135">1 hour</span></span>  <br><span data-ttu-id="abbce-136">(Seleccione un valor de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="abbce-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="abbce-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-138">Select **Save**.</span></span>

6. <span data-ttu-id="abbce-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="abbce-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="abbce-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="abbce-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="abbce-141">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="abbce-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="abbce-142">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="abbce-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="abbce-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="abbce-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="abbce-144">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="abbce-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="abbce-145">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="abbce-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="abbce-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="abbce-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="abbce-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="abbce-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="abbce-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="abbce-151">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abbce-151">Follow the steps below.</span></span>

1. <span data-ttu-id="abbce-p108">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="abbce-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="abbce-155">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="abbce-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="abbce-157">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-157">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="abbce-159">Elija **MX (Agente de intercambio de correo)** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="abbce-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="abbce-161">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="abbce-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="abbce-162">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="abbce-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="abbce-163">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="abbce-163">**Record type**</span></span>|<span data-ttu-id="abbce-164">**Host**</span><span class="sxs-lookup"><span data-stu-id="abbce-164">**Host**</span></span>|<span data-ttu-id="abbce-165">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="abbce-165">**Points to**</span></span>|<span data-ttu-id="abbce-166">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="abbce-166">**Priority**</span></span>|<span data-ttu-id="abbce-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="abbce-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="abbce-168">MX (intercambiador de correo)</span><span class="sxs-lookup"><span data-stu-id="abbce-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="abbce-169">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="abbce-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="abbce-170">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abbce-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="abbce-171">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="abbce-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="abbce-172">10  </span><span class="sxs-lookup"><span data-stu-id="abbce-172">10</span></span>  <br/> <span data-ttu-id="abbce-173">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="abbce-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="abbce-174">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="abbce-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="abbce-176">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="abbce-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="abbce-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="abbce-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="abbce-178">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abbce-178">Follow the steps below.</span></span>

1. <span data-ttu-id="abbce-p110">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="abbce-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="abbce-182">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="abbce-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="abbce-184">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-184">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="abbce-186">Elija **CNAME (Alias)** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="abbce-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="abbce-188">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="abbce-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="abbce-189">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="abbce-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="abbce-190">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="abbce-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="abbce-191">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="abbce-191">**Record type**</span></span>|<span data-ttu-id="abbce-192">**Host**</span><span class="sxs-lookup"><span data-stu-id="abbce-192">**Host**</span></span>|<span data-ttu-id="abbce-193">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="abbce-193">**Points to**</span></span>|<span data-ttu-id="abbce-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="abbce-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="abbce-195">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="abbce-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="abbce-196">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="abbce-196">autodiscover</span></span>  <br/> |<span data-ttu-id="abbce-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="abbce-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="abbce-198">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="abbce-199">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="abbce-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="abbce-200">sip</span><span class="sxs-lookup"><span data-stu-id="abbce-200">sip</span></span>  <br/> |<span data-ttu-id="abbce-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="abbce-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="abbce-202">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="abbce-203">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="abbce-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="abbce-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="abbce-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="abbce-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="abbce-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="abbce-206">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="abbce-207">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="abbce-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="abbce-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="abbce-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="abbce-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="abbce-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="abbce-210">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="abbce-211">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="abbce-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="abbce-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="abbce-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="abbce-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="abbce-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="abbce-214">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="abbce-215">Repita estos pasos para agregar el siguiente registro CNAME hasta que haya creado los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="abbce-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="abbce-216">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="abbce-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="abbce-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="abbce-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="abbce-218">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="abbce-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="abbce-219">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="abbce-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="abbce-220">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abbce-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="abbce-221">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="abbce-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="abbce-222">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abbce-222">Follow the steps below.</span></span>

1. <span data-ttu-id="abbce-p112">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="abbce-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="abbce-226">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="abbce-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="abbce-228">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-228">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="abbce-230">Elija **TXT (texto)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="abbce-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="abbce-232">En el cuadro para el nuevo registro, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="abbce-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="abbce-233">(Elija el valor **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="abbce-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="abbce-234">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="abbce-234">**Record type**</span></span>|<span data-ttu-id="abbce-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="abbce-235">**Host**</span></span>|<span data-ttu-id="abbce-236">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="abbce-236">**TXT Value**</span></span>|<span data-ttu-id="abbce-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="abbce-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="abbce-238">TXT (texto)</span><span class="sxs-lookup"><span data-stu-id="abbce-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="abbce-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="abbce-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="abbce-240">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="abbce-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="abbce-241">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="abbce-243">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="abbce-244">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="abbce-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="abbce-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="abbce-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="abbce-246">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abbce-246">Follow the steps below.</span></span>

1. <span data-ttu-id="abbce-p113">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="abbce-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="abbce-250">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="abbce-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="abbce-252">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-252">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="abbce-254">Elija **SRV (Servicio)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="abbce-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="abbce-256">Cree el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="abbce-256">Create the first SRV record.</span></span>

    <span data-ttu-id="abbce-257">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="abbce-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="abbce-258">(Elija los valores **tipo de registro** y **TTL** que se muestran en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="abbce-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="abbce-259">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="abbce-259">**Record type**</span></span>|<span data-ttu-id="abbce-260">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="abbce-260">**Name**</span></span>|<span data-ttu-id="abbce-261">**Destino**</span><span class="sxs-lookup"><span data-stu-id="abbce-261">**Target**</span></span>|<span data-ttu-id="abbce-262">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="abbce-262">**Protocol**</span></span>|<span data-ttu-id="abbce-263">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="abbce-263">**Service**</span></span>|<span data-ttu-id="abbce-264">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="abbce-264">**Priority**</span></span>|<span data-ttu-id="abbce-265">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="abbce-265">**Weight**</span></span>|<span data-ttu-id="abbce-266">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="abbce-266">**Port**</span></span>|<span data-ttu-id="abbce-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="abbce-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="abbce-268">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="abbce-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="abbce-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="abbce-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="abbce-270">_tls</span><span class="sxs-lookup"><span data-stu-id="abbce-270">_tls</span></span>  <br/> |<span data-ttu-id="abbce-271">_sip</span><span class="sxs-lookup"><span data-stu-id="abbce-271">_sip</span></span>  <br/> |<span data-ttu-id="abbce-272">100</span><span class="sxs-lookup"><span data-stu-id="abbce-272">100</span></span>  <br/> |<span data-ttu-id="abbce-273">1</span><span class="sxs-lookup"><span data-stu-id="abbce-273">1</span></span>  <br/> |<span data-ttu-id="abbce-274">443</span><span class="sxs-lookup"><span data-stu-id="abbce-274">443</span></span>  <br/> |<span data-ttu-id="abbce-275">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="abbce-276">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="abbce-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="abbce-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="abbce-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="abbce-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="abbce-278">_tcp</span></span>  <br/> |<span data-ttu-id="abbce-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="abbce-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="abbce-280">100</span><span class="sxs-lookup"><span data-stu-id="abbce-280">100</span></span>  <br/> |<span data-ttu-id="abbce-281">1</span><span class="sxs-lookup"><span data-stu-id="abbce-281">1</span></span>  <br/> |<span data-ttu-id="abbce-282">5061</span><span class="sxs-lookup"><span data-stu-id="abbce-282">5061</span></span>  <br/> |<span data-ttu-id="abbce-283">1 hora</span><span class="sxs-lookup"><span data-stu-id="abbce-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="abbce-285">Repita el **paso 5** para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="abbce-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="abbce-286">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="abbce-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="abbce-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="abbce-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
