---
title: Crear registros DNS en GoDaddy para Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en GoDaddy para Office 365.
ms.custom: okr_smb
ms.openlocfilehash: eceab4659dfc01d6a731c4ed07f27bb29214e5fb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211744"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="1a1b9-103">Crear registros DNS en GoDaddy para Office 365</span><span class="sxs-lookup"><span data-stu-id="1a1b9-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="1a1b9-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="1a1b9-105">Si GoDaddy es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="1a1b9-106">Después de agregar estos registros a GoDaddy, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="1a1b9-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="1a1b9-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1a1b9-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="1a1b9-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1a1b9-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1a1b9-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1a1b9-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="1a1b9-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="1a1b9-117">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-117">Follow the steps below.</span></span>

1. <span data-ttu-id="1a1b9-p104">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1a1b9-121">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1a1b9-123">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-123">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1a1b9-125">Elija **TXT (texto)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="1a1b9-126">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="1a1b9-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-127">**Record type**</span></span> |<span data-ttu-id="1a1b9-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-128">**Host**</span></span>|<span data-ttu-id="1a1b9-129">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-129">**TXT Value**</span></span>|<span data-ttu-id="1a1b9-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1a1b9-131">TXT (texto)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-131">TXT (Text)</span></span>|@|<span data-ttu-id="1a1b9-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1a1b9-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="1a1b9-133">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-133">**Note**: This is an example.</span></span> <span data-ttu-id="1a1b9-134">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="1a1b9-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="1a1b9-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="1a1b9-136">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-136">1 hour</span></span>  <br><span data-ttu-id="1a1b9-137">(Seleccione un valor de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="1a1b9-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-139">Select **Save**.</span></span>

6. <span data-ttu-id="1a1b9-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="1a1b9-141">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="1a1b9-142">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1a1b9-143">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1a1b9-144">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1a1b9-145">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="1a1b9-146">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="1a1b9-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="1a1b9-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="1a1b9-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="1a1b9-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1a1b9-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1a1b9-152">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-152">Follow the steps below.</span></span>

1. <span data-ttu-id="1a1b9-p108">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1a1b9-156">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1a1b9-158">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-158">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1a1b9-160">Elija **MX (Agente de intercambio de correo)** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="1a1b9-162">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="1a1b9-163">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="1a1b9-164">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-164">**Record type**</span></span>|<span data-ttu-id="1a1b9-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-165">**Host**</span></span>|<span data-ttu-id="1a1b9-166">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-166">**Points to**</span></span>|<span data-ttu-id="1a1b9-167">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-167">**Priority**</span></span>|<span data-ttu-id="1a1b9-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1a1b9-169">MX (intercambiador de correo)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="1a1b9-170">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="1a1b9-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1a1b9-171">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="1a1b9-172">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="1a1b9-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1a1b9-173">10 </span><span class="sxs-lookup"><span data-stu-id="1a1b9-173">10</span></span>  <br/> <span data-ttu-id="1a1b9-174">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="1a1b9-175">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="1a1b9-176">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="1a1b9-177">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="1a1b9-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="1a1b9-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1a1b9-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1a1b9-179">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-179">Follow the steps below.</span></span>

1. <span data-ttu-id="1a1b9-p110">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1a1b9-183">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1a1b9-185">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-185">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="1a1b9-187">Elija **CNAME (Alias)** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="1a1b9-189">Cree el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="1a1b9-190">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="1a1b9-191">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="1a1b9-192">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-192">**Record type**</span></span>|<span data-ttu-id="1a1b9-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-193">**Host**</span></span>|<span data-ttu-id="1a1b9-194">**Señala a**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-194">**Points to**</span></span>|<span data-ttu-id="1a1b9-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1a1b9-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1a1b9-197">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="1a1b9-197">autodiscover</span></span>  <br/> |<span data-ttu-id="1a1b9-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1a1b9-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="1a1b9-199">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1a1b9-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1a1b9-201">sip</span><span class="sxs-lookup"><span data-stu-id="1a1b9-201">sip</span></span>  <br/> |<span data-ttu-id="1a1b9-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1a1b9-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1a1b9-203">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1a1b9-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1a1b9-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1a1b9-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1a1b9-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1a1b9-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1a1b9-207">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1a1b9-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1a1b9-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1a1b9-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1a1b9-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1a1b9-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="1a1b9-211">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1a1b9-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1a1b9-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1a1b9-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1a1b9-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1a1b9-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="1a1b9-215">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="1a1b9-216">Repita estos pasos para agregar el siguiente registro CNAME hasta que haya creado los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1a1b9-217">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="1a1b9-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1a1b9-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1a1b9-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a1b9-219">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1a1b9-220">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1a1b9-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="1a1b9-222">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="1a1b9-223">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-223">Follow the steps below.</span></span>

1. <span data-ttu-id="1a1b9-p112">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1a1b9-227">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1a1b9-229">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-229">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1a1b9-231">Elija **TXT (texto)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="1a1b9-233">En el cuadro para el nuevo registro, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="1a1b9-234">(Elija el valor **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="1a1b9-235">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-235">**Record type**</span></span>|<span data-ttu-id="1a1b9-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-236">**Host**</span></span>|<span data-ttu-id="1a1b9-237">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-237">**TXT Value**</span></span>|<span data-ttu-id="1a1b9-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1a1b9-239">TXT (texto)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="1a1b9-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1a1b9-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1a1b9-241">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1a1b9-242">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="1a1b9-244">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="1a1b9-245">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="1a1b9-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="1a1b9-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1a1b9-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1a1b9-247">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-247">Follow the steps below.</span></span>

1. <span data-ttu-id="1a1b9-p113">Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1a1b9-251">En **dominios**, seleccione DNS en el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1a1b9-253">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-253">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1a1b9-255">Elija **SRV (Servicio)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="1a1b9-257">Cree el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-257">Create the first SRV record.</span></span>

    <span data-ttu-id="1a1b9-258">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="1a1b9-259">(Elija los valores **tipo de registro** y **TTL** que se muestran en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="1a1b9-260">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-260">**Record type**</span></span>|<span data-ttu-id="1a1b9-261">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-261">**Name**</span></span>|<span data-ttu-id="1a1b9-262">**Destino**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-262">**Target**</span></span>|<span data-ttu-id="1a1b9-263">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-263">**Protocol**</span></span>|<span data-ttu-id="1a1b9-264">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-264">**Service**</span></span>|<span data-ttu-id="1a1b9-265">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-265">**Priority**</span></span>|<span data-ttu-id="1a1b9-266">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-266">**Weight**</span></span>|<span data-ttu-id="1a1b9-267">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-267">**Port**</span></span>|<span data-ttu-id="1a1b9-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1a1b9-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1a1b9-269">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="1a1b9-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1a1b9-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1a1b9-271">_tls</span><span class="sxs-lookup"><span data-stu-id="1a1b9-271">_tls</span></span>  <br/> |<span data-ttu-id="1a1b9-272">_sip</span><span class="sxs-lookup"><span data-stu-id="1a1b9-272">_sip</span></span>  <br/> |<span data-ttu-id="1a1b9-273">100</span><span class="sxs-lookup"><span data-stu-id="1a1b9-273">100</span></span>  <br/> |<span data-ttu-id="1a1b9-274">1</span><span class="sxs-lookup"><span data-stu-id="1a1b9-274">1</span></span>  <br/> |<span data-ttu-id="1a1b9-275">443</span><span class="sxs-lookup"><span data-stu-id="1a1b9-275">443</span></span>  <br/> |<span data-ttu-id="1a1b9-276">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1a1b9-277">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="1a1b9-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="1a1b9-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1a1b9-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="1a1b9-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="1a1b9-279">_tcp</span></span>  <br/> |<span data-ttu-id="1a1b9-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1a1b9-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="1a1b9-281">100</span><span class="sxs-lookup"><span data-stu-id="1a1b9-281">100</span></span>  <br/> |<span data-ttu-id="1a1b9-282">1</span><span class="sxs-lookup"><span data-stu-id="1a1b9-282">1</span></span>  <br/> |<span data-ttu-id="1a1b9-283">5061</span><span class="sxs-lookup"><span data-stu-id="1a1b9-283">5061</span></span>  <br/> |<span data-ttu-id="1a1b9-284">1 hora</span><span class="sxs-lookup"><span data-stu-id="1a1b9-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="1a1b9-286">Repita el **paso 5** para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="1a1b9-287">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1a1b9-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a1b9-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1a1b9-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
