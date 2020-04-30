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
ms.openlocfilehash: afce9c21b0f717a038f378d4bf7114724748c2ac
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939288"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="522d8-103">Crear registros DNS en Dyn.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="522d8-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="522d8-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="522d8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="522d8-105">Si Dyn.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="522d8-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="522d8-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="522d8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="522d8-109">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="522d8-109">Add a TXT record for verification</span></span>
<span data-ttu-id="522d8-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="522d8-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="522d8-p102">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="522d8-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="522d8-114">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="522d8-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="522d8-115">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="522d8-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="522d8-116">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="522d8-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="522d8-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="522d8-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="522d8-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="522d8-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="522d8-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="522d8-119">**Host**</span></span>|<span data-ttu-id="522d8-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="522d8-120">**TTL**</span></span>|<span data-ttu-id="522d8-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="522d8-121">**Type**</span></span>|<span data-ttu-id="522d8-122">**Datos**</span><span class="sxs-lookup"><span data-stu-id="522d8-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="522d8-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="522d8-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="522d8-124">600</span><span class="sxs-lookup"><span data-stu-id="522d8-124">600</span></span>  <br/> |<span data-ttu-id="522d8-125">TXT</span><span class="sxs-lookup"><span data-stu-id="522d8-125">TXT</span></span>  <br/> |<span data-ttu-id="522d8-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="522d8-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="522d8-127">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="522d8-127">**Note:** This is an example.</span></span> <span data-ttu-id="522d8-128">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="522d8-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="522d8-129">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="522d8-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="522d8-131">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="522d8-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="522d8-133">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="522d8-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="522d8-134">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="522d8-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="522d8-135">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="522d8-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="522d8-136">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="522d8-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="522d8-137">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="522d8-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="522d8-138">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="522d8-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="522d8-139">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="522d8-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="522d8-p104">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="522d8-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="522d8-143">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="522d8-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="522d8-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="522d8-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="522d8-p105">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="522d8-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="522d8-148">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="522d8-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="522d8-149">En la página DNS de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="522d8-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="522d8-150">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="522d8-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="522d8-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="522d8-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="522d8-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="522d8-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="522d8-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="522d8-153">**Host**</span></span>|<span data-ttu-id="522d8-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="522d8-154">**TTL**</span></span>|<span data-ttu-id="522d8-155">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="522d8-155">**Type**</span></span>|<span data-ttu-id="522d8-156">**Datos**</span><span class="sxs-lookup"><span data-stu-id="522d8-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="522d8-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="522d8-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="522d8-158">600</span><span class="sxs-lookup"><span data-stu-id="522d8-158">600</span></span>  <br/> |<span data-ttu-id="522d8-159">MX</span><span class="sxs-lookup"><span data-stu-id="522d8-159">MX</span></span>  <br/> |<span data-ttu-id="522d8-160">10  *\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="522d8-161">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="522d8-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="522d8-p106">El valor de **10** se corresponde con la prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="522d8-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="522d8-164">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="522d8-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="522d8-165">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="522d8-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="522d8-166">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="522d8-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="522d8-168">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="522d8-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="522d8-170">Si hay otros registros MX, quítelos (para hacerlo, seleccione la casilla junto a cada registro en la columna **Eliminar**).</span><span class="sxs-lookup"><span data-stu-id="522d8-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="522d8-172">Seleccione **aplicar cambios**.</span><span class="sxs-lookup"><span data-stu-id="522d8-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="522d8-174">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="522d8-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="522d8-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="522d8-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="522d8-p108">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="522d8-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="522d8-179">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="522d8-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="522d8-180">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="522d8-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="522d8-181">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="522d8-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="522d8-182">Agregue el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="522d8-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="522d8-183">En la sección **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="522d8-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="522d8-184">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="522d8-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="522d8-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="522d8-185">**Host**</span></span>|<span data-ttu-id="522d8-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="522d8-186">**TTL**</span></span>|<span data-ttu-id="522d8-187">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="522d8-187">**Type**</span></span>|<span data-ttu-id="522d8-188">**Datos**</span><span class="sxs-lookup"><span data-stu-id="522d8-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="522d8-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="522d8-189">autodiscover</span></span>  <br/> |<span data-ttu-id="522d8-190">600</span><span class="sxs-lookup"><span data-stu-id="522d8-190">600</span></span>  <br/> |<span data-ttu-id="522d8-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="522d8-191">CNAME</span></span>  <br/> |<span data-ttu-id="522d8-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="522d8-193">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="522d8-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="522d8-194">sip</span><span class="sxs-lookup"><span data-stu-id="522d8-194">sip</span></span>  <br/> |<span data-ttu-id="522d8-195">600</span><span class="sxs-lookup"><span data-stu-id="522d8-195">600</span></span>  <br/> |<span data-ttu-id="522d8-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="522d8-196">CNAME</span></span>  <br/> |<span data-ttu-id="522d8-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="522d8-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="522d8-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="522d8-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="522d8-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="522d8-200">600</span><span class="sxs-lookup"><span data-stu-id="522d8-200">600</span></span>  <br/> |<span data-ttu-id="522d8-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="522d8-201">CNAME</span></span>  <br/> |<span data-ttu-id="522d8-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="522d8-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="522d8-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="522d8-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="522d8-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="522d8-205">600</span><span class="sxs-lookup"><span data-stu-id="522d8-205">600</span></span>  <br/> |<span data-ttu-id="522d8-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="522d8-206">CNAME</span></span>  <br/> |<span data-ttu-id="522d8-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="522d8-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="522d8-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="522d8-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="522d8-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="522d8-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="522d8-210">600</span><span class="sxs-lookup"><span data-stu-id="522d8-210">600</span></span>  <br/> |<span data-ttu-id="522d8-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="522d8-211">CNAME</span></span>  <br/> |<span data-ttu-id="522d8-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="522d8-213">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="522d8-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="522d8-215">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="522d8-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="522d8-217">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="522d8-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="522d8-218">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **crear registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="522d8-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="522d8-219">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="522d8-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="522d8-220">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="522d8-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="522d8-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="522d8-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="522d8-222">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="522d8-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="522d8-223">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="522d8-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="522d8-224">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="522d8-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="522d8-225">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="522d8-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="522d8-p110">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="522d8-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="522d8-229">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="522d8-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="522d8-230">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="522d8-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="522d8-231">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="522d8-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="522d8-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="522d8-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="522d8-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="522d8-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="522d8-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="522d8-234">**Host**</span></span>|<span data-ttu-id="522d8-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="522d8-235">**TTL**</span></span>|<span data-ttu-id="522d8-236">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="522d8-236">**Type**</span></span>|<span data-ttu-id="522d8-237">**Datos**</span><span class="sxs-lookup"><span data-stu-id="522d8-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="522d8-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="522d8-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="522d8-239">600</span><span class="sxs-lookup"><span data-stu-id="522d8-239">600</span></span>  <br/> |<span data-ttu-id="522d8-240">TXT</span><span class="sxs-lookup"><span data-stu-id="522d8-240">TXT</span></span>  <br/> |<span data-ttu-id="522d8-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="522d8-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="522d8-242">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="522d8-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="522d8-244">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="522d8-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="522d8-246">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="522d8-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="522d8-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="522d8-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="522d8-248">Para empezar, vaya a su página de dominios en Dyn.com a través de [este vínculo](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="522d8-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="522d8-249">Se le pedirá que inicie sesión primero</span><span class="sxs-lookup"><span data-stu-id="522d8-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="522d8-251">En la página **servicios de nivel de zona** , seleccione **servicio DNS estándar de Dyn** para el dominio que quiera editar.</span><span class="sxs-lookup"><span data-stu-id="522d8-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="522d8-252">En la página **DNS** de su dominio, seleccione **preferencias**.</span><span class="sxs-lookup"><span data-stu-id="522d8-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="522d8-253">Seleccione **Habilitar interfaz de experto**.</span><span class="sxs-lookup"><span data-stu-id="522d8-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="522d8-254">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="522d8-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="522d8-255">En la sección **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="522d8-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="522d8-256">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="522d8-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="522d8-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="522d8-257">**Host**</span></span>|<span data-ttu-id="522d8-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="522d8-258">**TTL**</span></span>|<span data-ttu-id="522d8-259">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="522d8-259">**Type**</span></span>|<span data-ttu-id="522d8-260">**Datos**</span><span class="sxs-lookup"><span data-stu-id="522d8-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="522d8-261">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="522d8-261">_sip._tls</span></span>|<span data-ttu-id="522d8-262">600</span><span class="sxs-lookup"><span data-stu-id="522d8-262">600</span></span>|<span data-ttu-id="522d8-263">SRV</span><span class="sxs-lookup"><span data-stu-id="522d8-263">SRV</span></span>|<span data-ttu-id="522d8-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="522d8-265">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="522d8-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="522d8-266">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="522d8-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="522d8-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="522d8-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="522d8-268">600</span><span class="sxs-lookup"><span data-stu-id="522d8-268">600</span></span>|<span data-ttu-id="522d8-269">SRV</span><span class="sxs-lookup"><span data-stu-id="522d8-269">SRV</span></span>|<span data-ttu-id="522d8-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="522d8-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="522d8-271">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="522d8-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="522d8-272">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="522d8-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="522d8-274">Seleccione **crear registro**.</span><span class="sxs-lookup"><span data-stu-id="522d8-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="522d8-276">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="522d8-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="522d8-277">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **crear registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="522d8-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="522d8-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="522d8-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
