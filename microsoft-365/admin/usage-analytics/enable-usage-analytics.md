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
description: Obtenga información sobre cómo empezar a recopilar datos para su inquilino mediante la aplicación de plantilla análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: 1ef50380041650763961ffbe6e01c63b26800ee3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913879"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c46a2-103">Habilitar análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c46a2-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c46a2-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="c46a2-104">The admin center is changing.</span></span> <span data-ttu-id="c46a2-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c46a2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c46a2-106">El análisis de uso de Microsoft 365 aún no está disponible para la Comunidad gubernamental de Estados Unidos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c46a2-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c46a2-107">Pasos para habilitar el análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c46a2-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="c46a2-108">Para empezar con el análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el Centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.</span><span class="sxs-lookup"><span data-stu-id="c46a2-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="c46a2-109">Obtener Power BI</span><span class="sxs-lookup"><span data-stu-id="c46a2-109">Get Power BI</span></span>

<span data-ttu-id="c46a2-110">Si aún no tiene Power BI, puede registrarse [en Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="c46a2-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="c46a2-111">Seleccione **Probar gratis** para registrarse en una versión de prueba o Comprar **ahora** para obtener Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="c46a2-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="c46a2-112">También puede expandir la sección **Productos** para comprar una versión de Power BI.</span><span class="sxs-lookup"><span data-stu-id="c46a2-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="c46a2-113">Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="c46a2-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="c46a2-114">Para obtener más información, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c46a2-114">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="c46a2-115">Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un servicio premium de [Power BI.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="c46a2-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="c46a2-116">Habilitar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="c46a2-116">Enable the template app</span></span>

<span data-ttu-id="c46a2-117">Para habilitar la aplicación de plantilla, debes ser administrador **global.**</span><span class="sxs-lookup"><span data-stu-id="c46a2-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="c46a2-118">Vea [acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c46a2-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="c46a2-119">En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.</span><span class="sxs-lookup"><span data-stu-id="c46a2-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="c46a2-120">En la **página Uso,** busque la tarjeta de análisis de uso de **Microsoft 365** y seleccione **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="c46a2-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="c46a2-121">En el panel Informes que se abre, establezca Hacer que los datos estén disponibles para el análisis de uso de **Microsoft 365** para Power BI en **Al** \> **guardar**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="c46a2-122">El proceso de recopilación de datos se completará en dos o 48 horas según el tamaño del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c46a2-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="c46a2-123">El **botón Ir a Power BI** se habilitará (ya no será gris) cuando se complete la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="c46a2-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="c46a2-124">Iniciar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="c46a2-124">Start the template app</span></span>

<span data-ttu-id="c46a2-125">Para iniciar la aplicación de plantilla, debe ser administrador **global,** lector de **informes,** administrador de **Exchange,** administrador de **Skype Empresarial** o administrador **de SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="c46a2-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="c46a2-126">Copie el identificador de inquilino y **seleccione Ir a Power BI**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="c46a2-127">Cuando llegue a Power BI, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c46a2-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="c46a2-128">A **continuación, selecciona Aplicaciones** Obtener -> **aplicaciones** en el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="c46a2-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="c46a2-129">En la **pestaña Aplicaciones,** escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione Análisis de uso de **Microsoft 365** \> **Obtenga ahora**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="c46a2-130">[![Seleccione Obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="c46a2-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="c46a2-131">Una vez instalada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c46a2-131">Once the app is installed.</span></span> <span data-ttu-id="c46a2-132">Seleccione el icono para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="c46a2-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="c46a2-133">Selecciona **Explorar aplicación** para ver la aplicación con datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c46a2-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="c46a2-134">Elige **Conectar** para conectar la aplicación a los datos de tu organización.</span><span class="sxs-lookup"><span data-stu-id="c46a2-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="c46a2-135">Elija **Conectar**, en la pantalla Conectarse a **Microsoft 365 usage analytics,** escriba el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="c46a2-136">En la siguiente pantalla, seleccione **OAuth2** como el **método de autenticación** \> **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="c46a2-137">Si eliges cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="c46a2-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Elegir cuenta de Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="c46a2-139">Después de crear una instancia de la aplicación de plantilla, el panel de análisis de uso de Microsoft 365 estará disponible en Power BI en la web.</span><span class="sxs-lookup"><span data-stu-id="c46a2-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="c46a2-140">La carga inicial del panel llevará entre 2 y 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="c46a2-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="c46a2-141">Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar.</span><span class="sxs-lookup"><span data-stu-id="c46a2-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="c46a2-142">**Los detalles de nivel de usuario solo estarán** disponibles alrededor del 5 del mes calendario siguiente después de participar en .</span><span class="sxs-lookup"><span data-stu-id="c46a2-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="c46a2-143">Esto afectará a todos los informes de Actividad de usuario (consulte Navegar y usar los informes de análisis de uso de [Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).</span><span class="sxs-lookup"><span data-stu-id="c46a2-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="c46a2-144">Establecer que los datos recopilados sean anónimos</span><span class="sxs-lookup"><span data-stu-id="c46a2-144">Make the collected data anonymous</span></span>

<span data-ttu-id="c46a2-145">Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global.</span><span class="sxs-lookup"><span data-stu-id="c46a2-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="c46a2-146">Esto ocultará información identificable como los nombres de usuario, grupo y sitio en informes y en la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="c46a2-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="c46a2-147">En el Centro de administración, vaya a **Configuración** de la organización y, en la pestaña \> Servicios, elija  **Informes**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="c46a2-148">Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="c46a2-149">Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="c46a2-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="c46a2-150">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="c46a2-150">Select **Save changes**.</span></span>