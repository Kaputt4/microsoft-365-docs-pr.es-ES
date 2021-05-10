---
title: Solución de problemas Microsoft 365 análisis de uso
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Obtén información sobre cómo solucionar problemas con la Microsoft 365 de plantilla análisis de uso.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293740"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="9cb00-103">Solución de problemas Microsoft 365 análisis de uso</span><span class="sxs-lookup"><span data-stu-id="9cb00-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="9cb00-104">Explore la siguiente lista de mensajes de error para obtener ayuda con los problemas más comunes con Microsoft 365 análisis de uso.</span><span class="sxs-lookup"><span data-stu-id="9cb00-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="9cb00-105">No podemos procesar su solicitud.</span><span class="sxs-lookup"><span data-stu-id="9cb00-105">We are unable to process your request.</span></span> <span data-ttu-id="9cb00-106">Primero debe suscribirse a estos datos desde el centro de administración Microsoft 365 de administración</span><span class="sxs-lookup"><span data-stu-id="9cb00-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="9cb00-107">**Código de error:** 422</span><span class="sxs-lookup"><span data-stu-id="9cb00-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="9cb00-108">**Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API.</span><span class="sxs-lookup"><span data-stu-id="9cb00-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9cb00-109">**Causa:** Antes de conectarte a la aplicación, tienes que suscribirte a los datos del centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="9cb00-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="9cb00-110">Si este paso no se realiza en primer lugar, no podrás conectarte a la aplicación de plantilla, incluso si proporcionas tu identificador Microsoft 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="9cb00-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="9cb00-111">**Para corregir este error:** Para suscribirse a los datos, vaya al Centro de administración Informes de uso y busque el icono Microsoft 365 análisis de uso en \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> la página del panel principal.</span><span class="sxs-lookup"><span data-stu-id="9cb00-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="9cb00-112">Seleccione el **botón** Introducción y, a continuación, en el panel Informes que se abre, active la opción Hacer que los datos estén **disponibles** para Microsoft 365 análisis de uso para Power BI y **Guardar**. </span><span class="sxs-lookup"><span data-stu-id="9cb00-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="9cb00-113">Estamos procesando sus datos</span><span class="sxs-lookup"><span data-stu-id="9cb00-113">We are processing your data</span></span>

 <span data-ttu-id="9cb00-114">**Donde verá este mensaje:** En el **icono Microsoft 365 análisis de** uso en el panel De uso del Centro Microsoft 365 administración. </span><span class="sxs-lookup"><span data-stu-id="9cb00-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="9cb00-115">**Causa:** Cuando [optas por ver](enable-usage-analytics.md) datos en la aplicación de plantilla desde el centro de administración de Microsoft 365, el sistema Microsoft 365 empieza a generar datos de uso histórico para tu organización.</span><span class="sxs-lookup"><span data-stu-id="9cb00-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="9cb00-116">Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="9cb00-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="9cb00-117">**Para corregir esto:** Solo tenga paciencia, pero si el mensaje no cambia a **Sus** datos está listo después de 3 días, póngase en contacto Microsoft 365 soporte técnico [para empresas](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="9cb00-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="9cb00-p105">No podemos procesar su solicitud en este momento. Aún estamos preparando los datos para su organización</span><span class="sxs-lookup"><span data-stu-id="9cb00-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="9cb00-120">**Código de error:** 423</span><span class="sxs-lookup"><span data-stu-id="9cb00-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="9cb00-121">**Donde verá este mensaje:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API.</span><span class="sxs-lookup"><span data-stu-id="9cb00-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9cb00-122">**Causa:** Cuando [optas por ver](enable-usage-analytics.md) datos en la aplicación de plantilla desde el centro de administración, el sistema Microsoft 365 empieza a generar datos de uso histórico para tu organización.</span><span class="sxs-lookup"><span data-stu-id="9cb00-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="9cb00-123">Según el tamaño del espacio empresarial, este paso podría tardar entre dos horas y 48 horas.</span><span class="sxs-lookup"><span data-stu-id="9cb00-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="9cb00-124">**Para corregir esto:** Solo tenga paciencia, pero si  el mensaje no cambia a Sus datos está listo incluso 3 días desde el inicio, póngase en contacto Microsoft 365 soporte técnico para [empresas](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="9cb00-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="9cb00-125">El id. de espacio empresarial que especificó no tiene el formato correcto</span><span class="sxs-lookup"><span data-stu-id="9cb00-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="9cb00-126">**Código de error:** 400</span><span class="sxs-lookup"><span data-stu-id="9cb00-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="9cb00-127">**Donde verá este mensaje:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API.</span><span class="sxs-lookup"><span data-stu-id="9cb00-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9cb00-128">**Causa:** El identificador de inquilino es un guid y debe tener el formato de xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="9cb00-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="9cb00-129">Si escribe cualquier otra cadena en el cuadro de entrada del espacio empresarial, recibirá este error.</span><span class="sxs-lookup"><span data-stu-id="9cb00-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="9cb00-130">**Para corregir este error:** Vaya al Centro de administración Informes de uso y busque el icono Microsoft 365 análisis de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso en la página principal del panel.</span><span class="sxs-lookup"><span data-stu-id="9cb00-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="9cb00-131">El identificador de inquilino aparece en el icono.</span><span class="sxs-lookup"><span data-stu-id="9cb00-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="9cb00-132">Puedes copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarte a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cb00-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="9cb00-133">El sistema no reconoce el id. de espacio empresarial que especificó</span><span class="sxs-lookup"><span data-stu-id="9cb00-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="9cb00-134">**Código de error:** 404</span><span class="sxs-lookup"><span data-stu-id="9cb00-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="9cb00-135">**Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API.</span><span class="sxs-lookup"><span data-stu-id="9cb00-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9cb00-136">**Causa:** El identificador de inquilino que proporcionó no es válido o no existe.</span><span class="sxs-lookup"><span data-stu-id="9cb00-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="9cb00-137">**Para corregir este error:** Vaya al Centro de administración Informes de uso y busque el icono Microsoft 365 análisis de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso en la página principal del panel.</span><span class="sxs-lookup"><span data-stu-id="9cb00-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="9cb00-138">El identificador de inquilino aparece en el icono.</span><span class="sxs-lookup"><span data-stu-id="9cb00-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="9cb00-139">Puedes copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarte a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cb00-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="9cb00-140">Vuelva a escribir las credenciales para volver a iniciar sesión en Power BI</span><span class="sxs-lookup"><span data-stu-id="9cb00-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="9cb00-141">Código de error: 302</span><span class="sxs-lookup"><span data-stu-id="9cb00-141">Error Code: 302</span></span>
  
 <span data-ttu-id="9cb00-142">**Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API.</span><span class="sxs-lookup"><span data-stu-id="9cb00-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9cb00-143">**Causa:** el código de autorización produjo errores y es posible que tenga que volver a escribir sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="9cb00-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="9cb00-144">**Para solucionar este error:** cierre la sesión de Power BI y, después, vuelva a iniciarla.</span><span class="sxs-lookup"><span data-stu-id="9cb00-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="9cb00-p110">No tiene la autorización correcta para obtener acceso estos datos. Para obtener acceso a los datos desde este servicio, necesita ser administrador global o uno de los administradores del producto</span><span class="sxs-lookup"><span data-stu-id="9cb00-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="9cb00-147">**Código de error:** 403</span><span class="sxs-lookup"><span data-stu-id="9cb00-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="9cb00-148">**Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API.</span><span class="sxs-lookup"><span data-stu-id="9cb00-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9cb00-149">**Causa:** Error en el código de autorización porque el usuario que intentó conectarse a la aplicación de plantilla no tiene el nivel adecuado de autorización para acceder a estos datos.</span><span class="sxs-lookup"><span data-stu-id="9cb00-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="9cb00-150">**Para corregir este error:** Proporcione las credenciales de un usuario que sea un  administrador **global**, un administrador de **Exchange**, un administrador Skype Empresarial , un administrador **SharePoint,** un lector **global** o un lector de informes para conectarse a la aplicación de plantilla. </span><span class="sxs-lookup"><span data-stu-id="9cb00-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="9cb00-151">Consulta [Acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9cb00-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="9cb00-152">No se pudo actualizar</span><span class="sxs-lookup"><span data-stu-id="9cb00-152">Refresh failed</span></span>

 <span data-ttu-id="9cb00-153">**Donde verá este mensaje:** correo electrónico de Power BI o estado de error en el historial de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="9cb00-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="9cb00-154">**Causa:** A veces, las credenciales del usuario que se ha conectado a la aplicación de plantilla se restablecen y no se actualizan en la configuración de conexión de la aplicación de plantilla, lo que hace que el usuario vea errores de actualización.</span><span class="sxs-lookup"><span data-stu-id="9cb00-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="9cb00-155">**Para corregir este error:** En Power BI, busque el conjunto de datos correspondiente a la aplicación  de plantilla Microsoft 365 Análisis de uso, seleccione Programar actualización y proporcione sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="9cb00-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="9cb00-156">Si eso no funciona, borra la caché y vuelve a crear la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cb00-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
