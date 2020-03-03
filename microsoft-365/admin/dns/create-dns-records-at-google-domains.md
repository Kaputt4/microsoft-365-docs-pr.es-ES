---
title: Crear registros DNS en Google Domains para Office 365
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync y otros servicios en Google Domains para Office 365.
ms.openlocfilehash: 5b72753dfdf44fa15cd0dffaa4baf61e843cf532
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349701"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="6bb3e-103">Crear registros DNS en Google Domains para Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb3e-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="6bb3e-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6bb3e-105">Si Google Domains es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="6bb3e-106">Después de agregar estos registros a Google Domains, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="6bb3e-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6bb3e-108">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6bb3e-109">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6bb3e-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6bb3e-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="6bb3e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6bb3e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6bb3e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6bb3e-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6bb3e-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6bb3e-p104">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="6bb3e-120">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="6bb3e-121">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="6bb3e-122">En la página **mis dominios** , busque el dominio que desea usar con Office 365 y seleccione el vínculo **administrar** junto a él.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="6bb3e-123">En el panel de navegación izquierdo, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="6bb3e-124">En la sección \* \* registros de recursos personalizados \* \*, en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6bb3e-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6bb3e-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6bb3e-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-127">**Name**</span></span> <br/> |<span data-ttu-id="6bb3e-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-128">**Type**</span></span> <br/> |<span data-ttu-id="6bb3e-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-129">**TTL**</span></span> <br/> |<span data-ttu-id="6bb3e-130">**Datos**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="6bb3e-131">TXT</span><span class="sxs-lookup"><span data-stu-id="6bb3e-131">TXT</span></span>  <br/> |<span data-ttu-id="6bb3e-132">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-132">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6bb3e-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6bb3e-134">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-134">**Note:** This is an example.</span></span> <span data-ttu-id="6bb3e-135">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="6bb3e-136">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="6bb3e-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="6bb3e-137">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="6bb3e-138">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6bb3e-139">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6bb3e-140">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6bb3e-141">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6bb3e-142">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6bb3e-143">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6bb3e-144">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6bb3e-145">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6bb3e-146">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6bb3e-147">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6bb3e-148">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb3e-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6bb3e-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6bb3e-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6bb3e-p108">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="6bb3e-153">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="6bb3e-154">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="6bb3e-155">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6bb3e-p109">Si tiene una cuenta de correo electrónico de G Suite, primero deberá eliminar los registros MX asociados a esa cuenta. Los registros MX de G Suite le impiden agregar otros registros MX, incluidos los que se requieren para Office 365. Tenga en cuenta que eliminar los registros de G Suite no elimina su cuenta de G Suite. Para eliminar sus registros MX de G Suite, siga los pasos que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="6bb3e-160">En la sección **registros sintéticos** , en el área **G Suite** , seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="6bb3e-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-161">(You may have to scroll down.)</span></span>
    
    ![Seleccione eliminar en la sección registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="6bb3e-163">Seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-163">Select **Delete**.</span></span>
    
    ![Seleccione eliminar.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="6bb3e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6bb3e-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6bb3e-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6bb3e-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-168">**Name**</span></span>|<span data-ttu-id="6bb3e-169">**Type**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-169">**Type**</span></span>|<span data-ttu-id="6bb3e-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-170">**TTL**</span></span>|<span data-ttu-id="6bb3e-171">**Datos**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="6bb3e-172">MX</span><span class="sxs-lookup"><span data-stu-id="6bb3e-172">MX</span></span>  <br/> |<span data-ttu-id="6bb3e-173">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-173">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-174">0  *\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="6bb3e-175">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="6bb3e-p110">El valor de **0** se corresponde con la prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="6bb3e-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="6bb3e-178">**Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="6bb3e-179">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="6bb3e-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="6bb3e-180">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="6bb3e-182">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-182">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="6bb3e-184">Si hay otros registros MX personalizados, quítelos:</span><span class="sxs-lookup"><span data-stu-id="6bb3e-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="6bb3e-185">Seleccione **Editar** en la fila del registro MX.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Seleccione Editar en la fila del registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="6bb3e-187">Para cada uno de los demás registros MX personalizados, seleccione la entrada en el cuadro **datos** y, después, presione la tecla **suprimir** en el teclado para eliminar ese registro.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="6bb3e-188">Continúe hasta haber eliminado la entrada **Datos** de cada uno de los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="6bb3e-190">Cuando haya eliminado la entrada de **datos** de cada uno de los demás registros MX, seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Seleccione Guardar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6bb3e-192">Agregue los cinco registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb3e-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="6bb3e-193">Para empezar, vaya a su página de [Google Domains]https://domains.google.com/registrar) (e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="6bb3e-194">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="6bb3e-195">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="6bb3e-196">En la sección **Registros de recursos personalizados**, en los cuadros del nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="6bb3e-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6bb3e-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6bb3e-199">**Name**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-199">**Name**</span></span>|<span data-ttu-id="6bb3e-200">**Type**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-200">**Type**</span></span>|<span data-ttu-id="6bb3e-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-201">**TTL**</span></span>|<span data-ttu-id="6bb3e-202">**Datos**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6bb3e-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6bb3e-203">autodiscover</span></span>  <br/> |<span data-ttu-id="6bb3e-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="6bb3e-204">CNAME</span></span>  <br/> |<span data-ttu-id="6bb3e-205">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-205">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="6bb3e-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6bb3e-208">sip</span><span class="sxs-lookup"><span data-stu-id="6bb3e-208">sip</span></span>  <br/> |<span data-ttu-id="6bb3e-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="6bb3e-209">CNAME</span></span>  <br/> |<span data-ttu-id="6bb3e-210">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-210">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6bb3e-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6bb3e-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6bb3e-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6bb3e-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="6bb3e-214">CNAME</span></span>  <br/> |<span data-ttu-id="6bb3e-215">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-215">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6bb3e-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6bb3e-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6bb3e-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6bb3e-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="6bb3e-219">CNAME</span></span>  <br/> |<span data-ttu-id="6bb3e-220">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-220">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="6bb3e-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6bb3e-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6bb3e-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6bb3e-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="6bb3e-224">CNAME</span></span>  <br/> |<span data-ttu-id="6bb3e-225">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-225">1H</span></span>  <br/> |<span data-ttu-id="6bb3e-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="6bb3e-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="6bb3e-229">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-229">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="6bb3e-231">Agregue los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="6bb3e-232">En la sección **registros de recursos personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="6bb3e-233">Repita este proceso hasta que haya creado todos los registros CNAME necesarios.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6bb3e-234">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="6bb3e-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6bb3e-235">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6bb3e-236">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6bb3e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6bb3e-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="6bb3e-239">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="6bb3e-239">Need examples?</span></span> <span data-ttu-id="6bb3e-240">Consulte los [Registros externos del sistema de nombres de dominio para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="6bb3e-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="6bb3e-p113">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="6bb3e-245">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="6bb3e-246">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="6bb3e-247">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="6bb3e-248">En la sección **registros de recursos personalizados** , en la fila registro TXT, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6bb3e-p114">Google Domains almacena los registros TXT como un conjunto que puede contener varios registros. Cuando tenga como mínimo otro registro TXT (como el registro TXT que usó para comprobar el dominio), necesitará agregar los nuevos registros TXT a ese conjunto de registros. Si intenta agregar otros registros TXT como entradas separadas, se mostrará el mensaje de error **Registro duplicado**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Seleccione Editar en la fila de registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="6bb3e-253">Seleccione el control **(+)** .</span><span class="sxs-lookup"><span data-stu-id="6bb3e-253">Select the **(+)** control.</span></span> 
    
    ![Seleccionar el control más](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="6bb3e-255">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6bb3e-256">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="6bb3e-257">**Datos**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="6bb3e-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6bb3e-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="6bb3e-259">Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="6bb3e-261">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-261">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6bb3e-263">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb3e-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6bb3e-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6bb3e-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="6bb3e-p115">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="6bb3e-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="6bb3e-268">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="6bb3e-269">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="6bb3e-270">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="6bb3e-271">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="6bb3e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6bb3e-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6bb3e-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6bb3e-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6bb3e-275">**Name**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-275">**Name**</span></span>|<span data-ttu-id="6bb3e-276">**Type**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-276">**Type**</span></span>|<span data-ttu-id="6bb3e-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-277">**TTL**</span></span>|<span data-ttu-id="6bb3e-278">**Datos**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6bb3e-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="6bb3e-279">_sip._tls</span></span>|<span data-ttu-id="6bb3e-280">SRV</span><span class="sxs-lookup"><span data-stu-id="6bb3e-280">SRV</span></span>|<span data-ttu-id="6bb3e-281">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-281">1H</span></span>|<span data-ttu-id="6bb3e-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="6bb3e-283">**Este valor debe terminar con un punto (.).** **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="6bb3e-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="6bb3e-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="6bb3e-285">SRV</span><span class="sxs-lookup"><span data-stu-id="6bb3e-285">SRV</span></span>|<span data-ttu-id="6bb3e-286">1H</span><span class="sxs-lookup"><span data-stu-id="6bb3e-286">1H</span></span>|<span data-ttu-id="6bb3e-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="6bb3e-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6bb3e-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="6bb3e-289">Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="6bb3e-291">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-291">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="6bb3e-293">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="6bb3e-294">En la sección **registros de recursos personalizados** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6bb3e-295">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6bb3e-296">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6bb3e-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6bb3e-297">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6bb3e-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
