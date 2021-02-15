---
title: Crear registros DNS en easyDNS para Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at easyDNS for Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656824"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="43e83-103">Crear registros DNS en easyDNS para Microsoft</span><span class="sxs-lookup"><span data-stu-id="43e83-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="43e83-104">[Consulte las preguntas más frecuentes sobre ](../setup/domains-faq.yml) dominios si no encuentra lo que está buscando.</span><span class="sxs-lookup"><span data-stu-id="43e83-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="43e83-105">Deberá agregar todos los siguientes registros DNS en el sitio web de su registrador para enrutar el correo a Microsoft, usar su dominio para Teams y Skype Empresarial, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="43e83-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="43e83-106">NOTA: Los registros SRV no están disponibles actualmente en todos los paquetes de servicio easyDNS.</span><span class="sxs-lookup"><span data-stu-id="43e83-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="43e83-107">Es posible que tenga que actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV necesarios para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="43e83-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="43e83-108">Comprobar que es el propietario del dominio con un registro TXT</span><span class="sxs-lookup"><span data-stu-id="43e83-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="43e83-109">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="43e83-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="43e83-110">En el **encabezado de todos los** dominios, seleccione **dns.**</span><span class="sxs-lookup"><span data-stu-id="43e83-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="43e83-111">En el **encabezado de registros TXT,** seleccione el botón editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="43e83-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="43e83-112">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="43e83-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="43e83-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="43e83-113">**Host**</span></span>|<span data-ttu-id="43e83-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="43e83-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="43e83-115">MS=msXXXXXXXX (Use el valor que se le proporciona en la página Dominios del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="43e83-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="43e83-116">Seleccione **SIGUIENTE**.</span><span class="sxs-lookup"><span data-stu-id="43e83-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="43e83-117">Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**.</span><span class="sxs-lookup"><span data-stu-id="43e83-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="43e83-118">Espere unos minutos antes de continuar, para que el registro que acaba de crear se propague por Internet y microsoft lo detecte.</span><span class="sxs-lookup"><span data-stu-id="43e83-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="43e83-119">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="43e83-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="43e83-120">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="43e83-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="43e83-121">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="43e83-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="43e83-122">En la **página Instalación,** seleccione **Iniciar configuración.**</span><span class="sxs-lookup"><span data-stu-id="43e83-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="43e83-123">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="43e83-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="43e83-124">Agregar un registro MX para enrutar el correo electrónico a Microsoft</span><span class="sxs-lookup"><span data-stu-id="43e83-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="43e83-125">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="43e83-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="43e83-126">En el **encabezado de todos los** dominios, seleccione **dns.**</span><span class="sxs-lookup"><span data-stu-id="43e83-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="43e83-127">En el **encabezado de registros MX,** seleccione el botón editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="43e83-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="43e83-128">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="43e83-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="43e83-129">**CORREO PARA ZONA**</span><span class="sxs-lookup"><span data-stu-id="43e83-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="43e83-130">**SERVIDOR DE CORREO**</span><span class="sxs-lookup"><span data-stu-id="43e83-130">**MAIL SERVER**</span></span>|<span data-ttu-id="43e83-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="43e83-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="43e83-132">\<domain-key\>.mail.protection.outlook.com (obtenga su \<domain-key\> valor de la página Dominios del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="43e83-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="43e83-133">0</span><span class="sxs-lookup"><span data-stu-id="43e83-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="43e83-134">Si desea guardar los demás registros MX con fines de copia de seguridad, cópielos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="43e83-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="43e83-135">Antes de seguir, quite todos los demás registros MX aquí.</span><span class="sxs-lookup"><span data-stu-id="43e83-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="43e83-136">Seleccione **SIGUIENTE**.</span><span class="sxs-lookup"><span data-stu-id="43e83-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="43e83-137">Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**.</span><span class="sxs-lookup"><span data-stu-id="43e83-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="43e83-138">Agregar los registros CNAME necesarios</span><span class="sxs-lookup"><span data-stu-id="43e83-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="43e83-139">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="43e83-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="43e83-140">En el **encabezado de todos los** dominios, seleccione **dns.**</span><span class="sxs-lookup"><span data-stu-id="43e83-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="43e83-141">En el **encabezado de registros CNAME/Alias,** seleccione el botón editar (icono llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="43e83-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="43e83-142">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="43e83-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="43e83-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="43e83-143">**HOST**</span></span>|<span data-ttu-id="43e83-144">**Dirección (debe terminar con un ".")**</span><span class="sxs-lookup"><span data-stu-id="43e83-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="43e83-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="43e83-145">autodiscover</span></span>  <br/> |<span data-ttu-id="43e83-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="43e83-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="43e83-147">sip</span><span class="sxs-lookup"><span data-stu-id="43e83-147">sip</span></span>  <br/> |<span data-ttu-id="43e83-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="43e83-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="43e83-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="43e83-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="43e83-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="43e83-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="43e83-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="43e83-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="43e83-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="43e83-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="43e83-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="43e83-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="43e83-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="43e83-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="43e83-155">Seleccione **SIGUIENTE**.</span><span class="sxs-lookup"><span data-stu-id="43e83-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="43e83-156">Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**.</span><span class="sxs-lookup"><span data-stu-id="43e83-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="43e83-157">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="43e83-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="43e83-158">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="43e83-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="43e83-159">En el **encabezado de todos los** dominios, seleccione **dns.**</span><span class="sxs-lookup"><span data-stu-id="43e83-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="43e83-160">En el **encabezado de registros TXT,** seleccione el botón editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="43e83-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="43e83-161">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="43e83-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="43e83-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="43e83-162">**Host**</span></span>|<span data-ttu-id="43e83-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="43e83-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="43e83-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="43e83-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="43e83-165">Seleccione **SIGUIENTE**.</span><span class="sxs-lookup"><span data-stu-id="43e83-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="43e83-166">Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**.</span><span class="sxs-lookup"><span data-stu-id="43e83-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="43e83-167">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="43e83-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="43e83-168">NOTA: Los registros SRV no están disponibles actualmente en el nivel de servicio Dominio más de easyDNS.</span><span class="sxs-lookup"><span data-stu-id="43e83-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="43e83-169">Es posible que deba actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV</span><span class="sxs-lookup"><span data-stu-id="43e83-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="43e83-170">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="43e83-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="43e83-171">En el **encabezado de todos los** dominios, seleccione **dns.**</span><span class="sxs-lookup"><span data-stu-id="43e83-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="43e83-172">En el encabezado **de registros SRV,** seleccione el botón editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="43e83-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="43e83-173">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="43e83-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="43e83-174">**SERVICIO**</span><span class="sxs-lookup"><span data-stu-id="43e83-174">**SERVICE**</span></span>|<span data-ttu-id="43e83-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="43e83-175">**PROTO**</span></span>|<span data-ttu-id="43e83-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="43e83-176">**HOST**</span></span>|<span data-ttu-id="43e83-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="43e83-177">**PRI**</span></span>|<span data-ttu-id="43e83-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="43e83-178">**WGT**</span></span>|<span data-ttu-id="43e83-179">**PUERTO**</span><span class="sxs-lookup"><span data-stu-id="43e83-179">**PORT**</span></span>|<span data-ttu-id="43e83-180">**TARGET(Debe terminar con un ".")**</span><span class="sxs-lookup"><span data-stu-id="43e83-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="43e83-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="43e83-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="43e83-182">_sip</span><span class="sxs-lookup"><span data-stu-id="43e83-182">_sip</span></span>  <br/> |<span data-ttu-id="43e83-183">TLS</span><span class="sxs-lookup"><span data-stu-id="43e83-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="43e83-184">100</span><span class="sxs-lookup"><span data-stu-id="43e83-184">100</span></span>  <br/> |<span data-ttu-id="43e83-185">1 </span><span class="sxs-lookup"><span data-stu-id="43e83-185">1</span></span>  <br/> |<span data-ttu-id="43e83-186">443</span><span class="sxs-lookup"><span data-stu-id="43e83-186">443</span></span>  <br/> |<span data-ttu-id="43e83-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="43e83-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="43e83-188">1800</span><span class="sxs-lookup"><span data-stu-id="43e83-188">1800</span></span>  <br/> |
    |<span data-ttu-id="43e83-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="43e83-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="43e83-190">TCP</span><span class="sxs-lookup"><span data-stu-id="43e83-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="43e83-191">100</span><span class="sxs-lookup"><span data-stu-id="43e83-191">100</span></span>  <br/> |<span data-ttu-id="43e83-192">1 </span><span class="sxs-lookup"><span data-stu-id="43e83-192">1</span></span>  <br/> |<span data-ttu-id="43e83-193">5061</span><span class="sxs-lookup"><span data-stu-id="43e83-193">5061</span></span>  <br/> |<span data-ttu-id="43e83-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="43e83-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="43e83-195">1800</span><span class="sxs-lookup"><span data-stu-id="43e83-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="43e83-196">Seleccione **SIGUIENTE**.</span><span class="sxs-lookup"><span data-stu-id="43e83-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="43e83-197">Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**.</span><span class="sxs-lookup"><span data-stu-id="43e83-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

