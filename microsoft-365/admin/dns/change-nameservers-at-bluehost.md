---
title: Cambiar los servidores DNS para configurar Office 365 con Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Obtenga información sobre cómo configurar Office 365 para administrar los registros DNS en Bluehost. '
ms.openlocfilehash: dbd06791df2e7f8e6ca085b82dc880e9626c065c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212346"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="9ab7e-103">Cambiar los servidores DNS para configurar Office 365 con Bluehost</span><span class="sxs-lookup"><span data-stu-id="9ab7e-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="9ab7e-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9ab7e-p101">Siga estas instrucciones si quiere que Office 365 administre automáticamente los registros DNS de Office 365. (Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en Bluehost](create-dns-records-at-bluehost.md)).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9ab7e-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="9ab7e-107">Add a TXT record for verification</span></span>

<span data-ttu-id="9ab7e-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ab7e-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9ab7e-112">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9ab7e-113">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="9ab7e-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9ab7e-114">En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="9ab7e-115">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="9ab7e-116">En el área **domain_name** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="9ab7e-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9ab7e-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9ab7e-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ab7e-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-119">**Host Record**</span></span> <br/> |<span data-ttu-id="9ab7e-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-120">**TTL**</span></span> <br/> |<span data-ttu-id="9ab7e-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-121">**Type**</span></span> <br/> |<span data-ttu-id="9ab7e-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="9ab7e-123">14400</span><span class="sxs-lookup"><span data-stu-id="9ab7e-123">14400</span></span>  <br/> |<span data-ttu-id="9ab7e-124">TXT</span><span class="sxs-lookup"><span data-stu-id="9ab7e-124">TXT</span></span>  <br/> |<span data-ttu-id="9ab7e-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9ab7e-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="9ab7e-126">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-126">**Note:** This is an example.</span></span> <span data-ttu-id="9ab7e-127">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-127">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="9ab7e-128">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9ab7e-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="9ab7e-129">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="9ab7e-130">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9ab7e-131">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9ab7e-132">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9ab7e-133">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9ab7e-134">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9ab7e-135">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9ab7e-136">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9ab7e-137">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9ab7e-138">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ab7e-139">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9ab7e-140">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="9ab7e-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="9ab7e-p107">Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9ab7e-p108">Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio. Por ejemplo, todos los correos que se envíen a su dominio (como, por ejemplo, rob@ *su_dominio*  .com) comenzarán a llegar a Office 365 después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="9ab7e-146">El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="9ab7e-147">> cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="9ab7e-148">Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9ab7e-149">Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="9ab7e-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9ab7e-150">En la página **dominios** , en el área **domain_name** , active la casilla correspondiente a su dominio y, a continuación, seleccione **servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="9ab7e-152">En el área **domain_name** , seleccione **usar servidores DNS personalizados**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="9ab7e-154">Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ab7e-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="9ab7e-155">Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="9ab7e-156">Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="9ab7e-157">Si aún NO se muestran servidores DNS en la lista</span><span class="sxs-lookup"><span data-stu-id="9ab7e-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="9ab7e-158">En la sección **Usar servidores DNS personalizados**, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ab7e-159">**Primera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-159">**First empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ab7e-161">**Segunda fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="9ab7e-164">Seleccione **Agregar fila**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="9ab7e-166">En la sección **Usar servidores de nombre personalizados**, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente en la nueva fila vacía.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ab7e-167">**Tercera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ab7e-169">**Cuarta fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="9ab7e-171">Para agregar el cuarto registro de servidor de nombres, seleccione **Agregar fila** de nuevo y cree un registro con los valores de la última fila de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="9ab7e-172">Seleccione **Guardar configuración de servidor DNS**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="9ab7e-p111">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="9ab7e-176">Si ya existen servidores de nombres enumerados</span><span class="sxs-lookup"><span data-stu-id="9ab7e-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="9ab7e-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="9ab7e-178">(Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="9ab7e-179">Si la lista contiene otros servidores DNS, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="9ab7e-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="9ab7e-181">En la sección **Usar servidores DNS personalizados**, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ab7e-182">**Primera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-182">**First empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ab7e-184">**Segunda fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="9ab7e-187">Seleccione **Agregar fila**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="9ab7e-189">En la sección **Usar servidores de nombre personalizados**, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente en la nueva fila vacía.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ab7e-190">**Tercera fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ab7e-192">**Cuarta fila vacía**</span><span class="sxs-lookup"><span data-stu-id="9ab7e-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="9ab7e-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ab7e-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="9ab7e-195">Para agregar el cuarto registro de servidor de nombres, seleccione **Agregar fila** de nuevo y cree un registro con los valores de la última fila de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="9ab7e-196">Seleccione **Guardar configuración de servidor DNS**.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="9ab7e-p113">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="9ab7e-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
