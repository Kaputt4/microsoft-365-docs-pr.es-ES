---
title: Cambiar los servidores de nombres para configurar Office 365 con MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Obtenga información acerca de cómo puede configurar Office 365 para administrar los registros DNS de su dominio personalizado en midominio.
ms.openlocfilehash: 90f1469bdf2f281be14e2a9e15a9fe7ac4a8cbee
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351621"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="794f6-103">Cambiar los servidores de nombres para configurar Office 365 con MyDomain</span><span class="sxs-lookup"><span data-stu-id="794f6-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="794f6-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="794f6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="794f6-p101">Siga estas instrucciones si quiere que Office 365 administre los registros DNS de Office 365 automáticamente. (Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en MyDomain](create-dns-records-at-mydomain.md)).</span><span class="sxs-lookup"><span data-stu-id="794f6-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="794f6-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="794f6-107">Add a TXT record for verification</span></span>

<span data-ttu-id="794f6-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="794f6-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="794f6-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="794f6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="794f6-p104">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="794f6-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="794f6-114">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="794f6-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="794f6-115">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="794f6-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="794f6-116">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="794f6-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="794f6-117">En la lista desplegable **Modificar**, elija **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="794f6-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="794f6-118">En **Contenido**, en el cuadro del nuevo registro, escriba o copie y pegue el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="794f6-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="794f6-119">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="794f6-119">**Content**</span></span> <br/> |
|<span data-ttu-id="794f6-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="794f6-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="794f6-121">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="794f6-121">**Note**: This is an example.</span></span> <span data-ttu-id="794f6-122">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="794f6-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="794f6-123">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="794f6-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="794f6-124">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="794f6-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="794f6-125">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="794f6-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="794f6-126">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="794f6-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="794f6-127">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="794f6-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="794f6-128">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="794f6-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="794f6-129">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="794f6-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="794f6-130">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="794f6-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="794f6-131">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="794f6-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="794f6-132">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="794f6-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="794f6-133">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="794f6-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="794f6-134">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="794f6-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="794f6-135">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="794f6-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="794f6-p107">Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="794f6-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="794f6-139">Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio.</span><span class="sxs-lookup"><span data-stu-id="794f6-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="794f6-140">Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="794f6-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="794f6-141">com) empezará a llegar a Office 365 después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="794f6-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="794f6-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="794f6-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="794f6-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="794f6-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="794f6-p110">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="794f6-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="794f6-146">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="794f6-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="794f6-147">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="794f6-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="794f6-148">En la fila **información general** , seleccione **servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="794f6-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Midominio-BP-redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="794f6-150">En la sección **Update Name Servers**, seleccione **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="794f6-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Midominio-BP-redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="794f6-152">Dependiendo de si ya hay o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="794f6-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="794f6-153">Si los servidores de nombres correctos ya aparecen</span><span class="sxs-lookup"><span data-stu-id="794f6-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="794f6-154">Si los servidores de nombres correctos ya aparecen, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="794f6-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Midominio-BP-redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="794f6-156">Si los servidores de nombres correctos todavía no aparecen</span><span class="sxs-lookup"><span data-stu-id="794f6-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="794f6-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="794f6-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="794f6-158">(Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="794f6-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="794f6-159">Elimine el servidor de nombres existente seleccionando cada entrada en el campo **Servidor de nombres:** y, después, presionando la tecla **Eliminar** de su teclado.</span><span class="sxs-lookup"><span data-stu-id="794f6-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Midominio-BP-redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="794f6-161">Seleccione **Agregar más** dos veces para agregar dos nuevas filas de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="794f6-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Midominio-BP-redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="794f6-163">En los cuadros para los registros, escriba o copie y pegue los valores del servidor de nombres de la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="794f6-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="794f6-164">**Servidor de nombres 1**</span><span class="sxs-lookup"><span data-stu-id="794f6-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="794f6-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="794f6-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="794f6-166">**Servidor de nombres 2**</span><span class="sxs-lookup"><span data-stu-id="794f6-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="794f6-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="794f6-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="794f6-168">**Servidor DNS 3**</span><span class="sxs-lookup"><span data-stu-id="794f6-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="794f6-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="794f6-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="794f6-170">**Servidor DNS 4**</span><span class="sxs-lookup"><span data-stu-id="794f6-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="794f6-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="794f6-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Midominio-BP-redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="794f6-173">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="794f6-173">Select **Save**.</span></span>
    
    ![Midominio-BP-redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="794f6-p112">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="794f6-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
