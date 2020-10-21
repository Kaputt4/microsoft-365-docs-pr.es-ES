---
title: Cambiar los servidores DNS para configurar Microsoft con 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Obtenga información sobre cómo configurar Office 365 operado por 21Vianet para administrar los registros DNS, cuando 1&1 Internet es el proveedor de host DNS.
ms.openlocfilehash: 8a783be20d2f8dbdb26e9826018f911289b35235
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646564"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="d6ef4-103">Cambiar los servidores DNS para configurar Microsoft 365 con 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="d6ef4-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="d6ef4-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d6ef4-105">Siga estas instrucciones si desea que Microsoft 365 administre los registros DNS de Microsoft 365 por usted.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="d6ef4-106">(Si lo prefiere, puede [administrar todos los registros DNS de Microsoft 365 en 1&1 IONOS](create-dns-records-at-1-1-internet.md)).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d6ef4-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="d6ef4-107">Add a TXT record for verification</span></span>


<span data-ttu-id="d6ef4-p102">Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6ef4-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="d6ef4-112">Siga los pasos siguientes o [vea el vídeo (empieza en 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="d6ef4-113">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="d6ef4-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="d6ef4-115">En **mis dominios**, seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d6ef4-116">En la página **centro de dominios** , busque el dominio que desea actualizar; a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="d6ef4-117">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="d6ef4-118">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="d6ef4-119">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="d6ef4-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d6ef4-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-121">**Type**</span></span> <br/> |<span data-ttu-id="d6ef4-122">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-122">**Prefix**</span></span> <br/> |<span data-ttu-id="d6ef4-123">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="d6ef4-124">TXT</span><span class="sxs-lookup"><span data-stu-id="d6ef4-124">TXT</span></span>  <br/> |<span data-ttu-id="d6ef4-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d6ef4-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d6ef4-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d6ef4-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="d6ef4-127">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-127">**Note**: This is an example.</span></span> <span data-ttu-id="d6ef4-128">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="d6ef4-129">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="d6ef4-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="d6ef4-130">Seleccione **Guardar**y vuelva a **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="d6ef4-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="d6ef4-131">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="d6ef4-132">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d6ef4-133">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="d6ef4-134">Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d6ef4-135">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d6ef4-136">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d6ef4-137">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d6ef4-138">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6ef4-139">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d6ef4-140">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d6ef4-141">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d6ef4-142">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="d6ef4-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="d6ef4-143">Para completar la configuración de su dominio con Microsoft 365, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="d6ef4-144">Esto configura Microsoft 365 para que actualice los registros DNS del dominio por usted.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="d6ef4-145">Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d6ef4-146">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft 365, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="d6ef4-147">Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ *your_domain*  . com) empezará a llegar a Microsoft 365 después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="d6ef4-148">¿Está preparado para cambiar los registros NS para que Microsoft 365 pueda configurar su dominio?</span><span class="sxs-lookup"><span data-stu-id="d6ef4-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="d6ef4-149">Siga los pasos siguientes o [vea el vídeo (empieza en 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="d6ef4-150">El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="d6ef4-151">> cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="d6ef4-152">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="d6ef4-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="d6ef4-154">En **mis dominios**, seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d6ef4-155">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="d6ef4-156">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="d6ef4-157">En la sección **Configuración de servidor DNS**, seleccione **Otros servidores DNS**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="d6ef4-158">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="d6ef4-159">Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6ef4-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="d6ef4-160">Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="d6ef4-161">Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="d6ef4-162">Si aún NO se muestran servidores DNS en la lista</span><span class="sxs-lookup"><span data-stu-id="d6ef4-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="d6ef4-163">En el cuadro **Servidor DNS 1**, escriba (o copie y pegue) el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="d6ef4-164">**Servidor DNS 1**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="d6ef4-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Especificación de un valor en el cuadro servidor DNS 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="d6ef4-167">En la lista desplegable **Servidores DNS adicionales**, elija **Mis servidores DNS secundarios**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="d6ef4-169">En los cuadros **Servidor DNS 2, 3 y 4**, escriba (o copie y pegue) el valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="d6ef4-170">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="d6ef4-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d6ef4-172">**Servidor DNS 3:**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="d6ef4-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d6ef4-174">**Servidor DNS 4**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="d6ef4-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![Introducción de los valores del servidor de nombres](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="d6ef4-177">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-177">Select **Save**.</span></span>
    
    ![Seleccione Guardar en la página Configuración del servidor de nombres](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="d6ef4-179">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Selección de la opción Guardar en el cuadro de diálogo Editar configuración DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="d6ef4-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="d6ef4-182">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="d6ef4-183">Si ya existen servidores de nombres enumerados</span><span class="sxs-lookup"><span data-stu-id="d6ef4-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="d6ef4-p113">Siga estos pasos  *solo*  si tiene servidores de nombres distintos de los cuatro servidores de nombres  *correctos*  . (Es decir, elimine  *solo*  los servidores de nombres actuales que  *no*  sean **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com** ).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="d6ef4-186">Si ya se muestran servidores DNS en los cuadros de **Servidor DNS**, elimínelos (para hacerlo, selecciónelos de uno en uno y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="d6ef4-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="d6ef4-188">En los cuadros **Servidor DNS 1, 2, 3 y 4**, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="d6ef4-189">**Servidor DNS 1**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="d6ef4-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d6ef4-191">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="d6ef4-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d6ef4-193">**Servidor DNS 3:**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="d6ef4-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d6ef4-195">**Servidor DNS 4**</span><span class="sxs-lookup"><span data-stu-id="d6ef4-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="d6ef4-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d6ef4-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Introducción de los valores del servidor de nombres](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="d6ef4-198">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-198">Select **Save**.</span></span>
    
    ![Seleccione Guardar en la página Configuración del servidor de nombres](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="d6ef4-200">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Selección de la opción Guardar en el cuadro de diálogo Editar configuración DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="d6ef4-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="d6ef4-203">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ef4-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


