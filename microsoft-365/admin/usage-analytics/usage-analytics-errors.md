---
title: Solución de problemas de análisis de uso de Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Obtenga información sobre cómo solucionar problemas relacionados con la aplicación de plantilla de análisis de uso de Microsoft 365.
ms.openlocfilehash: 7164aa246a79a8d8c5aa50d995b53b6221003c01
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212154"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="b8f7b-103">Solución de problemas de análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b8f7b-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="b8f7b-104">Explore la siguiente lista de mensajes de error para obtener ayuda con los problemas más comunes con el análisis de uso de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="b8f7b-105">No podemos procesar su solicitud.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-105">We are unable to process your request.</span></span> <span data-ttu-id="b8f7b-106">Primero tiene que suscribirse a estos datos desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b8f7b-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="b8f7b-107">**Código de error:** 422</span><span class="sxs-lookup"><span data-stu-id="b8f7b-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="b8f7b-108">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="b8f7b-109">**Causa:** Antes de poder conectarse a la aplicación, tiene que suscribirse a los datos desde el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="b8f7b-110">Si este paso no se realiza primero, no podrás conectar con la aplicación de plantilla, incluso si proporcionas tu identificador de inquilino de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="b8f7b-111">**Para solucionar este error:** Para suscribirse a los datos, vaya al \> centro de administración **informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> y busque el icono de análisis de uso de Microsoft 365 en la Página principal del panel.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="b8f7b-112">Seleccione el botón **Introducción** y, a continuación, en el panel de **informes** que se abre, active la opción hacer que los **datos estén disponibles en análisis de uso de Microsoft 365 para Power BI** en y **guarde**.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="b8f7b-113">Estamos procesando sus datos</span><span class="sxs-lookup"><span data-stu-id="b8f7b-113">We are processing your data</span></span>

 <span data-ttu-id="b8f7b-114">**Donde verá este mensaje:** En el mosaico de **análisis de uso de microsoft 365** , en el panel de **uso** del centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="b8f7b-115">**Causa:** Cuando se [opta por ver los datos en la aplicación de plantilla](enable-usage-analytics.md) desde el centro de administración de Microsoft 365, el sistema Microsoft 365 comienza a generar datos de uso históricos para la organización.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="b8f7b-116">Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="b8f7b-117">**Para solucionar esto:** Solo es paciente, pero si el mensaje no cambia a **sus datos están listos** después de tres días, [póngase en contacto con el soporte técnico de 365 para empresas de Microsoft](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="b8f7b-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="b8f7b-118">No podemos procesar su solicitud en este momento.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="b8f7b-119">Aún estamos preparando los datos para su organización</span><span class="sxs-lookup"><span data-stu-id="b8f7b-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="b8f7b-120">**Código de error:** 423</span><span class="sxs-lookup"><span data-stu-id="b8f7b-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="b8f7b-121">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="b8f7b-122">**Causa:** Cuando se [opta por ver los datos en la aplicación de plantilla](enable-usage-analytics.md) desde el centro de administración, el sistema Microsoft 365 comienza a generar datos de uso históricos para la organización.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="b8f7b-123">Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="b8f7b-124">**Para solucionar esto:** Solo es paciente, pero si el mensaje no cambia a **sus datos está listo** incluso durante 3 días desde el inicio, [póngase en contacto con el soporte técnico de Microsoft 365 para empresas](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="b8f7b-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="b8f7b-125">El id. de espacio empresarial que especificó no tiene el formato correcto</span><span class="sxs-lookup"><span data-stu-id="b8f7b-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="b8f7b-126">**Código de error:** 400</span><span class="sxs-lookup"><span data-stu-id="b8f7b-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="b8f7b-127">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="b8f7b-p107">**Causa:** el id. de espacio empresarial es un GUID y necesita estar en el formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Si escribe cualquier otra cadena en el cuadro de entrada del espacio empresarial, obtendrá este error.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="b8f7b-130">**Para solucionar este error:** \> Vaya al centro de administración de **informes** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> y busque el icono de análisis de uso de Microsoft 365 en la página del panel principal.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="b8f7b-131">El identificador de inquilino aparece en el icono.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="b8f7b-132">Puede copiarla desde aquí y pegarla en el cuadro de diálogo para conectarse a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="b8f7b-133">El sistema no reconoce el id. de espacio empresarial que especificó</span><span class="sxs-lookup"><span data-stu-id="b8f7b-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="b8f7b-134">**Código de error:** 404</span><span class="sxs-lookup"><span data-stu-id="b8f7b-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="b8f7b-135">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="b8f7b-136">**Causa:** el id. de espacio empresarial que especificó no es válido o no existe.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="b8f7b-137">**Para solucionar este error:** \> Vaya al centro de administración de **informes** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> y busque el icono de análisis de uso de Microsoft 365 en la página del panel principal.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="b8f7b-138">El identificador de inquilino aparece en el icono.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="b8f7b-139">Puede copiarla desde aquí y pegarla en el cuadro de diálogo para conectarse a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="b8f7b-140">Vuelva a escribir las credenciales para volver a iniciar sesión en Power BI</span><span class="sxs-lookup"><span data-stu-id="b8f7b-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="b8f7b-141">Código de error: 302</span><span class="sxs-lookup"><span data-stu-id="b8f7b-141">Error Code: 302</span></span>
  
 <span data-ttu-id="b8f7b-142">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="b8f7b-143">**Causa:** el código de autorización produjo errores y es posible que tenga que volver a escribir sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="b8f7b-144">**Para solucionar este error:** cierre la sesión de Power BI y, después, vuelva a iniciarla.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="b8f7b-145">No tiene la autorización correcta para obtener acceso estos datos.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="b8f7b-146">Para obtener acceso a los datos desde este servicio, necesita ser administrador global o uno de los administradores del producto</span><span class="sxs-lookup"><span data-stu-id="b8f7b-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="b8f7b-147">**Código de error:** 403</span><span class="sxs-lookup"><span data-stu-id="b8f7b-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="b8f7b-148">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="b8f7b-149">**Causa:** El código de autorización falló porque el usuario que intentó conectarse a la aplicación de plantilla no tiene el nivel correcto de autorización para obtener acceso a estos datos.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="b8f7b-150">**Para solucionar este error:** Proporcione las credenciales de un usuario que sea un **administrador global**, el administrador de **Exchange**, el **Administrador de Skype empresarial**, el **Administrador de SharePoint**, el lector **global** o el **lector de informes** para conectarse a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="b8f7b-151">Para obtener más información, vea acerca de los [roles de administrador](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="b8f7b-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="b8f7b-152">No se pudo actualizar</span><span class="sxs-lookup"><span data-stu-id="b8f7b-152">Refresh failed</span></span>

 <span data-ttu-id="b8f7b-153">**Donde verá este mensaje:** correo electrónico de Power BI o estado de error en el historial de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="b8f7b-154">**Causa:** A veces, las credenciales del usuario que se conectó a la aplicación de plantilla se restablecen y no se actualizan en la configuración de conexión de la aplicación de plantilla, lo que hace que el usuario vea errores de actualización.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="b8f7b-155">**Para solucionar este error:** En Power BI, busque el conjunto de aplicaciones correspondiente a la aplicación de plantilla de análisis de uso de Microsoft 365, seleccione **programar actualización** y proporcione sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="b8f7b-156">Si esto no funciona, borra la memoria caché y vuelve a crear la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
