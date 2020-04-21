---
title: Crear registros DNS en Google Domains para Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync y otros servicios en Google Domains para Microsoft.
ms.openlocfilehash: 20a3ba9baefcdb26936d2d0a5fda7ed1b5db971e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629544"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="47bcb-103">Crear registros DNS en Google Domains para Microsoft</span><span class="sxs-lookup"><span data-stu-id="47bcb-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="47bcb-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="47bcb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="47bcb-105">Si Google Domains es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.</span><span class="sxs-lookup"><span data-stu-id="47bcb-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="47bcb-106">Después de agregar estos registros a Google Domains, el dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47bcb-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="47bcb-107">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="47bcb-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="47bcb-108">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="47bcb-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="47bcb-109">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="47bcb-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="47bcb-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="47bcb-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="47bcb-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="47bcb-111">Add a TXT record for verification</span></span>
<span data-ttu-id="47bcb-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="47bcb-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="47bcb-113">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="47bcb-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="47bcb-114">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="47bcb-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47bcb-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="47bcb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="47bcb-p104">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="47bcb-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="47bcb-120">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="47bcb-121">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="47bcb-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="47bcb-122">En la página **mis dominios** , busque el dominio que desea usar con Microsoft y seleccione el vínculo **administrar** junto a él.</span><span class="sxs-lookup"><span data-stu-id="47bcb-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="47bcb-123">En el panel de navegación izquierdo, seleccione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="47bcb-124">En la sección \* \* registros de recursos personalizados \* \*, en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47bcb-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="47bcb-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="47bcb-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="47bcb-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="47bcb-127">**Name**</span></span> <br/> |<span data-ttu-id="47bcb-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="47bcb-128">**Type**</span></span> <br/> |<span data-ttu-id="47bcb-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="47bcb-129">**TTL**</span></span> <br/> |<span data-ttu-id="47bcb-130">**Datos**</span><span class="sxs-lookup"><span data-stu-id="47bcb-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="47bcb-131">TXT</span><span class="sxs-lookup"><span data-stu-id="47bcb-131">TXT</span></span>  <br/> |<span data-ttu-id="47bcb-132">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-132">1H</span></span>  <br/> |<span data-ttu-id="47bcb-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="47bcb-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="47bcb-134">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="47bcb-134">**Note:** This is an example.</span></span> <span data-ttu-id="47bcb-135">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="47bcb-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="47bcb-136">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="47bcb-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="47bcb-137">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="47bcb-138">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="47bcb-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="47bcb-139">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.</span><span class="sxs-lookup"><span data-stu-id="47bcb-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="47bcb-140">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="47bcb-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="47bcb-141">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="47bcb-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="47bcb-142">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="47bcb-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="47bcb-143">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="47bcb-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="47bcb-144">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="47bcb-145">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="47bcb-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="47bcb-146">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="47bcb-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="47bcb-147">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="47bcb-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="47bcb-148">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47bcb-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="47bcb-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="47bcb-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="47bcb-p108">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="47bcb-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="47bcb-153">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="47bcb-154">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="47bcb-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="47bcb-155">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="47bcb-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="47bcb-156">Si tiene una cuenta de correo electrónico de G Suite, primero deberá eliminar los registros MX asociados a esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="47bcb-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="47bcb-157">Los registros MX de G Suite le impiden agregar otros registros MX, incluidos los necesarios para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47bcb-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="47bcb-158">Tenga en cuenta que eliminar los registros de G Suite no elimina su cuenta de G Suite.</span><span class="sxs-lookup"><span data-stu-id="47bcb-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="47bcb-159">Para eliminar sus registros MX de G Suite, siga los pasos que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="47bcb-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="47bcb-160">En la sección **registros sintéticos** , en el área **G Suite** , seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="47bcb-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-161">(You may have to scroll down.)</span></span>
    
    ![Seleccione eliminar en la sección registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="47bcb-163">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-163">Select **Delete**.</span></span>
    
    ![Seleccione eliminar.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="47bcb-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="47bcb-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="47bcb-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="47bcb-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="47bcb-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="47bcb-168">**Name**</span></span>|<span data-ttu-id="47bcb-169">**Type**</span><span class="sxs-lookup"><span data-stu-id="47bcb-169">**Type**</span></span>|<span data-ttu-id="47bcb-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="47bcb-170">**TTL**</span></span>|<span data-ttu-id="47bcb-171">**Datos**</span><span class="sxs-lookup"><span data-stu-id="47bcb-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="47bcb-172">MX</span><span class="sxs-lookup"><span data-stu-id="47bcb-172">MX</span></span>  <br/> |<span data-ttu-id="47bcb-173">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-173">1H</span></span>  <br/> |<span data-ttu-id="47bcb-174">0  *\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="47bcb-175">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="47bcb-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="47bcb-p110">El valor de **0** se corresponde con la prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="47bcb-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="47bcb-178">**Nota:** Obtén tu \< *clave* \> de dominio de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47bcb-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="47bcb-179">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="47bcb-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="47bcb-180">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="47bcb-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="47bcb-182">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-182">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="47bcb-184">Si hay otros registros MX personalizados, quítelos:</span><span class="sxs-lookup"><span data-stu-id="47bcb-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="47bcb-185">Seleccione **Editar** en la fila del registro MX.</span><span class="sxs-lookup"><span data-stu-id="47bcb-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Seleccione Editar en la fila del registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="47bcb-187">Para cada uno de los demás registros MX personalizados, seleccione la entrada en el cuadro **datos** y, después, presione la tecla **suprimir** en el teclado para eliminar ese registro.</span><span class="sxs-lookup"><span data-stu-id="47bcb-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="47bcb-188">Continúe hasta haber eliminado la entrada **Datos** de cada uno de los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="47bcb-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="47bcb-190">Cuando haya eliminado la entrada de **datos** de cada uno de los demás registros MX, seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="47bcb-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Seleccione Guardar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="47bcb-192">Agregar los cinco registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="47bcb-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="47bcb-193">Para empezar, vaya a su página de [Google Domains]https://domains.google.com/registrar) (e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="47bcb-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="47bcb-194">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="47bcb-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="47bcb-195">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="47bcb-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="47bcb-196">En la sección **Registros de recursos personalizados**, en los cuadros del nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47bcb-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="47bcb-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="47bcb-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="47bcb-199">**Name**</span><span class="sxs-lookup"><span data-stu-id="47bcb-199">**Name**</span></span>|<span data-ttu-id="47bcb-200">**Type**</span><span class="sxs-lookup"><span data-stu-id="47bcb-200">**Type**</span></span>|<span data-ttu-id="47bcb-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="47bcb-201">**TTL**</span></span>|<span data-ttu-id="47bcb-202">**Datos**</span><span class="sxs-lookup"><span data-stu-id="47bcb-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="47bcb-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="47bcb-203">autodiscover</span></span>  <br/> |<span data-ttu-id="47bcb-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="47bcb-204">CNAME</span></span>  <br/> |<span data-ttu-id="47bcb-205">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-205">1H</span></span>  <br/> |<span data-ttu-id="47bcb-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="47bcb-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="47bcb-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="47bcb-208">sip</span><span class="sxs-lookup"><span data-stu-id="47bcb-208">sip</span></span>  <br/> |<span data-ttu-id="47bcb-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="47bcb-209">CNAME</span></span>  <br/> |<span data-ttu-id="47bcb-210">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-210">1H</span></span>  <br/> |<span data-ttu-id="47bcb-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="47bcb-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="47bcb-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="47bcb-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="47bcb-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="47bcb-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="47bcb-214">CNAME</span></span>  <br/> |<span data-ttu-id="47bcb-215">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-215">1H</span></span>  <br/> |<span data-ttu-id="47bcb-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="47bcb-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="47bcb-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="47bcb-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="47bcb-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="47bcb-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="47bcb-219">CNAME</span></span>  <br/> |<span data-ttu-id="47bcb-220">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-220">1H</span></span>  <br/> |<span data-ttu-id="47bcb-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="47bcb-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="47bcb-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="47bcb-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="47bcb-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="47bcb-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="47bcb-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="47bcb-224">CNAME</span></span>  <br/> |<span data-ttu-id="47bcb-225">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-225">1H</span></span>  <br/> |<span data-ttu-id="47bcb-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="47bcb-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="47bcb-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="47bcb-229">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-229">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="47bcb-231">Agregue los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="47bcb-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="47bcb-232">En la sección **registros de recursos personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="47bcb-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="47bcb-233">Repita este proceso hasta que haya creado todos los registros CNAME necesarios.</span><span class="sxs-lookup"><span data-stu-id="47bcb-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="47bcb-234">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="47bcb-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47bcb-235">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="47bcb-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="47bcb-236">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="47bcb-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="47bcb-237">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47bcb-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="47bcb-238">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un único registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="47bcb-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="47bcb-239">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="47bcb-239">Need examples?</span></span> <span data-ttu-id="47bcb-240">Consulte estos [registros del sistema de nombres de dominio externo para Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="47bcb-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="47bcb-241">Para validar su registro de SPF, puede usar una de estas [herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="47bcb-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="47bcb-p113">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="47bcb-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="47bcb-245">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="47bcb-246">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="47bcb-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="47bcb-247">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="47bcb-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="47bcb-248">En la sección **registros de recursos personalizados** , en la fila registro TXT, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="47bcb-p114">Google Domains almacena los registros TXT como un conjunto que puede contener varios registros. Cuando tenga como mínimo otro registro TXT (como el registro TXT que usó para comprobar el dominio), necesitará agregar los nuevos registros TXT a ese conjunto de registros. Si intenta agregar otros registros TXT como entradas separadas, se mostrará el mensaje de error **Registro duplicado**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Seleccione Editar en la fila de registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="47bcb-253">Seleccione el control **(+)** .</span><span class="sxs-lookup"><span data-stu-id="47bcb-253">Select the **(+)** control.</span></span> 
    
    ![Seleccionar el control más](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="47bcb-255">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47bcb-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="47bcb-256">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="47bcb-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="47bcb-257">**Datos**</span><span class="sxs-lookup"><span data-stu-id="47bcb-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="47bcb-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="47bcb-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="47bcb-259">Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="47bcb-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="47bcb-261">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-261">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="47bcb-263">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="47bcb-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="47bcb-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="47bcb-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="47bcb-p115">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="47bcb-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="47bcb-268">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="47bcb-269">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="47bcb-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="47bcb-270">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="47bcb-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="47bcb-271">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="47bcb-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="47bcb-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="47bcb-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="47bcb-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="47bcb-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="47bcb-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="47bcb-275">**Name**</span><span class="sxs-lookup"><span data-stu-id="47bcb-275">**Name**</span></span>|<span data-ttu-id="47bcb-276">**Type**</span><span class="sxs-lookup"><span data-stu-id="47bcb-276">**Type**</span></span>|<span data-ttu-id="47bcb-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="47bcb-277">**TTL**</span></span>|<span data-ttu-id="47bcb-278">**Datos**</span><span class="sxs-lookup"><span data-stu-id="47bcb-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="47bcb-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="47bcb-279">_sip._tls</span></span>|<span data-ttu-id="47bcb-280">SRV</span><span class="sxs-lookup"><span data-stu-id="47bcb-280">SRV</span></span>|<span data-ttu-id="47bcb-281">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-281">1H</span></span>|<span data-ttu-id="47bcb-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="47bcb-283">**Este valor debe terminar con un punto (.).** **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="47bcb-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="47bcb-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="47bcb-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="47bcb-285">SRV</span><span class="sxs-lookup"><span data-stu-id="47bcb-285">SRV</span></span>|<span data-ttu-id="47bcb-286">1H</span><span class="sxs-lookup"><span data-stu-id="47bcb-286">1H</span></span>|<span data-ttu-id="47bcb-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="47bcb-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="47bcb-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="47bcb-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="47bcb-289">Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="47bcb-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="47bcb-291">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="47bcb-291">Select **Add**.</span></span>
    
    ![Seleccione Agregar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="47bcb-293">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="47bcb-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="47bcb-294">En la sección **registros de recursos personalizados** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="47bcb-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="47bcb-295">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="47bcb-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="47bcb-296">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="47bcb-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="47bcb-297">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="47bcb-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
