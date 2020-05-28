---
title: Crear registros DNS en DNSMadeEasy para Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en DNSMadeEasy para Microsoft.
ms.openlocfilehash: db28ac0cb95bd86bc13a1a1ce47f273989aa4436
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400526"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="c52bc-103">Crear registros DNS en DNSMadeEasy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="c52bc-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="c52bc-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="c52bc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c52bc-105">Si DNSMadeEasy es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="c52bc-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c52bc-106">Después de agregar estos registros a DNSMadeEasy, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c52bc-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="c52bc-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="c52bc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c52bc-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="c52bc-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c52bc-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c52bc-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c52bc-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="c52bc-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c52bc-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c52bc-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c52bc-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="c52bc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c52bc-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="c52bc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c52bc-116">Para las cuentas de DNSMadeEasy, el dominio que agregó se compró de un registrador de dominios separado.</span><span class="sxs-lookup"><span data-stu-id="c52bc-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="c52bc-117">DNSMadeEasy no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="c52bc-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="c52bc-118">Su capacidad para iniciar sesión en DNSMadeEasy y crear el registro DNS es una prueba suficiente de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="c52bc-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="c52bc-119">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="c52bc-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c52bc-120">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c52bc-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c52bc-121">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c52bc-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c52bc-122">En la página **DNS administrados** , en el área **registros txt** , seleccione el **+** control () ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="c52bc-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="c52bc-123">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c52bc-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="c52bc-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c52bc-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="c52bc-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="c52bc-125">**Name**</span></span> <br/> |<span data-ttu-id="c52bc-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c52bc-126">**Value**</span></span> <br/> |<span data-ttu-id="c52bc-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c52bc-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="c52bc-128">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="c52bc-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c52bc-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c52bc-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c52bc-130">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c52bc-130">**Note:** This is an example.</span></span> <span data-ttu-id="c52bc-131">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="c52bc-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c52bc-132">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="c52bc-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c52bc-133">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="c52bc-134">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="c52bc-135">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="c52bc-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c52bc-136">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="c52bc-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c52bc-137">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="c52bc-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c52bc-138">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="c52bc-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c52bc-139">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="c52bc-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c52bc-140">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="c52bc-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c52bc-141">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c52bc-142">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="c52bc-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c52bc-143">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="c52bc-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c52bc-144">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c52bc-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c52bc-145">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c52bc-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c52bc-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c52bc-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c52bc-p108">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c52bc-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c52bc-149">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c52bc-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="c52bc-150">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c52bc-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="c52bc-152">En la página **DNS administrados** , en el área **registros MX** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="c52bc-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c52bc-153">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c52bc-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="c52bc-155">En el área **Agregar registros MX**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c52bc-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c52bc-156">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="c52bc-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="c52bc-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="c52bc-157">**Name**</span></span>|<span data-ttu-id="c52bc-158">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="c52bc-158">**Server**</span></span>|<span data-ttu-id="c52bc-159">**Nivel de MX**</span><span class="sxs-lookup"><span data-stu-id="c52bc-159">**MX Level**</span></span>|<span data-ttu-id="c52bc-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c52bc-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c52bc-161">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="c52bc-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="c52bc-162">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c52bc-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c52bc-163">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c52bc-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="c52bc-164">**Nota:** Obtén tu \<*domain-key*\> cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c52bc-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="c52bc-165">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="c52bc-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c52bc-166">10  </span><span class="sxs-lookup"><span data-stu-id="c52bc-166">10</span></span>  <br/> <span data-ttu-id="c52bc-167">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="c52bc-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="c52bc-168">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="c52bc-170">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="c52bc-172">Si en la sección **Registros MX** se muestran otros registros MX, selecciónelos para eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="c52bc-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="c52bc-174">Una vez seleccionados todos los registros, seleccione **eliminar seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="c52bc-176">En el cuadro de diálogo **eliminar registros MX** , seleccione **eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c52bc-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c52bc-178">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="c52bc-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c52bc-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c52bc-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c52bc-p110">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c52bc-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c52bc-182">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c52bc-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c52bc-183">En la página **DNS administrados** , en el área **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="c52bc-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c52bc-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c52bc-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="c52bc-186">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c52bc-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="c52bc-187">En el área **Agregar registros CNAME**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c52bc-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="c52bc-188">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c52bc-188">**Name**</span></span>|<span data-ttu-id="c52bc-189">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="c52bc-189">**Alias to**</span></span>|<span data-ttu-id="c52bc-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c52bc-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c52bc-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c52bc-191">autodiscover</span></span>  <br/> |<span data-ttu-id="c52bc-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c52bc-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="c52bc-193">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-194">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-194">1800</span></span>  <br/> |
    |<span data-ttu-id="c52bc-195">sip</span><span class="sxs-lookup"><span data-stu-id="c52bc-195">sip</span></span>  <br/> |<span data-ttu-id="c52bc-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c52bc-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c52bc-197">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-198">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-198">1800</span></span>  <br/> |
    |<span data-ttu-id="c52bc-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c52bc-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c52bc-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c52bc-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c52bc-201">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-202">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-202">1800</span></span>  <br/> |
    |<span data-ttu-id="c52bc-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c52bc-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c52bc-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="c52bc-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="c52bc-205">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-206">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-206">1800</span></span>  <br/> |
    |<span data-ttu-id="c52bc-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c52bc-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c52bc-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c52bc-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="c52bc-209">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-210">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="c52bc-212">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="c52bc-214">Agregue cada uno de los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c52bc-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="c52bc-215">En la sección **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="c52bc-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="c52bc-216">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c52bc-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c52bc-217">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c52bc-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c52bc-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c52bc-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c52bc-219">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="c52bc-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c52bc-220">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c52bc-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c52bc-221">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c52bc-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c52bc-222">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="c52bc-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="c52bc-223">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="c52bc-223">Need examples?</span></span> <span data-ttu-id="c52bc-224">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="c52bc-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="c52bc-225">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="c52bc-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="c52bc-226">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="c52bc-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c52bc-227">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c52bc-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c52bc-228">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c52bc-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c52bc-229">En la página **DNS administrados** , en el área **registros txt** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="c52bc-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c52bc-230">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="c52bc-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="c52bc-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c52bc-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="c52bc-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="c52bc-233">**Name**</span></span>|<span data-ttu-id="c52bc-234">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c52bc-234">**Value**</span></span>|<span data-ttu-id="c52bc-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c52bc-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c52bc-236">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="c52bc-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c52bc-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c52bc-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c52bc-238">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="c52bc-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c52bc-239">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="c52bc-241">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c52bc-243">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="c52bc-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c52bc-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c52bc-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c52bc-p113">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c52bc-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c52bc-247">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c52bc-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c52bc-248">En la página **DNS administrados** , en el área **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="c52bc-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c52bc-249">(Puede que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="c52bc-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="c52bc-251">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="c52bc-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="c52bc-252">En el área **Agregar registros SRV**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c52bc-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="c52bc-253">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c52bc-253">**Name**</span></span>|<span data-ttu-id="c52bc-254">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="c52bc-254">**Priority**</span></span>|<span data-ttu-id="c52bc-255">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="c52bc-255">**Weight**</span></span>|<span data-ttu-id="c52bc-256">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="c52bc-256">**Port**</span></span>|<span data-ttu-id="c52bc-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="c52bc-257">**Host**</span></span>|<span data-ttu-id="c52bc-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c52bc-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c52bc-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="c52bc-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="c52bc-260">100</span><span class="sxs-lookup"><span data-stu-id="c52bc-260">100</span></span>  <br/> |<span data-ttu-id="c52bc-261">1 </span><span class="sxs-lookup"><span data-stu-id="c52bc-261">1</span></span>  <br/> |<span data-ttu-id="c52bc-262">443</span><span class="sxs-lookup"><span data-stu-id="c52bc-262">443</span></span>  <br/> |<span data-ttu-id="c52bc-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c52bc-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c52bc-264">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-265">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-265">1800</span></span>  <br/> |
    |<span data-ttu-id="c52bc-266">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="c52bc-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="c52bc-267">100</span><span class="sxs-lookup"><span data-stu-id="c52bc-267">100</span></span>  <br/> |<span data-ttu-id="c52bc-268">1 </span><span class="sxs-lookup"><span data-stu-id="c52bc-268">1</span></span>  <br/> |<span data-ttu-id="c52bc-269">5061</span><span class="sxs-lookup"><span data-stu-id="c52bc-269">5061</span></span>  <br/> |<span data-ttu-id="c52bc-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c52bc-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="c52bc-271">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c52bc-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c52bc-272">1800</span><span class="sxs-lookup"><span data-stu-id="c52bc-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="c52bc-274">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c52bc-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="c52bc-276">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="c52bc-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="c52bc-277">En la sección **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="c52bc-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c52bc-278">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="c52bc-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c52bc-279">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="c52bc-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c52bc-280">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c52bc-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

