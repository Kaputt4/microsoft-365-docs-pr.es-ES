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
ms.openlocfilehash: 9a5cad6778cb66958539a324befee43ddb2dd8b9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247217"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="3bfa2-103">Crear registros DNS en Bluehost para Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfa2-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="3bfa2-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3bfa2-105">Si Bluehost es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3bfa2-106">Después de agregar estos registros a Bluehost, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="3bfa2-107">Para obtener información sobre hospedaje web y DNS para sitios web con Office 365, vea [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bfa2-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3bfa2-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3bfa2-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3bfa2-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="3bfa2-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3bfa2-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3bfa2-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3bfa2-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bfa2-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3bfa2-117">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3bfa2-118">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3bfa2-119">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3bfa2-120">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3bfa2-121">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3bfa2-122">En la página \* \* editor de la zona DNS \* \*, en el área **Agregar registro DNS** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3bfa2-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3bfa2-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3bfa2-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-124">**Host Record**</span></span> <br/> |<span data-ttu-id="3bfa2-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-125">**TTL**</span></span> <br/> |<span data-ttu-id="3bfa2-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-126">**Type**</span></span> <br/> |<span data-ttu-id="3bfa2-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3bfa2-128">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-128">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-129">TXT</span><span class="sxs-lookup"><span data-stu-id="3bfa2-129">TXT</span></span>  <br/> |<span data-ttu-id="3bfa2-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3bfa2-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3bfa2-131">**Nota:** Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-131">**Note:** This is an example.</span></span> <span data-ttu-id="3bfa2-132">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="3bfa2-133">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="3bfa2-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="3bfa2-134">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="3bfa2-135">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3bfa2-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3bfa2-137">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3bfa2-138">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="3bfa2-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3bfa2-139">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3bfa2-140">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3bfa2-141">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3bfa2-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3bfa2-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3bfa2-144">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="3bfa2-145">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfa2-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="3bfa2-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3bfa2-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3bfa2-147">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3bfa2-148">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3bfa2-149">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3bfa2-150">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3bfa2-151">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3bfa2-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3bfa2-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3bfa2-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3bfa2-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-154">**Host Record**</span></span>|<span data-ttu-id="3bfa2-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-155">**TTL**</span></span>|<span data-ttu-id="3bfa2-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-156">**Type**</span></span>|<span data-ttu-id="3bfa2-157">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-157">**Points To**</span></span>|<span data-ttu-id="3bfa2-158">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3bfa2-159">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-159">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-160">MX</span><span class="sxs-lookup"><span data-stu-id="3bfa2-160">MX</span></span>  <br/> | <span data-ttu-id="3bfa2-161">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="3bfa2-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="3bfa2-162">**Nota:** Obtenga la \< *clave* \> de dominio de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="3bfa2-163">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="3bfa2-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3bfa2-164">comprendi</span><span class="sxs-lookup"><span data-stu-id="3bfa2-164">0</span></span>  <br/> <span data-ttu-id="3bfa2-165">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="3bfa2-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Elija tipo en la lista desplegable](../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="3bfa2-167">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-167">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="3bfa2-169">Si hay otros registros MX en la sección **MX (agente de intercambio de correo)**, elimínelos.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="3bfa2-170">Para uno de los demás registros MX, seleccione **eliminar.**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Seleccione Eliminar para cada registro MX adicional](../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="3bfa2-172">En el cuadro de diálogo de confirmación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Seleccione Aceptar.](../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="3bfa2-174">Siga el mismo procedimiento para eliminar el resto de los registros MX que se muestren.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="3bfa2-175">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfa2-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="3bfa2-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3bfa2-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3bfa2-177">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3bfa2-178">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3bfa2-179">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3bfa2-180">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3bfa2-181">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3bfa2-182">En la sección registros de **A (host)** , busque la fila del registro de **detección automática** y, a continuación, seleccione **eliminar** para esa fila.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3bfa2-p110">Tiene que eliminar el registro **autodiscover** existente  *antes*  de agregar el registro **autodiscover** necesario para Office 365. Bluehost no le permite mantener de forma simultánea dos registros **autodiscover**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Seleccione eliminar.](../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="3bfa2-186">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-186">Select **OK**.</span></span>
    
    ![Seleccione Aceptar.](../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="3bfa2-188">Cree el primero de los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3bfa2-189">En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3bfa2-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3bfa2-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3bfa2-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-191">**Host Record**</span></span>|<span data-ttu-id="3bfa2-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-192">**TTL**</span></span>|<span data-ttu-id="3bfa2-193">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-193">**Type**</span></span>|<span data-ttu-id="3bfa2-194">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3bfa2-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3bfa2-195">autodiscover</span></span>  <br/> |<span data-ttu-id="3bfa2-196">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-196">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="3bfa2-197">CNAME</span></span>  <br/> |<span data-ttu-id="3bfa2-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3bfa2-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3bfa2-199">sip</span><span class="sxs-lookup"><span data-stu-id="3bfa2-199">sip</span></span>  <br/> |<span data-ttu-id="3bfa2-200">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-200">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="3bfa2-201">CNAME</span></span>  <br/> |<span data-ttu-id="3bfa2-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bfa2-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3bfa2-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3bfa2-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3bfa2-204">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-204">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="3bfa2-205">CNAME</span></span>  <br/> |<span data-ttu-id="3bfa2-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bfa2-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3bfa2-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3bfa2-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3bfa2-208">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-208">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="3bfa2-209">CNAME</span></span>  <br/> |<span data-ttu-id="3bfa2-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3bfa2-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3bfa2-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3bfa2-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3bfa2-212">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-212">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="3bfa2-213">CNAME</span></span>  <br/> |<span data-ttu-id="3bfa2-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3bfa2-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Crear el primer registro CNAME](../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="3bfa2-216">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-216">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="3bfa2-218">Agregue los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="3bfa2-219">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="3bfa2-220">Repita este proceso hasta crear los seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3bfa2-221">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="3bfa2-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3bfa2-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3bfa2-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bfa2-223">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3bfa2-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3bfa2-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="3bfa2-226">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="3bfa2-227">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="3bfa2-227">Need examples?</span></span> <span data-ttu-id="3bfa2-228">Consulte estos [registros del sistema de nombres de dominio externo para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="3bfa2-229">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="3bfa2-230">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3bfa2-231">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3bfa2-232">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3bfa2-233">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3bfa2-234">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3bfa2-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3bfa2-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3bfa2-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="3bfa2-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-237">**Host Record**</span></span>|<span data-ttu-id="3bfa2-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-238">**TTL**</span></span>|<span data-ttu-id="3bfa2-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-239">**Type**</span></span>|<span data-ttu-id="3bfa2-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3bfa2-241">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-241">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-242">TXT</span><span class="sxs-lookup"><span data-stu-id="3bfa2-242">TXT</span></span>  <br/> |<span data-ttu-id="3bfa2-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3bfa2-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="3bfa2-244">**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar el valor TXT](../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="3bfa2-246">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-246">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="3bfa2-248">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfa2-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="3bfa2-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3bfa2-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3bfa2-250">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3bfa2-251">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3bfa2-252">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3bfa2-253">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3bfa2-254">En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3bfa2-255">Cree el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3bfa2-256">En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3bfa2-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3bfa2-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3bfa2-258">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-258">**Service**</span></span>|<span data-ttu-id="3bfa2-259">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-259">**Protocol**</span></span>|<span data-ttu-id="3bfa2-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-260">**Host**</span></span>|<span data-ttu-id="3bfa2-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-261">**TTL**</span></span>|<span data-ttu-id="3bfa2-262">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-262">**Type**</span></span>|<span data-ttu-id="3bfa2-263">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-263">**Priority**</span></span>|<span data-ttu-id="3bfa2-264">**Peso**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-264">**Weight**</span></span>|<span data-ttu-id="3bfa2-265">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-265">**Port**</span></span>|<span data-ttu-id="3bfa2-266">**Apunta a**</span><span class="sxs-lookup"><span data-stu-id="3bfa2-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3bfa2-267">_sip</span><span class="sxs-lookup"><span data-stu-id="3bfa2-267">_sip</span></span>  <br/> |<span data-ttu-id="3bfa2-268">_tls</span><span class="sxs-lookup"><span data-stu-id="3bfa2-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="3bfa2-269">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-269">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-270">SRV</span><span class="sxs-lookup"><span data-stu-id="3bfa2-270">SRV</span></span>  <br/> |<span data-ttu-id="3bfa2-271">100</span><span class="sxs-lookup"><span data-stu-id="3bfa2-271">100</span></span>  <br/> |<span data-ttu-id="3bfa2-272">1</span><span class="sxs-lookup"><span data-stu-id="3bfa2-272">1</span></span>  <br/> |<span data-ttu-id="3bfa2-273">443</span><span class="sxs-lookup"><span data-stu-id="3bfa2-273">443</span></span>  <br/> |<span data-ttu-id="3bfa2-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bfa2-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3bfa2-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3bfa2-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3bfa2-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="3bfa2-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="3bfa2-277">14400</span><span class="sxs-lookup"><span data-stu-id="3bfa2-277">14400</span></span>  <br/> |<span data-ttu-id="3bfa2-278">SRV</span><span class="sxs-lookup"><span data-stu-id="3bfa2-278">SRV</span></span>  <br/> |<span data-ttu-id="3bfa2-279">100</span><span class="sxs-lookup"><span data-stu-id="3bfa2-279">100</span></span>  <br/> |<span data-ttu-id="3bfa2-280">1</span><span class="sxs-lookup"><span data-stu-id="3bfa2-280">1</span></span>  <br/> |<span data-ttu-id="3bfa2-281">5061</span><span class="sxs-lookup"><span data-stu-id="3bfa2-281">5061</span></span>  <br/> |<span data-ttu-id="3bfa2-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bfa2-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiar el valor del nuevo registro](../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="3bfa2-284">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-284">Select **add record**.</span></span>
    
    ![Seleccione Agregar registro](../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="3bfa2-286">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3bfa2-287">En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la otra fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3bfa2-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3bfa2-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3bfa2-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3bfa2-290">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3bfa2-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

