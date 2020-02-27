---
title: Crear registros DNS en MyDomain para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Obtenga información acerca de cómo verificar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online y otros servicios en mi dominio para Office 365.
ms.openlocfilehash: 5a935ea456175f6d63926c9aa33280c4ec113abd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249372"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="6adfd-103">Crear registros DNS en MiDominio para Office 365</span><span class="sxs-lookup"><span data-stu-id="6adfd-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="6adfd-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="6adfd-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="6adfd-p101">El sitio web MyDomain no admite los registros SRV, lo que significa que varias características de Skype Empresarial Online y Outlook Web App no funcionarán. No importa qué plan de Office 365 use, si administra sus registros DNS con MyDomain, existen [limitaciones de servicio considerables](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) y puede que quiera cambiar a un proveedor de host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="6adfd-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="6adfd-107">Si decide administrar sus propios registros DNS de Office 365 en MyDomain a pesar de las limitaciones del servicio, siga los pasos de este artículo para configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="6adfd-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="6adfd-108">Después de agregar estos registros a MyDomain, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adfd-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="6adfd-109">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6adfd-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6adfd-110">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6adfd-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6adfd-111">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6adfd-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6adfd-112">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6adfd-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6adfd-113">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="6adfd-113">Add a TXT record for verification</span></span>
<span data-ttu-id="6adfd-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6adfd-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6adfd-p103">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="6adfd-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6adfd-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="6adfd-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6adfd-119">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="6adfd-119">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="6adfd-120">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6adfd-120">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6adfd-121">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6adfd-122">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="6adfd-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6adfd-123">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6adfd-124">En la lista desplegable **Modificar**, elija **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="6adfd-125">En **Contenido**, en el cuadro del nuevo registro, escriba o copie y pegue el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6adfd-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="6adfd-126">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="6adfd-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="6adfd-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6adfd-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6adfd-128">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6adfd-128">**Note:** This is an example.</span></span> <span data-ttu-id="6adfd-129">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adfd-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="6adfd-130">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="6adfd-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6adfd-131">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="6adfd-132">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="6adfd-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6adfd-133">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="6adfd-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6adfd-134">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="6adfd-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6adfd-135">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="6adfd-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6adfd-136">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="6adfd-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6adfd-137">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="6adfd-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6adfd-138">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6adfd-139">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6adfd-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6adfd-140">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6adfd-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6adfd-141">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6adfd-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6adfd-142">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="6adfd-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6adfd-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6adfd-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6adfd-p108">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6adfd-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6adfd-146">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6adfd-147">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="6adfd-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6adfd-148">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6adfd-149">En la lista desplegable **Modificar**, elija **Registro MX**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="6adfd-151">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6adfd-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6adfd-152">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="6adfd-152">**Priority**</span></span>|<span data-ttu-id="6adfd-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="6adfd-153">**Host**</span></span>|<span data-ttu-id="6adfd-154">**Señala a:**</span><span class="sxs-lookup"><span data-stu-id="6adfd-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6adfd-155">0</span><span class="sxs-lookup"><span data-stu-id="6adfd-155">0</span></span>  <br/> <span data-ttu-id="6adfd-156">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="6adfd-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="6adfd-157">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="6adfd-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6adfd-158">**Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adfd-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="6adfd-159"> > [¿Cómo encuentro esto?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="6adfd-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="6adfd-161">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="6adfd-163">Si existen otros registros MX, seleccione **Quitar** de la columna **Acción** para cada uno que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="6adfd-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="6adfd-165">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6adfd-167">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6adfd-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="6adfd-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6adfd-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6adfd-p110">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6adfd-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6adfd-171">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6adfd-172">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="6adfd-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6adfd-173">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6adfd-174">En la lista desplegable **Modificar**, elija **Alias CNAME**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="6adfd-176">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="6adfd-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="6adfd-177">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6adfd-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6adfd-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="6adfd-178">**Host**</span></span>|<span data-ttu-id="6adfd-179">**Señala a:**</span><span class="sxs-lookup"><span data-stu-id="6adfd-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6adfd-180">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="6adfd-180">autodiscover</span></span>  <br/> |<span data-ttu-id="6adfd-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6adfd-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6adfd-182">sip</span><span class="sxs-lookup"><span data-stu-id="6adfd-182">sip</span></span>  <br/> |<span data-ttu-id="6adfd-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6adfd-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6adfd-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6adfd-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6adfd-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6adfd-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6adfd-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6adfd-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6adfd-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6adfd-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6adfd-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6adfd-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6adfd-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6adfd-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="6adfd-191">Elija **Agregar** para agregar el primer registro.</span><span class="sxs-lookup"><span data-stu-id="6adfd-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="6adfd-193">Agregue el segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="6adfd-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="6adfd-194">Use los valores de la segunda fila de la tabla anterior y, a continuación, elija **Agregar** para agregar el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="6adfd-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="6adfd-195">Agregue los registros restantes de la misma manera, usando los valores de la tercera, la cuarta, la quinta y la sexta fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6adfd-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6adfd-196">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="6adfd-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6adfd-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6adfd-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6adfd-198">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="6adfd-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6adfd-199">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="6adfd-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6adfd-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adfd-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6adfd-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="6adfd-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="6adfd-202">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="6adfd-202">Need examples?</span></span> <span data-ttu-id="6adfd-203">Consulte los [Registros externos del sistema de nombres de dominio para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="6adfd-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="6adfd-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6adfd-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="6adfd-205">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="6adfd-205">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="6adfd-206">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6adfd-206">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6adfd-207">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6adfd-208">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="6adfd-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6adfd-209">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6adfd-210">En la lista desplegable **Modificar**, elija **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="6adfd-212">En **Contenido**, en el cuadro del nuevo registro, escriba o copie y pegue el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6adfd-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="6adfd-213">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="6adfd-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="6adfd-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6adfd-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6adfd-215">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="6adfd-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="6adfd-217">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6adfd-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6adfd-219">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6adfd-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6adfd-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6adfd-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="6adfd-p113">El sitio web MyDomain no admite los registros SRV, lo que significa que varias características de Skype Empresarial Online y Outlook Web App no funcionarán. No importa qué plan de Office 365 use, si administra sus registros DNS con MyDomain, existen [limitaciones de servicio considerables](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) y puede que quiera cambiar a un proveedor de host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="6adfd-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6adfd-223">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6adfd-223">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6adfd-224">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6adfd-224">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6adfd-225">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6adfd-225">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
