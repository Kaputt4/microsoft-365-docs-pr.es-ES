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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en DNSMadeEasy para Microsoft.
ms.openlocfilehash: 643ed0b692c14dfa058d872095fd10ea579aeda3
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939312"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="7f7e0-103">Crear registros DNS en DNSMadeEasy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f7e0-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="7f7e0-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7f7e0-105">Si DNSMadeEasy es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7f7e0-106">Después de agregar estos registros a DNSMadeEasy, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="7f7e0-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7f7e0-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7f7e0-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7f7e0-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="7f7e0-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7f7e0-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7e0-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7f7e0-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f7e0-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7f7e0-116">Para las cuentas de DNSMadeEasy, el dominio que agregó se compró de un registrador de dominios separado.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="7f7e0-117">DNSMadeEasy no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="7f7e0-118">Su capacidad para iniciar sesión en DNSMadeEasy y crear el registro DNS es una prueba suficiente de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="7f7e0-119">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="7f7e0-120">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="7f7e0-121">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="7f7e0-122">En la página **DNS administrados** , en el área **registros txt** , seleccione el **+** control () ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="7f7e0-123">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7f7e0-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="7f7e0-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="7f7e0-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-125">**Name**</span></span> <br/> |<span data-ttu-id="7f7e0-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-126">**Value**</span></span> <br/> |<span data-ttu-id="7f7e0-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="7f7e0-128">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7f7e0-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7f7e0-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7f7e0-130">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-130">**Note:** This is an example.</span></span> <span data-ttu-id="7f7e0-131">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7f7e0-132">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="7f7e0-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7f7e0-133">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="7f7e0-134">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="7f7e0-135">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7f7e0-136">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7f7e0-137">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7f7e0-138">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7f7e0-139">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7f7e0-140">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7f7e0-141">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f7e0-142">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7f7e0-143">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7f7e0-144">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7f7e0-145">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f7e0-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7f7e0-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7e0-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7f7e0-p108">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="7f7e0-149">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="7f7e0-150">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="7f7e0-152">En la página **DNS administrados** , en el área **registros MX** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="7f7e0-153">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7f7e0-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="7f7e0-155">En el área **Agregar registros MX**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7f7e0-156">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="7f7e0-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-157">**Name**</span></span>|<span data-ttu-id="7f7e0-158">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-158">**Server**</span></span>|<span data-ttu-id="7f7e0-159">**Nivel de MX**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-159">**MX Level**</span></span>|<span data-ttu-id="7f7e0-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f7e0-161">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="7f7e0-162">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="7f7e0-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7f7e0-163">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7f7e0-164">**Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="7f7e0-165">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="7f7e0-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7f7e0-166">10  </span><span class="sxs-lookup"><span data-stu-id="7f7e0-166">10</span></span>  <br/> <span data-ttu-id="7f7e0-167">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="7f7e0-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="7f7e0-168">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="7f7e0-170">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="7f7e0-172">Si en la sección **Registros MX** se muestran otros registros MX, selecciónelos para eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="7f7e0-174">Una vez seleccionados todos los registros, seleccione **eliminar seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="7f7e0-176">En el cuadro de diálogo **eliminar registros MX** , seleccione **eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7f7e0-178">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f7e0-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7f7e0-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7e0-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7f7e0-p110">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="7f7e0-182">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="7f7e0-183">En la página **DNS administrados** , en el área **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="7f7e0-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7f7e0-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="7f7e0-186">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="7f7e0-187">En el área **Agregar registros CNAME**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="7f7e0-188">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-188">**Name**</span></span>|<span data-ttu-id="7f7e0-189">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-189">**Alias to**</span></span>|<span data-ttu-id="7f7e0-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7f7e0-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7f7e0-191">autodiscover</span></span>  <br/> |<span data-ttu-id="7f7e0-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7f7e0-193">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-194">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-194">1800</span></span>  <br/> |
    |<span data-ttu-id="7f7e0-195">sip</span><span class="sxs-lookup"><span data-stu-id="7f7e0-195">sip</span></span>  <br/> |<span data-ttu-id="7f7e0-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7f7e0-197">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-198">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-198">1800</span></span>  <br/> |
    |<span data-ttu-id="7f7e0-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7f7e0-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7f7e0-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7f7e0-201">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-202">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-202">1800</span></span>  <br/> |
    |<span data-ttu-id="7f7e0-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7f7e0-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7f7e0-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7f7e0-205">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-206">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-206">1800</span></span>  <br/> |
    |<span data-ttu-id="7f7e0-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7f7e0-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7f7e0-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7f7e0-209">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-210">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="7f7e0-212">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="7f7e0-214">Agregue cada uno de los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="7f7e0-215">En la sección **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="7f7e0-216">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7f7e0-217">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7f7e0-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7f7e0-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7e0-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f7e0-219">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7f7e0-220">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7f7e0-221">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7f7e0-222">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="7f7e0-223">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="7f7e0-223">Need examples?</span></span> <span data-ttu-id="7f7e0-224">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-224">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="7f7e0-225">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="7f7e0-226">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="7f7e0-227">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="7f7e0-228">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="7f7e0-229">En la página **DNS administrados** , en el área **registros txt** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="7f7e0-230">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="7f7e0-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="7f7e0-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-233">**Name**</span></span>|<span data-ttu-id="7f7e0-234">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-234">**Value**</span></span>|<span data-ttu-id="7f7e0-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7f7e0-236">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7f7e0-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7f7e0-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7f7e0-238">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7f7e0-239">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="7f7e0-241">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7f7e0-243">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f7e0-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7f7e0-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7e0-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7f7e0-p113">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="7f7e0-247">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="7f7e0-248">En la página **DNS administrados** , en el área **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="7f7e0-249">(Puede que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="7f7e0-251">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7f7e0-252">En el área **Agregar registros SRV**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="7f7e0-253">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-253">**Name**</span></span>|<span data-ttu-id="7f7e0-254">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-254">**Priority**</span></span>|<span data-ttu-id="7f7e0-255">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-255">**Weight**</span></span>|<span data-ttu-id="7f7e0-256">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-256">**Port**</span></span>|<span data-ttu-id="7f7e0-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-257">**Host**</span></span>|<span data-ttu-id="7f7e0-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f7e0-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="7f7e0-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="7f7e0-260">100</span><span class="sxs-lookup"><span data-stu-id="7f7e0-260">100</span></span>  <br/> |<span data-ttu-id="7f7e0-261">1</span><span class="sxs-lookup"><span data-stu-id="7f7e0-261">1</span></span>  <br/> |<span data-ttu-id="7f7e0-262">443</span><span class="sxs-lookup"><span data-stu-id="7f7e0-262">443</span></span>  <br/> |<span data-ttu-id="7f7e0-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7f7e0-264">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-265">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-265">1800</span></span>  <br/> |
    |<span data-ttu-id="7f7e0-266">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="7f7e0-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7f7e0-267">100</span><span class="sxs-lookup"><span data-stu-id="7f7e0-267">100</span></span>  <br/> |<span data-ttu-id="7f7e0-268">1</span><span class="sxs-lookup"><span data-stu-id="7f7e0-268">1</span></span>  <br/> |<span data-ttu-id="7f7e0-269">5061</span><span class="sxs-lookup"><span data-stu-id="7f7e0-269">5061</span></span>  <br/> |<span data-ttu-id="7f7e0-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="7f7e0-271">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="7f7e0-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7f7e0-272">1800</span><span class="sxs-lookup"><span data-stu-id="7f7e0-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="7f7e0-274">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="7f7e0-276">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7f7e0-277">En la sección **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7f7e0-278">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7f7e0-279">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="7f7e0-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7f7e0-280">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f7e0-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

