---
title: Crear registros DNS en Bluehost para Office 365
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Bluehost para Office 365.
ms.openlocfilehash: 0e64ed8787dca9822e71a63c57de7a7a3e2b3fe4
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350961"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="b866b-103">Crear registros DNS en Bluehost para Office 365</span><span class="sxs-lookup"><span data-stu-id="b866b-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="b866b-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="b866b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b866b-105">Si Bluehost es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="b866b-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b866b-106">Después de agregar estos registros a Bluehost, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b866b-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b866b-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="b866b-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b866b-108">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="b866b-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b866b-109">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="b866b-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b866b-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b866b-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b866b-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="b866b-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b866b-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b866b-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b866b-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b866b-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="b866b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b866b-117">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b866b-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b866b-118">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="b866b-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b866b-119">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b866b-120">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="b866b-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b866b-121">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="b866b-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b866b-122">En la página \* \* editor de la zona DNS \* \*, en el área **Agregar registro DNS** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b866b-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b866b-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b866b-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b866b-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b866b-124">**Host Record**</span></span> <br/> |<span data-ttu-id="b866b-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b866b-125">**TTL**</span></span> <br/> |<span data-ttu-id="b866b-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b866b-126">**Type**</span></span> <br/> |<span data-ttu-id="b866b-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b866b-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b866b-128">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-128">14400</span></span>  <br/> |<span data-ttu-id="b866b-129">TXT</span><span class="sxs-lookup"><span data-stu-id="b866b-129">TXT</span></span>  <br/> |<span data-ttu-id="b866b-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b866b-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b866b-131">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b866b-131">**Note:** This is an example.</span></span> <span data-ttu-id="b866b-132">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b866b-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="b866b-133">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="b866b-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="b866b-134">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="b866b-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="b866b-135">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="b866b-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b866b-136">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="b866b-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b866b-137">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b866b-138">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="b866b-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b866b-139">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="b866b-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b866b-140">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="b866b-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b866b-141">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="b866b-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b866b-142">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="b866b-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b866b-143">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="b866b-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b866b-144">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b866b-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b866b-145">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="b866b-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b866b-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b866b-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b866b-147">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b866b-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b866b-148">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="b866b-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b866b-149">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b866b-150">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="b866b-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b866b-151">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="b866b-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b866b-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b866b-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b866b-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b866b-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b866b-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b866b-154">**Host Record**</span></span>|<span data-ttu-id="b866b-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b866b-155">**TTL**</span></span>|<span data-ttu-id="b866b-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b866b-156">**Type**</span></span>|<span data-ttu-id="b866b-157">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="b866b-157">**Points To**</span></span>|<span data-ttu-id="b866b-158">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="b866b-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b866b-159">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-159">14400</span></span>  <br/> |<span data-ttu-id="b866b-160">MX</span><span class="sxs-lookup"><span data-stu-id="b866b-160">MX</span></span>  <br/> | <span data-ttu-id="b866b-161">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="b866b-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="b866b-162">**Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b866b-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="b866b-163">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="b866b-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b866b-164">comprendi</span><span class="sxs-lookup"><span data-stu-id="b866b-164">0</span></span>  <br/> <span data-ttu-id="b866b-165">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="b866b-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Elija tipo en la lista desplegable](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="b866b-167">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="b866b-167">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="b866b-169">Si hay otros registros MX en la sección **MX (agente de intercambio de correo)**, elimínelos.</span><span class="sxs-lookup"><span data-stu-id="b866b-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="b866b-170">Para uno de los demás registros MX, seleccione **eliminar.**</span><span class="sxs-lookup"><span data-stu-id="b866b-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Seleccione Eliminar para cada registro MX adicional](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="b866b-172">En el cuadro de diálogo de confirmación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b866b-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Seleccione Aceptar.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="b866b-174">Siga el mismo procedimiento para eliminar el resto de los registros MX que se muestren.</span><span class="sxs-lookup"><span data-stu-id="b866b-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b866b-175">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="b866b-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b866b-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b866b-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b866b-177">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b866b-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b866b-178">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="b866b-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b866b-179">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b866b-180">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="b866b-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b866b-181">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="b866b-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b866b-182">En la sección registros de **A (host)** , busque la fila del registro de **detección automática** y, a continuación, seleccione **eliminar** para esa fila.</span><span class="sxs-lookup"><span data-stu-id="b866b-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b866b-p110">Tiene que eliminar el registro **autodiscover** existente  *antes*  de agregar el registro **autodiscover** necesario para Office 365. Bluehost no le permite mantener de forma simultánea dos registros **autodiscover**.</span><span class="sxs-lookup"><span data-stu-id="b866b-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Seleccione eliminar.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="b866b-186">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b866b-186">Select **OK**.</span></span>
    
    ![Seleccione Aceptar.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="b866b-188">Cree el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="b866b-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b866b-189">En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b866b-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="b866b-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b866b-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b866b-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b866b-191">**Host Record**</span></span>|<span data-ttu-id="b866b-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b866b-192">**TTL**</span></span>|<span data-ttu-id="b866b-193">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b866b-193">**Type**</span></span>|<span data-ttu-id="b866b-194">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="b866b-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b866b-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b866b-195">autodiscover</span></span>  <br/> |<span data-ttu-id="b866b-196">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-196">14400</span></span>  <br/> |<span data-ttu-id="b866b-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="b866b-197">CNAME</span></span>  <br/> |<span data-ttu-id="b866b-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b866b-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b866b-199">sip</span><span class="sxs-lookup"><span data-stu-id="b866b-199">sip</span></span>  <br/> |<span data-ttu-id="b866b-200">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-200">14400</span></span>  <br/> |<span data-ttu-id="b866b-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="b866b-201">CNAME</span></span>  <br/> |<span data-ttu-id="b866b-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b866b-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b866b-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b866b-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b866b-204">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-204">14400</span></span>  <br/> |<span data-ttu-id="b866b-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="b866b-205">CNAME</span></span>  <br/> |<span data-ttu-id="b866b-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b866b-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b866b-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b866b-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b866b-208">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-208">14400</span></span>  <br/> |<span data-ttu-id="b866b-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="b866b-209">CNAME</span></span>  <br/> |<span data-ttu-id="b866b-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b866b-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b866b-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b866b-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b866b-212">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-212">14400</span></span>  <br/> |<span data-ttu-id="b866b-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="b866b-213">CNAME</span></span>  <br/> |<span data-ttu-id="b866b-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b866b-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Crear el primer registro CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="b866b-216">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="b866b-216">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="b866b-218">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="b866b-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="b866b-219">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="b866b-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="b866b-220">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="b866b-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b866b-221">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b866b-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b866b-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b866b-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b866b-223">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b866b-224">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b866b-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b866b-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="b866b-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b866b-226">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="b866b-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b866b-227">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="b866b-227">Need examples?</span></span> <span data-ttu-id="b866b-228">Consulte los [Registros externos del sistema de nombres de dominio para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="b866b-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="b866b-229">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b866b-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="b866b-230">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b866b-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b866b-231">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="b866b-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b866b-232">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b866b-233">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="b866b-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b866b-234">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="b866b-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b866b-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b866b-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b866b-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b866b-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="b866b-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b866b-237">**Host Record**</span></span>|<span data-ttu-id="b866b-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b866b-238">**TTL**</span></span>|<span data-ttu-id="b866b-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b866b-239">**Type**</span></span>|<span data-ttu-id="b866b-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b866b-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b866b-241">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-241">14400</span></span>  <br/> |<span data-ttu-id="b866b-242">TXT</span><span class="sxs-lookup"><span data-stu-id="b866b-242">TXT</span></span>  <br/> |<span data-ttu-id="b866b-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b866b-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b866b-244">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="b866b-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar el valor TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="b866b-246">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="b866b-246">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b866b-248">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="b866b-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b866b-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b866b-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b866b-250">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b866b-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b866b-251">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="b866b-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b866b-252">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="b866b-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b866b-253">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="b866b-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b866b-254">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="b866b-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b866b-255">Cree el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="b866b-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="b866b-256">En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b866b-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="b866b-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b866b-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b866b-258">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="b866b-258">**Service**</span></span>|<span data-ttu-id="b866b-259">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="b866b-259">**Protocol**</span></span>|<span data-ttu-id="b866b-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="b866b-260">**Host**</span></span>|<span data-ttu-id="b866b-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b866b-261">**TTL**</span></span>|<span data-ttu-id="b866b-262">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b866b-262">**Type**</span></span>|<span data-ttu-id="b866b-263">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="b866b-263">**Priority**</span></span>|<span data-ttu-id="b866b-264">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="b866b-264">**Weight**</span></span>|<span data-ttu-id="b866b-265">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="b866b-265">**Port**</span></span>|<span data-ttu-id="b866b-266">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="b866b-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b866b-267">_sip</span><span class="sxs-lookup"><span data-stu-id="b866b-267">_sip</span></span>  <br/> |<span data-ttu-id="b866b-268">_tls</span><span class="sxs-lookup"><span data-stu-id="b866b-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="b866b-269">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-269">14400</span></span>  <br/> |<span data-ttu-id="b866b-270">SRV</span><span class="sxs-lookup"><span data-stu-id="b866b-270">SRV</span></span>  <br/> |<span data-ttu-id="b866b-271">100</span><span class="sxs-lookup"><span data-stu-id="b866b-271">100</span></span>  <br/> |<span data-ttu-id="b866b-272">1</span><span class="sxs-lookup"><span data-stu-id="b866b-272">1</span></span>  <br/> |<span data-ttu-id="b866b-273">443</span><span class="sxs-lookup"><span data-stu-id="b866b-273">443</span></span>  <br/> |<span data-ttu-id="b866b-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b866b-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b866b-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b866b-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b866b-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="b866b-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="b866b-277">14400</span><span class="sxs-lookup"><span data-stu-id="b866b-277">14400</span></span>  <br/> |<span data-ttu-id="b866b-278">SRV</span><span class="sxs-lookup"><span data-stu-id="b866b-278">SRV</span></span>  <br/> |<span data-ttu-id="b866b-279">100</span><span class="sxs-lookup"><span data-stu-id="b866b-279">100</span></span>  <br/> |<span data-ttu-id="b866b-280">1</span><span class="sxs-lookup"><span data-stu-id="b866b-280">1</span></span>  <br/> |<span data-ttu-id="b866b-281">5061</span><span class="sxs-lookup"><span data-stu-id="b866b-281">5061</span></span>  <br/> |<span data-ttu-id="b866b-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b866b-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiar el valor del nuevo registro](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="b866b-284">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="b866b-284">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="b866b-286">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="b866b-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="b866b-287">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la otra fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="b866b-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b866b-288">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="b866b-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b866b-289">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="b866b-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b866b-290">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b866b-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

