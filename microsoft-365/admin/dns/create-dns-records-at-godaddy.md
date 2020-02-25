---
title: Crear registros DNS en GoDaddy para Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en GoDaddy para Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245373"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="33e9a-103">Crear registros DNS en GoDaddy para Office 365</span><span class="sxs-lookup"><span data-stu-id="33e9a-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="33e9a-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="33e9a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="33e9a-105">Si GoDaddy es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="33e9a-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="33e9a-106">Después de agregar estos registros a GoDaddy, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="33e9a-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="33e9a-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="33e9a-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="33e9a-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="33e9a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="33e9a-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="33e9a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="33e9a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="33e9a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="33e9a-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="33e9a-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="33e9a-117">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33e9a-117">Follow the steps below.</span></span>

1. <span data-ttu-id="33e9a-p104">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="33e9a-121">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="33e9a-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="33e9a-123">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-123">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="33e9a-125">Elija **TXT (texto)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33e9a-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="33e9a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="33e9a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="33e9a-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="33e9a-127">**Record type**</span></span> |<span data-ttu-id="33e9a-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="33e9a-128">**Host**</span></span>|<span data-ttu-id="33e9a-129">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="33e9a-129">**TXT Value**</span></span>|<span data-ttu-id="33e9a-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="33e9a-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="33e9a-131">TXT (texto)</span><span class="sxs-lookup"><span data-stu-id="33e9a-131">TXT (Text)</span></span>|@|<span data-ttu-id="33e9a-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="33e9a-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="33e9a-133">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33e9a-133">**Note**: This is an example.</span></span> <span data-ttu-id="33e9a-134">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="33e9a-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="33e9a-135">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="33e9a-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="33e9a-136">1 hour</span><span class="sxs-lookup"><span data-stu-id="33e9a-136">1 hour</span></span>  <br><span data-ttu-id="33e9a-137">(Seleccione un valor de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="33e9a-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="33e9a-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-139">Select **Save**.</span></span>

6. <span data-ttu-id="33e9a-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="33e9a-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="33e9a-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="33e9a-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="33e9a-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="33e9a-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="33e9a-143">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="33e9a-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="33e9a-144">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="33e9a-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="33e9a-145">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="33e9a-146">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="33e9a-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="33e9a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="33e9a-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="33e9a-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="33e9a-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="33e9a-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="33e9a-152">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33e9a-152">Follow the steps below.</span></span>

1. <span data-ttu-id="33e9a-p108">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="33e9a-156">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="33e9a-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="33e9a-158">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-158">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="33e9a-160">Elija **MX (Agente de intercambio de correo)** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33e9a-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="33e9a-162">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="33e9a-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="33e9a-163">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="33e9a-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="33e9a-164">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="33e9a-164">**Record type**</span></span>|<span data-ttu-id="33e9a-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="33e9a-165">**Host**</span></span>|<span data-ttu-id="33e9a-166">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="33e9a-166">**Points to**</span></span>|<span data-ttu-id="33e9a-167">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="33e9a-167">**Priority**</span></span>|<span data-ttu-id="33e9a-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="33e9a-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="33e9a-169">MX (intercambiador de correo)</span><span class="sxs-lookup"><span data-stu-id="33e9a-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="33e9a-170">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="33e9a-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="33e9a-171">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="33e9a-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="33e9a-172">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="33e9a-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="33e9a-173">10 </span><span class="sxs-lookup"><span data-stu-id="33e9a-173">10</span></span>  <br/> <span data-ttu-id="33e9a-174">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="33e9a-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="33e9a-175">1 hora</span><span class="sxs-lookup"><span data-stu-id="33e9a-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="33e9a-176">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="33e9a-177">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="33e9a-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="33e9a-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="33e9a-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="33e9a-179">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33e9a-179">Follow the steps below.</span></span>

1. <span data-ttu-id="33e9a-p110">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="33e9a-183">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="33e9a-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="33e9a-185">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-185">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="33e9a-187">Elija **CNAME (Alias)** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33e9a-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="33e9a-189">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="33e9a-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="33e9a-190">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="33e9a-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="33e9a-191">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="33e9a-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="33e9a-192">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="33e9a-192">**Record type**</span></span>|<span data-ttu-id="33e9a-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="33e9a-193">**Host**</span></span>|<span data-ttu-id="33e9a-194">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="33e9a-194">**Points to**</span></span>|<span data-ttu-id="33e9a-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="33e9a-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="33e9a-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="33e9a-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="33e9a-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="33e9a-197">autodiscover</span></span>  <br/> |<span data-ttu-id="33e9a-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="33e9a-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="33e9a-199">1 hour</span><span class="sxs-lookup"><span data-stu-id="33e9a-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="33e9a-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="33e9a-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="33e9a-201">sip</span><span class="sxs-lookup"><span data-stu-id="33e9a-201">sip</span></span>  <br/> |<span data-ttu-id="33e9a-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33e9a-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="33e9a-203">1 hora</span><span class="sxs-lookup"><span data-stu-id="33e9a-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="33e9a-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="33e9a-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="33e9a-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="33e9a-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="33e9a-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33e9a-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="33e9a-207">1 hora</span><span class="sxs-lookup"><span data-stu-id="33e9a-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="33e9a-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="33e9a-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="33e9a-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="33e9a-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="33e9a-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="33e9a-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="33e9a-211">1 hora</span><span class="sxs-lookup"><span data-stu-id="33e9a-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="33e9a-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="33e9a-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="33e9a-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="33e9a-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="33e9a-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33e9a-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="33e9a-215">1 hour</span><span class="sxs-lookup"><span data-stu-id="33e9a-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="33e9a-216">Repita estos pasos para agregar el siguiente registro CNAME hasta que haya creado los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="33e9a-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="33e9a-217">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="33e9a-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="33e9a-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="33e9a-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="33e9a-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="33e9a-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="33e9a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="33e9a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="33e9a-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="33e9a-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="33e9a-222">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="33e9a-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="33e9a-223">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33e9a-223">Follow the steps below.</span></span>

1. <span data-ttu-id="33e9a-p112">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="33e9a-227">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="33e9a-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="33e9a-229">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-229">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="33e9a-231">Elija **TXT (texto)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33e9a-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="33e9a-233">En el cuadro para el nuevo registro, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="33e9a-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="33e9a-234">(Elija el valor **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="33e9a-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="33e9a-235">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="33e9a-235">**Record type**</span></span>|<span data-ttu-id="33e9a-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="33e9a-236">**Host**</span></span>|<span data-ttu-id="33e9a-237">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="33e9a-237">**TXT Value**</span></span>|<span data-ttu-id="33e9a-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="33e9a-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="33e9a-239">TXT (texto)</span><span class="sxs-lookup"><span data-stu-id="33e9a-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="33e9a-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="33e9a-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="33e9a-241">**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="33e9a-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="33e9a-242">1 hour</span><span class="sxs-lookup"><span data-stu-id="33e9a-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="33e9a-244">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="33e9a-245">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="33e9a-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="33e9a-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="33e9a-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="33e9a-247">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33e9a-247">Follow the steps below.</span></span>

1. <span data-ttu-id="33e9a-p113">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="33e9a-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="33e9a-251">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="33e9a-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="33e9a-253">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-253">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="33e9a-255">Elija **SRV (Servicio)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33e9a-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="33e9a-257">Cree el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="33e9a-257">Create the first SRV record.</span></span>

    <span data-ttu-id="33e9a-258">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="33e9a-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="33e9a-259">(Elija los valores **tipo de registro** y **TTL** que se muestran en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="33e9a-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="33e9a-260">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="33e9a-260">**Record type**</span></span>|<span data-ttu-id="33e9a-261">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="33e9a-261">**Name**</span></span>|<span data-ttu-id="33e9a-262">**Destino**</span><span class="sxs-lookup"><span data-stu-id="33e9a-262">**Target**</span></span>|<span data-ttu-id="33e9a-263">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="33e9a-263">**Protocol**</span></span>|<span data-ttu-id="33e9a-264">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="33e9a-264">**Service**</span></span>|<span data-ttu-id="33e9a-265">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="33e9a-265">**Priority**</span></span>|<span data-ttu-id="33e9a-266">**Peso**</span><span class="sxs-lookup"><span data-stu-id="33e9a-266">**Weight**</span></span>|<span data-ttu-id="33e9a-267">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="33e9a-267">**Port**</span></span>|<span data-ttu-id="33e9a-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="33e9a-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="33e9a-269">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="33e9a-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="33e9a-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33e9a-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="33e9a-271">_tls</span><span class="sxs-lookup"><span data-stu-id="33e9a-271">_tls</span></span>  <br/> |<span data-ttu-id="33e9a-272">_sip</span><span class="sxs-lookup"><span data-stu-id="33e9a-272">_sip</span></span>  <br/> |<span data-ttu-id="33e9a-273">100</span><span class="sxs-lookup"><span data-stu-id="33e9a-273">100</span></span>  <br/> |<span data-ttu-id="33e9a-274">1</span><span class="sxs-lookup"><span data-stu-id="33e9a-274">1</span></span>  <br/> |<span data-ttu-id="33e9a-275">443</span><span class="sxs-lookup"><span data-stu-id="33e9a-275">443</span></span>  <br/> |<span data-ttu-id="33e9a-276">1 hora</span><span class="sxs-lookup"><span data-stu-id="33e9a-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="33e9a-277">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="33e9a-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="33e9a-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33e9a-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="33e9a-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="33e9a-279">_tcp</span></span>  <br/> |<span data-ttu-id="33e9a-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="33e9a-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="33e9a-281">100</span><span class="sxs-lookup"><span data-stu-id="33e9a-281">100</span></span>  <br/> |<span data-ttu-id="33e9a-282">1</span><span class="sxs-lookup"><span data-stu-id="33e9a-282">1</span></span>  <br/> |<span data-ttu-id="33e9a-283">5061</span><span class="sxs-lookup"><span data-stu-id="33e9a-283">5061</span></span>  <br/> |<span data-ttu-id="33e9a-284">1 hora</span><span class="sxs-lookup"><span data-stu-id="33e9a-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="33e9a-286">Repita el **paso 5** para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="33e9a-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="33e9a-287">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="33e9a-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="33e9a-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="33e9a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
