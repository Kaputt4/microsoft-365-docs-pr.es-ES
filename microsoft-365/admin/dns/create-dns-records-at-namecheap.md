---
title: Crear registros DNS en Namecheap para Microsoft
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Namecheap para Microsoft.
ms.openlocfilehash: 3de8c4fb7809423848564590193e00537362c034
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910155"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="14568-103">Crear registros DNS en Namecheap para Microsoft</span><span class="sxs-lookup"><span data-stu-id="14568-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="14568-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="14568-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="14568-105">Si Namecheap es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="14568-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="14568-106">Después de agregar estos registros en Namecheap, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14568-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14568-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14568-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="14568-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="14568-110">Add a TXT record for verification</span></span>
<span data-ttu-id="14568-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="14568-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="14568-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="14568-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14568-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="14568-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="14568-116">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="14568-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="14568-117">Para empezar, vaya a la página de dominios de Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="14568-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="14568-118">Se te pedirá que inicies sesión y continúes.</span><span class="sxs-lookup"><span data-stu-id="14568-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="14568-120">En la **página Aterrizaje,** en **Cuenta**, elija **Lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="14568-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="14568-122">En la **página Lista de** dominios, busque el nombre del dominio que desea editar y, a continuación, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="14568-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="14568-124">Seleccione **DNS avanzado**.</span><span class="sxs-lookup"><span data-stu-id="14568-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="14568-126">En la **sección REGISTROS DE HOST,** seleccione **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="14568-128">En la **lista** desplegable Tipo, seleccione **Registro TXT**.</span><span class="sxs-lookup"><span data-stu-id="14568-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14568-129">La **lista** desplegable Tipo aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="14568-131">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="14568-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="14568-132">(Elija el **valor TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="14568-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="14568-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14568-133">**Type**</span></span>|<span data-ttu-id="14568-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="14568-134">**Host**</span></span>|<span data-ttu-id="14568-135">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14568-135">**Value**</span></span>|<span data-ttu-id="14568-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14568-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14568-137">TXT</span><span class="sxs-lookup"><span data-stu-id="14568-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="14568-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="14568-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="14568-139">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="14568-139">**Note:** This is an example.</span></span> <span data-ttu-id="14568-140">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="14568-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="14568-141">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="14568-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="14568-142">30 min</span><span class="sxs-lookup"><span data-stu-id="14568-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="14568-144">Seleccione el **control Guardar cambios** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="14568-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="14568-146">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="14568-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="14568-147">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="14568-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="14568-148">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="14568-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="14568-149">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="14568-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="14568-150">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="14568-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="14568-151">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="14568-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="14568-152">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="14568-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="14568-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14568-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="14568-156">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="14568-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="14568-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="14568-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="14568-158">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="14568-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="14568-159">Para empezar, vaya a la página de dominios de Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="14568-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="14568-160">Se te pedirá que inicies sesión y continúes.</span><span class="sxs-lookup"><span data-stu-id="14568-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="14568-162">En la **página Aterrizaje,** en **Cuenta**, elija **Lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="14568-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="14568-164">En la **página Lista de** dominios, busque el nombre del dominio que desea editar y, a continuación, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="14568-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="14568-166">Seleccione **DNS avanzado**.</span><span class="sxs-lookup"><span data-stu-id="14568-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="14568-168">En la **sección CONFIGURACIÓN DEL CORREO,** seleccione **MX personalizado** en **la** lista desplegable Reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14568-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="14568-169">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="14568-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="14568-171">Seleccione **Agregar nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="14568-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="14568-173">En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="14568-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="14568-174">(El **cuadro** Prioridad es el cuadro sin nombre situado a la derecha del **cuadro** Valor.</span><span class="sxs-lookup"><span data-stu-id="14568-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="14568-175">Elija el **valor TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="14568-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="14568-176">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14568-176">**Type**</span></span>|<span data-ttu-id="14568-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="14568-177">**Host**</span></span>|<span data-ttu-id="14568-178">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14568-178">**Value**</span></span>|<span data-ttu-id="14568-179">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="14568-179">**Priority**</span></span>|<span data-ttu-id="14568-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14568-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14568-181">Registro MX</span><span class="sxs-lookup"><span data-stu-id="14568-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="14568-182">\<*domain-key*\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="14568-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="14568-183">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="14568-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="14568-184">**Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14568-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="14568-185">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="14568-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="14568-186">0</span><span class="sxs-lookup"><span data-stu-id="14568-186">0</span></span>  <br/> <span data-ttu-id="14568-187">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="14568-187">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="14568-188">30 min</span><span class="sxs-lookup"><span data-stu-id="14568-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="14568-190">Seleccione el **control Guardar cambios** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="14568-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="14568-192">Si existen otros registros MX, quite cada uno de ellos usando el procedimiento de dos pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="14568-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="14568-193">En primer lugar, seleccione **el icono Eliminar** (papelera) del registro que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="14568-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="14568-195">En segundo lugar, **seleccione Sí** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="14568-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="14568-197">Quite todos los registros MX excepto el que agregó anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="14568-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="14568-198">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="14568-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="14568-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="14568-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="14568-200">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="14568-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="14568-201">Para empezar, vaya a la página de dominios de Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="14568-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="14568-202">Se te pedirá que inicies sesión y continúes.</span><span class="sxs-lookup"><span data-stu-id="14568-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="14568-204">En la **página Aterrizaje,** en **Cuenta**, elija **Lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="14568-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="14568-206">En la **página Lista de** dominios, busque el nombre del dominio que desea editar y, a continuación, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="14568-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="14568-208">Seleccione **DNS avanzado**.</span><span class="sxs-lookup"><span data-stu-id="14568-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="14568-210">En la **sección REGISTROS DE HOST,** seleccione **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="14568-212">En la **lista** desplegable Tipo, seleccione **Registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="14568-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14568-213">La **lista** desplegable Tipo aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="14568-215">En los cuadros vacíos para el nuevo registro, seleccione **CNAME** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="14568-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="14568-216">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14568-216">**Type**</span></span>|<span data-ttu-id="14568-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="14568-217">**Host**</span></span>|<span data-ttu-id="14568-218">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14568-218">**Value**</span></span>|<span data-ttu-id="14568-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14568-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14568-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="14568-220">CNAME</span></span>  <br/> |<span data-ttu-id="14568-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="14568-221">autodiscover</span></span>  <br/> |<span data-ttu-id="14568-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="14568-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="14568-223">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="14568-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-224">3600</span><span class="sxs-lookup"><span data-stu-id="14568-224">3600</span></span>  <br/> |
    |<span data-ttu-id="14568-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="14568-225">CNAME</span></span>  <br/> |<span data-ttu-id="14568-226">sip</span><span class="sxs-lookup"><span data-stu-id="14568-226">sip</span></span>  <br/> |<span data-ttu-id="14568-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14568-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="14568-228">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="14568-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-229">3600</span><span class="sxs-lookup"><span data-stu-id="14568-229">3600</span></span>  <br/> |
    |<span data-ttu-id="14568-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="14568-230">CNAME</span></span>  <br/> |<span data-ttu-id="14568-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="14568-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="14568-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14568-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="14568-233">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="14568-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-234">3600</span><span class="sxs-lookup"><span data-stu-id="14568-234">3600</span></span>  <br/> |
    |<span data-ttu-id="14568-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="14568-235">CNAME</span></span>  <br/> |<span data-ttu-id="14568-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="14568-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="14568-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="14568-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="14568-238">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="14568-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-239">3600</span><span class="sxs-lookup"><span data-stu-id="14568-239">3600</span></span>  <br/> |
    |<span data-ttu-id="14568-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="14568-240">CNAME</span></span>  <br/> |<span data-ttu-id="14568-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="14568-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="14568-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="14568-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="14568-243">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="14568-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-244">3600</span><span class="sxs-lookup"><span data-stu-id="14568-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="14568-246">Seleccione el **control Guardar cambios** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="14568-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="14568-248">Con los cuatro pasos anteriores y los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="14568-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="14568-249">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="14568-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="14568-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="14568-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14568-251">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="14568-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="14568-252">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="14568-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="14568-253">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14568-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="14568-254">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="14568-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="14568-255">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="14568-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="14568-256">Para empezar, vaya a la página de dominios de Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="14568-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="14568-257">Se te pedirá que inicies sesión y continúes.</span><span class="sxs-lookup"><span data-stu-id="14568-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="14568-258">En la **página Aterrizaje,** en **Cuenta**, elija **Lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="14568-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="14568-260">En la **página Lista de** dominios, busque el nombre del dominio que desea editar y, a continuación, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="14568-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="14568-262">Seleccione **DNS avanzado**.</span><span class="sxs-lookup"><span data-stu-id="14568-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="14568-264">En la **sección REGISTROS DE HOST,** seleccione **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="14568-266">En la **lista** desplegable Tipo, seleccione **Registro TXT**.</span><span class="sxs-lookup"><span data-stu-id="14568-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14568-267">La **lista** desplegable Tipo aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="14568-269">En los cuadros del nuevo registro, escriba o copie y pegue los siguientes valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="14568-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="14568-270">(Elija el **valor TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="14568-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="14568-271">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14568-271">**Type**</span></span>|<span data-ttu-id="14568-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="14568-272">**Host**</span></span>|<span data-ttu-id="14568-273">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14568-273">**Value**</span></span>|<span data-ttu-id="14568-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14568-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14568-275">TXT</span><span class="sxs-lookup"><span data-stu-id="14568-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="14568-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="14568-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="14568-277">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="14568-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="14568-278">30 min</span><span class="sxs-lookup"><span data-stu-id="14568-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="14568-280">Seleccione el **control Guardar cambios** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="14568-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="14568-282">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="14568-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="14568-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="14568-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="14568-284">Para empezar, vaya a la página de dominios de Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="14568-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="14568-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="14568-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="14568-287">En la **página Aterrizaje,** en **Cuenta**, elija **Lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="14568-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="14568-289">En la **página Lista de** dominios, busque el nombre del dominio que desea editar y, a continuación, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="14568-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="14568-291">Seleccione **DNS avanzado**.</span><span class="sxs-lookup"><span data-stu-id="14568-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="14568-293">En la **sección REGISTROS DE HOST,** seleccione **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="14568-295">En la **lista** desplegable Tipo, seleccione **Registro SRV**.</span><span class="sxs-lookup"><span data-stu-id="14568-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14568-296">La **lista** desplegable Tipo aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.</span><span class="sxs-lookup"><span data-stu-id="14568-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="14568-298">En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="14568-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="14568-299">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="14568-299">**Service**</span></span>|<span data-ttu-id="14568-300">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="14568-300">**Protocol**</span></span>|<span data-ttu-id="14568-301">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="14568-301">**Priority**</span></span>|<span data-ttu-id="14568-302">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="14568-302">**Weight**</span></span>|<span data-ttu-id="14568-303">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="14568-303">**Port**</span></span>|<span data-ttu-id="14568-304">**Destino**</span><span class="sxs-lookup"><span data-stu-id="14568-304">**Target**</span></span>|<span data-ttu-id="14568-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14568-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14568-306">_sip</span><span class="sxs-lookup"><span data-stu-id="14568-306">_sip</span></span>  <br/> |<span data-ttu-id="14568-307">_tls</span><span class="sxs-lookup"><span data-stu-id="14568-307">_tls</span></span>  <br/> |<span data-ttu-id="14568-308">100</span><span class="sxs-lookup"><span data-stu-id="14568-308">100</span></span>  <br/> |<span data-ttu-id="14568-309">1</span><span class="sxs-lookup"><span data-stu-id="14568-309">1</span></span>  <br/> |<span data-ttu-id="14568-310">443</span><span class="sxs-lookup"><span data-stu-id="14568-310">443</span></span>  <br/> |<span data-ttu-id="14568-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14568-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="14568-312">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="14568-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-313">30 min</span><span class="sxs-lookup"><span data-stu-id="14568-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="14568-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="14568-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="14568-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="14568-315">_tcp</span></span>  <br/> |<span data-ttu-id="14568-316">100</span><span class="sxs-lookup"><span data-stu-id="14568-316">100</span></span>  <br/> |<span data-ttu-id="14568-317">1</span><span class="sxs-lookup"><span data-stu-id="14568-317">1</span></span>  <br/> |<span data-ttu-id="14568-318">5061</span><span class="sxs-lookup"><span data-stu-id="14568-318">5061</span></span>  <br/> |<span data-ttu-id="14568-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14568-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="14568-320">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="14568-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14568-321">30 min</span><span class="sxs-lookup"><span data-stu-id="14568-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="14568-323">Seleccione el **control Guardar cambios** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="14568-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="14568-325">Con los cuatro pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="14568-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14568-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14568-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

