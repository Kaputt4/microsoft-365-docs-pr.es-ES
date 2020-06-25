---
title: Ver el uso de etiquetas con el análisis de etiquetas
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información acerca de cómo ver rápidamente las etiquetas de retención y de confidencialidad que se usan con mayor frecuencia y a qué contenido se aplican.
ms.openlocfilehash: 89ccdce54b0d7e6146260037b8dcb085631b408e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817509"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="e9081-103">Ver el uso de etiquetas con el análisis de etiquetas</span><span class="sxs-lookup"><span data-stu-id="e9081-103">View label usage with label analytics</span></span>

<span data-ttu-id="e9081-104">Después de crear sus etiquetas de retención y de confidencialidad, le interesará ver cómo se utilizan en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="e9081-104">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="e9081-105">Con el análisis de etiquetas en el Centro de cumplimiento de Microsoft 365 y el Centro de seguridad de Microsoft 365, puede ver rápidamente las etiquetas que más se usan y dónde se aplican</span><span class="sxs-lookup"><span data-stu-id="e9081-105">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="e9081-106">Por ejemplo, con el análisis de etiquetas, puede ver:</span><span class="sxs-lookup"><span data-stu-id="e9081-106">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="e9081-107">El número total de etiquetas de retención y etiquetas de confidencialidad aplicadas al contenido.</span><span class="sxs-lookup"><span data-stu-id="e9081-107">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="e9081-108">Las etiquetas principales y el número de veces que se ha aplicado cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="e9081-108">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="e9081-109">Las ubicaciones en las que se aplican las etiquetas y el número de veces en cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="e9081-109">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="e9081-110">El número de archivos y carpetas cuya etiqueta de retención se ha cambiado o eliminado.</span><span class="sxs-lookup"><span data-stu-id="e9081-110">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="e9081-111">Puede encontrar el análisis de etiquetas en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/labelanalytics) o [Centro de seguridad de Microsoft 365](https://security.microsoft.com/labelanalytics) > **Clasificación**  >  **Análisis de etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="e9081-111">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![Página de análisis de etiquetas](../media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="e9081-113">Uso de etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="e9081-113">Sensitivity label usage</span></span>

<span data-ttu-id="e9081-114">Los datos sobre el uso de las etiqueta de confidencialidad se extraen de los informes de Azure Information Protection: para obtener más información, vea [Informes centrales de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span><span class="sxs-lookup"><span data-stu-id="e9081-114">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="e9081-115">Tenga en cuenta que los informes de Azure Information Protection tienen [requisitos previos](/azure/information-protection/reports-aip#prerequisites) que también se aplican a los análisis de etiquetas en las etiquetas de confidencialidad en el Centro de seguridad de Microsoft 365 y el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9081-115">Note that the Azure Information Protection reports have [prerequisites](/azure/information-protection/reports-aip#prerequisites) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="e9081-116">Por ejemplo, necesita una suscripción de Azure que incluya Log Analytics porque estos informes son el resultado de enviar eventos de auditoría de protección de información de clientes de Azure Information Protection y escáneres a una ubicación centralizada basada en el servicio Log Analytics de Azure.</span><span class="sxs-lookup"><span data-stu-id="e9081-116">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="e9081-117">Para el uso de etiquetas de confidencialidad:</span><span class="sxs-lookup"><span data-stu-id="e9081-117">For sensitivity label usage:</span></span>

- <span data-ttu-id="e9081-118">No hay ninguna latencia en los datos.</span><span class="sxs-lookup"><span data-stu-id="e9081-118">There is no latency in the data.</span></span> <span data-ttu-id="e9081-119">Se trata de un informe en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="e9081-119">This is a real-time report.</span></span>
- <span data-ttu-id="e9081-120">Para ver la cantidad de cada etiqueta principal, seleccione el gráfico de barras y lea la información sobre herramientas que aparece.</span><span class="sxs-lookup"><span data-stu-id="e9081-120">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="e9081-121">El informe muestra dónde se aplican las etiquetas de confidencialidad por aplicación (mientras que las etiquetas de retención se muestran por ubicación).</span><span class="sxs-lookup"><span data-stu-id="e9081-121">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![Informe de uso de etiquetas de confidencialidad](../media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="e9081-123">Uso de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="e9081-123">Retention label usage</span></span>

<span data-ttu-id="e9081-124">Este informe muestra una vista rápida de cuáles son las etiquetas principales y dónde se aplican.</span><span class="sxs-lookup"><span data-stu-id="e9081-124">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="e9081-125">Para obtener más información sobre cómo se etiqueta contenido en SharePoint y OneDrive, vea [Ver la actividad de etiqueta de documentos](view-label-activity-for-documents.md).</span><span class="sxs-lookup"><span data-stu-id="e9081-125">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="e9081-126">Para el uso de etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="e9081-126">For retention label usage:</span></span>

- <span data-ttu-id="e9081-127">Los datos se agregan semanalmente, por lo que pueden tardar hasta siete días en aparecer en el informe.</span><span class="sxs-lookup"><span data-stu-id="e9081-127">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="e9081-128">Para ver la cantidad de cada etiqueta principal, seleccione el gráfico de barras y lea la información sobre herramientas que aparece.</span><span class="sxs-lookup"><span data-stu-id="e9081-128">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="e9081-129">El informe muestra dónde se aplican las etiquetas de retención por ubicación (mientras que las etiquetas de confidencialidad se muestran por aplicación).</span><span class="sxs-lookup"><span data-stu-id="e9081-129">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="e9081-130">Para las etiquetas de retención, este es un resumen de todos los datos del espacio empresarial; no se filtra para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="e9081-130">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="e9081-131">Por el contrario, el [Explorador de actividad de etiquetas](view-label-activity-for-documents.md) muestra los datos de solo los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e9081-131">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![Informe de uso de etiquetas de retención](../media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="e9081-133">Ver todo el contenido con una etiqueta de retención específica</span><span class="sxs-lookup"><span data-stu-id="e9081-133">View all content with a specific retention label</span></span>

<span data-ttu-id="e9081-134">En el informe de uso de etiquetas de retención, puede explorar rápidamente todo el contenido con esa etiqueta aplicada.</span><span class="sxs-lookup"><span data-stu-id="e9081-134">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="e9081-135">(Tenga en cuenta que estamos trabajando actualmente en esta característica, por lo que requerirá menos pasos para ver todo el contenido con la etiqueta).</span><span class="sxs-lookup"><span data-stu-id="e9081-135">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="e9081-136">Primero, elija **Ver detalles** en la parte inferior del informe.</span><span class="sxs-lookup"><span data-stu-id="e9081-136">First, choose **View Details** at the bottom of the report.</span></span>

![Opción de Ver detalles en la parte inferior del informe de uso de etiquetas de retención](../media/retention-label-usage-view-details.png)

<span data-ttu-id="e9081-138">Después elija una etiqueta de retención > **Explorar elementos** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="e9081-138">Then choose a retention label > **Explore items** in the right pane.</span></span>

![Opción Explorar los elementos en el panel derecho](../media/retention-label-usage-explore-items.png)

<span data-ttu-id="e9081-140">Para esa etiqueta, puede elegir la ficha **Actividad** para ver el número de elementos con esa etiqueta según la ubicación.</span><span class="sxs-lookup"><span data-stu-id="e9081-140">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![Ficha actividad para una etiqueta de retención](../media/retention-label-usage-activity-tab.png)

<span data-ttu-id="e9081-142">También puede elegir la ficha **Elementos con esta etiqueta**. Después, puede explorar ubicaciones específicas:</span><span class="sxs-lookup"><span data-stu-id="e9081-142">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="e9081-143">Para Exchange Online, verá una lista de buzones con el número de elementos con la etiqueta en cada buzón.</span><span class="sxs-lookup"><span data-stu-id="e9081-143">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="e9081-144">En SharePoint Online y OneDrive para la Empresa, verá una lista de colecciones de sitios y cuentas de OneDrive con el número de elementos etiquetados en cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="e9081-144">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="e9081-145">Al elegir una colección de sitios o un buzón, puede ver una lista de los elementos con esa etiqueta de retención en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="e9081-145">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![Ficha Elementos con esta etiqueta que muestra todos los elementos con esa etiqueta de retención](../media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="e9081-147">Permisos</span><span class="sxs-lookup"><span data-stu-id="e9081-147">Permissions</span></span>

<span data-ttu-id="e9081-148">Para ver el análisis de etiquetas, debe tener asignado uno de los roles siguientes de Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="e9081-148">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="e9081-149">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9081-149">Global administrator</span></span>
- <span data-ttu-id="e9081-150">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e9081-150">Compliance administrator</span></span>
- <span data-ttu-id="e9081-151">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="e9081-151">Security administrator</span></span>
- <span data-ttu-id="e9081-152">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="e9081-152">Security reader</span></span>

<span data-ttu-id="e9081-153">Además, tenga en cuenta que estos informes usan Azure Monitor para almacenar los datos en un área de trabajo de Log Analytics que pertenezca a su organización.</span><span class="sxs-lookup"><span data-stu-id="e9081-153">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="e9081-154">Por lo tanto, el usuario debería agregarse como un lector para el espacio de trabajo de supervisión de Azure que contiene los datos. Para obtener más información, vea [Permisos necesarios para los análisis de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span><span class="sxs-lookup"><span data-stu-id="e9081-154">Therefore, the user should be added as a reader to the Azure Monitoring workspace that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

