---
title: Crear registros DNS en 123-reg.co.uk para Office 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en 123-reg.co.uk para Office 365.
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211864"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="1c283-103">Crear registros DNS en 123-reg.co.uk para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c283-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="1c283-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="1c283-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1c283-105">Si 123-reg.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="1c283-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1c283-106">Después de agregar estos registros a 123-reg.co.uk, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c283-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="1c283-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="1c283-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c283-108">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="1c283-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1c283-109">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="1c283-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1c283-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1c283-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1c283-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="1c283-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1c283-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1c283-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1c283-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="1c283-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c283-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="1c283-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1c283-117">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="1c283-117">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="1c283-118">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="1c283-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c283-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1c283-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1c283-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1c283-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1c283-121">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="1c283-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1c283-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c283-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1c283-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1c283-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1c283-124">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="1c283-124">**Hostname**</span></span> <br/> |<span data-ttu-id="1c283-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c283-125">**Type**</span></span> <br/> |<span data-ttu-id="1c283-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="1c283-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="1c283-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="1c283-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="1c283-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1c283-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1c283-129">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1c283-129">**Note:** This is an example.</span></span> <span data-ttu-id="1c283-130">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c283-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="1c283-131">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="1c283-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="1c283-132">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c283-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="1c283-133">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="1c283-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1c283-134">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="1c283-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="1c283-135">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="1c283-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1c283-136">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="1c283-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1c283-137">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="1c283-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1c283-138">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="1c283-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1c283-139">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="1c283-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1c283-140">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="1c283-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1c283-141">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="1c283-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1c283-142">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1c283-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="1c283-143">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="1c283-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="1c283-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1c283-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1c283-p107">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="1c283-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c283-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1c283-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1c283-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1c283-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1c283-149">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="1c283-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1c283-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c283-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1c283-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1c283-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c283-152">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="1c283-152">**Hostname**</span></span>|<span data-ttu-id="1c283-153">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c283-153">**Type**</span></span>|<span data-ttu-id="1c283-154">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="1c283-154">**Priority**</span></span>|<span data-ttu-id="1c283-155">**MX de destino**</span><span class="sxs-lookup"><span data-stu-id="1c283-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1c283-156">MX</span><span class="sxs-lookup"><span data-stu-id="1c283-156">MX</span></span>  <br/> |<span data-ttu-id="1c283-157">1</span><span class="sxs-lookup"><span data-stu-id="1c283-157">1</span></span>  <br/> <span data-ttu-id="1c283-158">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="1c283-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="1c283-159">*\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1c283-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1c283-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1c283-161">**Nota:** Obtenga la \<clave-de-dominio\> desde su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c283-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="1c283-162">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="1c283-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar y pegar valores de la tabla](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="1c283-164">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c283-164">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="1c283-166">Si hay otros registros MX, quítelos (para hacerlo, elija el icono **Eliminar [papelera]** de ese registro).</span><span class="sxs-lookup"><span data-stu-id="1c283-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Seleccione Eliminar (el icono de la papelera)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="1c283-168">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c283-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="1c283-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1c283-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1c283-p109">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="1c283-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c283-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1c283-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1c283-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1c283-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1c283-174">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="1c283-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1c283-175">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1c283-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="1c283-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c283-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1c283-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1c283-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c283-178">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="1c283-178">**Hostname**</span></span>|<span data-ttu-id="1c283-179">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c283-179">**Type**</span></span>|<span data-ttu-id="1c283-180">**CNAME de destino**</span><span class="sxs-lookup"><span data-stu-id="1c283-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1c283-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1c283-181">autodiscover</span></span>  <br/> |<span data-ttu-id="1c283-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c283-182">CNAME</span></span>  <br/> |<span data-ttu-id="1c283-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1c283-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1c283-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1c283-185">sip</span><span class="sxs-lookup"><span data-stu-id="1c283-185">sip</span></span>  <br/> |<span data-ttu-id="1c283-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c283-186">CNAME</span></span>  <br/> |<span data-ttu-id="1c283-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1c283-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1c283-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1c283-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1c283-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1c283-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c283-190">CNAME</span></span>  <br/> |<span data-ttu-id="1c283-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1c283-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1c283-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1c283-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1c283-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1c283-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c283-194">CNAME</span></span>  <br/> |<span data-ttu-id="1c283-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1c283-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1c283-196">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="1c283-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1c283-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1c283-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1c283-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c283-198">CNAME</span></span>  <br/> |<span data-ttu-id="1c283-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1c283-200">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="1c283-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="1c283-202">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c283-202">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="1c283-204">Cree los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1c283-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="1c283-205">En la sección **DNS avanzado** , cree un registro con los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="1c283-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="1c283-206">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1c283-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1c283-207">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="1c283-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1c283-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1c283-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c283-209">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="1c283-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1c283-210">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1c283-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1c283-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c283-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="1c283-212">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="1c283-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1c283-213">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="1c283-213">Need examples?</span></span> <span data-ttu-id="1c283-214">Consulte los [Registros externos del sistema de nombres de dominio para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="1c283-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="1c283-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="1c283-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="1c283-216">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="1c283-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="1c283-217">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="1c283-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c283-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1c283-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1c283-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1c283-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1c283-220">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="1c283-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1c283-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c283-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1c283-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1c283-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c283-223">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="1c283-223">**Hostname**</span></span>|<span data-ttu-id="1c283-224">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c283-224">**Type**</span></span>|<span data-ttu-id="1c283-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="1c283-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1c283-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="1c283-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="1c283-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1c283-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1c283-228">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1c283-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="1c283-230">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c283-230">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="1c283-232">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c283-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="1c283-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1c283-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1c283-p112">Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="1c283-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c283-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1c283-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1c283-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1c283-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1c283-238">En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** .</span><span class="sxs-lookup"><span data-stu-id="1c283-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1c283-239">Agregue el primero de los dos registros SRV:</span><span class="sxs-lookup"><span data-stu-id="1c283-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="1c283-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c283-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1c283-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1c283-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1c283-242">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="1c283-242">Hostname</span></span>|<span data-ttu-id="1c283-243">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c283-243">Type</span></span>|<span data-ttu-id="1c283-244">Prioridad</span><span class="sxs-lookup"><span data-stu-id="1c283-244">Priority</span></span>|<span data-ttu-id="1c283-245">TTL</span><span class="sxs-lookup"><span data-stu-id="1c283-245">TTL</span></span>|<span data-ttu-id="1c283-246">SRV de destino</span><span class="sxs-lookup"><span data-stu-id="1c283-246">Destination SRV</span></span>|
    |<span data-ttu-id="1c283-247">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="1c283-247">_sip._tls</span></span>|<span data-ttu-id="1c283-248">SRV</span><span class="sxs-lookup"><span data-stu-id="1c283-248">SRV</span></span>|<span data-ttu-id="1c283-249">100</span><span class="sxs-lookup"><span data-stu-id="1c283-249">100</span></span>|<span data-ttu-id="1c283-250">3600</span><span class="sxs-lookup"><span data-stu-id="1c283-250">3600</span></span>|<span data-ttu-id="1c283-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="1c283-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1c283-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="1c283-253">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1c283-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="1c283-254">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="1c283-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1c283-255">SRV</span><span class="sxs-lookup"><span data-stu-id="1c283-255">SRV</span></span>|<span data-ttu-id="1c283-256">100</span><span class="sxs-lookup"><span data-stu-id="1c283-256">100</span></span>|<span data-ttu-id="1c283-257">3600</span><span class="sxs-lookup"><span data-stu-id="1c283-257">3600</span></span>|<span data-ttu-id="1c283-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c283-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="1c283-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1c283-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="1c283-260">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1c283-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar y pegar los valores de la tabla](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="1c283-262">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c283-262">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="1c283-264">Para agregar el otro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="1c283-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="1c283-265">En la sección **DNS avanzado** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="1c283-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1c283-266">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="1c283-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1c283-267">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="1c283-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1c283-268">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1c283-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
