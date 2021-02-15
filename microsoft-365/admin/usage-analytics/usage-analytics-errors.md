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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Obtenga información sobre cómo solucionar problemas con la aplicación de plantilla análisis de uso de Microsoft 365.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841440"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="01150-103">Solución de problemas de análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01150-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="01150-104">Explore la siguiente lista de mensajes de error para obtener ayuda con los problemas más comunes con el análisis de uso de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="01150-105">No podemos procesar su solicitud.</span><span class="sxs-lookup"><span data-stu-id="01150-105">We are unable to process your request.</span></span> <span data-ttu-id="01150-106">Primero debe suscribirse a estos datos desde el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01150-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="01150-107">**Código de error:** 422</span><span class="sxs-lookup"><span data-stu-id="01150-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="01150-108">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla análisis de uso de Microsoft 365 o cuando llama directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="01150-109">**Causa:** Para poder conectarse a la aplicación, debe suscribirse a los datos desde el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="01150-110">Si este paso no se realiza primero, no podrá conectarse a la aplicación de plantilla, incluso si proporciona su id. de inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="01150-111">**Para corregir este error:** Para suscribirse a los datos, vaya al Centro de administración Informes de uso y busque el icono de análisis de uso de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 en la página del panel principal.</span><span class="sxs-lookup"><span data-stu-id="01150-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="01150-112">Seleccione el **botón** Introducción y, a continuación, en el panel Informes que se abre, active la opción Hacer que los datos estén disponibles para el análisis de uso de **Microsoft 365** para Power BI **y** guarde . </span><span class="sxs-lookup"><span data-stu-id="01150-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="01150-113">Estamos procesando sus datos</span><span class="sxs-lookup"><span data-stu-id="01150-113">We are processing your data</span></span>

 <span data-ttu-id="01150-114">**Donde verá este mensaje:** En el icono de análisis de uso de **Microsoft 365** en **el** panel de uso del Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="01150-115">**Causa:** Cuando [opta](enable-usage-analytics.md) por ver datos en la aplicación de plantilla desde el Centro de administración de Microsoft 365, el sistema de Microsoft 365 empieza a generar datos de uso históricos para su organización.</span><span class="sxs-lookup"><span data-stu-id="01150-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="01150-116">Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="01150-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="01150-117">**Para corregir esto:** Tenga paciencia, pero si el  mensaje no cambia a Sus datos está listo después de 3 días, póngase en contacto con el soporte técnico de [Microsoft 365 para empresas.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="01150-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="01150-118">No podemos procesar su solicitud en este momento.</span><span class="sxs-lookup"><span data-stu-id="01150-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="01150-119">Aún estamos preparando los datos para su organización</span><span class="sxs-lookup"><span data-stu-id="01150-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="01150-120">**Código de error:** 423</span><span class="sxs-lookup"><span data-stu-id="01150-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="01150-121">**Donde verá este mensaje:** En Power BI, cuando se conecta a la aplicación de plantilla de Análisis de uso de Microsoft 365 o cuando llama directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="01150-122">**Causa:** Cuando [opta por ver](enable-usage-analytics.md) datos en la aplicación de plantilla desde el centro de administración, el sistema de Microsoft 365 empieza a generar datos de uso históricos para su organización.</span><span class="sxs-lookup"><span data-stu-id="01150-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="01150-123">Según el tamaño del espacio empresarial, este paso puede tardar entre dos horas y 48 horas.</span><span class="sxs-lookup"><span data-stu-id="01150-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="01150-124">**Para corregir esto:** Tenga paciencia, pero si el  mensaje no cambia a Sus datos está listo incluso 3 días después del inicio, póngase en contacto con el soporte técnico de [Microsoft 365 para empresas.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="01150-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="01150-125">El id. de espacio empresarial que especificó no tiene el formato correcto</span><span class="sxs-lookup"><span data-stu-id="01150-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="01150-126">**Código de error:** 400</span><span class="sxs-lookup"><span data-stu-id="01150-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="01150-127">**Donde verá este mensaje:** En Power BI, cuando se conecta a la aplicación de plantilla de Análisis de uso de Microsoft 365 o cuando llama directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="01150-128">**Causa:** El id. de inquilino es un guid y debe tener el formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="01150-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="01150-129">Si escribe cualquier otra cadena en el cuadro de entrada del espacio empresarial, recibirá este error.</span><span class="sxs-lookup"><span data-stu-id="01150-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="01150-130">**Para corregir este error:** Vaya al Centro de administración Informes de uso y busque el icono de análisis de uso de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 en la página del panel principal.</span><span class="sxs-lookup"><span data-stu-id="01150-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="01150-131">El id. de inquilino aparece en el icono.</span><span class="sxs-lookup"><span data-stu-id="01150-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="01150-132">Puedes copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarte a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="01150-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="01150-133">El sistema no reconoce el id. de espacio empresarial que especificó</span><span class="sxs-lookup"><span data-stu-id="01150-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="01150-134">**Código de error:** 404</span><span class="sxs-lookup"><span data-stu-id="01150-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="01150-135">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla análisis de uso de Microsoft 365 o cuando llama directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="01150-136">**Causa:** El id. de inquilino que proporcionó no es válido o no existe.</span><span class="sxs-lookup"><span data-stu-id="01150-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="01150-137">**Para corregir este error:** Vaya al Centro de administración Informes de uso y busque el icono de análisis de uso de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 en la página del panel principal.</span><span class="sxs-lookup"><span data-stu-id="01150-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="01150-138">El id. de inquilino aparece en el icono.</span><span class="sxs-lookup"><span data-stu-id="01150-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="01150-139">Puedes copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarte a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="01150-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="01150-140">Vuelva a escribir las credenciales para volver a iniciar sesión en Power BI</span><span class="sxs-lookup"><span data-stu-id="01150-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="01150-141">Código de error: 302</span><span class="sxs-lookup"><span data-stu-id="01150-141">Error Code: 302</span></span>
  
 <span data-ttu-id="01150-142">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla análisis de uso de Microsoft 365 o cuando llama directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="01150-143">**Causa:** el código de autorización produjo errores y es posible que tenga que volver a escribir sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="01150-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="01150-144">**Para solucionar este error:** cierre la sesión de Power BI y, después, vuelva a iniciarla.</span><span class="sxs-lookup"><span data-stu-id="01150-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="01150-145">No tiene la autorización correcta para obtener acceso estos datos.</span><span class="sxs-lookup"><span data-stu-id="01150-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="01150-146">Para obtener acceso a los datos desde este servicio, necesita ser administrador global o uno de los administradores del producto</span><span class="sxs-lookup"><span data-stu-id="01150-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="01150-147">**Código de error:** 403</span><span class="sxs-lookup"><span data-stu-id="01150-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="01150-148">**Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla análisis de uso de Microsoft 365 o cuando llama directamente a las API de informes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01150-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="01150-149">**Causa:** Error en el código de autorización porque el usuario que intentó conectarse a la aplicación de plantilla no tiene el nivel correcto de autorización para acceder a estos datos.</span><span class="sxs-lookup"><span data-stu-id="01150-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="01150-150">**Para corregir este error:** Proporcione las credenciales de un usuario que sea administrador  **global,** administrador de **Exchange,** administrador de **Skype** Empresarial, administrador de **SharePoint,** lector **global** o lector de informes para conectarse a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="01150-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="01150-151">Consulta [Acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="01150-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="01150-152">No se pudo actualizar</span><span class="sxs-lookup"><span data-stu-id="01150-152">Refresh failed</span></span>

 <span data-ttu-id="01150-153">**Donde verá este mensaje:** correo electrónico de Power BI o estado de error en el historial de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="01150-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="01150-154">**Causa:** A veces, las credenciales del usuario que se conectó a la aplicación de plantilla se restablecen y no se actualizan en la configuración de conexión de la aplicación de plantilla, lo que hace que el usuario vea errores de actualización.</span><span class="sxs-lookup"><span data-stu-id="01150-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="01150-155">**Para corregir este error:** En Power BI, busque el conjunto de datos correspondiente a  la aplicación de plantilla análisis de uso de Microsoft 365, seleccione programar la actualización y proporcione sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="01150-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="01150-156">Si eso no funciona, borra la memoria caché y vuelve a crear la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="01150-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
