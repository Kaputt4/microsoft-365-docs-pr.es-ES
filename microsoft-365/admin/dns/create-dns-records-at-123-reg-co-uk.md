---
title: Crear registros DNS en 123-reg.co.uk para Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en 123-reg.co.uk para Microsoft.
ms.openlocfilehash: 51542e1f00153a87ca06ec540d391de6ca621bab
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307036"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="7e102-103">Crear registros DNS en 123-reg.co.uk para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e102-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="7e102-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="7e102-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7e102-105">Si 123-reg.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="7e102-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7e102-106">Después de agregar estos registros a 123-reg.co.uk, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e102-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="7e102-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7e102-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7e102-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="7e102-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e102-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e102-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7e102-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="7e102-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7e102-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7e102-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7e102-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e102-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e102-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="7e102-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7e102-p104">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="7e102-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e102-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="7e102-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7e102-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7e102-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="7e102-120">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="7e102-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="7e102-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e102-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7e102-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7e102-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="7e102-123">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="7e102-123">**Hostname**</span></span> <br/> |<span data-ttu-id="7e102-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e102-124">**Type**</span></span> <br/> |<span data-ttu-id="7e102-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="7e102-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="7e102-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="7e102-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="7e102-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7e102-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7e102-128">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7e102-128">**Note:** This is an example.</span></span> <span data-ttu-id="7e102-129">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="7e102-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7e102-130">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="7e102-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="7e102-131">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e102-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="7e102-132">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="7e102-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7e102-133">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="7e102-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="7e102-134">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e102-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7e102-135">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e102-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7e102-136">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="7e102-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7e102-137">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="7e102-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7e102-138">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="7e102-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7e102-139">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7e102-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7e102-140">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="7e102-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e102-141">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e102-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7e102-142">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e102-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7e102-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7e102-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7e102-p107">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="7e102-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e102-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="7e102-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7e102-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7e102-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="7e102-148">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="7e102-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="7e102-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e102-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7e102-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7e102-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7e102-151">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="7e102-151">**Hostname**</span></span>|<span data-ttu-id="7e102-152">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e102-152">**Type**</span></span>|<span data-ttu-id="7e102-153">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="7e102-153">**Priority**</span></span>|<span data-ttu-id="7e102-154">**MX de destino**</span><span class="sxs-lookup"><span data-stu-id="7e102-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7e102-155">MX</span><span class="sxs-lookup"><span data-stu-id="7e102-155">MX</span></span>  <br/> |<span data-ttu-id="7e102-156">1 </span><span class="sxs-lookup"><span data-stu-id="7e102-156">1</span></span>  <br/> <span data-ttu-id="7e102-157">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="7e102-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="7e102-158">*\<domain-key\>*  . mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7e102-159">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7e102-160">\*\*Nota: \*\* Obtenga la \<domain-key\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e102-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="7e102-161">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="7e102-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar y pegar valores de la tabla](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="7e102-163">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e102-163">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="7e102-165">Si hay otros registros MX, quítelos (para hacerlo, elija el icono **Eliminar [papelera]** de ese registro).</span><span class="sxs-lookup"><span data-stu-id="7e102-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Seleccione Eliminar (el icono de la papelera)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7e102-167">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e102-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7e102-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7e102-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7e102-p109">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="7e102-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e102-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="7e102-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7e102-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7e102-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="7e102-173">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="7e102-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="7e102-174">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7e102-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7e102-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e102-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7e102-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7e102-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7e102-177">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="7e102-177">**Hostname**</span></span>|<span data-ttu-id="7e102-178">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e102-178">**Type**</span></span>|<span data-ttu-id="7e102-179">**CNAME de destino**</span><span class="sxs-lookup"><span data-stu-id="7e102-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7e102-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7e102-180">autodiscover</span></span>  <br/> |<span data-ttu-id="7e102-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e102-181">CNAME</span></span>  <br/> |<span data-ttu-id="7e102-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7e102-183">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e102-184">sip</span><span class="sxs-lookup"><span data-stu-id="7e102-184">sip</span></span>  <br/> |<span data-ttu-id="7e102-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e102-185">CNAME</span></span>  <br/> |<span data-ttu-id="7e102-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7e102-187">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e102-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7e102-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7e102-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e102-189">CNAME</span></span>  <br/> |<span data-ttu-id="7e102-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7e102-191">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e102-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7e102-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7e102-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e102-193">CNAME</span></span>  <br/> |<span data-ttu-id="7e102-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7e102-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7e102-195">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e102-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7e102-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7e102-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e102-197">CNAME</span></span>  <br/> |<span data-ttu-id="7e102-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7e102-199">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7e102-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="7e102-201">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e102-201">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="7e102-203">Cree los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7e102-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="7e102-204">En la sección **DNS avanzado** , cree un registro con los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="7e102-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="7e102-205">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7e102-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7e102-206">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7e102-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7e102-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7e102-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e102-208">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="7e102-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7e102-209">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7e102-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7e102-210">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsfot.</span><span class="sxs-lookup"><span data-stu-id="7e102-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="7e102-211">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="7e102-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="7e102-212">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="7e102-212">Need examples?</span></span> <span data-ttu-id="7e102-213">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="7e102-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="7e102-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="7e102-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="7e102-215">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="7e102-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="7e102-216">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="7e102-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e102-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="7e102-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7e102-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7e102-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="7e102-219">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="7e102-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="7e102-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e102-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7e102-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7e102-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7e102-222">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="7e102-222">**Hostname**</span></span>|<span data-ttu-id="7e102-223">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e102-223">**Type**</span></span>|<span data-ttu-id="7e102-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="7e102-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7e102-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="7e102-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="7e102-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7e102-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7e102-227">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="7e102-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="7e102-229">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e102-229">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7e102-231">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e102-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7e102-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7e102-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7e102-p112">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="7e102-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e102-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="7e102-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7e102-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7e102-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="7e102-237">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="7e102-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="7e102-238">Agregue el primero de los dos registros SRV:</span><span class="sxs-lookup"><span data-stu-id="7e102-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="7e102-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e102-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7e102-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7e102-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e102-241">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="7e102-241">Hostname</span></span>|<span data-ttu-id="7e102-242">Tipo</span><span class="sxs-lookup"><span data-stu-id="7e102-242">Type</span></span>|<span data-ttu-id="7e102-243">Prioridad</span><span class="sxs-lookup"><span data-stu-id="7e102-243">Priority</span></span>|<span data-ttu-id="7e102-244">TTL</span><span class="sxs-lookup"><span data-stu-id="7e102-244">TTL</span></span>|<span data-ttu-id="7e102-245">SRV de destino</span><span class="sxs-lookup"><span data-stu-id="7e102-245">Destination SRV</span></span>|
    |<span data-ttu-id="7e102-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7e102-246">_sip._tls</span></span>|<span data-ttu-id="7e102-247">SRV</span><span class="sxs-lookup"><span data-stu-id="7e102-247">SRV</span></span>|<span data-ttu-id="7e102-248">100</span><span class="sxs-lookup"><span data-stu-id="7e102-248">100</span></span>|<span data-ttu-id="7e102-249">3600</span><span class="sxs-lookup"><span data-stu-id="7e102-249">3600</span></span>|<span data-ttu-id="7e102-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="7e102-251">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="7e102-252">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="7e102-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="7e102-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7e102-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7e102-254">SRV</span><span class="sxs-lookup"><span data-stu-id="7e102-254">SRV</span></span>|<span data-ttu-id="7e102-255">100</span><span class="sxs-lookup"><span data-stu-id="7e102-255">100</span></span>|<span data-ttu-id="7e102-256">3600</span><span class="sxs-lookup"><span data-stu-id="7e102-256">3600</span></span>|<span data-ttu-id="7e102-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e102-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="7e102-258">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="7e102-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="7e102-259">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="7e102-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar y pegar los valores de la tabla](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="7e102-261">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e102-261">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="7e102-263">Para agregar el otro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="7e102-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="7e102-264">En la sección **DNS avanzado** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="7e102-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7e102-265">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7e102-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7e102-266">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="7e102-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e102-267">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e102-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
