---
title: Habilitar análisis de uso de Microsoft 365
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtenga información sobre cómo empezar a recopilar datos para su inquilino con la aplicación de plantilla de análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: 20228b0e2070065834ce203e22af619480311367
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502954"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="58f99-103">Habilitar análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58f99-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="58f99-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="58f99-104">The admin center is changing.</span></span> <span data-ttu-id="58f99-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="58f99-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="58f99-106">El análisis de uso de Microsoft 365 todavía no está disponible para la comunidad de Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="58f99-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="58f99-107">Pasos para habilitar el análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58f99-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="58f99-108">Para empezar con los análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.</span><span class="sxs-lookup"><span data-stu-id="58f99-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="58f99-109">Obtener Power BI</span><span class="sxs-lookup"><span data-stu-id="58f99-109">Get Power BI</span></span>

<span data-ttu-id="58f99-110">Si aún no tiene Power BI, puede [registrarse en Power Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="58f99-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="58f99-111">Seleccione **probar gratis** para suscribirse a una versión de prueba o **comprar ahora** para obtener Power Bi Pro.</span><span class="sxs-lookup"><span data-stu-id="58f99-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="58f99-112">También puede expandir la sección **Productos** para comprar una versión de Power BI.</span><span class="sxs-lookup"><span data-stu-id="58f99-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="58f99-113">Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="58f99-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="58f99-114">Para obtener más información, vea [requisitos previos](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="58f99-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="58f99-115">Necesita una licencia de Power BI Pro para compartir el contenido y las personas con las que lo comparte también lo hacen, o el contenido debe estar en un área de trabajo con una [capacidad Premium](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="58f99-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="58f99-116">Habilitar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="58f99-116">Enable the template app</span></span>

<span data-ttu-id="58f99-117">Para habilitar la aplicación de plantilla, debe ser **administrador global**, **lector de informes**, administrador de **Exchange**, **Administrador de Skype empresarial**o administrador de **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="58f99-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="58f99-118">Para obtener más información, vea acerca de los [roles de administrador](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="58f99-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="58f99-119">En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.</span><span class="sxs-lookup"><span data-stu-id="58f99-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="58f99-120">En la página **uso** , busque la tarjeta de **análisis de uso de Microsoft 365** y **Seleccione introducción**.</span><span class="sxs-lookup"><span data-stu-id="58f99-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="58f99-121">En el panel de informes que se abre, establezca hacer que los **datos estén disponibles para el análisis de uso de Microsoft 365 para Power BI** **en el** \> **almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="58f99-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="58f99-122">Esto inicia el proceso de recopilación de datos y finalizará en 2 a 48 horas, según el tamaño del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="58f99-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="58f99-123">El botón **ir a Power BI** estará habilitado (no estará en gris) cuando se complete la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="58f99-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="58f99-124">Iniciar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="58f99-124">Initiate the template app</span></span>

<span data-ttu-id="58f99-125">Para iniciar la aplicación de plantilla, debe ser **administrador global**, **lector de informes**, administrador de **Exchange**, **Administrador de Skype empresarial**o administrador de **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="58f99-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="58f99-126">Copie el identificador de inquilino y seleccione **ir a Power BI**.</span><span class="sxs-lookup"><span data-stu-id="58f99-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="58f99-127">Cuando llegue a Power BI, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="58f99-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="58f99-128">Seleccione aplicaciones: >obtener aplicaciones desde el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="58f99-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="58f99-129">En la pestaña **apps** , escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione **Microsoft 365 Usage Analytics** \> **ahora**.</span><span class="sxs-lookup"><span data-stu-id="58f99-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="58f99-130">[![Seleccionar obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="58f99-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="58f99-131">Una vez instalada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58f99-131">Once the app is installed.</span></span> <span data-ttu-id="58f99-132">Haga clic en el icono para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="58f99-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="58f99-133">Haga clic en **explorar aplicación** para ver la aplicación con los datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58f99-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="58f99-134">Haga clic en **conectar** para conectar la aplicación con los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="58f99-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="58f99-135">Después de hacer clic en **conectar**, en la pantalla **conectar con el análisis de uso de Microsoft 365** , escriba el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="58f99-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="58f99-136">En la siguiente pantalla, seleccione **oAuth2** como el **método de autenticación** , \> **inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="58f99-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="58f99-137">Si elige cualquier otro método de autenticación, se producirá un error en la conexión con la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="58f99-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="58f99-139">Una vez que se crea una instancia de la aplicación de plantilla, el panel de análisis de uso de Microsoft 365 estará disponible en Power BI en la Web.</span><span class="sxs-lookup"><span data-stu-id="58f99-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="58f99-140">La carga inicial del panel tardará entre 2 y 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="58f99-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="58f99-141">Los agregados a nivel de inquilino estarán disponibles en todos los informes.</span><span class="sxs-lookup"><span data-stu-id="58f99-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="58f99-142">**Los detalles en el nivel de usuario solo estarán disponibles después del 1º o el 15 del mes del calendario después de optar**.</span><span class="sxs-lookup"><span data-stu-id="58f99-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="58f99-143">Esto afectará a todos los informes de actividad de usuario (consulte [navegación y uso de los informes en Microsoft 365 Usage Analytics](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).</span><span class="sxs-lookup"><span data-stu-id="58f99-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="58f99-144">Establecer que los datos recopilados sean anónimos</span><span class="sxs-lookup"><span data-stu-id="58f99-144">Make the collected data anonymous</span></span>

<span data-ttu-id="58f99-145">Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global.</span><span class="sxs-lookup"><span data-stu-id="58f99-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="58f99-146">Esto ocultará la información identificable como nombres de usuario, grupo y sitio en los informes y en la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="58f99-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="58f99-147">En el centro de administración, vaya a configuración **de la** \> **organización**y, en la ficha **servicios** , elija **informes**.</span><span class="sxs-lookup"><span data-stu-id="58f99-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="58f99-148">Seleccione **informes**y, a continuación, elija para **Mostrar identificadores anónimos**.</span><span class="sxs-lookup"><span data-stu-id="58f99-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="58f99-149">Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="58f99-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="58f99-150">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="58f99-150">Select **Save changes**.</span></span>
