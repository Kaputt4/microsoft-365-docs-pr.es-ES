---
title: Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios
f1.keywords:
- CSH
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
description: Learn how to add and set up your domain in Microsoft 365 so that your services like email and Skype for Business Online use your own domain name.
ms.openlocfilehash: 492bc5d2a5f3fd9810f045e7effda1ea20fa15ed
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688254"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="7e410-103">Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios</span><span class="sxs-lookup"><span data-stu-id="7e410-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="7e410-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="7e410-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7e410-105">Compruebe [primero configurar su dominio (instrucciones específicas del host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para ver si tenemos instrucciones para su registrador.</span><span class="sxs-lookup"><span data-stu-id="7e410-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="7e410-106">Siga estas instrucciones para agregar y configurar su dominio en Microsoft 365 para que sus servicios como el correo electrónico y Teams usen su propio nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="7e410-107">Para ello, comprobará su dominio y, a continuación, cambiará los servidores dns de su dominio a Microsoft 365 para que los registros DNS correctos se puedan configurar por usted.</span><span class="sxs-lookup"><span data-stu-id="7e410-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="7e410-108">Siga estos pasos si las siguientes instrucciones describen su situación:</span><span class="sxs-lookup"><span data-stu-id="7e410-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="7e410-109">Tiene su propio dominio y desea configurarlo para que funcione con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e410-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="7e410-110">Quiere que Microsoft 365 administre los registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="7e410-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="7e410-111">(Si lo prefiere, puede [administrar sus propios registros DNS](../setup/add-domain.md)).</span><span class="sxs-lookup"><span data-stu-id="7e410-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="7e410-112">Agregar un registro TXT o MX para su verificación</span><span class="sxs-lookup"><span data-stu-id="7e410-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="7e410-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7e410-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="7e410-p103">Sólo debe crear uno de los dos registros. TXT es el tipo de registro preferido, pero algunos proveedores de host DNS no lo admiten. De ser así, puede crear un registro MX.</span><span class="sxs-lookup"><span data-stu-id="7e410-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="7e410-p104">Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e410-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="7e410-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="7e410-120">Busque el área en el sitio web del proveedor de hospedaje DNS donde puede crear un nuevo registro</span><span class="sxs-lookup"><span data-stu-id="7e410-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="7e410-121">Inicie sesión en el sitio web del proveedor de host DNS.</span><span class="sxs-lookup"><span data-stu-id="7e410-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="7e410-122">Elija su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="7e410-123">Busque la página donde puede modificar los registros DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="7e410-124">Crear el registro</span><span class="sxs-lookup"><span data-stu-id="7e410-124">Create the record</span></span>

<span data-ttu-id="7e410-125">En función de si se está creando un registro TXT o un registro MX, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e410-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="7e410-126">**Si crea un registro TXT, utilice estos valores:**</span><span class="sxs-lookup"><span data-stu-id="7e410-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e410-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="7e410-127">**Record Type**</span></span> <br/> |<span data-ttu-id="7e410-128">**Alias** o **Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="7e410-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="7e410-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7e410-129">**Value**</span></span> <br/> |<span data-ttu-id="7e410-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7e410-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="7e410-131">TXT</span><span class="sxs-lookup"><span data-stu-id="7e410-131">TXT</span></span>  <br/> |<span data-ttu-id="7e410-132">Realice una de las siguientes acciones: escriba **@**, deje el campo vacío o escriba el nombre de dominio.  </span><span class="sxs-lookup"><span data-stu-id="7e410-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="7e410-133">> [!NOTE]> Los distintos hosts DNS tienen requisitos distintos para este campo.</span><span class="sxs-lookup"><span data-stu-id="7e410-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="7e410-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7e410-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7e410-135">> [!NOTE]> Esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7e410-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="7e410-136">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e410-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="7e410-137">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="7e410-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7e410-138">Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="7e410-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="7e410-139">**Si crea un registro MX, utilice estos valores:**</span><span class="sxs-lookup"><span data-stu-id="7e410-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e410-140">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="7e410-140">**Record Type**</span></span>|<span data-ttu-id="7e410-141">**Alias** o **Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="7e410-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="7e410-142">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7e410-142">**Value**</span></span>|<span data-ttu-id="7e410-143">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="7e410-143">**Priority**</span></span>|<span data-ttu-id="7e410-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7e410-144">**TTL**</span></span>|
|<span data-ttu-id="7e410-145">MX</span><span class="sxs-lookup"><span data-stu-id="7e410-145">MX</span></span>|<span data-ttu-id="7e410-146">Escriba **@** o el nombre del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="7e410-147">MS=ms *XXXXXXXX* > [!NOTE]> Esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7e410-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="7e410-148">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e410-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="7e410-149">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="7e410-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7e410-150">Para **Prioridad**, para evitar conflictos con el registro MX usado para el flujo de correo, use una prioridad más baja que la prioridad de cualquier registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="7e410-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="7e410-151">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="7e410-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="7e410-152">Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="7e410-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="7e410-153">Guardar el registro</span><span class="sxs-lookup"><span data-stu-id="7e410-153">Save the record</span></span>

<span data-ttu-id="7e410-154">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="7e410-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="7e410-155">Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="7e410-156">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e410-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="7e410-157">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="7e410-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="7e410-158">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="7e410-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="7e410-159">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="7e410-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7e410-p109">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e410-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="7e410-163">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="7e410-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="7e410-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="7e410-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="7e410-165">Cuando llegue al último paso del asistente para la configuración de dominios en Microsoft 365, queda una tarea.</span><span class="sxs-lookup"><span data-stu-id="7e410-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="7e410-166">Para configurar su dominio con servicios de Microsoft 365, como el correo electrónico, cambie los registros del servidor dns (o NS) de su dominio en el registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e410-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="7e410-167">A continuación, dado que Microsoft 365 hospeda su DNS, los registros DNS necesarios para sus servicios se configurarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7e410-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="7e410-168">Puede actualizar los registros NS usted mismo siguiendo los pasos que su registrador de dominios debe proporcionar en el apartado de ayuda de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="7e410-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="7e410-169">Si no está familiarizado con DNS, pónganse en contacto con el registrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="7e410-170">Para cambiar los servidores DNS en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e410-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="7e410-171">Busque el área en el sitio web del registrador de dominios donde puede cambiar los servidores dns de su dominio o un área donde pueda usar servidores dns personalizados.</span><span class="sxs-lookup"><span data-stu-id="7e410-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="7e410-172">Cree registros de servidor dns o edite los registros existentes del servidor dns para que coincidan con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7e410-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="7e410-173">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="7e410-173">First nameserver</span></span>  <br/> |<span data-ttu-id="7e410-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e410-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7e410-175">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="7e410-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="7e410-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e410-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7e410-177">Tercer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="7e410-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="7e410-178">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e410-178">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7e410-179">Cuarto servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="7e410-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="7e410-180">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e410-180">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="7e410-181">Es mejor agregar los cuatro registros, pero si su registrador solo admite dos, agregue ns1.bdm.microsoftonline.com **y** **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="7e410-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="7e410-182">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="7e410-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="7e410-183">Al cambiar los registros NS de su dominio para que apunten a los servidores dns de Microsoft 365, se verán afectados todos los servicios asociados actualmente con su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="7e410-184">Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos.</span><span class="sxs-lookup"><span data-stu-id="7e410-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="7e410-185">De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="7e410-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="7e410-186">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="7e410-187">Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e410-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="7e410-188">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="7e410-188">First nameserver</span></span>  <br/> |<span data-ttu-id="7e410-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="7e410-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="7e410-190">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="7e410-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="7e410-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="7e410-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="7e410-192">Debe usar al menos dos registros de servidor dns.</span><span class="sxs-lookup"><span data-stu-id="7e410-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="7e410-193">Si hay otros servidores de nombres enumerados, puede eliminarlos o cambiarlos a ns3.dns.partner.microsoftonline.cn **y** **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="7e410-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="7e410-194">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="7e410-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="7e410-195">Al cambiar los registros NS de su dominio para que apunten a los servidores dns de Office 365 operados por 21Vianet, se verán afectados todos los servicios asociados actualmente con su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="7e410-196">Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos.</span><span class="sxs-lookup"><span data-stu-id="7e410-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="7e410-197">De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="7e410-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="7e410-198">Por ejemplo, aquí se indican algunos pasos adicionales que podrían ser necesarios para el hospedaje de correo electrónico y sitios web:</span><span class="sxs-lookup"><span data-stu-id="7e410-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="7e410-199">Mueva todas las direcciones de correo electrónico que usan su dominio a Microsoft 365 antes de cambiar los registros NS.</span><span class="sxs-lookup"><span data-stu-id="7e410-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="7e410-200">¿Quiere agregar un dominio que se utiliza actualmente con una dirección de página web, como www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="7e410-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="7e410-201">Puede seguir los pasos siguientes mientras agrega el dominio para mantener su sitio web hospedado donde se hospeda el sitio ahora para que los usuarios aún puedan acceder al sitio web después de cambiar los registros NS del dominio para que apunten a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e410-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="7e410-202">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7e410-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="7e410-203">En la **página Dominios,** seleccione el dominio y, a continuación, elija **Registros DNS.**</span><span class="sxs-lookup"><span data-stu-id="7e410-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="7e410-204">En **Administrar DNS,** seleccione **Registros personalizados** y, a continuación, **elija Nuevo registro personalizado.**</span><span class="sxs-lookup"><span data-stu-id="7e410-204">Under **Manage DNS**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="7e410-205">Seleccione el tipo de registro DNS que desea agregar y escriba la información del nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="7e410-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="7e410-206">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e410-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7e410-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="7e410-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e410-208">A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="7e410-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
