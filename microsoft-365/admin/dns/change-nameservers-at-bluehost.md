---
title: Cambiar los servidores DNS para configurar Microsoft con Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Obtenga información sobre cómo configurar Microsoft para administrar los registros DNS en Bluehost. '
ms.openlocfilehash: 78b138a501054a573c2b36cc486dda833be7ae35
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658013"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="4782c-103">Cambiar los servidores DNS para configurar Microsoft con Bluehost</span><span class="sxs-lookup"><span data-stu-id="4782c-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="4782c-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="4782c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4782c-105">Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="4782c-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="4782c-106">(Si lo prefiere, puede [administrar todos los registros DNS en Bluehost](create-dns-records-at-bluehost.md)).</span><span class="sxs-lookup"><span data-stu-id="4782c-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4782c-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="4782c-107">Add a TXT record for verification</span></span>

<span data-ttu-id="4782c-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="4782c-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4782c-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="4782c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4782c-112">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="4782c-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="4782c-113">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="4782c-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4782c-114">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="4782c-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="4782c-115">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="4782c-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="4782c-116">En el área **domain_name** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="4782c-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="4782c-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4782c-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4782c-118">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="4782c-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4782c-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="4782c-119">**Host Record**</span></span> <br/> |<span data-ttu-id="4782c-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4782c-120">**TTL**</span></span> <br/> |<span data-ttu-id="4782c-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4782c-121">**Type**</span></span> <br/> |<span data-ttu-id="4782c-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="4782c-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="4782c-123">14400</span><span class="sxs-lookup"><span data-stu-id="4782c-123">14400</span></span>  <br/> |<span data-ttu-id="4782c-124">TXT</span><span class="sxs-lookup"><span data-stu-id="4782c-124">TXT</span></span>  <br/> |<span data-ttu-id="4782c-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4782c-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="4782c-126">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4782c-126">**Note:** This is an example.</span></span> <span data-ttu-id="4782c-127">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="4782c-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="4782c-128">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="4782c-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="4782c-129">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="4782c-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="4782c-130">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="4782c-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4782c-131">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="4782c-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="4782c-132">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="4782c-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4782c-133">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="4782c-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4782c-134">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="4782c-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4782c-135">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="4782c-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4782c-136">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="4782c-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4782c-137">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="4782c-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4782c-138">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="4782c-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4782c-139">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4782c-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4782c-140">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="4782c-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="4782c-141">Para completar la configuración de su dominio con Microsoft, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario.</span><span class="sxs-lookup"><span data-stu-id="4782c-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="4782c-142">Esto configura a Microsoft para que actualice los registros DNS del dominio por usted.</span><span class="sxs-lookup"><span data-stu-id="4782c-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="4782c-143">Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="4782c-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4782c-144">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="4782c-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4782c-145">Por ejemplo, todos los mensajes de correo electrónico enviados a su dominio (como rob@ *your_domain*  . com) empezarán a llegar a Microsoft después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="4782c-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="4782c-146">El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen.</span><span class="sxs-lookup"><span data-stu-id="4782c-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="4782c-147">> cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="4782c-148">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="4782c-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="4782c-149">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="4782c-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4782c-150">En la página **dominios** , en el área **domain_name** , active la casilla correspondiente a su dominio y, a continuación, seleccione **servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="4782c-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="4782c-152">En el área **domain_name** , seleccione **usar servidores DNS personalizados**.</span><span class="sxs-lookup"><span data-stu-id="4782c-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="4782c-154">Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4782c-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="4782c-155">Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="4782c-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="4782c-156">Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="4782c-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="4782c-157">Si aún NO se muestran servidores DNS en la lista</span><span class="sxs-lookup"><span data-stu-id="4782c-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="4782c-158">En la sección **Usar servidores DNS personalizados**, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4782c-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="4782c-159">**Primera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-159">**First empty row**</span></span> <br/> |<span data-ttu-id="4782c-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4782c-161">**Segunda fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="4782c-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="4782c-164">Seleccione **Agregar fila**.</span><span class="sxs-lookup"><span data-stu-id="4782c-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="4782c-166">En la sección **Usar servidores de nombre personalizados**, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente en la nueva fila vacía.</span><span class="sxs-lookup"><span data-stu-id="4782c-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="4782c-167">**Tercera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="4782c-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4782c-169">**Cuarta fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="4782c-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
  
4. <span data-ttu-id="4782c-171">Para agregar el cuarto registro de servidor de nombres, seleccione **Agregar fila** de nuevo y cree un registro con los valores de la última fila de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="4782c-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="4782c-172">Seleccione **Guardar configuración de servidor DNS**.</span><span class="sxs-lookup"><span data-stu-id="4782c-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="4782c-174">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="4782c-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4782c-175">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="4782c-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="4782c-176">Si ya existen servidores de nombres enumerados</span><span class="sxs-lookup"><span data-stu-id="4782c-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="4782c-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="4782c-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="4782c-178">(Es decir, elimine solo los servidores DNS actuales que  *no*  tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com** o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="4782c-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="4782c-179">Si la lista contiene otros servidores DNS, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="4782c-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="4782c-181">En la sección **Usar servidores DNS personalizados**, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4782c-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="4782c-182">**Primera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-182">**First empty row**</span></span> <br/> |<span data-ttu-id="4782c-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4782c-184">**Segunda fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="4782c-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="4782c-187">Seleccione **Agregar fila**.</span><span class="sxs-lookup"><span data-stu-id="4782c-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="4782c-189">En la sección **Usar servidores de nombre personalizados**, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente en la nueva fila vacía.</span><span class="sxs-lookup"><span data-stu-id="4782c-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="4782c-190">**Tercera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="4782c-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4782c-192">**Cuarta fila vacía**</span><span class="sxs-lookup"><span data-stu-id="4782c-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="4782c-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4782c-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="4782c-195">Para agregar el cuarto registro de servidor de nombres, seleccione **Agregar fila** de nuevo y cree un registro con los valores de la última fila de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="4782c-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="4782c-196">Seleccione **Guardar configuración de servidor DNS**.</span><span class="sxs-lookup"><span data-stu-id="4782c-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="4782c-198">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="4782c-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4782c-199">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="4782c-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
