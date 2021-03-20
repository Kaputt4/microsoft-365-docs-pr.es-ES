---
title: Crear registros DNS en Google Domains para Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Obtenga información sobre cómo comprobar el dominio y configurar los registros DNS para el correo electrónico, Lync y otros servicios en Google Domains para Microsoft.
ms.openlocfilehash: 9a1d0a8513f6071a3c9c686c10f6fd282f1a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910227"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="85310-103">Crear registros DNS en Google Domains para Microsoft</span><span class="sxs-lookup"><span data-stu-id="85310-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="85310-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="85310-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="85310-105">Si Google Domains es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.</span><span class="sxs-lookup"><span data-stu-id="85310-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="85310-106">Después de agregar estos registros a Google Domains, el dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85310-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="85310-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="85310-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="85310-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="85310-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="85310-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="85310-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="85310-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="85310-110">Add a TXT record for verification</span></span>
<span data-ttu-id="85310-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="85310-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="85310-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="85310-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85310-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="85310-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="85310-p104">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="85310-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="85310-119">Seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="85310-120">Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="85310-121">En la página **Mis dominios**, busque el dominio que quiere usar con Microsoft y seleccione el vínculo **ADMINISTRAR** situado al lado.</span><span class="sxs-lookup"><span data-stu-id="85310-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="85310-122">En el panel de navegación izquierdo, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="85310-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="85310-123">En la sección **Registros de recursos personalizados**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="85310-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85310-124">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="85310-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="85310-125">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="85310-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85310-126">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="85310-126">**Name**</span></span> <br/> |<span data-ttu-id="85310-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="85310-127">**Type**</span></span> <br/> |<span data-ttu-id="85310-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85310-128">**TTL**</span></span> <br/> |<span data-ttu-id="85310-129">**Datos**</span><span class="sxs-lookup"><span data-stu-id="85310-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="85310-130">TXT</span><span class="sxs-lookup"><span data-stu-id="85310-130">TXT</span></span>  <br/> |<span data-ttu-id="85310-131">1H</span><span class="sxs-lookup"><span data-stu-id="85310-131">1H</span></span>  <br/> |<span data-ttu-id="85310-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="85310-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="85310-133">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85310-133">**Note:** This is an example.</span></span> <span data-ttu-id="85310-134">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="85310-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="85310-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="85310-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="85310-136">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="85310-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="85310-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="85310-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="85310-138">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="85310-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="85310-139">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="85310-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="85310-140">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="85310-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="85310-141">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="85310-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="85310-142">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="85310-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="85310-143">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="85310-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="85310-144">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="85310-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="85310-145">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="85310-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="85310-146">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="85310-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="85310-147">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="85310-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="85310-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="85310-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="85310-p108">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="85310-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="85310-152">Seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="85310-153">Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="85310-154">En la página **Dominios**, en la sección **Dominio**, seleccione **Configurar DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="85310-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="85310-155">Si tiene una cuenta de correo electrónico de G Suite, primero deberá eliminar los registros MX asociados a esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="85310-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="85310-156">Los registros MX de G Suite le impiden agregar otros registros MX, incluidos los que se requieren para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85310-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="85310-157">Tenga en cuenta que eliminar los registros de G Suite no elimina su cuenta de G Suite.</span><span class="sxs-lookup"><span data-stu-id="85310-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="85310-158">Para eliminar sus registros MX de G Suite, siga los pasos que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="85310-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="85310-159">En la sección **Registros sintéticos**, en el área **G Suite**, seleccione **Eliminar**</span><span class="sxs-lookup"><span data-stu-id="85310-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="85310-160">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="85310-160">(You may have to scroll down.)</span></span>
    
    ![Seleccione Eliminar en la sección Registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="85310-162">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="85310-162">Select **Delete**.</span></span>
    
    ![Seleccione Eliminar](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="85310-164">En la sección **Registros de recursos personalizados**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="85310-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85310-165">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="85310-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="85310-166">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="85310-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85310-167">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="85310-167">**Name**</span></span>|<span data-ttu-id="85310-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="85310-168">**Type**</span></span>|<span data-ttu-id="85310-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85310-169">**TTL**</span></span>|<span data-ttu-id="85310-170">**Datos**</span><span class="sxs-lookup"><span data-stu-id="85310-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="85310-171">MX</span><span class="sxs-lookup"><span data-stu-id="85310-171">MX</span></span>  <br/> |<span data-ttu-id="85310-172">1H</span><span class="sxs-lookup"><span data-stu-id="85310-172">1H</span></span>  <br/> |<span data-ttu-id="85310-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="85310-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="85310-174">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="85310-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="85310-p110">El valor de **0** se corresponde con la prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="85310-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="85310-177">**Nota:** Obtenga la \<*domain-key*\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85310-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="85310-178">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="85310-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="85310-179">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="85310-179">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Escriba o pegue valores en la sección Registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="85310-181">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="85310-181">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="85310-183">Si hay otros registros MX personalizados, quítelos.</span><span class="sxs-lookup"><span data-stu-id="85310-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="85310-184">Seleccione **Editar** en la fila de registro MX.</span><span class="sxs-lookup"><span data-stu-id="85310-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Seleccione Editar en la fila de registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="85310-186">Para cada registro MX personalizado restante, seleccione la entrada en el cuadro **Datos** y después pulse la tecla **Suprimir** en el teclado para eliminar ese registro.</span><span class="sxs-lookup"><span data-stu-id="85310-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="85310-187">Continúe hasta haber eliminado la entrada **Datos** de cada uno de los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="85310-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="85310-189">Después de eliminar la entrada **Datos** del resto de los registros MX, seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="85310-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Seleccione Guardar.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="85310-191">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="85310-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="85310-192">Para empezar, vaya a su [página de Google Domains] (https://domains.google.com/registrar) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="85310-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="85310-193">En la página **Dominios**, en la sección **Dominio**, seleccione **Configurar DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="85310-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="85310-194">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="85310-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="85310-195">En la sección **Registros de recursos personalizados**, en los cuadros del nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="85310-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="85310-196">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="85310-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="85310-197">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="85310-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85310-198">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="85310-198">**Name**</span></span>|<span data-ttu-id="85310-199">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="85310-199">**Type**</span></span>|<span data-ttu-id="85310-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85310-200">**TTL**</span></span>|<span data-ttu-id="85310-201">**Datos**</span><span class="sxs-lookup"><span data-stu-id="85310-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85310-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="85310-202">autodiscover</span></span>  <br/> |<span data-ttu-id="85310-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="85310-203">CNAME</span></span>  <br/> |<span data-ttu-id="85310-204">1H</span><span class="sxs-lookup"><span data-stu-id="85310-204">1H</span></span>  <br/> |<span data-ttu-id="85310-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="85310-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="85310-206">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="85310-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85310-207">sip</span><span class="sxs-lookup"><span data-stu-id="85310-207">sip</span></span>  <br/> |<span data-ttu-id="85310-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="85310-208">CNAME</span></span>  <br/> |<span data-ttu-id="85310-209">1H</span><span class="sxs-lookup"><span data-stu-id="85310-209">1H</span></span>  <br/> |<span data-ttu-id="85310-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85310-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85310-211">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="85310-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85310-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="85310-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="85310-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="85310-213">CNAME</span></span>  <br/> |<span data-ttu-id="85310-214">1H</span><span class="sxs-lookup"><span data-stu-id="85310-214">1H</span></span>  <br/> |<span data-ttu-id="85310-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85310-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85310-216">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="85310-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85310-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="85310-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="85310-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="85310-218">CNAME</span></span>  <br/> |<span data-ttu-id="85310-219">1H</span><span class="sxs-lookup"><span data-stu-id="85310-219">1H</span></span>  <br/> |<span data-ttu-id="85310-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="85310-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="85310-221">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="85310-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85310-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="85310-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="85310-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="85310-223">CNAME</span></span>  <br/> |<span data-ttu-id="85310-224">1H</span><span class="sxs-lookup"><span data-stu-id="85310-224">1H</span></span>  <br/> |<span data-ttu-id="85310-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="85310-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="85310-226">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="85310-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Escriba o pegue valores en la sección Registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="85310-228">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="85310-228">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="85310-230">Agregue los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="85310-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="85310-231">En la sección **Registros de recursos personalizados**, cree un registro mediante los valores de la siguiente fila de la tabla y vuelva a seleccionar **Agregar** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="85310-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="85310-232">Repita este proceso hasta crear todos los registros CNAME necesarios.</span><span class="sxs-lookup"><span data-stu-id="85310-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="85310-233">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="85310-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85310-234">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="85310-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="85310-235">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="85310-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="85310-236">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85310-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="85310-237">En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="85310-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="85310-238">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="85310-238">Need examples?</span></span> <span data-ttu-id="85310-239">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="85310-239">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords).</span></span> <span data-ttu-id="85310-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="85310-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="85310-p113">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="85310-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="85310-244">Seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="85310-245">Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="85310-246">En la página **Dominios**, en la sección **Dominio**, seleccione **Configurar DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="85310-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="85310-247">En la sección **Registros de recursos personalizados**, en la fila del registro TXT, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85310-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="85310-p114">Google Domains almacena los registros TXT como un conjunto que puede contener varios registros. Cuando tenga como mínimo otro registro TXT (como el registro TXT que usó para comprobar el dominio), necesitará agregar los nuevos registros TXT a ese conjunto de registros. Si intenta agregar otros registros TXT como entradas separadas, se mostrará el mensaje de error **Registro duplicado**.</span><span class="sxs-lookup"><span data-stu-id="85310-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Seleccione Editar en la fila de registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="85310-252">Seleccione el control **(+)**.</span><span class="sxs-lookup"><span data-stu-id="85310-252">Select the **(+)** control.</span></span> 
    
    ![Seleccione el control más](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="85310-254">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="85310-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="85310-255">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="85310-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="85310-256">**Datos**</span><span class="sxs-lookup"><span data-stu-id="85310-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="85310-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="85310-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="85310-258">Recomendamos copiar y pegar esta entrada, para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="85310-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Escriba o pegue valores en la sección Registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="85310-260">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="85310-260">Select **Save**.</span></span>
    
    ![Seleccione Guardar.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="85310-262">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="85310-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="85310-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="85310-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="85310-p115">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="85310-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="85310-267">Seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="85310-268">Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="85310-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="85310-269">En la página **Dominios**, en la sección **Dominio**, seleccione **Configurar DNS** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="85310-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="85310-270">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="85310-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="85310-271">En la sección **Registros de recursos personalizados**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="85310-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85310-272">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="85310-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="85310-273">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="85310-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85310-274">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="85310-274">**Name**</span></span>|<span data-ttu-id="85310-275">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="85310-275">**Type**</span></span>|<span data-ttu-id="85310-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85310-276">**TTL**</span></span>|<span data-ttu-id="85310-277">**Datos**</span><span class="sxs-lookup"><span data-stu-id="85310-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85310-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="85310-278">_sip._tls</span></span>|<span data-ttu-id="85310-279">SRV</span><span class="sxs-lookup"><span data-stu-id="85310-279">SRV</span></span>|<span data-ttu-id="85310-280">1H</span><span class="sxs-lookup"><span data-stu-id="85310-280">1H</span></span>|<span data-ttu-id="85310-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85310-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="85310-282">**Este valor DEBE terminar en punto (.)** **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="85310-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="85310-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="85310-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="85310-284">SRV</span><span class="sxs-lookup"><span data-stu-id="85310-284">SRV</span></span>|<span data-ttu-id="85310-285">1H</span><span class="sxs-lookup"><span data-stu-id="85310-285">1H</span></span>|<span data-ttu-id="85310-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85310-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="85310-287">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="85310-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="85310-288">Recomendamos copiar y pegar esta entrada, para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="85310-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Escriba o pegue valores en la sección Registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="85310-290">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="85310-290">Select **Add**.</span></span>
    
    ![Seleccione Agregar.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="85310-292">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="85310-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="85310-293">En la sección **Registros de recursos personalizados**, cree un registro mediante los valores de la segunda fila de la tabla y vuelva a seleccionar **Agregar** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="85310-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="85310-294">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="85310-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="85310-295">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="85310-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="85310-296">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="85310-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
