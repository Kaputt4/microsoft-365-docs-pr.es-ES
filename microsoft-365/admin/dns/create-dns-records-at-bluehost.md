---
title: Crear registros DNS en Bluehost para Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Bluehost para Microsoft.
ms.openlocfilehash: 7b241c4635ecc4a8092702f95d19df7ed94ce1cd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400562"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="8427a-103">Crear registros DNS en Bluehost para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8427a-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="8427a-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="8427a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8427a-105">Si Bluehost es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="8427a-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8427a-106">Después de agregar estos registros a Bluehost, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8427a-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="8427a-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="8427a-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8427a-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="8427a-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8427a-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8427a-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8427a-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="8427a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="8427a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8427a-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8427a-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8427a-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="8427a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8427a-116">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="8427a-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="8427a-117">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="8427a-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8427a-118">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="8427a-119">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="8427a-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="8427a-120">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="8427a-120">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="8427a-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8427a-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8427a-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8427a-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8427a-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="8427a-123">**Host Record**</span></span> <br/> |<span data-ttu-id="8427a-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8427a-124">**TTL**</span></span> <br/> |<span data-ttu-id="8427a-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8427a-125">**Type**</span></span> <br/> |<span data-ttu-id="8427a-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="8427a-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="8427a-127">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-127">14400</span></span>  <br/> |<span data-ttu-id="8427a-128">TXT</span><span class="sxs-lookup"><span data-stu-id="8427a-128">TXT</span></span>  <br/> |<span data-ttu-id="8427a-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8427a-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8427a-130">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8427a-130">**Note:** This is an example.</span></span> <span data-ttu-id="8427a-131">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="8427a-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="8427a-132">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="8427a-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="8427a-133">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="8427a-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="8427a-134">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="8427a-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8427a-135">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="8427a-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="8427a-136">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8427a-137">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="8427a-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8427a-138">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="8427a-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8427a-139">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="8427a-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8427a-140">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="8427a-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8427a-141">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="8427a-141">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8427a-142">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="8427a-142">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8427a-143">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8427a-143">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8427a-144">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8427a-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8427a-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8427a-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8427a-146">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="8427a-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="8427a-147">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="8427a-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8427a-148">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="8427a-149">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="8427a-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="8427a-150">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="8427a-150">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="8427a-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8427a-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8427a-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8427a-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8427a-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="8427a-153">**Host Record**</span></span>|<span data-ttu-id="8427a-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8427a-154">**TTL**</span></span>|<span data-ttu-id="8427a-155">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8427a-155">**Type**</span></span>|<span data-ttu-id="8427a-156">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="8427a-156">**Points To**</span></span>|<span data-ttu-id="8427a-157">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="8427a-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8427a-158">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-158">14400</span></span>  <br/> |<span data-ttu-id="8427a-159">MX</span><span class="sxs-lookup"><span data-stu-id="8427a-159">MX</span></span>  <br/> | <span data-ttu-id="8427a-160">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8427a-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="8427a-161">**Nota:** Obtén tu \<*domain-key*\> cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8427a-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="8427a-162">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="8427a-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8427a-163">comprendi</span><span class="sxs-lookup"><span data-stu-id="8427a-163">0</span></span>  <br/> <span data-ttu-id="8427a-164">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="8427a-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Elija tipo en la lista desplegable](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="8427a-166">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="8427a-166">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="8427a-168">Si hay otros registros MX en la sección **MX (agente de intercambio de correo)**, elimínelos.</span><span class="sxs-lookup"><span data-stu-id="8427a-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="8427a-169">Para uno de los demás registros MX, seleccione **eliminar.**</span><span class="sxs-lookup"><span data-stu-id="8427a-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Seleccione Eliminar para cada registro MX adicional](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="8427a-171">En el cuadro de diálogo de confirmación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8427a-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Seleccione Aceptar.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="8427a-173">Siga el mismo procedimiento para eliminar el resto de los registros MX que se muestren.</span><span class="sxs-lookup"><span data-stu-id="8427a-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8427a-174">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8427a-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8427a-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8427a-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8427a-176">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="8427a-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="8427a-177">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="8427a-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8427a-178">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="8427a-179">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="8427a-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="8427a-180">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="8427a-180">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="8427a-181">En la sección registros de **A (host)** , busque la fila del registro de **detección automática** y, a continuación, seleccione **eliminar** para esa fila.</span><span class="sxs-lookup"><span data-stu-id="8427a-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8427a-182">Debe eliminar el registro de **detección automática** existente *antes* de agregar el registro de **detección automática** que necesita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8427a-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="8427a-183">Bluehost no le permite mantener de forma simultánea dos registros **autodiscover**.</span><span class="sxs-lookup"><span data-stu-id="8427a-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Seleccione eliminar.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="8427a-185">Seleccione **ACEPTAR**.</span><span class="sxs-lookup"><span data-stu-id="8427a-185">Select **OK**.</span></span>
    
    ![Seleccione Aceptar.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="8427a-187">Cree el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8427a-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8427a-188">En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8427a-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8427a-189">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8427a-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8427a-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="8427a-190">**Host Record**</span></span>|<span data-ttu-id="8427a-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8427a-191">**TTL**</span></span>|<span data-ttu-id="8427a-192">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8427a-192">**Type**</span></span>|<span data-ttu-id="8427a-193">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="8427a-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8427a-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8427a-194">autodiscover</span></span>  <br/> |<span data-ttu-id="8427a-195">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-195">14400</span></span>  <br/> |<span data-ttu-id="8427a-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="8427a-196">CNAME</span></span>  <br/> |<span data-ttu-id="8427a-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8427a-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8427a-198">sip</span><span class="sxs-lookup"><span data-stu-id="8427a-198">sip</span></span>  <br/> |<span data-ttu-id="8427a-199">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-199">14400</span></span>  <br/> |<span data-ttu-id="8427a-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="8427a-200">CNAME</span></span>  <br/> |<span data-ttu-id="8427a-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8427a-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8427a-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8427a-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8427a-203">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-203">14400</span></span>  <br/> |<span data-ttu-id="8427a-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="8427a-204">CNAME</span></span>  <br/> |<span data-ttu-id="8427a-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8427a-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8427a-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8427a-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8427a-207">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-207">14400</span></span>  <br/> |<span data-ttu-id="8427a-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="8427a-208">CNAME</span></span>  <br/> |<span data-ttu-id="8427a-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8427a-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8427a-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8427a-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8427a-211">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-211">14400</span></span>  <br/> |<span data-ttu-id="8427a-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="8427a-212">CNAME</span></span>  <br/> |<span data-ttu-id="8427a-213">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8427a-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Crear el primer registro CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="8427a-215">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="8427a-215">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="8427a-217">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8427a-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="8427a-218">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="8427a-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="8427a-219">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8427a-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8427a-220">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="8427a-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8427a-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8427a-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8427a-222">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8427a-223">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="8427a-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8427a-224">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8427a-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8427a-225">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8427a-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="8427a-226">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="8427a-226">Need examples?</span></span> <span data-ttu-id="8427a-227">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="8427a-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="8427a-228">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8427a-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="8427a-229">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="8427a-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="8427a-230">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="8427a-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8427a-231">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="8427a-232">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="8427a-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="8427a-233">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="8427a-233">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="8427a-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8427a-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8427a-235">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8427a-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="8427a-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="8427a-236">**Host Record**</span></span>|<span data-ttu-id="8427a-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8427a-237">**TTL**</span></span>|<span data-ttu-id="8427a-238">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8427a-238">**Type**</span></span>|<span data-ttu-id="8427a-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="8427a-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8427a-240">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-240">14400</span></span>  <br/> |<span data-ttu-id="8427a-241">TXT</span><span class="sxs-lookup"><span data-stu-id="8427a-241">TXT</span></span>  <br/> |<span data-ttu-id="8427a-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8427a-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="8427a-243">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="8427a-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar el valor TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="8427a-245">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="8427a-245">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8427a-247">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8427a-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8427a-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8427a-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="8427a-249">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="8427a-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="8427a-250">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="8427a-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8427a-251">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="8427a-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="8427a-252">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="8427a-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="8427a-253">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="8427a-253">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="8427a-254">Cree el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="8427a-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="8427a-255">En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8427a-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8427a-256">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8427a-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8427a-257">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="8427a-257">**Service**</span></span>|<span data-ttu-id="8427a-258">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="8427a-258">**Protocol**</span></span>|<span data-ttu-id="8427a-259">**Host**</span><span class="sxs-lookup"><span data-stu-id="8427a-259">**Host**</span></span>|<span data-ttu-id="8427a-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8427a-260">**TTL**</span></span>|<span data-ttu-id="8427a-261">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8427a-261">**Type**</span></span>|<span data-ttu-id="8427a-262">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="8427a-262">**Priority**</span></span>|<span data-ttu-id="8427a-263">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="8427a-263">**Weight**</span></span>|<span data-ttu-id="8427a-264">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="8427a-264">**Port**</span></span>|<span data-ttu-id="8427a-265">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="8427a-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8427a-266">_sip</span><span class="sxs-lookup"><span data-stu-id="8427a-266">_sip</span></span>  <br/> |<span data-ttu-id="8427a-267">_tls</span><span class="sxs-lookup"><span data-stu-id="8427a-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="8427a-268">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-268">14400</span></span>  <br/> |<span data-ttu-id="8427a-269">SRV</span><span class="sxs-lookup"><span data-stu-id="8427a-269">SRV</span></span>  <br/> |<span data-ttu-id="8427a-270">100</span><span class="sxs-lookup"><span data-stu-id="8427a-270">100</span></span>  <br/> |<span data-ttu-id="8427a-271">1 </span><span class="sxs-lookup"><span data-stu-id="8427a-271">1</span></span>  <br/> |<span data-ttu-id="8427a-272">443</span><span class="sxs-lookup"><span data-stu-id="8427a-272">443</span></span>  <br/> |<span data-ttu-id="8427a-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8427a-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8427a-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8427a-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="8427a-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="8427a-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="8427a-276">14400</span><span class="sxs-lookup"><span data-stu-id="8427a-276">14400</span></span>  <br/> |<span data-ttu-id="8427a-277">SRV</span><span class="sxs-lookup"><span data-stu-id="8427a-277">SRV</span></span>  <br/> |<span data-ttu-id="8427a-278">100</span><span class="sxs-lookup"><span data-stu-id="8427a-278">100</span></span>  <br/> |<span data-ttu-id="8427a-279">1 </span><span class="sxs-lookup"><span data-stu-id="8427a-279">1</span></span>  <br/> |<span data-ttu-id="8427a-280">5061</span><span class="sxs-lookup"><span data-stu-id="8427a-280">5061</span></span>  <br/> |<span data-ttu-id="8427a-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8427a-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiar el valor del nuevo registro](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="8427a-283">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="8427a-283">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="8427a-285">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="8427a-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="8427a-286">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la otra fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="8427a-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8427a-287">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="8427a-287">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8427a-288">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="8427a-288">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8427a-289">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8427a-289">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

