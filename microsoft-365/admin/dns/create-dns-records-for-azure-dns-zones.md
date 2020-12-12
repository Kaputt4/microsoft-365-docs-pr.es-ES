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
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en zonas DNS de Azure para Microsoft.
ms.openlocfilehash: c276570ec1d5ff079348bd8202ea597ef61e88f6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656872"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="188a4-103">Crear registros DNS para zonas DNS de Azure</span><span class="sxs-lookup"><span data-stu-id="188a4-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="188a4-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="188a4-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="188a4-105">Si Azure es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="188a4-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="188a4-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="188a4-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="188a4-107">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="188a4-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="188a4-108">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="188a4-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="188a4-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="188a4-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="188a4-110">Agregar los cuatro registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="188a4-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="188a4-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="188a4-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="188a4-112">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="188a4-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="188a4-113">Después de agregar estos registros a Azure, el dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="188a4-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="188a4-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="188a4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="188a4-117">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="188a4-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="188a4-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="188a4-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="188a4-119">Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.</span><span class="sxs-lookup"><span data-stu-id="188a4-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="188a4-120">Al registrarse en Azure, ha creado un grupo de recursos dentro de una zona DNS y, a continuación, ha asignado el nombre de dominio a ese grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="188a4-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="188a4-121">Ese nombre de dominio está registrado en un registrador de dominios externo; Azure no ofrece servicios de registro de dominios.</span><span class="sxs-lookup"><span data-stu-id="188a4-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="188a4-122">Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de Azure asignados a su grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="188a4-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="188a4-123">Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="188a4-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="188a4-124">En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="188a4-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="188a4-125">Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.</span><span class="sxs-lookup"><span data-stu-id="188a4-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="188a4-126">A continuación se muestra un ejemplo de los servidores de nombres asignados de Azure.</span><span class="sxs-lookup"><span data-stu-id="188a4-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="188a4-127">**Primer servidor de nombres:** Use el valor de servidor de nombres asignado por Azure.</span><span class="sxs-lookup"><span data-stu-id="188a4-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="188a4-128">**Segundo servidor de nombres:** Use el valor de servidor de nombres asignado por Azure.</span><span class="sxs-lookup"><span data-stu-id="188a4-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="188a4-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="188a4-130">You should use at least two name server records.</span></span> <span data-ttu-id="188a4-131">Si hay otros servidores de nombres enumerados en el sitio web del registrador de dominios, debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="188a4-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="188a4-132">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="188a4-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="188a4-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="188a4-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="188a4-134">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="188a4-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="188a4-135">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="188a4-135">Add a TXT record for verification</span></span>
<span data-ttu-id="188a4-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="188a4-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="188a4-p106">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="188a4-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="188a4-p107">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="188a4-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="188a4-141">Para empezar, vaya a su página de dominios en Azure con [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="188a4-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="188a4-142">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="188a4-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="188a4-144">En la **barra de búsqueda** de la página **Panel** , escriba en **zonas DNS**.</span><span class="sxs-lookup"><span data-stu-id="188a4-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="188a4-145">En la pantalla de resultados, seleccione **zonas DNS** en la parte **servicios** .</span><span class="sxs-lookup"><span data-stu-id="188a4-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="188a4-146">Una vez que se haya Redirigido, seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="188a4-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="188a4-148">En la página de **configuración** de su dominio, en el área **zona DNS** , seleccione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="188a4-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="188a4-150">En el área **Agregar conjunto de registros** , en los cuadros para el nuevo conjunto de registros, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="188a4-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="188a4-151">(Elija los valores **tipo** y TTL de la **unidad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="188a4-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="188a4-152">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="188a4-152">**Name**</span></span>|<span data-ttu-id="188a4-153">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="188a4-153">**Type**</span></span>|<span data-ttu-id="188a4-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-154">**TTL**</span></span>|<span data-ttu-id="188a4-155">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-155">**TTL unit**</span></span>|<span data-ttu-id="188a4-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="188a4-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="188a4-157">TXT</span><span class="sxs-lookup"><span data-stu-id="188a4-157">TXT</span></span>  <br/> |<span data-ttu-id="188a4-158">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-158">1</span></span>  <br/> |<span data-ttu-id="188a4-159">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-159">Hours</span></span>  <br/> |<span data-ttu-id="188a4-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="188a4-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="188a4-161">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="188a4-161">**Note:** This is an example.</span></span> <span data-ttu-id="188a4-162">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="188a4-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="188a4-163">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="188a4-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="188a4-165">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="188a4-166">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="188a4-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="188a4-167">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="188a4-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="188a4-168">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="188a4-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="188a4-169">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="188a4-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="188a4-170">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="188a4-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="188a4-171">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="188a4-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="188a4-172">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="188a4-p111">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="188a4-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="188a4-176">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="188a4-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="188a4-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="188a4-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="188a4-178">Para empezar, vaya a su página de dominios en Azure con [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="188a4-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="188a4-179">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="188a4-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="188a4-181">En la página **Panel** , en el área **todos los recursos** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="188a4-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="188a4-183">En la página de **configuración** de su dominio, en el área **zona DNS** , seleccione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="188a4-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="188a4-185">En el área **Agregar conjunto de registros** , en los cuadros para el nuevo conjunto de registros, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="188a4-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="188a4-186">(Elija los valores **tipo** y TTL de la **unidad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="188a4-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="188a4-187">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="188a4-187">**Name**</span></span>|<span data-ttu-id="188a4-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="188a4-188">**Type**</span></span>|<span data-ttu-id="188a4-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-189">**TTL**</span></span>|<span data-ttu-id="188a4-190">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-190">**TTL unit**</span></span>|<span data-ttu-id="188a4-191">**Preferencia**</span><span class="sxs-lookup"><span data-stu-id="188a4-191">**Preference**</span></span>|<span data-ttu-id="188a4-192">**Intercambio de correo**</span><span class="sxs-lookup"><span data-stu-id="188a4-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="188a4-193">MX</span><span class="sxs-lookup"><span data-stu-id="188a4-193">MX</span></span>  <br/> |<span data-ttu-id="188a4-194">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-194">1</span></span>  <br/> |<span data-ttu-id="188a4-195">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-195">Hours</span></span>  <br/> |<span data-ttu-id="188a4-196">10 </span><span class="sxs-lookup"><span data-stu-id="188a4-196">10</span></span>  <br/> <span data-ttu-id="188a4-197">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="188a4-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="188a4-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="188a4-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="188a4-199">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="188a4-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="188a4-200">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="188a4-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="188a4-202">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-202">Select **OK**.</span></span>
    
    ![Azure-BP-configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="188a4-204">Si hay otros registros MX enumerados en la sección **registros MX** , debe eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="188a4-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="188a4-205">En primer lugar, en el área **zona DNS** , seleccione el **conjunto de registros MX**.</span><span class="sxs-lookup"><span data-stu-id="188a4-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="188a4-207">A continuación, seleccione el registro MX que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="188a4-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="188a4-209">Seleccione el **menú contextual (...)** y, a continuación, elija **quitar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="188a4-211">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-211">Select **Save**.</span></span>
    
    ![Azure-BP-configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="188a4-213">Agregar los cuatro registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="188a4-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="188a4-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="188a4-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="188a4-215">Para empezar, vaya a su página de dominios en Azure con [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="188a4-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="188a4-216">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="188a4-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="188a4-218">En la página **Panel** , en el área **todos los recursos** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="188a4-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="188a4-220">En la página de **configuración** de su dominio, en el área **zona DNS** , seleccione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="188a4-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="188a4-222">Agregue el primero de los cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="188a4-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="188a4-223">En el área **Agregar conjunto de registros** , en los cuadros para el nuevo conjunto de registros, escriba o copie y pegue los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="188a4-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="188a4-224">(Elija los valores **tipo** y TTL de la **unidad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="188a4-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="188a4-225">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="188a4-225">**Name**</span></span>|<span data-ttu-id="188a4-226">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="188a4-226">**Type**</span></span>|<span data-ttu-id="188a4-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-227">**TTL**</span></span>|<span data-ttu-id="188a4-228">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-228">**TTL unit**</span></span>|<span data-ttu-id="188a4-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="188a4-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="188a4-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="188a4-230">autodiscover</span></span>  <br/> |<span data-ttu-id="188a4-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="188a4-231">CNAME</span></span>  <br/> |<span data-ttu-id="188a4-232">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-232">1</span></span>  <br/> |<span data-ttu-id="188a4-233">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-233">Hours</span></span>  <br/> |<span data-ttu-id="188a4-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="188a4-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="188a4-235">sip</span><span class="sxs-lookup"><span data-stu-id="188a4-235">sip</span></span>  <br/> |<span data-ttu-id="188a4-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="188a4-236">CNAME</span></span>  <br/> |<span data-ttu-id="188a4-237">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-237">1</span></span>  <br/> |<span data-ttu-id="188a4-238">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-238">Hours</span></span>  <br/> |<span data-ttu-id="188a4-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="188a4-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="188a4-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="188a4-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="188a4-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="188a4-241">CNAME</span></span>  <br/> |<span data-ttu-id="188a4-242">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-242">1</span></span>  <br/> |<span data-ttu-id="188a4-243">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-243">Hours</span></span>  <br/> |<span data-ttu-id="188a4-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="188a4-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="188a4-246">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-246">Select **OK**.</span></span>
    
    ![Azure-BP-configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="188a4-248">Agregue cada uno de los otros tres registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="188a4-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="188a4-249">En el área **zona DNS** , seleccione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="188a4-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="188a4-250">A continuación, en el conjunto de registros vacío, cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y vuelva a seleccionar **Aceptar** para completar ese registro).</span><span class="sxs-lookup"><span data-stu-id="188a4-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="188a4-251">Repita este proceso hasta que haya creado los cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="188a4-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="188a4-252">Opcional Agregue 2 registros CNAME para MDM.</span><span class="sxs-lookup"><span data-stu-id="188a4-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="188a4-253">Si tiene administración de dispositivos móviles (MDM) para Microsoft, debe crear dos registros CNAME adicionales.</span><span class="sxs-lookup"><span data-stu-id="188a4-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="188a4-254">Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="188a4-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="188a4-255">(Si no tiene MDM, puede omitir este paso).</span><span class="sxs-lookup"><span data-stu-id="188a4-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="188a4-256">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="188a4-256">**Name**</span></span>|<span data-ttu-id="188a4-257">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="188a4-257">**Type**</span></span>|<span data-ttu-id="188a4-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-258">**TTL**</span></span>|<span data-ttu-id="188a4-259">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-259">**TTL unit**</span></span>|<span data-ttu-id="188a4-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="188a4-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="188a4-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="188a4-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="188a4-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="188a4-262">CNAME</span></span>  <br/> |<span data-ttu-id="188a4-263">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-263">1</span></span>  <br/> |<span data-ttu-id="188a4-264">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-264">Hours</span></span>  <br/> |<span data-ttu-id="188a4-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="188a4-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="188a4-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="188a4-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="188a4-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="188a4-267">CNAME</span></span>  <br/> |<span data-ttu-id="188a4-268">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-268">1</span></span>  <br/> |<span data-ttu-id="188a4-269">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-269">Hours</span></span>  <br/> |<span data-ttu-id="188a4-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="188a4-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="188a4-271">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="188a4-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="188a4-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="188a4-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="188a4-273">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="188a4-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="188a4-274">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="188a4-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="188a4-275">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="188a4-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="188a4-276">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="188a4-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="188a4-277">Para empezar, vaya a su página de dominios en Azure con [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="188a4-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="188a4-278">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="188a4-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="188a4-280">En la página **Panel** , en el área **todos los recursos** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="188a4-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="188a4-282">En el área **zona DNS** , seleccione el **conjunto de registros txt**.</span><span class="sxs-lookup"><span data-stu-id="188a4-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="188a4-284">En el área **propiedades del conjunto de registros** , en los cuadros para el nuevo conjunto de registros, seleccione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="188a4-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="188a4-285">(Elija los valores **tipo** y TTL de la **unidad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="188a4-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="188a4-286">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="188a4-286">**Name**</span></span>|<span data-ttu-id="188a4-287">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="188a4-287">**Type**</span></span>|<span data-ttu-id="188a4-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-288">**TTL**</span></span>|<span data-ttu-id="188a4-289">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-289">**TTL unit**</span></span>|<span data-ttu-id="188a4-290">**Valor**</span><span class="sxs-lookup"><span data-stu-id="188a4-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="188a4-291">TXT</span><span class="sxs-lookup"><span data-stu-id="188a4-291">TXT</span></span>  <br/> |<span data-ttu-id="188a4-292">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-292">1</span></span>  <br/> |<span data-ttu-id="188a4-293">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-293">Hours</span></span>  <br/> |<span data-ttu-id="188a4-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="188a4-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="188a4-295">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="188a4-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="188a4-297">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-297">Select **Save**.</span></span>
    
    ![Azure-BP-configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="188a4-299">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="188a4-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="188a4-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="188a4-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="188a4-301">Para empezar, vaya a su página de dominios en Azure con [este vínculo](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="188a4-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="188a4-302">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="188a4-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="188a4-304">En la página **Panel** , en el área **todos los recursos** , seleccione el dominio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="188a4-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="188a4-306">En la página de **configuración** de su dominio, en el área **zona DNS** , seleccione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="188a4-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="188a4-308">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="188a4-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="188a4-309">En el área **Agregar conjunto de registros** , en los cuadros para el nuevo conjunto de registros, seleccione los valores de la primera fila en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="188a4-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="188a4-310">(Elija los valores **tipo** y TTL de la **unidad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="188a4-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="188a4-311">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="188a4-311">**Name**</span></span>|<span data-ttu-id="188a4-312">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="188a4-312">**Type**</span></span>|<span data-ttu-id="188a4-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-313">**TTL**</span></span>|<span data-ttu-id="188a4-314">**Unidad TTL**</span><span class="sxs-lookup"><span data-stu-id="188a4-314">**TTL unit**</span></span>|<span data-ttu-id="188a4-315">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="188a4-315">**Priority**</span></span>|<span data-ttu-id="188a4-316">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="188a4-316">**Weight**</span></span>|<span data-ttu-id="188a4-317">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="188a4-317">**Port**</span></span>|<span data-ttu-id="188a4-318">**Destino**</span><span class="sxs-lookup"><span data-stu-id="188a4-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="188a4-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="188a4-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="188a4-320">SRV</span><span class="sxs-lookup"><span data-stu-id="188a4-320">SRV</span></span>  <br/> |<span data-ttu-id="188a4-321">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-321">1</span></span>  <br/> |<span data-ttu-id="188a4-322">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-322">Hours</span></span>  <br/> |<span data-ttu-id="188a4-323">100</span><span class="sxs-lookup"><span data-stu-id="188a4-323">100</span></span>  <br/> |<span data-ttu-id="188a4-324">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-324">1</span></span>  <br/> |<span data-ttu-id="188a4-325">443</span><span class="sxs-lookup"><span data-stu-id="188a4-325">443</span></span>  <br/> |<span data-ttu-id="188a4-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="188a4-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="188a4-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="188a4-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="188a4-328">SRV</span><span class="sxs-lookup"><span data-stu-id="188a4-328">SRV</span></span>  <br/> |<span data-ttu-id="188a4-329">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-329">1</span></span>  <br/> |<span data-ttu-id="188a4-330">Horas</span><span class="sxs-lookup"><span data-stu-id="188a4-330">Hours</span></span>  <br/> |<span data-ttu-id="188a4-331">100</span><span class="sxs-lookup"><span data-stu-id="188a4-331">100</span></span>  <br/> |<span data-ttu-id="188a4-332">1 </span><span class="sxs-lookup"><span data-stu-id="188a4-332">1</span></span>  <br/> |<span data-ttu-id="188a4-333">5061</span><span class="sxs-lookup"><span data-stu-id="188a4-333">5061</span></span>  <br/> |<span data-ttu-id="188a4-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="188a4-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="188a4-336">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="188a4-336">Select **OK**.</span></span>
    
    ![Azure-BP-configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="188a4-338">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="188a4-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="188a4-339">En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la segunda fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="188a4-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="188a4-p120">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="188a4-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
