---
title: Crear registros DNS para zonas DNS de Azure
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en zonas DNS de Azure para Microsoft.
ms.openlocfilehash: be4baa80d0f96e92dc9dd9004054f29f12f6415b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916147"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="3acdb-103">Crear registros DNS para zonas DNS de Azure</span><span class="sxs-lookup"><span data-stu-id="3acdb-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="3acdb-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="3acdb-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3acdb-105">Si Azure es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="3acdb-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3acdb-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="3acdb-107">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="3acdb-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="3acdb-108">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="3acdb-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="3acdb-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3acdb-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="3acdb-110">Agregar los cuatro registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3acdb-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="3acdb-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="3acdb-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="3acdb-112">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3acdb-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="3acdb-113">Después de agregar estos registros en Azure, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3acdb-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3acdb-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3acdb-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="3acdb-117">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="3acdb-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="3acdb-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="3acdb-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3acdb-119">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="3acdb-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="3acdb-120">Cuando se inscribió en Azure, creó un grupo de recursos dentro de una zona DNS y, a continuación, asignó el nombre de dominio a ese grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="3acdb-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="3acdb-121">Ese nombre de dominio está registrado en un registrador de dominio externo; Azure no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="3acdb-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="3acdb-122">Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de Azure asignados al grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="3acdb-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="3acdb-123">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3acdb-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="3acdb-124">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="3acdb-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="3acdb-125">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros existentes del servidor de nombres para que coincidan con estos valores.</span><span class="sxs-lookup"><span data-stu-id="3acdb-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="3acdb-126">A continuación se muestra un ejemplo de servidores de nombres asignados de Azure.</span><span class="sxs-lookup"><span data-stu-id="3acdb-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="3acdb-127">**Primer servidor de nombres:** Use el valor de servidor de nombres asignado por Azure.</span><span class="sxs-lookup"><span data-stu-id="3acdb-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="3acdb-128">**Segundo servidor de nombres:** Use el valor de servidor de nombres asignado por Azure.</span><span class="sxs-lookup"><span data-stu-id="3acdb-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="3acdb-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="3acdb-130">You should use at least two name server records.</span></span> <span data-ttu-id="3acdb-131">Si hay otros servidores de nombres enumerados en el sitio web del registrador de dominios, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="3acdb-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="3acdb-132">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="3acdb-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3acdb-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3acdb-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="3acdb-134">A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="3acdb-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3acdb-135">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="3acdb-135">Add a TXT record for verification</span></span>
<span data-ttu-id="3acdb-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3acdb-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3acdb-p106">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3acdb-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3acdb-p107">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="3acdb-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3acdb-141">Para empezar, vaya a la página dominios de Azure mediante [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="3acdb-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="3acdb-142">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="3acdb-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="3acdb-144">Con la **barra de búsqueda de** la página **Panel,** escriba zonas **DNS**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="3acdb-145">En la presentación de resultados, seleccione **zonas DNS en** la **parte** Servicios.</span><span class="sxs-lookup"><span data-stu-id="3acdb-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="3acdb-146">Una vez que te redirijan, selecciona el dominio que quieres actualizar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="3acdb-148">En la **página Configuración** del dominio, en el área **zona DNS,** seleccione **+ Conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="3acdb-150">En el **área Agregar conjunto de** registros, en los cuadros del nuevo conjunto de registros, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3acdb-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="3acdb-151">(Elija los **valores de unidad Type** y **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="3acdb-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3acdb-152">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3acdb-152">**Name**</span></span>|<span data-ttu-id="3acdb-153">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-153">**Type**</span></span>|<span data-ttu-id="3acdb-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-154">**TTL**</span></span>|<span data-ttu-id="3acdb-155">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-155">**TTL unit**</span></span>|<span data-ttu-id="3acdb-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="3acdb-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3acdb-157">TXT</span><span class="sxs-lookup"><span data-stu-id="3acdb-157">TXT</span></span>  <br/> |<span data-ttu-id="3acdb-158">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-158">1</span></span>  <br/> |<span data-ttu-id="3acdb-159">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-159">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3acdb-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3acdb-161">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3acdb-161">**Note:** This is an example.</span></span> <span data-ttu-id="3acdb-162">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="3acdb-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3acdb-163">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="3acdb-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="3acdb-165">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="3acdb-166">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="3acdb-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3acdb-167">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="3acdb-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3acdb-168">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="3acdb-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3acdb-169">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="3acdb-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3acdb-170">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="3acdb-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3acdb-171">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3acdb-172">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3acdb-p111">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3acdb-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3acdb-176">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3acdb-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3acdb-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3acdb-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3acdb-178">Para empezar, vaya a la página dominios de Azure mediante [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="3acdb-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="3acdb-179">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="3acdb-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="3acdb-181">En la **página Panel,** en el **área Todos los** recursos, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="3acdb-183">En la **página Configuración** del dominio, en el área **zona DNS,** seleccione **+ Conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="3acdb-185">En el **área Agregar conjunto de** registros, en los cuadros del nuevo conjunto de registros, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3acdb-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="3acdb-186">(Elija los **valores de unidad Type** y **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="3acdb-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3acdb-187">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3acdb-187">**Name**</span></span>|<span data-ttu-id="3acdb-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-188">**Type**</span></span>|<span data-ttu-id="3acdb-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-189">**TTL**</span></span>|<span data-ttu-id="3acdb-190">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-190">**TTL unit**</span></span>|<span data-ttu-id="3acdb-191">**Preferencia**</span><span class="sxs-lookup"><span data-stu-id="3acdb-191">**Preference**</span></span>|<span data-ttu-id="3acdb-192">**Intercambio de correo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3acdb-193">MX</span><span class="sxs-lookup"><span data-stu-id="3acdb-193">MX</span></span>  <br/> |<span data-ttu-id="3acdb-194">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-194">1</span></span>  <br/> |<span data-ttu-id="3acdb-195">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-195">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-196">10  </span><span class="sxs-lookup"><span data-stu-id="3acdb-196">10</span></span>  <br/> <span data-ttu-id="3acdb-197">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="3acdb-197">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="3acdb-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3acdb-199">**Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3acdb-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="3acdb-200">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="3acdb-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="3acdb-202">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="3acdb-204">Si hay otros registros MX enumerados en la sección **Registros MX,** debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="3acdb-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="3acdb-205">En primer lugar, en el **área zona DNS,** seleccione el conjunto **de registros MX**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="3acdb-207">A continuación, seleccione el registro MX que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="3acdb-209">Seleccione el **menú Contextual (...)** y, a continuación, elija **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="3acdb-211">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3acdb-213">Agregar los cuatro registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3acdb-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3acdb-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3acdb-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3acdb-215">Para empezar, vaya a la página dominios de Azure mediante [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="3acdb-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="3acdb-216">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="3acdb-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="3acdb-218">En la **página Panel,** en el **área Todos los** recursos, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="3acdb-220">En la **página Configuración** del dominio, en el área **zona DNS,** seleccione **+ Conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="3acdb-222">Agregue el primero de los cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3acdb-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="3acdb-223">En el **área Agregar conjunto de** registros, en los cuadros del nuevo conjunto de registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3acdb-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3acdb-224">(Elija los **valores de unidad Type** y **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="3acdb-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3acdb-225">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3acdb-225">**Name**</span></span>|<span data-ttu-id="3acdb-226">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-226">**Type**</span></span>|<span data-ttu-id="3acdb-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-227">**TTL**</span></span>|<span data-ttu-id="3acdb-228">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-228">**TTL unit**</span></span>|<span data-ttu-id="3acdb-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="3acdb-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3acdb-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3acdb-230">autodiscover</span></span>  <br/> |<span data-ttu-id="3acdb-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acdb-231">CNAME</span></span>  <br/> |<span data-ttu-id="3acdb-232">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-232">1</span></span>  <br/> |<span data-ttu-id="3acdb-233">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-233">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3acdb-235">sip</span><span class="sxs-lookup"><span data-stu-id="3acdb-235">sip</span></span>  <br/> |<span data-ttu-id="3acdb-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acdb-236">CNAME</span></span>  <br/> |<span data-ttu-id="3acdb-237">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-237">1</span></span>  <br/> |<span data-ttu-id="3acdb-238">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-238">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3acdb-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3acdb-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3acdb-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acdb-241">CNAME</span></span>  <br/> |<span data-ttu-id="3acdb-242">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-242">1</span></span>  <br/> |<span data-ttu-id="3acdb-243">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-243">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="3acdb-246">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="3acdb-248">Agregue cada uno de los otros tres registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3acdb-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="3acdb-249">En el **área zona DNS,** seleccione **+ Conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="3acdb-250">A continuación, en el conjunto de registros vacío, cree un registro mediante los valores de la siguiente fila de la tabla y, de nuevo, seleccione **Aceptar** para completar dicho registro.</span><span class="sxs-lookup"><span data-stu-id="3acdb-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="3acdb-251">Repita este proceso hasta que haya creado los cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3acdb-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="3acdb-252">(Opcional) Agrega 2 registros CNAME para MDM.</span><span class="sxs-lookup"><span data-stu-id="3acdb-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3acdb-253">Si tienes Administración de dispositivos móviles (MDM) para Microsoft, debes crear dos registros CNAME adicionales.</span><span class="sxs-lookup"><span data-stu-id="3acdb-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="3acdb-254">Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="3acdb-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="3acdb-255">(Si no tienes MDM, puedes omitir este paso).</span><span class="sxs-lookup"><span data-stu-id="3acdb-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="3acdb-256">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3acdb-256">**Name**</span></span>|<span data-ttu-id="3acdb-257">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-257">**Type**</span></span>|<span data-ttu-id="3acdb-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-258">**TTL**</span></span>|<span data-ttu-id="3acdb-259">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-259">**TTL unit**</span></span>|<span data-ttu-id="3acdb-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="3acdb-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3acdb-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3acdb-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3acdb-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acdb-262">CNAME</span></span>  <br/> |<span data-ttu-id="3acdb-263">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-263">1</span></span>  <br/> |<span data-ttu-id="3acdb-264">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-264">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3acdb-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="3acdb-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3acdb-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3acdb-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acdb-267">CNAME</span></span>  <br/> |<span data-ttu-id="3acdb-268">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-268">1</span></span>  <br/> |<span data-ttu-id="3acdb-269">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-269">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3acdb-271">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="3acdb-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3acdb-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3acdb-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3acdb-273">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="3acdb-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3acdb-274">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3acdb-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3acdb-275">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3acdb-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3acdb-276">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="3acdb-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="3acdb-277">Para empezar, vaya a la página dominios de Azure mediante [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="3acdb-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="3acdb-278">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="3acdb-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="3acdb-280">En la **página Panel,** en el **área Todos los** recursos, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="3acdb-282">En el **área zona DNS,** seleccione el **conjunto de registros TXT**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="3acdb-284">En el **área Propiedades del conjunto de** registros, en los cuadros del nuevo conjunto de registros, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3acdb-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="3acdb-285">(Elija los **valores de unidad Type** y **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="3acdb-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3acdb-286">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3acdb-286">**Name**</span></span>|<span data-ttu-id="3acdb-287">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-287">**Type**</span></span>|<span data-ttu-id="3acdb-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-288">**TTL**</span></span>|<span data-ttu-id="3acdb-289">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-289">**TTL unit**</span></span>|<span data-ttu-id="3acdb-290">**Valor**</span><span class="sxs-lookup"><span data-stu-id="3acdb-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3acdb-291">TXT</span><span class="sxs-lookup"><span data-stu-id="3acdb-291">TXT</span></span>  <br/> |<span data-ttu-id="3acdb-292">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-292">1</span></span>  <br/> |<span data-ttu-id="3acdb-293">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-293">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3acdb-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3acdb-295">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3acdb-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="3acdb-297">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3acdb-299">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3acdb-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3acdb-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3acdb-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3acdb-301">Para empezar, vaya a la página dominios de Azure mediante [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="3acdb-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="3acdb-302">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="3acdb-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="3acdb-304">En la **página Panel,** en el **área Todos los** recursos, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="3acdb-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="3acdb-306">En la **página Configuración** del dominio, en el área **zona DNS,** seleccione **+ Conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="3acdb-308">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="3acdb-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3acdb-309">En el **área Agregar conjunto de** registros, en los cuadros del nuevo conjunto de registros, seleccione los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3acdb-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3acdb-310">(Elija los **valores de unidad Type** y **TTL** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="3acdb-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3acdb-311">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3acdb-311">**Name**</span></span>|<span data-ttu-id="3acdb-312">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acdb-312">**Type**</span></span>|<span data-ttu-id="3acdb-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-313">**TTL**</span></span>|<span data-ttu-id="3acdb-314">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="3acdb-314">**TTL unit**</span></span>|<span data-ttu-id="3acdb-315">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="3acdb-315">**Priority**</span></span>|<span data-ttu-id="3acdb-316">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="3acdb-316">**Weight**</span></span>|<span data-ttu-id="3acdb-317">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="3acdb-317">**Port**</span></span>|<span data-ttu-id="3acdb-318">**Destino**</span><span class="sxs-lookup"><span data-stu-id="3acdb-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3acdb-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3acdb-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="3acdb-320">SRV</span><span class="sxs-lookup"><span data-stu-id="3acdb-320">SRV</span></span>  <br/> |<span data-ttu-id="3acdb-321">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-321">1</span></span>  <br/> |<span data-ttu-id="3acdb-322">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-322">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-323">100</span><span class="sxs-lookup"><span data-stu-id="3acdb-323">100</span></span>  <br/> |<span data-ttu-id="3acdb-324">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-324">1</span></span>  <br/> |<span data-ttu-id="3acdb-325">443</span><span class="sxs-lookup"><span data-stu-id="3acdb-325">443</span></span>  <br/> |<span data-ttu-id="3acdb-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3acdb-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3acdb-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3acdb-328">SRV</span><span class="sxs-lookup"><span data-stu-id="3acdb-328">SRV</span></span>  <br/> |<span data-ttu-id="3acdb-329">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-329">1</span></span>  <br/> |<span data-ttu-id="3acdb-330">Horas</span><span class="sxs-lookup"><span data-stu-id="3acdb-330">Hours</span></span>  <br/> |<span data-ttu-id="3acdb-331">100</span><span class="sxs-lookup"><span data-stu-id="3acdb-331">100</span></span>  <br/> |<span data-ttu-id="3acdb-332">1</span><span class="sxs-lookup"><span data-stu-id="3acdb-332">1</span></span>  <br/> |<span data-ttu-id="3acdb-333">5061</span><span class="sxs-lookup"><span data-stu-id="3acdb-333">5061</span></span>  <br/> |<span data-ttu-id="3acdb-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3acdb-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="3acdb-336">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3acdb-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="3acdb-338">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="3acdb-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3acdb-339">En los cuadros del nuevo registro, escriba o copie y pegue los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3acdb-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3acdb-p120">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3acdb-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
