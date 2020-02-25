---
title: Crear registros DNS en DNSMadeEasy para Office 365
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en DNSMadeEasy para Office 365.
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248825"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="34f6d-103">Crear registros DNS en DNSMadeEasy para Office 365</span><span class="sxs-lookup"><span data-stu-id="34f6d-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="34f6d-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="34f6d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="34f6d-105">Si DNSMadeEasy es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="34f6d-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="34f6d-106">Después de agregar estos registros a DNSMadeEasy, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34f6d-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="34f6d-107">Para obtener información sobre hospedaje web y DNS para sitios web con Office 365, vea [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="34f6d-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="34f6d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="34f6d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="34f6d-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="34f6d-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="34f6d-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="34f6d-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="34f6d-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="34f6d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="34f6d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="34f6d-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="34f6d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34f6d-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="34f6d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="34f6d-117">Para las cuentas de DNSMadeEasy, el dominio que agregó se compró de un registrador de dominios separado.</span><span class="sxs-lookup"><span data-stu-id="34f6d-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="34f6d-118">DNSMadeEasy no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="34f6d-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="34f6d-119">Su capacidad para iniciar sesión en DNSMadeEasy y crear el registro DNS es una prueba suficiente de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="34f6d-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="34f6d-120">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="34f6d-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="34f6d-121">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="34f6d-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="34f6d-122">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="34f6d-123">En la página **DNS administrados** , en el área **registros txt** , seleccione el **+** control () ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="34f6d-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="34f6d-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="34f6d-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="34f6d-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="34f6d-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="34f6d-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="34f6d-126">**Name**</span></span> <br/> |<span data-ttu-id="34f6d-127">**Valor**</span><span class="sxs-lookup"><span data-stu-id="34f6d-127">**Value**</span></span> <br/> |<span data-ttu-id="34f6d-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34f6d-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="34f6d-129">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="34f6d-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="34f6d-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="34f6d-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="34f6d-131">**Nota:** Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="34f6d-131">**Note:** This is an example.</span></span> <span data-ttu-id="34f6d-132">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34f6d-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="34f6d-133">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="34f6d-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="34f6d-134">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="34f6d-135">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="34f6d-136">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="34f6d-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="34f6d-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="34f6d-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="34f6d-138">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="34f6d-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="34f6d-139">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="34f6d-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="34f6d-140">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="34f6d-141">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="34f6d-142">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="34f6d-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="34f6d-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="34f6d-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="34f6d-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="34f6d-145">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="34f6d-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="34f6d-146">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="34f6d-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="34f6d-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6d-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="34f6d-p108">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="34f6d-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="34f6d-150">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="34f6d-151">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-configure-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="34f6d-153">En la página **DNS administrados** , en el área **registros MX** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="34f6d-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="34f6d-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="34f6d-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="34f6d-156">En el área **Agregar registros MX**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34f6d-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="34f6d-157">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="34f6d-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="34f6d-158">**Name**</span><span class="sxs-lookup"><span data-stu-id="34f6d-158">**Name**</span></span>|<span data-ttu-id="34f6d-159">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="34f6d-159">**Server**</span></span>|<span data-ttu-id="34f6d-160">**Nivel de MX**</span><span class="sxs-lookup"><span data-stu-id="34f6d-160">**MX Level**</span></span>|<span data-ttu-id="34f6d-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34f6d-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34f6d-162">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="34f6d-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="34f6d-163">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="34f6d-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="34f6d-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="34f6d-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="34f6d-165">**Nota:** Obtenga la \< *clave* \> de dominio de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34f6d-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="34f6d-166">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="34f6d-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="34f6d-167">10 </span><span class="sxs-lookup"><span data-stu-id="34f6d-167">10</span></span>  <br/> <span data-ttu-id="34f6d-168">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="34f6d-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="34f6d-169">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="34f6d-171">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="34f6d-173">Si en la sección **Registros MX** se muestran otros registros MX, selecciónelos para eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="34f6d-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="34f6d-175">Una vez seleccionados todos los registros, seleccione **eliminar seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="34f6d-177">En el cuadro de diálogo **eliminar registros MX** , seleccione **eliminar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="34f6d-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="34f6d-179">Agregue los cinco registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="34f6d-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="34f6d-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6d-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="34f6d-p110">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="34f6d-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="34f6d-183">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="34f6d-184">En la página **DNS administrados** , en el área **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="34f6d-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="34f6d-185">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="34f6d-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="34f6d-187">Agregue el primero de los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="34f6d-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="34f6d-188">En el área **Agregar registros CNAME**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34f6d-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="34f6d-189">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="34f6d-189">**Name**</span></span>|<span data-ttu-id="34f6d-190">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="34f6d-190">**Alias to**</span></span>|<span data-ttu-id="34f6d-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34f6d-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="34f6d-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="34f6d-192">autodiscover</span></span>  <br/> |<span data-ttu-id="34f6d-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="34f6d-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="34f6d-194">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-195">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-195">1800</span></span>  <br/> |
    |<span data-ttu-id="34f6d-196">sip</span><span class="sxs-lookup"><span data-stu-id="34f6d-196">sip</span></span>  <br/> |<span data-ttu-id="34f6d-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="34f6d-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="34f6d-198">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-199">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-199">1800</span></span>  <br/> |
    |<span data-ttu-id="34f6d-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="34f6d-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="34f6d-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="34f6d-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="34f6d-202">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-203">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-203">1800</span></span>  <br/> |
    |<span data-ttu-id="34f6d-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="34f6d-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="34f6d-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="34f6d-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="34f6d-206">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-207">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-207">1800</span></span>  <br/> |
    |<span data-ttu-id="34f6d-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="34f6d-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="34f6d-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="34f6d-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="34f6d-210">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-211">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="34f6d-213">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="34f6d-215">Agregue cada uno de los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="34f6d-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="34f6d-216">En la sección **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="34f6d-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="34f6d-217">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="34f6d-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="34f6d-218">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="34f6d-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="34f6d-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6d-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f6d-220">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="34f6d-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="34f6d-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="34f6d-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="34f6d-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="34f6d-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="34f6d-223">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="34f6d-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="34f6d-224">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="34f6d-224">Need examples?</span></span> <span data-ttu-id="34f6d-225">Consulte estos [registros del sistema de nombres de dominio externo para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="34f6d-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="34f6d-226">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="34f6d-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="34f6d-227">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="34f6d-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="34f6d-228">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="34f6d-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="34f6d-229">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="34f6d-230">En la página **DNS administrados** , en el área **registros txt** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="34f6d-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="34f6d-231">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="34f6d-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="34f6d-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="34f6d-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="34f6d-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="34f6d-234">**Name**</span></span>|<span data-ttu-id="34f6d-235">**Valor**</span><span class="sxs-lookup"><span data-stu-id="34f6d-235">**Value**</span></span>|<span data-ttu-id="34f6d-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34f6d-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="34f6d-237">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="34f6d-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="34f6d-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="34f6d-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="34f6d-239">**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="34f6d-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="34f6d-240">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="34f6d-242">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="34f6d-244">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="34f6d-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="34f6d-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6d-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="34f6d-p113">Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="34f6d-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="34f6d-248">En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="34f6d-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="34f6d-249">En la página **DNS administrados** , en el área **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**).</span><span class="sxs-lookup"><span data-stu-id="34f6d-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="34f6d-250">(Puede que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="34f6d-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-configure-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="34f6d-252">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="34f6d-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="34f6d-253">En el área **Agregar registros SRV**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="34f6d-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="34f6d-254">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="34f6d-254">**Name**</span></span>|<span data-ttu-id="34f6d-255">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="34f6d-255">**Priority**</span></span>|<span data-ttu-id="34f6d-256">**Peso**</span><span class="sxs-lookup"><span data-stu-id="34f6d-256">**Weight**</span></span>|<span data-ttu-id="34f6d-257">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="34f6d-257">**Port**</span></span>|<span data-ttu-id="34f6d-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="34f6d-258">**Host**</span></span>|<span data-ttu-id="34f6d-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34f6d-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="34f6d-260">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="34f6d-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="34f6d-261">100</span><span class="sxs-lookup"><span data-stu-id="34f6d-261">100</span></span>  <br/> |<span data-ttu-id="34f6d-262">1</span><span class="sxs-lookup"><span data-stu-id="34f6d-262">1</span></span>  <br/> |<span data-ttu-id="34f6d-263">443</span><span class="sxs-lookup"><span data-stu-id="34f6d-263">443</span></span>  <br/> |<span data-ttu-id="34f6d-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="34f6d-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="34f6d-265">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-266">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-266">1800</span></span>  <br/> |
    |<span data-ttu-id="34f6d-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="34f6d-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="34f6d-268">100</span><span class="sxs-lookup"><span data-stu-id="34f6d-268">100</span></span>  <br/> |<span data-ttu-id="34f6d-269">1</span><span class="sxs-lookup"><span data-stu-id="34f6d-269">1</span></span>  <br/> |<span data-ttu-id="34f6d-270">5061</span><span class="sxs-lookup"><span data-stu-id="34f6d-270">5061</span></span>  <br/> |<span data-ttu-id="34f6d-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="34f6d-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="34f6d-272">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="34f6d-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="34f6d-273">1800</span><span class="sxs-lookup"><span data-stu-id="34f6d-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="34f6d-275">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="34f6d-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="34f6d-277">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="34f6d-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="34f6d-278">En la sección **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="34f6d-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="34f6d-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="34f6d-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="34f6d-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="34f6d-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="34f6d-281">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="34f6d-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

