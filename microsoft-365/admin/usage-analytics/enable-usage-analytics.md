---
title: Habilitar análisis de uso de Microsoft 365
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtenga información sobre cómo empezar a recopilar datos para su inquilino mediante la aplicación de plantilla análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: 7c92fb643f9be6b5f1474f08df659c4f488a9a41
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579067"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="ebc3d-103">Habilitar análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebc3d-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="ebc3d-104">El análisis de uso de Microsoft 365 aún no está disponible para la Comunidad gubernamental de Estados Unidos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="ebc3d-105">Pasos para habilitar el análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebc3d-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="ebc3d-106">Para empezar con el análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el Centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="ebc3d-107">Obtener Power BI</span><span class="sxs-lookup"><span data-stu-id="ebc3d-107">Get Power BI</span></span>

<span data-ttu-id="ebc3d-108">Si aún no tiene Power BI, puede registrarse [en Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="ebc3d-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="ebc3d-109">Seleccione **Probar gratis** para registrarse en una versión de prueba o Comprar **ahora** para obtener Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="ebc3d-110">También puede expandir la sección **Productos** para comprar una versión de Power BI.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="ebc3d-111">Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="ebc3d-112">Para obtener más información, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="ebc3d-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="ebc3d-113">Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un servicio premium de [Power BI.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="ebc3d-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="ebc3d-114">Habilitar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="ebc3d-114">Enable the template app</span></span>

<span data-ttu-id="ebc3d-115">Para habilitar la aplicación de plantilla, debes ser administrador **global.**</span><span class="sxs-lookup"><span data-stu-id="ebc3d-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="ebc3d-116">Vea [acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="ebc3d-117">En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="ebc3d-118">En la **página Uso,** busque la tarjeta de análisis de uso de **Microsoft 365** y seleccione **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="ebc3d-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="ebc3d-119">En el panel Informes que se abre, establezca Hacer que los datos estén disponibles para el análisis de uso de **Microsoft 365** para Power BI en **Al** \> **guardar**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="ebc3d-120">El proceso de recopilación de datos se completará en dos o 48 horas según el tamaño del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="ebc3d-121">El **botón Ir a Power BI** se habilitará (ya no será gris) cuando se complete la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="ebc3d-122">Iniciar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="ebc3d-122">Start the template app</span></span>

<span data-ttu-id="ebc3d-123">Para iniciar la aplicación de plantilla, debe ser administrador **global,** lector de **informes,** administrador de **Exchange,** administrador de **Skype Empresarial** o administrador **de SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="ebc3d-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="ebc3d-124">Copie el identificador de inquilino y **seleccione Ir a Power BI**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="ebc3d-125">Cuando llegue a Power BI, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="ebc3d-126">A **continuación, selecciona Aplicaciones** Obtener -> **aplicaciones** en el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="ebc3d-127">En la **pestaña Aplicaciones,** escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione Análisis de uso de **Microsoft 365** \> **Obtenga ahora**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="ebc3d-128">[![Seleccione Obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="ebc3d-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="ebc3d-129">Una vez instalada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-129">Once the app is installed.</span></span> <span data-ttu-id="ebc3d-130">Seleccione el icono para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="ebc3d-131">Selecciona **Explorar aplicación** para ver la aplicación con datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="ebc3d-132">Elige **Conectar** para conectar la aplicación a los datos de tu organización.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="ebc3d-133">Elija **Conectar**, en la pantalla Conectarse a **Microsoft 365 usage analytics,** escriba el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="ebc3d-134">En la siguiente pantalla, seleccione **OAuth2** como el **método de autenticación** \> **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="ebc3d-135">Si eliges cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Elegir cuenta de Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="ebc3d-137">Después de crear una instancia de la aplicación de plantilla, el panel de análisis de uso de Microsoft 365 estará disponible en Power BI en la web.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="ebc3d-138">La carga inicial del panel llevará entre 2 y 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="ebc3d-139">Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="ebc3d-140">**Los detalles de nivel de usuario solo estarán** disponibles alrededor del 5 del mes calendario siguiente después de participar en .</span><span class="sxs-lookup"><span data-stu-id="ebc3d-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="ebc3d-141">Esto afectará a todos los informes de Actividad de usuario (consulte Navegar y usar los informes de análisis de uso de [Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).</span><span class="sxs-lookup"><span data-stu-id="ebc3d-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="ebc3d-142">Establecer que los datos recopilados sean anónimos</span><span class="sxs-lookup"><span data-stu-id="ebc3d-142">Make the collected data anonymous</span></span>

<span data-ttu-id="ebc3d-143">Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="ebc3d-144">Esto ocultará información identificable como los nombres de usuario, grupo y sitio en informes y en la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="ebc3d-145">En el Centro de administración, vaya a **Configuración** de la organización y, en la pestaña \> Servicios, elija  **Informes**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="ebc3d-146">Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="ebc3d-147">Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="ebc3d-148">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="ebc3d-148">Select **Save changes**.</span></span>