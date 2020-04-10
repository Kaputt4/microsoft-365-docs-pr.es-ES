---
title: Crear registros DNS en easyDNS para Office 365
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en easyDNS para Office 365.
ms.openlocfilehash: 9d48896de8f841863e25929a46b2f1d2e1b3ced2
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210557"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="7333f-103">Crear registros DNS en easyDNS para Office 365</span><span class="sxs-lookup"><span data-stu-id="7333f-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="7333f-104">[Consulte preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que está buscando.</span><span class="sxs-lookup"><span data-stu-id="7333f-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7333f-105">Deberá agregar todos los registros DNS siguientes al sitio web de su registrador para enrutar el correo a Office 365, usar su dominio para Teams y Skype empresarial, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="7333f-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="7333f-106">Nota: Actualmente, los registros SRV no están disponibles en todos los paquetes del servicio de easyDNS.</span><span class="sxs-lookup"><span data-stu-id="7333f-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="7333f-107">Es posible que necesite actualizar a un nivel de servicio superior con easyDNS para agregar los registros SRV necesarios para Office 365 Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="7333f-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="7333f-108">Comprobar que es el propietario del dominio con un registro TXT</span><span class="sxs-lookup"><span data-stu-id="7333f-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="7333f-109">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7333f-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7333f-110">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7333f-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7333f-111">En el encabezado **registros txt** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="7333f-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7333f-112">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="7333f-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7333f-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="7333f-113">**Host**</span></span>|<span data-ttu-id="7333f-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="7333f-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="7333f-115">MS = msXXXXXXXX (use el valor que se proporciona en la página de dominios del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="7333f-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="7333f-116">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7333f-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7333f-117">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7333f-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="7333f-118">Espere unos minutos antes de continuar, para que el registro que acaba de crear pueda propagarse a través de Internet y ser detectado por Office 365.</span><span class="sxs-lookup"><span data-stu-id="7333f-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="7333f-119">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="7333f-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="7333f-120">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="7333f-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="7333f-121">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="7333f-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="7333f-122">En la página **configuración** , seleccione **Iniciar configuración.**</span><span class="sxs-lookup"><span data-stu-id="7333f-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="7333f-123">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="7333f-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="7333f-124">Agregar un registro MX para enrutar correo electrónico a Office 365</span><span class="sxs-lookup"><span data-stu-id="7333f-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="7333f-125">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7333f-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7333f-126">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7333f-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7333f-127">En el encabezado **registros MX** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="7333f-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7333f-128">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="7333f-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7333f-129">**CORREO PARA LA ZONA**</span><span class="sxs-lookup"><span data-stu-id="7333f-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="7333f-130">**SERVIDOR DE CORREO**</span><span class="sxs-lookup"><span data-stu-id="7333f-130">**MAIL SERVER**</span></span>|<span data-ttu-id="7333f-131">**DISTINGUIR**</span><span class="sxs-lookup"><span data-stu-id="7333f-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7333f-132">\<Domain-Key\>. mail.Protection.Outlook.com (obtener el \<valor de clave\> de dominio de la página de dominios del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="7333f-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="7333f-133">comprendi</span><span class="sxs-lookup"><span data-stu-id="7333f-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="7333f-134">Si desea guardar los demás registros MX para fines de copia de seguridad, cópielos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="7333f-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="7333f-135">Antes de continuar, elimine todos los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="7333f-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="7333f-136">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7333f-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7333f-137">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7333f-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="7333f-138">Agregar los registros CNAME necesarios</span><span class="sxs-lookup"><span data-stu-id="7333f-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="7333f-139">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7333f-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7333f-140">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7333f-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7333f-141">En el encabezado **registros CNAME/alias** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="7333f-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7333f-142">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="7333f-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="7333f-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="7333f-143">**HOST**</span></span>|<span data-ttu-id="7333f-144">**Address (debe terminar con un ".")**</span><span class="sxs-lookup"><span data-stu-id="7333f-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7333f-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7333f-145">autodiscover</span></span>  <br/> |<span data-ttu-id="7333f-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7333f-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="7333f-147">sip</span><span class="sxs-lookup"><span data-stu-id="7333f-147">sip</span></span>  <br/> |<span data-ttu-id="7333f-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7333f-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7333f-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7333f-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7333f-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7333f-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7333f-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7333f-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7333f-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7333f-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="7333f-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7333f-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7333f-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7333f-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="7333f-155">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7333f-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7333f-156">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7333f-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7333f-157">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="7333f-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="7333f-158">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7333f-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7333f-159">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7333f-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7333f-160">En el encabezado **registros txt** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="7333f-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7333f-161">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="7333f-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7333f-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="7333f-162">**Host**</span></span>|<span data-ttu-id="7333f-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="7333f-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="7333f-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7333f-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="7333f-165">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7333f-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7333f-166">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7333f-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7333f-167">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="7333f-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="7333f-168">Nota: Actualmente, los registros SRV no están disponibles en easyDNS ' dominio más nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="7333f-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="7333f-169">Es posible que necesite actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV</span><span class="sxs-lookup"><span data-stu-id="7333f-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="7333f-170">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7333f-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7333f-171">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7333f-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7333f-172">En el encabezado **registros SRV** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="7333f-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7333f-173">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="7333f-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7333f-174">**SERVICIO**</span><span class="sxs-lookup"><span data-stu-id="7333f-174">**SERVICE**</span></span>|<span data-ttu-id="7333f-175">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="7333f-175">**PROTO**</span></span>|<span data-ttu-id="7333f-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="7333f-176">**HOST**</span></span>|<span data-ttu-id="7333f-177">**PRIORIDAD**</span><span class="sxs-lookup"><span data-stu-id="7333f-177">**PRI**</span></span>|<span data-ttu-id="7333f-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="7333f-178">**WGT**</span></span>|<span data-ttu-id="7333f-179">**PUERTO**</span><span class="sxs-lookup"><span data-stu-id="7333f-179">**PORT**</span></span>|<span data-ttu-id="7333f-180">**DESTINO (debe terminar con ".")**</span><span class="sxs-lookup"><span data-stu-id="7333f-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="7333f-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7333f-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7333f-182">_sip</span><span class="sxs-lookup"><span data-stu-id="7333f-182">_sip</span></span>  <br/> |<span data-ttu-id="7333f-183">TLS</span><span class="sxs-lookup"><span data-stu-id="7333f-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="7333f-184">100</span><span class="sxs-lookup"><span data-stu-id="7333f-184">100</span></span>  <br/> |<span data-ttu-id="7333f-185">1</span><span class="sxs-lookup"><span data-stu-id="7333f-185">1</span></span>  <br/> |<span data-ttu-id="7333f-186">443</span><span class="sxs-lookup"><span data-stu-id="7333f-186">443</span></span>  <br/> |<span data-ttu-id="7333f-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7333f-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7333f-188">1800</span><span class="sxs-lookup"><span data-stu-id="7333f-188">1800</span></span>  <br/> |
    |<span data-ttu-id="7333f-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7333f-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7333f-190">TCP</span><span class="sxs-lookup"><span data-stu-id="7333f-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="7333f-191">100</span><span class="sxs-lookup"><span data-stu-id="7333f-191">100</span></span>  <br/> |<span data-ttu-id="7333f-192">1</span><span class="sxs-lookup"><span data-stu-id="7333f-192">1</span></span>  <br/> |<span data-ttu-id="7333f-193">5061</span><span class="sxs-lookup"><span data-stu-id="7333f-193">5061</span></span>  <br/> |<span data-ttu-id="7333f-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7333f-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7333f-195">1800</span><span class="sxs-lookup"><span data-stu-id="7333f-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="7333f-196">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7333f-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7333f-197">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7333f-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

