---
title: Cambiar los servidores DNS para configurar Microsoft con midominio
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Obtenga información acerca de cómo configurar Microsoft para que administre los registros DNS de su dominio personalizado en midominio.
ms.openlocfilehash: 8f4a72aa0ece24ed09c4d036239a2a13c196be6c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629796"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="6426b-103">Cambiar los servidores DNS para configurar Microsoft con midominio</span><span class="sxs-lookup"><span data-stu-id="6426b-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="6426b-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="6426b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="6426b-105">Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="6426b-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="6426b-106">(Si lo prefiere, puede [administrar todos los registros DNS de Microsoft en midominio](create-dns-records-at-mydomain.md)).</span><span class="sxs-lookup"><span data-stu-id="6426b-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6426b-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="6426b-107">Add a TXT record for verification</span></span>

<span data-ttu-id="6426b-108">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="6426b-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6426b-109">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="6426b-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6426b-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="6426b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6426b-p104">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6426b-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6426b-114">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="6426b-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6426b-115">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="6426b-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6426b-116">En la fila **Información general**, elija **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6426b-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6426b-117">En la lista desplegable **Modificar**, elija **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="6426b-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="6426b-118">En **Contenido**, en el cuadro del nuevo registro, escriba o copie y pegue el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6426b-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="6426b-119">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="6426b-119">**Content**</span></span> <br/> |
|<span data-ttu-id="6426b-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6426b-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6426b-121">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6426b-121">**Note**: This is an example.</span></span> <span data-ttu-id="6426b-122">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6426b-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="6426b-123">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="6426b-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6426b-124">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6426b-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="6426b-125">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="6426b-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6426b-126">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft 365 y pedirá a Microsoft 365 que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="6426b-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="6426b-127">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="6426b-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6426b-128">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="6426b-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6426b-129">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="6426b-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6426b-130">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="6426b-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6426b-131">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="6426b-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6426b-132">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="6426b-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6426b-133">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6426b-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6426b-134">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6426b-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6426b-135">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="6426b-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="6426b-136">Para completar la configuración de su dominio con Microsoft, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6426b-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="6426b-137">Esto configura a Microsoft para que actualice los registros DNS del dominio por usted.</span><span class="sxs-lookup"><span data-stu-id="6426b-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="6426b-138">Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="6426b-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6426b-139">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="6426b-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6426b-140">Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="6426b-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="6426b-141">com) empezará a llegar a Microsoft después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="6426b-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6426b-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="6426b-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="6426b-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="6426b-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="6426b-p110">Para empezar, vaya a su página de dominios en MyDomain a través de [este vínculo](https://www.mydomain.com/controlpanel). Se le pedirá que primero que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6426b-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6426b-146">En la sección **Mis favoritos**, elija **Dominio Central**.</span><span class="sxs-lookup"><span data-stu-id="6426b-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6426b-147">En **Dominio**, elige el nombre del dominio que deseas editar.</span><span class="sxs-lookup"><span data-stu-id="6426b-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6426b-148">En la fila **información general** , seleccione **servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="6426b-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Midominio-BP-redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="6426b-150">En la sección **Update Name Servers**, seleccione **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="6426b-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Midominio-BP-redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="6426b-152">Dependiendo de si ya hay o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6426b-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="6426b-153">Si los servidores de nombres correctos ya aparecen</span><span class="sxs-lookup"><span data-stu-id="6426b-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="6426b-154">Si los servidores de nombres correctos ya aparecen, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="6426b-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Midominio-BP-redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="6426b-156">Si los servidores de nombres correctos todavía no aparecen</span><span class="sxs-lookup"><span data-stu-id="6426b-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="6426b-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="6426b-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="6426b-158">(Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="6426b-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="6426b-159">Elimine el servidor de nombres existente seleccionando cada entrada en el campo **Servidor de nombres:** y, después, presionando la tecla **Eliminar** de su teclado.</span><span class="sxs-lookup"><span data-stu-id="6426b-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Midominio-BP-redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="6426b-161">Seleccione **Agregar más** dos veces para agregar dos nuevas filas de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="6426b-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Midominio-BP-redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="6426b-163">En los cuadros para los registros, escriba o copie y pegue los valores del servidor de nombres de la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6426b-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6426b-164">**Servidor de nombres 1**</span><span class="sxs-lookup"><span data-stu-id="6426b-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="6426b-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6426b-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6426b-166">**Servidor de nombres 2**</span><span class="sxs-lookup"><span data-stu-id="6426b-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="6426b-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6426b-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6426b-168">**Servidor DNS 3**</span><span class="sxs-lookup"><span data-stu-id="6426b-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="6426b-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6426b-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6426b-170">**Servidor DNS 4**</span><span class="sxs-lookup"><span data-stu-id="6426b-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="6426b-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6426b-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Midominio-BP-redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="6426b-173">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6426b-173">Select **Save**.</span></span>
    
    ![Midominio-BP-redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="6426b-175">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="6426b-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6426b-176">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="6426b-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
