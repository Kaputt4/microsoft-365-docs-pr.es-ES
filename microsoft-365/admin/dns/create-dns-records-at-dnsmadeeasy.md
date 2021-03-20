---
title: Crear registros DNS en DNSMadeEasy para Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en DNSMadeEasy para Microsoft.
ms.openlocfilehash: 11e8072ab3c798ed550043370d0e6e79c7370b4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910395"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="9ab96-103">Crear registros DNS en DNSMadeEasy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ab96-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="9ab96-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9ab96-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9ab96-105">Si DNSMadeEasy es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="9ab96-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9ab96-106">Después de agregar estos registros en DNSMadeEasy, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ab96-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="9ab96-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9ab96-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9ab96-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9ab96-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ab96-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ab96-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9ab96-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="9ab96-110">Add a TXT record for verification</span></span>
<span data-ttu-id="9ab96-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab96-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9ab96-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab96-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ab96-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="9ab96-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9ab96-116">Para las cuentas de DNSMadeEasy, el dominio que agregó se compró de un registrador de dominios separado.</span><span class="sxs-lookup"><span data-stu-id="9ab96-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="9ab96-117">DNSMadeEasy no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="9ab96-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="9ab96-118">Su capacidad para iniciar sesión en DNSMadeEasy y crear el registro DNS es una prueba suficiente de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="9ab96-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="9ab96-119">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="9ab96-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="9ab96-120">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="9ab96-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9ab96-121">En la **página Consola de** administración, en el área Dominios **actualizados** recientemente, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ab96-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9ab96-122">En la **página DNS administrado,** en el área **Registros TXT,** seleccione el control ( **+** ) ( Agregar **nuevo**).</span><span class="sxs-lookup"><span data-stu-id="9ab96-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="9ab96-123">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab96-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="9ab96-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9ab96-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="9ab96-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="9ab96-125">**Name**</span></span> <br/> |<span data-ttu-id="9ab96-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9ab96-126">**Value**</span></span> <br/> |<span data-ttu-id="9ab96-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9ab96-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="9ab96-128">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9ab96-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9ab96-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9ab96-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9ab96-130">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ab96-130">**Note:** This is an example.</span></span> <span data-ttu-id="9ab96-131">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ab96-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9ab96-132">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9ab96-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9ab96-133">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="9ab96-134">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="9ab96-135">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="9ab96-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9ab96-136">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="9ab96-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9ab96-137">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab96-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9ab96-138">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="9ab96-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9ab96-139">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="9ab96-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9ab96-140">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9ab96-141">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9ab96-142">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9ab96-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9ab96-143">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9ab96-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ab96-144">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ab96-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9ab96-145">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ab96-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9ab96-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab96-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9ab96-p108">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="9ab96-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9ab96-149">En la **página Consola de** administración, en el área Dominios **actualizados** recientemente, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ab96-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="9ab96-150">En la **página Consola de** administración, en el área Dominios **actualizados** recientemente, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ab96-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="9ab96-152">En la **página DNS administrado,** en el área **Registros MX,** seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="9ab96-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9ab96-153">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab96-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="9ab96-155">En el área **Agregar registros MX**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ab96-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9ab96-156">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab96-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="9ab96-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="9ab96-157">**Name**</span></span>|<span data-ttu-id="9ab96-158">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="9ab96-158">**Server**</span></span>|<span data-ttu-id="9ab96-159">**Nivel de MX**</span><span class="sxs-lookup"><span data-stu-id="9ab96-159">**MX Level**</span></span>|<span data-ttu-id="9ab96-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9ab96-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9ab96-161">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9ab96-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="9ab96-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9ab96-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9ab96-163">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9ab96-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="9ab96-164">**Nota:** Obtenga la \<*domain-key*\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ab96-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="9ab96-165">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9ab96-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9ab96-166">10  </span><span class="sxs-lookup"><span data-stu-id="9ab96-166">10</span></span>  <br/> <span data-ttu-id="9ab96-167">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="9ab96-167">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="9ab96-168">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="9ab96-170">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="9ab96-172">Si en la sección **Registros MX** se muestran otros registros MX, selecciónelos para eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="9ab96-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="9ab96-174">Cuando todos los registros estén seleccionados, **seleccione Eliminar seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="9ab96-176">En el **cuadro de diálogo Eliminar registros MX,** seleccione **Eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9ab96-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9ab96-178">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ab96-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9ab96-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab96-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9ab96-p110">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="9ab96-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9ab96-182">En la **página Consola de** administración, en el área Dominios **actualizados** recientemente, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ab96-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9ab96-183">En la **página DNS administrado,** en el área **Registros CNAME,** seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="9ab96-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9ab96-184">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab96-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="9ab96-186">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9ab96-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="9ab96-187">En el área **Agregar registros CNAME**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ab96-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="9ab96-188">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9ab96-188">**Name**</span></span>|<span data-ttu-id="9ab96-189">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="9ab96-189">**Alias to**</span></span>|<span data-ttu-id="9ab96-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9ab96-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9ab96-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9ab96-191">autodiscover</span></span>  <br/> |<span data-ttu-id="9ab96-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9ab96-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="9ab96-193">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9ab96-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-194">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-194">1800</span></span>  <br/> |
    |<span data-ttu-id="9ab96-195">sip</span><span class="sxs-lookup"><span data-stu-id="9ab96-195">sip</span></span>  <br/> |<span data-ttu-id="9ab96-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9ab96-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9ab96-197">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9ab96-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-198">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-198">1800</span></span>  <br/> |
    |<span data-ttu-id="9ab96-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9ab96-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9ab96-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9ab96-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9ab96-201">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9ab96-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-202">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-202">1800</span></span>  <br/> |
    |<span data-ttu-id="9ab96-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9ab96-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9ab96-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="9ab96-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="9ab96-205">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9ab96-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-206">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-206">1800</span></span>  <br/> |
    |<span data-ttu-id="9ab96-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9ab96-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9ab96-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9ab96-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="9ab96-209">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="9ab96-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-210">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="9ab96-212">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="9ab96-214">Agregue cada uno de los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9ab96-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="9ab96-215">En la sección **Registros CNAME,** seleccione el control **(+)** ( **Agregar** nuevo ), cree un registro  con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar Enviar para completar dicho registro.</span><span class="sxs-lookup"><span data-stu-id="9ab96-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="9ab96-216">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9ab96-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9ab96-217">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="9ab96-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9ab96-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab96-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ab96-219">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab96-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9ab96-220">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="9ab96-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9ab96-221">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ab96-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9ab96-222">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="9ab96-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="9ab96-223">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="9ab96-223">Need examples?</span></span> <span data-ttu-id="9ab96-224">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="9ab96-224">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="9ab96-225">Para validar el registro SPF, puede usar una de estas herramientas[de validación de SPF](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="9ab96-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="9ab96-226">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="9ab96-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="9ab96-227">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="9ab96-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9ab96-228">En la **página Consola de** administración, en el área Dominios **actualizados** recientemente, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ab96-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9ab96-229">En la **página DNS administrado,** en el área **Registros TXT,** seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="9ab96-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9ab96-230">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab96-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="9ab96-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9ab96-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="9ab96-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="9ab96-233">**Name**</span></span>|<span data-ttu-id="9ab96-234">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9ab96-234">**Value**</span></span>|<span data-ttu-id="9ab96-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9ab96-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9ab96-236">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9ab96-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9ab96-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9ab96-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9ab96-238">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="9ab96-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="9ab96-239">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="9ab96-241">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9ab96-243">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ab96-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9ab96-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab96-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9ab96-p113">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="9ab96-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9ab96-247">En la **página Consola de** administración, en el área Dominios **actualizados** recientemente, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="9ab96-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9ab96-248">En la **página DNS administrado,** en el área **Registros SRV,** seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="9ab96-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9ab96-249">(Puede que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab96-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="9ab96-251">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="9ab96-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9ab96-252">En el área **Agregar registros SRV**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ab96-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="9ab96-253">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9ab96-253">**Name**</span></span>|<span data-ttu-id="9ab96-254">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="9ab96-254">**Priority**</span></span>|<span data-ttu-id="9ab96-255">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="9ab96-255">**Weight**</span></span>|<span data-ttu-id="9ab96-256">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="9ab96-256">**Port**</span></span>|<span data-ttu-id="9ab96-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="9ab96-257">**Host**</span></span>|<span data-ttu-id="9ab96-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9ab96-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9ab96-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9ab96-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="9ab96-260">100</span><span class="sxs-lookup"><span data-stu-id="9ab96-260">100</span></span>  <br/> |<span data-ttu-id="9ab96-261">1</span><span class="sxs-lookup"><span data-stu-id="9ab96-261">1</span></span>  <br/> |<span data-ttu-id="9ab96-262">443</span><span class="sxs-lookup"><span data-stu-id="9ab96-262">443</span></span>  <br/> |<span data-ttu-id="9ab96-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9ab96-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9ab96-264">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9ab96-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-265">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-265">1800</span></span>  <br/> |
    |<span data-ttu-id="9ab96-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9ab96-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9ab96-267">100</span><span class="sxs-lookup"><span data-stu-id="9ab96-267">100</span></span>  <br/> |<span data-ttu-id="9ab96-268">1</span><span class="sxs-lookup"><span data-stu-id="9ab96-268">1</span></span>  <br/> |<span data-ttu-id="9ab96-269">5061</span><span class="sxs-lookup"><span data-stu-id="9ab96-269">5061</span></span>  <br/> |<span data-ttu-id="9ab96-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9ab96-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="9ab96-271">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="9ab96-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9ab96-272">1800</span><span class="sxs-lookup"><span data-stu-id="9ab96-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="9ab96-274">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9ab96-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="9ab96-276">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="9ab96-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="9ab96-277">En la sección **Registros SRV,** seleccione el control **(+)** ( **Agregar** nuevo ), cree un registro  con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar Enviar para completar dicho registro.</span><span class="sxs-lookup"><span data-stu-id="9ab96-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9ab96-278">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9ab96-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9ab96-279">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9ab96-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ab96-280">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ab96-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
