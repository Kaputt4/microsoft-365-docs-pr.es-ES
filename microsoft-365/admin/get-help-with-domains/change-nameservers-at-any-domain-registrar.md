---
title: Cambiar los servidores de nombres para configurar Microsoft 365 con cualquier registrador de dominio
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
description: Obtenga información sobre cómo agregar y configurar el dominio en Microsoft 365 para que los servicios como correo electrónico y Skype Empresarial Online usen su propio nombre de dominio.
ms.openlocfilehash: 447cc69aa2c4c3edcf1c4c6a2435cdc27fc22cd2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582997"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="9f37f-103">Cambiar los servidores de nombres para configurar Microsoft 365 con cualquier registrador de dominio</span><span class="sxs-lookup"><span data-stu-id="9f37f-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="9f37f-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9f37f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9f37f-105">Siga estas instrucciones para agregar y configurar el dominio en Microsoft 365 para que los servicios como correo electrónico y Teams usarán su propio nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="9f37f-106">Para ello, comprobará el dominio y, a continuación, cambiará los servidores de nombres de su dominio a Microsoft 365 para que los registros DNS correctos se puedan configurar por usted.</span><span class="sxs-lookup"><span data-stu-id="9f37f-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="9f37f-107">Siga estos pasos si las siguientes instrucciones describen su situación:</span><span class="sxs-lookup"><span data-stu-id="9f37f-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="9f37f-108">Tiene su propio dominio y desea configurarlo para que funcione con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f37f-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="9f37f-109">Desea que Microsoft 365 los registros DNS.</span><span class="sxs-lookup"><span data-stu-id="9f37f-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="9f37f-110">(Si lo prefiere, puede [administrar sus propios registros DNS](../setup/add-domain.md)).</span><span class="sxs-lookup"><span data-stu-id="9f37f-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="9f37f-111">Agregar un registro TXT o MX para su verificación</span><span class="sxs-lookup"><span data-stu-id="9f37f-111">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="9f37f-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9f37f-112"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="9f37f-p103">Sólo debe crear uno de los dos registros. TXT es el tipo de registro preferido, pero algunos proveedores de host DNS no lo admiten. De ser así, puede crear un registro MX.</span><span class="sxs-lookup"><span data-stu-id="9f37f-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="9f37f-p104">Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f37f-p105">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="9f37f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="9f37f-119">Buscar el área en el sitio web del proveedor de hospedaje DNS donde puede crear un nuevo registro</span><span class="sxs-lookup"><span data-stu-id="9f37f-119">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="9f37f-120">Inicie sesión en el sitio web del proveedor de host DNS.</span><span class="sxs-lookup"><span data-stu-id="9f37f-120">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="9f37f-121">Elija su dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-121">Choose your domain.</span></span>
    
3. <span data-ttu-id="9f37f-122">Busque la página donde puede modificar los registros DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-122">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="9f37f-123">Crear el registro</span><span class="sxs-lookup"><span data-stu-id="9f37f-123">Create the record</span></span>

<span data-ttu-id="9f37f-124">En función de si se está creando un registro TXT o un registro MX, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f37f-124">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="9f37f-125">**Si crea un registro TXT, utilice estos valores:**</span><span class="sxs-lookup"><span data-stu-id="9f37f-125">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f37f-126">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="9f37f-126">**Record Type**</span></span> <br/> |<span data-ttu-id="9f37f-127">**Alias** o **Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="9f37f-127">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="9f37f-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9f37f-128">**Value**</span></span> <br/> |<span data-ttu-id="9f37f-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9f37f-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="9f37f-130">TXT</span><span class="sxs-lookup"><span data-stu-id="9f37f-130">TXT</span></span>  <br/> |<span data-ttu-id="9f37f-131">Realice una de las siguientes acciones: escriba **@**, deje el campo vacío o escriba el nombre de dominio.  </span><span class="sxs-lookup"><span data-stu-id="9f37f-131">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="9f37f-132">> [!NOTE]> Los distintos hosts DNS tienen requisitos distintos para este campo.</span><span class="sxs-lookup"><span data-stu-id="9f37f-132">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="9f37f-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9f37f-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9f37f-134">> [!NOTE]> Esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9f37f-134">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="9f37f-135">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f37f-135">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="9f37f-136">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9f37f-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9f37f-137">Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="9f37f-137">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="9f37f-138">**Si crea un registro MX, utilice estos valores:**</span><span class="sxs-lookup"><span data-stu-id="9f37f-138">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f37f-139">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="9f37f-139">**Record Type**</span></span>|<span data-ttu-id="9f37f-140">**Alias** o **Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="9f37f-140">**Alias** or **Host Name**</span></span>|<span data-ttu-id="9f37f-141">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9f37f-141">**Value**</span></span>|<span data-ttu-id="9f37f-142">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="9f37f-142">**Priority**</span></span>|<span data-ttu-id="9f37f-143">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9f37f-143">**TTL**</span></span>|
|<span data-ttu-id="9f37f-144">MX</span><span class="sxs-lookup"><span data-stu-id="9f37f-144">MX</span></span>|<span data-ttu-id="9f37f-145">Escriba **@** o el nombre del dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-145">Type either **@** or your domain name.</span></span> |<span data-ttu-id="9f37f-146">MS=ms *XXXXXXXX* > [!NOTE]> Esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9f37f-146">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="9f37f-147">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f37f-147">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="9f37f-148">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9f37f-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9f37f-149">Para **Prioridad**, para evitar conflictos con el registro MX usado para el flujo de correo, use una prioridad más baja que la prioridad de cualquier registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="9f37f-149">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="9f37f-150">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="9f37f-150">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="9f37f-151">Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="9f37f-151">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="9f37f-152">Guardar el registro</span><span class="sxs-lookup"><span data-stu-id="9f37f-152">Save the record</span></span>

<span data-ttu-id="9f37f-153">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="9f37f-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="9f37f-154">Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-154">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="9f37f-155">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="9f37f-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9f37f-156">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="9f37f-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="9f37f-157">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-157">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="9f37f-158">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9f37f-p109">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9f37f-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9f37f-162">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="9f37f-162">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9f37f-163"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9f37f-163"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="9f37f-164">Cuando llegue al último paso del asistente para la configuración de dominios en Microsoft 365, queda una tarea.</span><span class="sxs-lookup"><span data-stu-id="9f37f-164">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="9f37f-165">Para configurar el dominio con servicios Microsoft 365, como el correo electrónico, se cambian los registros de servidor de nombres (o NS) del dominio en el registrador de dominio para que apunten Microsoft 365 servidores de nombres principales y secundarios.</span><span class="sxs-lookup"><span data-stu-id="9f37f-165">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="9f37f-166">A continuación, dado Microsoft 365 hospeda el DNS, los registros DNS necesarios para sus servicios se configurarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9f37f-166">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="9f37f-167">Puede actualizar los registros NS usted mismo siguiendo los pasos que su registrador de dominios debe proporcionar en el apartado de ayuda de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="9f37f-167">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="9f37f-168">Si no está familiarizado con DNS, pónganse en contacto con el registrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-168">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="9f37f-169">Para cambiar los servidores DNS en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f37f-169">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="9f37f-170">Busque el área en el sitio web del registrador de dominios donde puede cambiar los servidores de nombres de su dominio o un área donde puede usar servidores de nombres personalizados.</span><span class="sxs-lookup"><span data-stu-id="9f37f-170">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="9f37f-171">Cree registros de servidor de nombres o edite los registros de servidor de nombres existentes para que coincidan con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="9f37f-171">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="9f37f-172">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="9f37f-172">First nameserver</span></span>  <br/> |<span data-ttu-id="9f37f-173">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9f37f-173">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9f37f-174">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="9f37f-174">Second nameserver</span></span>  <br/> |<span data-ttu-id="9f37f-175">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9f37f-175">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9f37f-176">Tercer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="9f37f-176">Third nameserver</span></span>  <br/> |<span data-ttu-id="9f37f-177">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9f37f-177">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9f37f-178">Cuarto servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="9f37f-178">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="9f37f-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9f37f-179">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="9f37f-180">Es mejor agregar los cuatro registros, pero si el registrador solo admite dos, agregue ns1.bdm.microsoftonline.com **y** **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-180">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="9f37f-181">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="9f37f-181">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="9f37f-182">Al cambiar los registros NS del dominio para que apunten a los servidores de nombres Microsoft 365, se ven afectados todos los servicios que están asociados actualmente con el dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-182">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="9f37f-183">Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos.</span><span class="sxs-lookup"><span data-stu-id="9f37f-183">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="9f37f-184">De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="9f37f-184">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="9f37f-185">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-185">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9f37f-186">Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f37f-186">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="9f37f-187">Primer servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="9f37f-187">First nameserver</span></span>  <br/> |<span data-ttu-id="9f37f-188">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="9f37f-188">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="9f37f-189">Segundo servidor de nombres</span><span class="sxs-lookup"><span data-stu-id="9f37f-189">Second nameserver</span></span>  <br/> |<span data-ttu-id="9f37f-190">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="9f37f-190">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="9f37f-191">Debe usar al menos dos registros de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="9f37f-191">You should use at least two nameserver records.</span></span> <span data-ttu-id="9f37f-192">Si hay otros servidores de nombres enumerados, puede eliminarlos o cambiarlos a **ns3.dns.partner.microsoftonline.cn** y **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-192">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="9f37f-193">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="9f37f-193">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="9f37f-194">Al cambiar los registros NS de su dominio para que apunten al Office 365 operado por 21 servidores de nombres deVianet, se ven afectados todos los servicios que están asociados actualmente con el dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-194">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="9f37f-195">Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos.</span><span class="sxs-lookup"><span data-stu-id="9f37f-195">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="9f37f-196">De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="9f37f-196">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="9f37f-197">Por ejemplo, aquí se indican algunos pasos adicionales que podrían ser necesarios para el hospedaje de correo electrónico y sitios web:</span><span class="sxs-lookup"><span data-stu-id="9f37f-197">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="9f37f-198">Mueva todas las direcciones de correo electrónico que usan el dominio Microsoft 365 antes de cambiar los registros NS.</span><span class="sxs-lookup"><span data-stu-id="9f37f-198">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="9f37f-199">¿Quiere agregar un dominio que se utiliza actualmente con una dirección de página web, como www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="9f37f-199">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="9f37f-200">Puede seguir los pasos siguientes mientras agrega el dominio para mantener su sitio web hospedado donde el sitio está hospedado ahora para que los usuarios puedan llegar al sitio web después de cambiar los registros NS del dominio para que apunten a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f37f-200">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="9f37f-201">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="9f37f-201">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="9f37f-202">En la página **Dominios**, seleccione un dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-202">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="9f37f-203">En la página de detalles del dominio, seleccione la **pestaña Registros DNS.**</span><span class="sxs-lookup"><span data-stu-id="9f37f-203">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="9f37f-204">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-204">Select **Add record**.</span></span>

5. <span data-ttu-id="9f37f-205">En el **panel Agregar un registro DNS** personalizado, en la lista desplegable Tipo, seleccione A **(Dirección).** </span><span class="sxs-lookup"><span data-stu-id="9f37f-205">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="9f37f-206">En el **cuadro Nombre de host o Alias,** escriba **@** .</span><span class="sxs-lookup"><span data-stu-id="9f37f-206">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="9f37f-207">En el **cuadro Dirección IP,** escriba la dirección IP estática del sitio web donde está hospedado actualmente.</span><span class="sxs-lookup"><span data-stu-id="9f37f-207">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="9f37f-208">Por ejemplo, 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="9f37f-208">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="9f37f-209">Debe ser una dirección IP _estática_ para el sitio web, no una _dirección_ IP dinámica.</span><span class="sxs-lookup"><span data-stu-id="9f37f-209">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="9f37f-210">Para asegurarse de que puede obtener una dirección IP estática para su sitio web público, consulte con el sitio que hospeda el sitio web.</span><span class="sxs-lookup"><span data-stu-id="9f37f-210">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="9f37f-211">Si desea cambiar la configuración de TTL para el registro, seleccione un nuevo período de tiempo en la lista desplegable **TTL.**</span><span class="sxs-lookup"><span data-stu-id="9f37f-211">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="9f37f-212">De lo contrario, continúe con el paso 9.</span><span class="sxs-lookup"><span data-stu-id="9f37f-212">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="9f37f-213">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-213">Select **Save**.</span></span> 
    
<span data-ttu-id="9f37f-214">Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.</span><span class="sxs-lookup"><span data-stu-id="9f37f-214">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="9f37f-215">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-215">Select **Add record**.</span></span>

3.  <span data-ttu-id="9f37f-216">En el panel Agregar un registro  **DNS** personalizado, en la lista desplegable Tipo, seleccione **CNAME (Alias).**</span><span class="sxs-lookup"><span data-stu-id="9f37f-216">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="9f37f-217">En el **cuadro Nombre de host o Alias,** escriba **www**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-217">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="9f37f-218">En el **cuadro Dirección de puntos** a, escriba el nombre de dominio completo (FQDN) del sitio web.</span><span class="sxs-lookup"><span data-stu-id="9f37f-218">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="9f37f-219">Por ejemplo, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-219">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="9f37f-220">Si desea cambiar la configuración de TTL para el registro, seleccione un nuevo período de tiempo en la lista desplegable **TTL.**</span><span class="sxs-lookup"><span data-stu-id="9f37f-220">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="9f37f-221">De lo contrario, continúe con el paso 6.</span><span class="sxs-lookup"><span data-stu-id="9f37f-221">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="9f37f-222">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9f37f-222">Select **Save**.</span></span>

<span data-ttu-id="9f37f-223">Después de actualizar los registros del servidor de nombres para que apunten a Microsoft, se completa la configuración del dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-223">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="9f37f-224">El correo electrónico se enruta a Microsoft y el tráfico a la dirección de su sitio web continúa en el host del sitio web actual.'</span><span class="sxs-lookup"><span data-stu-id="9f37f-224">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="9f37f-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9f37f-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9f37f-226">A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="9f37f-226">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="9f37f-227">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9f37f-227">Related content</span></span>

<span data-ttu-id="9f37f-228">[Agregar registros DNS para conectar el dominio](create-dns-records-at-any-dns-hosting-provider.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9f37f-228">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>

<span data-ttu-id="9f37f-229">[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9f37f-229">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="9f37f-230">[Administrar dominios](index.yml) (página de vínculo)</span><span class="sxs-lookup"><span data-stu-id="9f37f-230">[Manage domains](index.yml) (link page)</span></span>
