---
title: Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Obtenga información sobre cómo agregar y configurar el dominio en Microsoft 365 para que sus servicios como el correo electrónico y Skype empresarial online usen su propio nombre de dominio.
ms.openlocfilehash: 16e8699c1c8588a4368f04078fea44c165c13e29
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399997"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="bb1ff-103">Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios</span><span class="sxs-lookup"><span data-stu-id="bb1ff-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="bb1ff-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bb1ff-105">Compruebe primero [la configuración del dominio (instrucciones específicas del host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para ver si tenemos instrucciones para su registrador.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="bb1ff-106">Siga estas instrucciones para agregar y configurar el dominio en Microsoft 365 para que sus servicios como el correo electrónico y Skype empresarial online usen su propio nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="bb1ff-107">Para ello, deberá comprobar el dominio y, a continuación, cambiar los servidores de nombres de dominio a Microsoft 365 para que se puedan configurar los registros DNS correctos.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="bb1ff-108">Siga estos pasos si la siguiente instrucción describe su situación:</span><span class="sxs-lookup"><span data-stu-id="bb1ff-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="bb1ff-109">Tiene su propio dominio y desea configurarlo para que funcione con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="bb1ff-110">Desea que Microsoft 365 administre sus registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="bb1ff-111">(Si lo prefiere, puede [administrar sus propios registros DNS](../setup/add-domain.md)).</span><span class="sxs-lookup"><span data-stu-id="bb1ff-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="bb1ff-112">Agregar un registro TXT o MX para su verificación</span><span class="sxs-lookup"><span data-stu-id="bb1ff-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="bb1ff-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bb1ff-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="bb1ff-p103">Sólo debe crear uno de los dos registros. TXT es el tipo de registro preferido, pero algunos proveedores de host DNS no lo admiten. De ser así, puede crear un registro MX.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="bb1ff-p104">Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb1ff-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="bb1ff-120">Busque el área del sitio web de su proveedor de host DNS en la que puede crear un registro nuevo</span><span class="sxs-lookup"><span data-stu-id="bb1ff-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="bb1ff-121">Inicie sesión en el sitio web del proveedor de host DNS.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="bb1ff-122">Elija su dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="bb1ff-123">Busque la página donde puede modificar los registros DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="bb1ff-124">Crear el registro</span><span class="sxs-lookup"><span data-stu-id="bb1ff-124">Create the record</span></span>

<span data-ttu-id="bb1ff-125">En función de si se está creando un registro TXT o un registro MX, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1ff-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="bb1ff-126">**Si crea un registro TXT, utilice estos valores:**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb1ff-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-127">**Record Type**</span></span> <br/> |<span data-ttu-id="bb1ff-128">**Alias** o **Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="bb1ff-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-129">**Value**</span></span> <br/> |<span data-ttu-id="bb1ff-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="bb1ff-131">TXT</span><span class="sxs-lookup"><span data-stu-id="bb1ff-131">TXT</span></span>  <br/> |<span data-ttu-id="bb1ff-132">Realice una de las siguientes acciones: escriba **@**, deje el campo vacío o escriba el nombre de dominio.  </span><span class="sxs-lookup"><span data-stu-id="bb1ff-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="bb1ff-133">> [!NOTE]> Los distintos hosts DNS tienen requisitos distintos para este campo.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="bb1ff-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bb1ff-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bb1ff-135">> [!NOTE]> Esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="bb1ff-136">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="bb1ff-137">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="bb1ff-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="bb1ff-138">Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="bb1ff-139">**Si crea un registro MX, utilice estos valores:**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb1ff-140">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-140">**Record Type**</span></span>|<span data-ttu-id="bb1ff-141">**Alias** o **Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="bb1ff-142">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-142">**Value**</span></span>|<span data-ttu-id="bb1ff-143">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-143">**Priority**</span></span>|<span data-ttu-id="bb1ff-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bb1ff-144">**TTL**</span></span>|
|<span data-ttu-id="bb1ff-145">MX</span><span class="sxs-lookup"><span data-stu-id="bb1ff-145">MX</span></span>|<span data-ttu-id="bb1ff-146">Escriba **@** o el nombre del dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="bb1ff-147">MS=ms *XXXXXXXX* > [!NOTE]> Esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="bb1ff-148">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="bb1ff-149">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="bb1ff-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="bb1ff-150">Para**Prioridad**, para evitar conflictos con el registro MX usado para el flujo de correo, use una prioridad más baja que la prioridad de cualquier registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="bb1ff-151">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="bb1ff-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="bb1ff-152">Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="bb1ff-153">Guardar el registro</span><span class="sxs-lookup"><span data-stu-id="bb1ff-153">Save the record</span></span>

<span data-ttu-id="bb1ff-154">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="bb1ff-155">Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="bb1ff-156">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="bb1ff-157">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="bb1ff-158">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="bb1ff-159">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bb1ff-p109">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bb1ff-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="bb1ff-163">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="bb1ff-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="bb1ff-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="bb1ff-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="bb1ff-165">Cuando llegue al último paso del asistente de configuración de dominios de Microsoft 365, tiene una tarea restante.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="bb1ff-166">Para configurar el dominio con los servicios de Microsoft 365, como el correo electrónico, cambie los registros del servidor de nombres (o NS) de su dominio en su registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="bb1ff-167">A continuación, como Microsoft 365 hospeda el DNS, los registros DNS necesarios para los servicios se configuran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="bb1ff-168">Puede actualizar los registros NS usted mismo siguiendo los pasos que su registrador de dominios debe proporcionar en el apartado de ayuda de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="bb1ff-169">Si no está familiarizado con DNS, pónganse en contacto con el registrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="bb1ff-170">Para cambiar los servidores DNS en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb1ff-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="bb1ff-171">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="bb1ff-172">Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1ff-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="bb1ff-173">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="bb1ff-173">First nameserver</span></span>  <br/> |<span data-ttu-id="bb1ff-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb1ff-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb1ff-175">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="bb1ff-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="bb1ff-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb1ff-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="bb1ff-177">Debe usar al menos dos registros de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="bb1ff-178">Si en la lista se muestran otros servidores DNS, puede eliminarlos o cambiarlos a **NS3.BDM.microsoftonline.com** y **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="bb1ff-179">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="bb1ff-180">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft 365, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="bb1ff-181">Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="bb1ff-182">De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="bb1ff-183">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="bb1ff-184">Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1ff-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="bb1ff-185">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="bb1ff-185">First nameserver</span></span>  <br/> |<span data-ttu-id="bb1ff-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="bb1ff-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="bb1ff-187">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="bb1ff-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="bb1ff-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="bb1ff-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="bb1ff-189">Debe usar al menos dos registros de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="bb1ff-190">Si en la lista se muestran otros servidores DNS, puede eliminarlos o cambiarlos a **NS3.DNS.Partner.microsoftonline.cn** y **NS4.DNS.Partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="bb1ff-191">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="bb1ff-192">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Office 365 operados por 21Vianet, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="bb1ff-193">Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="bb1ff-194">De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="bb1ff-195">Por ejemplo, aquí se indican algunos pasos adicionales que podrían ser necesarios para el hospedaje de correo electrónico y sitios web:</span><span class="sxs-lookup"><span data-stu-id="bb1ff-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="bb1ff-196">Mueva todas las direcciones de correo electrónico que usan su dominio a Microsoft 365 antes de cambiar los registros NS.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="bb1ff-197">¿Quiere agregar un dominio que se utiliza actualmente con una dirección de página web, como www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="bb1ff-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="bb1ff-198">Puede seguir los pasos que se indican a continuación mientras agrega el dominio para mantener su sitio web hospedado donde se hospeda el sitio ahora, de modo que los usuarios puedan seguir teniendo acceso al sitio web después de cambiar los registros NS del dominio para que apunten a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="bb1ff-199">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="bb1ff-200">En la página Dominios, seleccione un dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="bb1ff-201">En **configuración DNS**, seleccione **registros personalizados**y, a continuación, seleccione **nuevo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="bb1ff-202">Seleccione el tipo de registro DNS que desea agregar y escriba la información para el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="bb1ff-203">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb1ff-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb1ff-205">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="bb1ff-205">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  

