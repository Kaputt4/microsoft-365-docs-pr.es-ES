---
title: Crear registros DNS en Network Solutions for Microsoft
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Aprenda a comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Network Solutions for Microsoft.
ms.openlocfilehash: fb5fd2d2bcb263a62306617d728f08b07bb6da34
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048932"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="8ea87-103">Crear registros DNS en Network Solutions for Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="8ea87-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="8ea87-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8ea87-105">Si Network Solutions es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="8ea87-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8ea87-106">Estos son los registros principales que agregar.</span><span class="sxs-lookup"><span data-stu-id="8ea87-106">These are the main records to add.</span></span> <span data-ttu-id="8ea87-107">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8ea87-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="8ea87-108">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="8ea87-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="8ea87-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="8ea87-110">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="8ea87-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="8ea87-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="8ea87-112">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="8ea87-113">Después de agregar estos registros a Network Solutions, el dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ea87-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="8ea87-p102">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ea87-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8ea87-117">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="8ea87-117">Add a TXT record for verification</span></span>
<span data-ttu-id="8ea87-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8ea87-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8ea87-p103">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="8ea87-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ea87-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="8ea87-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8ea87-123">Siga los pasos siguientes o [vea el vídeo (empieza en 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8ea87-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ea87-124">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8ea87-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8ea87-125">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ea87-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ea87-126">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="8ea87-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ea87-128">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8ea87-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ea87-130">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-130">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ea87-132">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ea87-133">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-133">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ea87-135">Desplácese hacia abajo hasta la sección **texto (registros txt)** y, a continuación, seleccione **Editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Seleccionar Editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="8ea87-137">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ea87-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="8ea87-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="8ea87-138">**Host**</span></span>|<span data-ttu-id="8ea87-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8ea87-139">**TTL**</span></span>|<span data-ttu-id="8ea87-140">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8ea87-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="8ea87-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8ea87-142">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-142">3600</span></span>  <br/> |<span data-ttu-id="8ea87-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8ea87-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8ea87-144">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8ea87-144">**Note:** This is an example.</span></span> <span data-ttu-id="8ea87-145">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="8ea87-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="8ea87-146">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="8ea87-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Escribir o pegar valores en los cuadros para el nuevo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="8ea87-148">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-148">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="8ea87-150">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-150">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="8ea87-152">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="8ea87-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8ea87-153">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="8ea87-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8ea87-154">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="8ea87-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="8ea87-155">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="8ea87-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8ea87-156">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="8ea87-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8ea87-157">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="8ea87-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8ea87-158">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8ea87-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ea87-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8ea87-162">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8ea87-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8ea87-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8ea87-164">Siga los pasos siguientes o [vea el vídeo (empieza en 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8ea87-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ea87-165">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8ea87-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8ea87-166">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ea87-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ea87-167">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="8ea87-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ea87-169">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8ea87-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ea87-171">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-171">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ea87-173">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ea87-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-174">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ea87-176">Desplácese hacia abajo hasta la sección **servidores de correo (registros MX)** y, a continuación, seleccione **Editar registros MX**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Seleccionar Editar registros MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="8ea87-178">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ea87-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8ea87-179">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="8ea87-179">**Priority**</span></span>|<span data-ttu-id="8ea87-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8ea87-180">**TTL**</span></span>|<span data-ttu-id="8ea87-181">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="8ea87-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8ea87-182">10  </span><span class="sxs-lookup"><span data-stu-id="8ea87-182">10</span></span>  <br/> <span data-ttu-id="8ea87-183">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="8ea87-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="8ea87-184">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-184">3600</span></span>  <br/> | <span data-ttu-id="8ea87-185">*\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8ea87-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8ea87-186">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8ea87-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8ea87-187">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ea87-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="8ea87-188">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="8ea87-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Escribir o pegar valores en los cuadros para el nuevo registro](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="8ea87-190">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-190">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="8ea87-192">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-192">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="8ea87-194">Si hay otros registros MX, elimínelos todos (para hacerlo, seleccione **Eliminar** junto a cada registro).</span><span class="sxs-lookup"><span data-stu-id="8ea87-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="8ea87-196">Cuando estén todos seleccionados, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-196">When they are all selected, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="8ea87-198">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-198">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8ea87-200">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8ea87-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8ea87-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8ea87-202">Siga los pasos siguientes o [vea el vídeo (empieza en 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8ea87-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ea87-203">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8ea87-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8ea87-204">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ea87-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ea87-205">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="8ea87-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ea87-207">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8ea87-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ea87-209">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-209">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ea87-211">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ea87-212">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-212">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ea87-214">Desplácese hacia abajo hasta la sección **alias de host (registros CNAME)** y, a continuación, seleccione **Editar registros CNAME**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Seleccione Editar registros CNAME en alias de host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="8ea87-216">En los cuadros de los cuatro nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ea87-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8ea87-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8ea87-217">**Alias**</span></span>|<span data-ttu-id="8ea87-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8ea87-218">**TTL**</span></span>|<span data-ttu-id="8ea87-219">**Referencia a nombre de host**</span><span class="sxs-lookup"><span data-stu-id="8ea87-219">**Refers to Host Name**</span></span>|<span data-ttu-id="8ea87-220">**Otro host          (seleccione el botón de opción **Otro host**)**</span><span class="sxs-lookup"><span data-stu-id="8ea87-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8ea87-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8ea87-221">autodiscover</span></span>  <br/> |<span data-ttu-id="8ea87-222">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-222">3600</span></span>  <br/> |<span data-ttu-id="8ea87-223">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="8ea87-223">(No setting)</span></span>  <br/> |<span data-ttu-id="8ea87-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8ea87-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8ea87-225">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8ea87-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ea87-226">sip</span><span class="sxs-lookup"><span data-stu-id="8ea87-226">sip</span></span>  <br/> |<span data-ttu-id="8ea87-227">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-227">3600</span></span>  <br/> |<span data-ttu-id="8ea87-228">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="8ea87-228">(No setting)</span></span>  <br/> |<span data-ttu-id="8ea87-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ea87-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ea87-230">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="8ea87-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ea87-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8ea87-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8ea87-232">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-232">3600</span></span>  <br/> |<span data-ttu-id="8ea87-233">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="8ea87-233">(No setting)</span></span>  <br/> |<span data-ttu-id="8ea87-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ea87-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ea87-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8ea87-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ea87-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8ea87-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8ea87-237">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-237">3600</span></span>  <br/> |<span data-ttu-id="8ea87-238">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="8ea87-238">(No setting)</span></span>  <br/> |<span data-ttu-id="8ea87-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8ea87-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="8ea87-240">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="8ea87-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ea87-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8ea87-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8ea87-242">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-242">3600</span></span>  <br/> |<span data-ttu-id="8ea87-243">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="8ea87-243">(No setting)</span></span>  <br/> |<span data-ttu-id="8ea87-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8ea87-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="8ea87-245">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8ea87-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Escriba o pegue los valores de los nuevos registros](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="8ea87-247">Una vez que haya agregado todos los registros CNAME que necesita, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="8ea87-249">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-249">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8ea87-251">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="8ea87-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8ea87-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8ea87-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ea87-253">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="8ea87-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8ea87-254">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="8ea87-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8ea87-255">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ea87-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8ea87-256">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8ea87-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="8ea87-257">Siga los pasos siguientes o [vea el vídeo (empieza en 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8ea87-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ea87-258">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8ea87-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8ea87-259">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ea87-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ea87-260">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="8ea87-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ea87-262">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8ea87-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ea87-264">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-264">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ea87-266">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ea87-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-267">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ea87-269">Desplácese hacia abajo hasta la sección **texto (registros txt)** y, a continuación, seleccione **Editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Seleccione Editar registros TXT en texto](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="8ea87-271">En el cuadro para el nuevo registro, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="8ea87-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="8ea87-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="8ea87-272">**Host**</span></span>|<span data-ttu-id="8ea87-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8ea87-273">**TTL**</span></span>|<span data-ttu-id="8ea87-274">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8ea87-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="8ea87-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8ea87-276">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-276">3600</span></span>  <br/> |<span data-ttu-id="8ea87-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8ea87-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8ea87-278">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="8ea87-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Escribir o pegar valores para el nuevo registro](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="8ea87-280">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-280">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="8ea87-282">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-282">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8ea87-284">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ea87-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8ea87-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8ea87-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8ea87-286">Siga los pasos siguientes o [vea el vídeo (empieza en 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8ea87-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ea87-p113">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ea87-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ea87-289">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="8ea87-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ea87-291">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8ea87-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ea87-293">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-293">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ea87-295">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ea87-296">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8ea87-296">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ea87-298">Desplácese hacia abajo hasta la sección **servicio (registros SRV)** y, a continuación, seleccione **Editar registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Seleccione Editar registros SRV en servicio](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="8ea87-300">En los cuadros de los dos nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ea87-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8ea87-301">(Elija los valores **Servicio** y **Protocolo** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="8ea87-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="8ea87-302">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="8ea87-302">**Service**</span></span>|<span data-ttu-id="8ea87-303">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="8ea87-303">**Protocol**</span></span>|<span data-ttu-id="8ea87-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8ea87-304">**TTL**</span></span>|<span data-ttu-id="8ea87-305">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="8ea87-305">**Priority**</span></span>|<span data-ttu-id="8ea87-306">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="8ea87-306">**Weight**</span></span>|<span data-ttu-id="8ea87-307">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="8ea87-307">**Port**</span></span>|<span data-ttu-id="8ea87-308">**Destino**</span><span class="sxs-lookup"><span data-stu-id="8ea87-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8ea87-309">_sip</span><span class="sxs-lookup"><span data-stu-id="8ea87-309">_sip</span></span>  <br/> |<span data-ttu-id="8ea87-310">_tls</span><span class="sxs-lookup"><span data-stu-id="8ea87-310">_tls</span></span>  <br/> |<span data-ttu-id="8ea87-311">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-311">3600</span></span>  <br/> |<span data-ttu-id="8ea87-312">100</span><span class="sxs-lookup"><span data-stu-id="8ea87-312">100</span></span>  <br/> |<span data-ttu-id="8ea87-313">1</span><span class="sxs-lookup"><span data-stu-id="8ea87-313">1</span></span>  <br/> |<span data-ttu-id="8ea87-314">443</span><span class="sxs-lookup"><span data-stu-id="8ea87-314">443</span></span>  <br/> |<span data-ttu-id="8ea87-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ea87-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ea87-316">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="8ea87-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ea87-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8ea87-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="8ea87-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="8ea87-318">_tcp</span></span>  <br/> |<span data-ttu-id="8ea87-319">3600</span><span class="sxs-lookup"><span data-stu-id="8ea87-319">3600</span></span>  <br/> |<span data-ttu-id="8ea87-320">100</span><span class="sxs-lookup"><span data-stu-id="8ea87-320">100</span></span>  <br/> |<span data-ttu-id="8ea87-321">1</span><span class="sxs-lookup"><span data-stu-id="8ea87-321">1</span></span>  <br/> |<span data-ttu-id="8ea87-322">5061</span><span class="sxs-lookup"><span data-stu-id="8ea87-322">5061</span></span>  <br/> |<span data-ttu-id="8ea87-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ea87-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ea87-324">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8ea87-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Escriba o pegue los valores de los nuevos registros](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="8ea87-326">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-326">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="8ea87-328">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8ea87-328">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="8ea87-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ea87-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
