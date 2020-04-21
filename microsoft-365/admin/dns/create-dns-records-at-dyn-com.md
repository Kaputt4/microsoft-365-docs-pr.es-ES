---
title: Crear registros DNS en Dyn.com para Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Dyn.com para Microsoft.
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629592"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="3c16b-103">Crear registros DNS en Dyn.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c16b-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="3c16b-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="3c16b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3c16b-105">Si Dyn.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="3c16b-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="3c16b-106">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="3c16b-106">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3c16b-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c16b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3c16b-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="3c16b-110">Add a TXT record for verification</span></span>
<span data-ttu-id="3c16b-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3c16b-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="3c16b-p102">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3c16b-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c16b-115">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="3c16b-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c16b-116">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c16b-117">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c16b-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c16b-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3c16b-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3c16b-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c16b-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c16b-120">**Host**</span></span>|<span data-ttu-id="3c16b-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c16b-121">**TTL**</span></span>|<span data-ttu-id="3c16b-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c16b-122">**Type**</span></span>|<span data-ttu-id="3c16b-123">**Datos**</span><span class="sxs-lookup"><span data-stu-id="3c16b-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c16b-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3c16b-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3c16b-125">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-125">600</span></span>  <br/> |<span data-ttu-id="3c16b-126">TXT</span><span class="sxs-lookup"><span data-stu-id="3c16b-126">TXT</span></span>  <br/> |<span data-ttu-id="3c16b-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3c16b-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3c16b-128">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3c16b-128">**Note:** This is an example.</span></span> <span data-ttu-id="3c16b-129">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3c16b-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3c16b-130">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="3c16b-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="3c16b-132">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="3c16b-134">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="3c16b-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3c16b-135">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.</span><span class="sxs-lookup"><span data-stu-id="3c16b-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3c16b-136">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="3c16b-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3c16b-137">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="3c16b-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3c16b-138">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="3c16b-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3c16b-139">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="3c16b-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3c16b-140">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3c16b-p104">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c16b-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3c16b-144">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c16b-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3c16b-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3c16b-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3c16b-p105">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3c16b-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c16b-149">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="3c16b-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c16b-150">En la página DNS de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c16b-151">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c16b-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c16b-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3c16b-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3c16b-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c16b-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c16b-154">**Host**</span></span>|<span data-ttu-id="3c16b-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c16b-155">**TTL**</span></span>|<span data-ttu-id="3c16b-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c16b-156">**Type**</span></span>|<span data-ttu-id="3c16b-157">**Datos**</span><span class="sxs-lookup"><span data-stu-id="3c16b-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c16b-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3c16b-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3c16b-159">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-159">600</span></span>  <br/> |<span data-ttu-id="3c16b-160">MX</span><span class="sxs-lookup"><span data-stu-id="3c16b-160">MX</span></span>  <br/> |<span data-ttu-id="3c16b-161">10  *\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3c16b-162">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="3c16b-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3c16b-p106">El valor de **10** se corresponde con la prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="3c16b-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3c16b-165">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c16b-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3c16b-166">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="3c16b-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="3c16b-167">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="3c16b-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="3c16b-169">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="3c16b-171">Si hay otros registros MX, quítelos (para hacerlo, seleccione la casilla junto a cada registro en la columna **Eliminar**).</span><span class="sxs-lookup"><span data-stu-id="3c16b-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="3c16b-173">Seleccione **aplicar cambios**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c16b-175">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c16b-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3c16b-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3c16b-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3c16b-p108">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3c16b-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c16b-180">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="3c16b-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c16b-181">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c16b-182">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c16b-183">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3c16b-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3c16b-184">En la sección **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c16b-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3c16b-185">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="3c16b-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c16b-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c16b-186">**Host**</span></span>|<span data-ttu-id="3c16b-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c16b-187">**TTL**</span></span>|<span data-ttu-id="3c16b-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c16b-188">**Type**</span></span>|<span data-ttu-id="3c16b-189">**Datos**</span><span class="sxs-lookup"><span data-stu-id="3c16b-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c16b-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3c16b-190">autodiscover</span></span>  <br/> |<span data-ttu-id="3c16b-191">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-191">600</span></span>  <br/> |<span data-ttu-id="3c16b-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c16b-192">CNAME</span></span>  <br/> |<span data-ttu-id="3c16b-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3c16b-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3c16b-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c16b-195">sip</span><span class="sxs-lookup"><span data-stu-id="3c16b-195">sip</span></span>  <br/> |<span data-ttu-id="3c16b-196">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-196">600</span></span>  <br/> |<span data-ttu-id="3c16b-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c16b-197">CNAME</span></span>  <br/> |<span data-ttu-id="3c16b-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3c16b-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3c16b-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c16b-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3c16b-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3c16b-201">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-201">600</span></span>  <br/> |<span data-ttu-id="3c16b-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c16b-202">CNAME</span></span>  <br/> |<span data-ttu-id="3c16b-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3c16b-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3c16b-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c16b-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3c16b-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3c16b-206">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-206">600</span></span>  <br/> |<span data-ttu-id="3c16b-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c16b-207">CNAME</span></span>  <br/> |<span data-ttu-id="3c16b-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3c16b-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3c16b-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3c16b-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c16b-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3c16b-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3c16b-211">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-211">600</span></span>  <br/> |<span data-ttu-id="3c16b-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c16b-212">CNAME</span></span>  <br/> |<span data-ttu-id="3c16b-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3c16b-214">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="3c16b-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="3c16b-216">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="3c16b-218">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3c16b-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="3c16b-219">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **crear registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="3c16b-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="3c16b-220">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3c16b-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3c16b-221">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3c16b-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3c16b-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3c16b-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c16b-223">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="3c16b-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3c16b-224">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3c16b-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3c16b-225">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c16b-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3c16b-226">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="3c16b-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="3c16b-p110">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="3c16b-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c16b-230">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="3c16b-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c16b-231">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c16b-232">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c16b-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c16b-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3c16b-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3c16b-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c16b-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c16b-235">**Host**</span></span>|<span data-ttu-id="3c16b-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c16b-236">**TTL**</span></span>|<span data-ttu-id="3c16b-237">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c16b-237">**Type**</span></span>|<span data-ttu-id="3c16b-238">**Datos**</span><span class="sxs-lookup"><span data-stu-id="3c16b-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c16b-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3c16b-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3c16b-240">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-240">600</span></span>  <br/> |<span data-ttu-id="3c16b-241">TXT</span><span class="sxs-lookup"><span data-stu-id="3c16b-241">TXT</span></span>  <br/> |<span data-ttu-id="3c16b-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3c16b-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3c16b-243">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3c16b-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="3c16b-245">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c16b-247">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c16b-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3c16b-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3c16b-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3c16b-249">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="3c16b-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="3c16b-250">Se le pedirá que inicie sesión primero</span><span class="sxs-lookup"><span data-stu-id="3c16b-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c16b-252">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="3c16b-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c16b-253">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c16b-254">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c16b-255">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="3c16b-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3c16b-256">En la sección **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c16b-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3c16b-257">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="3c16b-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c16b-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c16b-258">**Host**</span></span>|<span data-ttu-id="3c16b-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c16b-259">**TTL**</span></span>|<span data-ttu-id="3c16b-260">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c16b-260">**Type**</span></span>|<span data-ttu-id="3c16b-261">**Datos**</span><span class="sxs-lookup"><span data-stu-id="3c16b-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c16b-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="3c16b-262">_sip._tls</span></span>|<span data-ttu-id="3c16b-263">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-263">600</span></span>|<span data-ttu-id="3c16b-264">SRV</span><span class="sxs-lookup"><span data-stu-id="3c16b-264">SRV</span></span>|<span data-ttu-id="3c16b-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3c16b-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3c16b-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="3c16b-267">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3c16b-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3c16b-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="3c16b-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3c16b-269">600</span><span class="sxs-lookup"><span data-stu-id="3c16b-269">600</span></span>|<span data-ttu-id="3c16b-270">SRV</span><span class="sxs-lookup"><span data-stu-id="3c16b-270">SRV</span></span>|<span data-ttu-id="3c16b-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c16b-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3c16b-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3c16b-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="3c16b-273">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3c16b-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="3c16b-275">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="3c16b-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="3c16b-277">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="3c16b-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3c16b-278">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **crear registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="3c16b-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="3c16b-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c16b-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
