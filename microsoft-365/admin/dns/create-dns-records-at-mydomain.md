---
title: Crear registros DNS en MiDominio para Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Obtenga información acerca de cómo verificar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online y otros servicios en Mi dominio para Microsoft.
ms.openlocfilehash: f306e84509ddbea9f2e7bba598f0f490080e9f2a
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221972"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="32698-103">Crear registros DNS en MiDominio para Microsoft</span><span class="sxs-lookup"><span data-stu-id="32698-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="32698-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="32698-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="32698-p101">El sitio web MyDomain no admite los registros SRV, lo que significa que varias de las características de Skype Empresarial Online y Outlook Web App no funcionarán. No importa qué plan de Microsoft use, si administra sus registros DNS con MyDomain, existen [limitaciones de servicio considerables](../setup/domains-faq.yml) y puede que quiera cambiar a un proveedor de host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="32698-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="32698-107">Si decide administrar sus propios registros DNS de Microsoft en MyDomain a pesar de las limitaciones del servicio, siga los pasos de este artículo para configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="32698-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="32698-108">Después de agregar estos registros a MyDomain, su dominio estará configurado para trabajar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32698-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="32698-109">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="32698-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="32698-110">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="32698-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="32698-111">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="32698-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="32698-112">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="32698-112">Add a TXT record for verification</span></span>
<span data-ttu-id="32698-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="32698-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="32698-p103">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="32698-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="32698-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="32698-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="32698-p105">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="32698-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="32698-120">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="32698-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="32698-121">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="32698-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="32698-122">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="32698-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="32698-123">En la lista desplegable **Modificar**, elija **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="32698-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="32698-124">En **Contenido**, en el cuadro del nuevo registro, escriba o copie y pegue el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="32698-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="32698-125">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="32698-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="32698-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="32698-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="32698-127">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="32698-127">**Note:** This is an example.</span></span> <span data-ttu-id="32698-128">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="32698-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="32698-129">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="32698-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="32698-130">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="32698-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="32698-131">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="32698-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="32698-132">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="32698-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="32698-133">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="32698-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="32698-134">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="32698-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="32698-135">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="32698-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="32698-136">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="32698-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="32698-137">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="32698-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="32698-138">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="32698-138">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="32698-139">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="32698-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="32698-140">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="32698-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="32698-141">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="32698-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="32698-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="32698-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="32698-p108">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="32698-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="32698-145">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="32698-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="32698-146">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="32698-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="32698-147">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="32698-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="32698-148">En la lista desplegable **Modificar**, elija **Registro MX**.</span><span class="sxs-lookup"><span data-stu-id="32698-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="32698-150">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="32698-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="32698-151">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="32698-151">**Priority**</span></span>|<span data-ttu-id="32698-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="32698-152">**Host**</span></span>|<span data-ttu-id="32698-153">**Señala a:**</span><span class="sxs-lookup"><span data-stu-id="32698-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="32698-154">0</span><span class="sxs-lookup"><span data-stu-id="32698-154">0</span></span>  <br/> <span data-ttu-id="32698-155">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="32698-155">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |@  <br/> | <span data-ttu-id="32698-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="32698-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="32698-157">**Nota:** Obtenga la \<*domain-key*\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32698-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="32698-158"> > [¿Cómo encuentro esto?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="32698-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="32698-160">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="32698-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="32698-162">Si existen otros registros MX, seleccione **Quitar** de la columna **Acción** para cada uno que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="32698-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="32698-164">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32698-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="32698-166">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="32698-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="32698-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="32698-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="32698-p110">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="32698-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="32698-170">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="32698-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="32698-171">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="32698-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="32698-172">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="32698-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="32698-173">En la lista desplegable **Modificar**, elija **Alias CNAME**.</span><span class="sxs-lookup"><span data-stu-id="32698-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="32698-175">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="32698-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="32698-176">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="32698-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="32698-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="32698-177">**Host**</span></span>|<span data-ttu-id="32698-178">**Señala a:**</span><span class="sxs-lookup"><span data-stu-id="32698-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="32698-179">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="32698-179">autodiscover</span></span>  <br/> |<span data-ttu-id="32698-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="32698-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="32698-181">sip</span><span class="sxs-lookup"><span data-stu-id="32698-181">sip</span></span>  <br/> |<span data-ttu-id="32698-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="32698-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="32698-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="32698-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="32698-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="32698-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="32698-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="32698-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="32698-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="32698-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="32698-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="32698-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="32698-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="32698-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="32698-190">Elija **Agregar** para agregar el primer registro.</span><span class="sxs-lookup"><span data-stu-id="32698-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="32698-192">Agregue el segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="32698-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="32698-193">Use los valores de la segunda fila de la tabla anterior y, a continuación, elija **Agregar** para agregar el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="32698-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="32698-194">Agregue los registros restantes de la misma manera, usando los valores de la tercera, la cuarta, la quinta y la sexta fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="32698-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="32698-195">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="32698-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="32698-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="32698-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="32698-197">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="32698-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="32698-198">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="32698-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="32698-199">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32698-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="32698-200">En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="32698-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="32698-201">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="32698-201">Need examples?</span></span> <span data-ttu-id="32698-202">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="32698-202">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="32698-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="32698-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="32698-p112">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="32698-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="32698-206">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="32698-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="32698-207">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="32698-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="32698-208">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="32698-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="32698-209">En la lista desplegable **Modificar**, elija **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="32698-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="32698-211">En **Contenido**, en el cuadro del nuevo registro, escriba o copie y pegue el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="32698-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="32698-212">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="32698-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="32698-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="32698-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="32698-214">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="32698-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="32698-216">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="32698-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="32698-218">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="32698-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="32698-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="32698-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="32698-p113">El sitio web MyDomain no admite los registros SRV, lo que significa que varias de las características de Skype Empresarial Online y Outlook Web App no funcionarán. No importa qué plan de Microsoft use, si administra sus registros DNS con MyDomain, existen [limitaciones de servicio considerables](../setup/domains-faq.yml) y puede que quiera cambiar a un proveedor de host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="32698-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="32698-222">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="32698-222">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="32698-223">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="32698-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="32698-224">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="32698-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
