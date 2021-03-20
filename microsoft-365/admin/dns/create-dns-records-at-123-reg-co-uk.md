---
title: Crear registros DNS en 123-reg.co.uk microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en 123-reg.co.uk microsoft.
ms.openlocfilehash: d1e4d3d01a5e6b4f72c98fe09cf57374dd2417a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910431"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="87505-103">Crear registros DNS en 123-reg.co.uk microsoft</span><span class="sxs-lookup"><span data-stu-id="87505-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="87505-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="87505-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="87505-105">Si 123-reg.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="87505-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="87505-106">Después de agregar estos registros en 123-reg.co.uk, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87505-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="87505-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="87505-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="87505-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="87505-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="87505-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="87505-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="87505-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="87505-110">Add a TXT record for verification</span></span>
<span data-ttu-id="87505-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="87505-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="87505-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="87505-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87505-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="87505-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="87505-p104">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="87505-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="87505-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="87505-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="87505-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="87505-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="87505-120">En la **página Administrar su DNS,** seleccione la **pestaña DNS** avanzado.</span><span class="sxs-lookup"><span data-stu-id="87505-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="87505-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="87505-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87505-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="87505-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="87505-123">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="87505-123">**Hostname**</span></span> <br/> |<span data-ttu-id="87505-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="87505-124">**Type**</span></span> <br/> |<span data-ttu-id="87505-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="87505-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="87505-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="87505-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="87505-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="87505-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="87505-128">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="87505-128">**Note:** This is an example.</span></span> <span data-ttu-id="87505-129">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="87505-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="87505-130">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="87505-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="87505-131">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87505-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="87505-132">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="87505-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="87505-133">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="87505-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="87505-134">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="87505-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="87505-135">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="87505-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="87505-136">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="87505-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="87505-137">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="87505-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="87505-138">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="87505-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="87505-139">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="87505-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="87505-140">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="87505-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="87505-141">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="87505-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="87505-142">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="87505-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="87505-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="87505-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="87505-p107">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="87505-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="87505-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="87505-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="87505-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="87505-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="87505-148">En la **página Administrar su DNS,** seleccione la **pestaña DNS** avanzado.</span><span class="sxs-lookup"><span data-stu-id="87505-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="87505-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="87505-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87505-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="87505-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="87505-151">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="87505-151">**Hostname**</span></span>|<span data-ttu-id="87505-152">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="87505-152">**Type**</span></span>|<span data-ttu-id="87505-153">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="87505-153">**Priority**</span></span>|<span data-ttu-id="87505-154">**MX de destino**</span><span class="sxs-lookup"><span data-stu-id="87505-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="87505-155">MX</span><span class="sxs-lookup"><span data-stu-id="87505-155">MX</span></span>  <br/> |<span data-ttu-id="87505-156">1</span><span class="sxs-lookup"><span data-stu-id="87505-156">1</span></span>  <br/> <span data-ttu-id="87505-157">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="87505-157">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="87505-158">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="87505-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="87505-159">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="87505-160">**Nota:** Obtenga la \<domain-key\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87505-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="87505-161">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="87505-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar y pegar valores de la tabla](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="87505-163">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87505-163">Select **Add**.</span></span>
    
    ![Captura de pantalla del cuadro de diálogo con el botón Agregar seleccionado](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="87505-165">Si hay otros registros MX, quítelos (para hacerlo, elija el icono **Eliminar [papelera]** de ese registro).</span><span class="sxs-lookup"><span data-stu-id="87505-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Seleccione Eliminar (icono de papelera)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="87505-167">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="87505-167">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="87505-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="87505-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="87505-p109">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="87505-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="87505-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="87505-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="87505-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="87505-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="87505-173">En la **página Administrar su DNS,** seleccione la **pestaña DNS** avanzado.</span><span class="sxs-lookup"><span data-stu-id="87505-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="87505-174">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="87505-174">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="87505-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="87505-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87505-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="87505-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="87505-177">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="87505-177">**Hostname**</span></span>|<span data-ttu-id="87505-178">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="87505-178">**Type**</span></span>|<span data-ttu-id="87505-179">**CNAME de destino**</span><span class="sxs-lookup"><span data-stu-id="87505-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="87505-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="87505-180">autodiscover</span></span>  <br/> |<span data-ttu-id="87505-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="87505-181">CNAME</span></span>  <br/> |<span data-ttu-id="87505-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="87505-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="87505-183">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="87505-184">sip</span><span class="sxs-lookup"><span data-stu-id="87505-184">sip</span></span>  <br/> |<span data-ttu-id="87505-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="87505-185">CNAME</span></span>  <br/> |<span data-ttu-id="87505-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="87505-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="87505-187">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="87505-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="87505-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="87505-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="87505-189">CNAME</span></span>  <br/> |<span data-ttu-id="87505-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="87505-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="87505-191">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="87505-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="87505-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="87505-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="87505-193">CNAME</span></span>  <br/> |<span data-ttu-id="87505-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="87505-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="87505-195">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="87505-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="87505-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="87505-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="87505-197">CNAME</span></span>  <br/> |<span data-ttu-id="87505-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="87505-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="87505-199">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="87505-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Captura de pantalla con CNAME de destino para copiar y pegar](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="87505-201">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87505-201">Select **Add**.</span></span>
    
    ![Captura de pantalla para agregar CNAME de destino](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="87505-203">Agregue los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="87505-203">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="87505-204">En la **sección DNS avanzado,** cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **Agregar** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="87505-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="87505-205">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="87505-205">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="87505-206">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="87505-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="87505-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="87505-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87505-208">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="87505-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="87505-209">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="87505-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="87505-210">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87505-210">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="87505-211">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="87505-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="87505-212">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="87505-212">Need examples?</span></span> <span data-ttu-id="87505-213">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="87505-213">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="87505-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="87505-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="87505-215">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="87505-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="87505-216">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="87505-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="87505-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="87505-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="87505-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="87505-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="87505-219">En la **página Administrar su DNS,** seleccione la **pestaña DNS** avanzado.</span><span class="sxs-lookup"><span data-stu-id="87505-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="87505-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="87505-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87505-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="87505-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="87505-222">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="87505-222">**Hostname**</span></span>|<span data-ttu-id="87505-223">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="87505-223">**Type**</span></span>|<span data-ttu-id="87505-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="87505-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="87505-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="87505-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="87505-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="87505-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="87505-227">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="87505-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="87505-229">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87505-229">Select **Add**.</span></span>
    
    ![Captura de pantalla con TXT/SPF de destino](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="87505-231">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="87505-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="87505-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="87505-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="87505-p112">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="87505-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="87505-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="87505-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="87505-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="87505-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="87505-237">En la **página Administrar su DNS,** seleccione la **pestaña DNS** avanzado.</span><span class="sxs-lookup"><span data-stu-id="87505-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="87505-238">Agregue el primero de los dos registros SRV:</span><span class="sxs-lookup"><span data-stu-id="87505-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="87505-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="87505-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87505-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="87505-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="87505-241">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="87505-241">Hostname</span></span>|<span data-ttu-id="87505-242">Tipo</span><span class="sxs-lookup"><span data-stu-id="87505-242">Type</span></span>|<span data-ttu-id="87505-243">Prioridad</span><span class="sxs-lookup"><span data-stu-id="87505-243">Priority</span></span>|<span data-ttu-id="87505-244">TTL</span><span class="sxs-lookup"><span data-stu-id="87505-244">TTL</span></span>|<span data-ttu-id="87505-245">SRV de destino</span><span class="sxs-lookup"><span data-stu-id="87505-245">Destination SRV</span></span>|
    |<span data-ttu-id="87505-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="87505-246">_sip._tls</span></span>|<span data-ttu-id="87505-247">SRV</span><span class="sxs-lookup"><span data-stu-id="87505-247">SRV</span></span>|<span data-ttu-id="87505-248">100</span><span class="sxs-lookup"><span data-stu-id="87505-248">100</span></span>|<span data-ttu-id="87505-249">3600</span><span class="sxs-lookup"><span data-stu-id="87505-249">3600</span></span>|<span data-ttu-id="87505-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="87505-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="87505-251">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="87505-252">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="87505-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="87505-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="87505-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="87505-254">SRV</span><span class="sxs-lookup"><span data-stu-id="87505-254">SRV</span></span>|<span data-ttu-id="87505-255">100</span><span class="sxs-lookup"><span data-stu-id="87505-255">100</span></span>|<span data-ttu-id="87505-256">3600</span><span class="sxs-lookup"><span data-stu-id="87505-256">3600</span></span>|<span data-ttu-id="87505-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="87505-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="87505-258">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="87505-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="87505-259">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="87505-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Captura de pantalla con valores DNS de la tabla](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="87505-261">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87505-261">Select **Add**.</span></span>
    
    ![Captura de pantalla para agregar SRV de destino](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="87505-263">Para agregar el otro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="87505-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="87505-264">En la **sección DNS** avanzado, cree un registro con los valores de la segunda fila de la tabla y, a continuación, vuelva a seleccionar **Agregar** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="87505-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="87505-265">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="87505-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="87505-266">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="87505-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="87505-267">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="87505-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
