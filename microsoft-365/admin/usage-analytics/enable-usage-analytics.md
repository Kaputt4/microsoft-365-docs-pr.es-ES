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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtén información sobre cómo empezar a recopilar datos para el inquilino mediante la aplicación de plantilla Microsoft 365 de análisis de uso en Power BI.
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394754"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="4d0e9-103">Habilitar análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d0e9-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="4d0e9-104">Microsoft 365 análisis de uso aún no está disponible para Microsoft 365 us government Community.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4d0e9-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4d0e9-105">Before you begin</span></span>

<span data-ttu-id="4d0e9-106">Para empezar con el Microsoft 365 de uso, primero debes hacer que los datos estén disponibles en el Centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>

## <a name="get-power-bi"></a><span data-ttu-id="4d0e9-107">Obtener Power BI</span><span class="sxs-lookup"><span data-stu-id="4d0e9-107">Get Power BI</span></span>

<span data-ttu-id="4d0e9-108">Si aún no tiene Power BI, puede [registrarse](https://go.microsoft.com/fwlink/p/?linkid=845347)para obtener Power BI Pro .</span><span class="sxs-lookup"><span data-stu-id="4d0e9-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="4d0e9-109">Selecciona **Probar gratis** para suscribirte a una prueba o Comprar **ahora** para obtener Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>


<span data-ttu-id="4d0e9-110">También puede expandir la sección **Productos** para comprar una versión de Power BI.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-110">You can also expand **Products** to buy a version of Power BI.</span></span>

> [!NOTE]
> <span data-ttu-id="4d0e9-111">Necesitas una licencia Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="4d0e9-112">Para obtener más información, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="4d0e9-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="4d0e9-113">Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un servicio [Power BI premium](/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="4d0e9-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span>

## <a name="enable-the-template-app"></a><span data-ttu-id="4d0e9-114">Habilitar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="4d0e9-114">Enable the template app</span></span>

<span data-ttu-id="4d0e9-115">Para habilitar la aplicación de plantilla, debes ser administrador **global.**</span><span class="sxs-lookup"><span data-stu-id="4d0e9-115">To enable the template app, you have to be a **Global administrator**.</span></span>

<span data-ttu-id="4d0e9-116">Vea [acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

1. <span data-ttu-id="4d0e9-117">En el Centro de administración, vaya a la **Configuración** configuración de la \>  \> **organización.**</span><span class="sxs-lookup"><span data-stu-id="4d0e9-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span>

2. <span data-ttu-id="4d0e9-118">En la **pestaña Servicios,** seleccione  **Informes**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-118">On the **Services** tab, select  **Reports**.</span></span>

3. <span data-ttu-id="4d0e9-119">En el panel Informes que se abre, establezca Hacer que los datos del informe estén **disponibles para** Microsoft 365 análisis de uso para Power BI en **Al** \> **guardar**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span>

<span data-ttu-id="4d0e9-120">El proceso de recopilación de datos se completará en dos o 48 horas según el tamaño del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="4d0e9-121">El **botón Ir a Power BI** se habilitará (ya no es gris) cuando se complete la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span>

## <a name="start-the-template-app"></a><span data-ttu-id="4d0e9-122">Iniciar la aplicación de plantilla</span><span class="sxs-lookup"><span data-stu-id="4d0e9-122">Start the template app</span></span>

<span data-ttu-id="4d0e9-123">Para iniciar la aplicación de plantilla, debe ser un administrador **global,** un lector de **informes,** un **Exchange,** un Skype Empresarial **o** **un SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="4d0e9-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span>

1. <span data-ttu-id="4d0e9-124">Copie el identificador de inquilino y **seleccione Ir a Power BI**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-124">Copy the tenant ID and select **Go to Power BI**.</span></span>

2. <span data-ttu-id="4d0e9-125">Cuando llegue a Power BI, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="4d0e9-126">A **continuación, selecciona Aplicaciones** Obtener -> **aplicaciones** en el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>

3. <span data-ttu-id="4d0e9-127">En la **pestaña** Aplicaciones, escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, **seleccione Microsoft 365 análisis de** uso Obtener \> **ahora**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="4d0e9-128">[![Seleccione Obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="4d0e9-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>

4. <span data-ttu-id="4d0e9-129">Una vez instalada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-129">Once the app is installed.</span></span> <span data-ttu-id="4d0e9-130">Seleccione el icono para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-130">Select the tile to open it.</span></span>

5. <span data-ttu-id="4d0e9-131">Selecciona **Explorar aplicación** para ver la aplicación con datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="4d0e9-132">Elige **Conectar** para conectar la aplicación a los datos de tu organización.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6. <span data-ttu-id="4d0e9-133">Elija **Conectar**, en la pantalla Conectar para Microsoft 365 análisis de uso, **escriba** el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>

7. <span data-ttu-id="4d0e9-134">En la siguiente pantalla, seleccione **OAuth2** como el **método de autenticación** \> **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="4d0e9-135">Si eliges cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>

    ![Elegir cuenta de Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. <span data-ttu-id="4d0e9-137">Después de crear una instancia de la aplicación de plantilla, Microsoft 365 panel de análisis de uso estará disponible en Power BI en la web.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="4d0e9-138">La carga inicial del panel llevará entre 2 y 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>

<span data-ttu-id="4d0e9-139">Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="4d0e9-140">**Los detalles de nivel de usuario solo estarán** disponibles alrededor del 5 del mes calendario siguiente después de participar en .</span><span class="sxs-lookup"><span data-stu-id="4d0e9-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="4d0e9-141">Esto afectará a todos los informes en Actividad del usuario (consulte Navegar y usar los informes en análisis de uso de [Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).</span><span class="sxs-lookup"><span data-stu-id="4d0e9-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>

## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="4d0e9-142">Establecer que los datos recopilados sean anónimos</span><span class="sxs-lookup"><span data-stu-id="4d0e9-142">Make the collected data anonymous</span></span>

<span data-ttu-id="4d0e9-143">Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="4d0e9-144">Esto ocultará información identificable como los nombres de usuario, grupo y sitio en informes y en la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>

1. <span data-ttu-id="4d0e9-145">En el Centro de  administración, vaya a la Configuración org Configuración y, en la pestaña \> Servicios, elija **Informes**. </span><span class="sxs-lookup"><span data-stu-id="4d0e9-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>

2. <span data-ttu-id="4d0e9-146">Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="4d0e9-147">Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>

3. <span data-ttu-id="4d0e9-148">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="4d0e9-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="4d0e9-149">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="4d0e9-149">Related content</span></span>

<span data-ttu-id="4d0e9-150">[Acerca del análisis de uso](usage-analytics.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4d0e9-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="4d0e9-151">[Obtener la versión más reciente de análisis de uso](get-the-latest-version-of-usage-analytics.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4d0e9-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="4d0e9-152">[Navegar y usar los informes de Microsoft 365 análisis de uso](navigate-and-utilize-reports.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4d0e9-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>