---
title: Cambiar los servidores de nombres para configurar Microsoft con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Obtenga información sobre cómo configurar Microsoft para administrar los registros DNS de su dominio personalizado en Hostgator.
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658025"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="4e93f-103">Cambiar los servidores de nombres para configurar Microsoft 365 con Hostgator</span><span class="sxs-lookup"><span data-stu-id="4e93f-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="4e93f-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="4e93f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="4e93f-105">Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="4e93f-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="4e93f-106">(Si lo prefiere, puede administrar todos los registros DNS de [Microsoft en Hostgator).](create-dns-records-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="4e93f-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="4e93f-107">Apunte el dominio a su cuenta de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="4e93f-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e93f-108">Necesita realizar este procedimiento antes de realizar el procedimiento de la sección siguiente ( **Agregar un registro TXT para comprobación** ).</span><span class="sxs-lookup"><span data-stu-id="4e93f-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="4e93f-109">Siga estos pasos para asociar el dominio y las cuentas de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="4e93f-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="4e93f-p102">Para empezar, vaya a la página de su portal de clientes en Hostgator con [este vínculo](https://portal.hostgator.com/domain/manage). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="4e93f-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="4e93f-113">Seleccione la **pestaña** Dominios.</span><span class="sxs-lookup"><span data-stu-id="4e93f-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="4e93f-115">En la **página Administrar dominios,** en el área **Mis dominios,** seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="4e93f-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="4e93f-117">En la **página Información general de** dominios, en el área Servidores **dns,** seleccione **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="4e93f-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="4e93f-119">En la **página Servidores** dns de  su dominio, en la  lista desplegable Seleccionar cuenta de hospedaje, elija la cuenta de hospedaje asociada a su dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="4e93f-121">Seleccione **Guardar servidores dns.**</span><span class="sxs-lookup"><span data-stu-id="4e93f-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4e93f-123">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="4e93f-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e93f-124">Antes de llevar a cabo este procedimiento, primero debe realizar el procedimiento de la primera sección de este artículo, Apuntar el dominio [a la cuenta de hospedaje.](#point-your-domain-to-your-hosting-account).</span><span class="sxs-lookup"><span data-stu-id="4e93f-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="4e93f-p103">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e93f-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="4e93f-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="4e93f-p105">Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="4e93f-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="4e93f-p106">(Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. La suscripción de correo electrónico que ha recibido de Hostgator especificará esa dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="4e93f-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4e93f-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="4e93f-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="4e93f-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e93f-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="4e93f-136">En la **página Panel de control,** en el área **Dominios,** seleccione **Editor de zona DNS avanzado.**</span><span class="sxs-lookup"><span data-stu-id="4e93f-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="4e93f-137">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="4e93f-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="4e93f-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4e93f-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4e93f-139">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="4e93f-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e93f-140">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4e93f-140">**Name**</span></span> <br/> |<span data-ttu-id="4e93f-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4e93f-141">**TTL**</span></span> <br/> |<span data-ttu-id="4e93f-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4e93f-142">**Type**</span></span> <br/> |<span data-ttu-id="4e93f-143">**Datos TXT**</span><span class="sxs-lookup"><span data-stu-id="4e93f-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="4e93f-p108">Use su  *nombre_de_dominio*  . (por ejemplo, fourthcoffee.com.)  </span><span class="sxs-lookup"><span data-stu-id="4e93f-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="4e93f-146">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="4e93f-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4e93f-147">1 </span><span class="sxs-lookup"><span data-stu-id="4e93f-147">1</span></span>  <br/> |<span data-ttu-id="4e93f-148">TXT</span><span class="sxs-lookup"><span data-stu-id="4e93f-148">TXT</span></span>  <br/> |<span data-ttu-id="4e93f-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4e93f-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4e93f-150">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4e93f-150">**Note:** This is an example.</span></span> <span data-ttu-id="4e93f-151">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="4e93f-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="4e93f-152">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="4e93f-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="4e93f-153">Seleccione **Agregar registro.**</span><span class="sxs-lookup"><span data-stu-id="4e93f-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="4e93f-154">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="4e93f-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4e93f-155">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="4e93f-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="4e93f-156">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4e93f-157">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="4e93f-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4e93f-158">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="4e93f-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4e93f-159">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="4e93f-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4e93f-160">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="4e93f-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4e93f-161">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="4e93f-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4e93f-162">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="4e93f-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4e93f-163">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4e93f-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4e93f-164">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="4e93f-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="4e93f-165">Para completar la configuración de su dominio con Microsoft, cambie los registros NS de su dominio en el registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e93f-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="4e93f-166">Esto configura Microsoft para que actualice automáticamente los registros DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="4e93f-167">Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="4e93f-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4e93f-168">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se verán afectados todos los servicios asociados actualmente a su dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4e93f-169">Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ your_domain .com) empezará a llegar *a*  Microsoft después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e93f-170">El siguiente procedimiento le mostrará cómo eliminar cualquier otro servidor de nombres no deseado de la lista y también cómo agregar los servidores de nombres correctos si aún no aparecen en la lista.</span><span class="sxs-lookup"><span data-stu-id="4e93f-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="4e93f-171">Cuando haya completado los pasos de esta sección, los únicos servidores de nombres que deben aparecer son los cuatro siguientes:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** y **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="4e93f-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="4e93f-p114">Para empezar, vaya a la página de su portal de clientes en Hostgator con [este vínculo](https://portal.hostgator.com/domain/manage). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="4e93f-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="4e93f-175">Seleccione la **pestaña** Dominios.</span><span class="sxs-lookup"><span data-stu-id="4e93f-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="4e93f-177">En la **página Administrar dominios,** en el área **Mis dominios,** seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="4e93f-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="4e93f-179">En la **página Información general del** dominio, en el área Servidores **dns,** seleccione **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="4e93f-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="4e93f-181">En la **página Servidores** dns de  su dominio, en la  lista desplegable Seleccionar cuenta de hospedaje, elija la cuenta de hospedaje asociada a su dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="4e93f-183">Seleccione **Establecer manualmente mis servidores de nombres.**</span><span class="sxs-lookup"><span data-stu-id="4e93f-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="4e93f-185">**PRECAUCIÓN:** Siga estos pasos solo si tiene servidores de nombres existentes distintos de los cuatro servidores de nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="4e93f-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="4e93f-186">(Es decir, elimine solo los servidores  de nombres actuales que no se denominan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="4e93f-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="4e93f-187">En la página **Servidores DNS** del dominio, en la lista de servidores DNS, elimine todos los servidores DNS de la lista (para hacerlo, seleccione los servidores DNS en la lista y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="4e93f-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="4e93f-189">En la lista de servidores DNS, escriba (o copie y pegue) los dos primeros valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e93f-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="4e93f-190">**Servidor DNS 1:**</span><span class="sxs-lookup"><span data-stu-id="4e93f-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="4e93f-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4e93f-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4e93f-192">**Servidor DNS 2:**</span><span class="sxs-lookup"><span data-stu-id="4e93f-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="4e93f-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4e93f-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4e93f-194">**Servidor DNS 3:**</span><span class="sxs-lookup"><span data-stu-id="4e93f-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="4e93f-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4e93f-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4e93f-196">**Servidor DNS 4:**</span><span class="sxs-lookup"><span data-stu-id="4e93f-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="4e93f-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4e93f-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="4e93f-199">Agregue los demás valores de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="4e93f-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="4e93f-200">Seleccione **(+)** agregar y, a continuación, escriba o copie y pegue el valor de la siguiente fila de la tabla en el cuadro del registro.</span><span class="sxs-lookup"><span data-stu-id="4e93f-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="4e93f-201">Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="4e93f-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="4e93f-203">Seleccione **Guardar servidores dns.**</span><span class="sxs-lookup"><span data-stu-id="4e93f-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="4e93f-205">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="4e93f-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4e93f-206">A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="4e93f-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
