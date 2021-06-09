---
title: Introducción al panel de alertas de prevención de pérdida de datos
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Introducción a la definición y administración de alertas para directivas de prevención de pérdida de datos.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843871"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="1e082-103">Introducción al panel de alertas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="1e082-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="1e082-104">Las directivas de prevención de pérdida de datos (DLP) pueden realizar acciones de protección para evitar el uso compartido involuntario de elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="1e082-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="1e082-105">Cuando se hace una acción en un elemento confidencial, se le puede notificar configurando alertas para DLP.</span><span class="sxs-lookup"><span data-stu-id="1e082-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="1e082-106">En este artículo se muestra cómo definir directivas de alerta enriquecciones vinculadas a las directivas de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="1e082-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="1e082-107">Verá cómo usar el panel de administración de alertas [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) en el Centro de cumplimiento de [Microsoft 365](https://compliance.microsoft.com/) para ver alertas, eventos y metadatos asociados para infracciones de directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="1e082-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="1e082-108">Si no es nuevo en las alertas dlp, debe revisar Información sobre el panel de [alertas de](dlp-alerts-dashboard-learn.md) prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="1e082-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1e082-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="1e082-109">Before you begin</span></span>

<span data-ttu-id="1e082-110">Antes de comenzar, asegúrese de que tiene los requisitos previos necesarios:</span><span class="sxs-lookup"><span data-stu-id="1e082-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="1e082-111">Licencias para el panel de administración de alertas DLP</span><span class="sxs-lookup"><span data-stu-id="1e082-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="1e082-112">Licencias para opciones de configuración de alertas</span><span class="sxs-lookup"><span data-stu-id="1e082-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="1e082-113">Funciones</span><span class="sxs-lookup"><span data-stu-id="1e082-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="1e082-114">Licencias para el panel de administración de alertas DLP</span><span class="sxs-lookup"><span data-stu-id="1e082-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="1e082-115">Todos los inquilinos elegibles para Office 365 DLP pueden acceder al panel de administración de alertas DLP.</span><span class="sxs-lookup"><span data-stu-id="1e082-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="1e082-116">Para empezar, debes ser elegible para dlp Office 365 para Exchange Online, SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="1e082-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="1e082-117">Para obtener más información acerca de los requisitos de licencia para Office 365 DLP, vea ¿Qué licencias proporcionan los derechos para que un usuario se beneficie [del servicio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span><span class="sxs-lookup"><span data-stu-id="1e082-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="1e082-118">Los clientes que usan [DLP](endpoint-dlp-learn-about.md) de extremo que son elegibles para [Teams DLP](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y Teams de directivas DLP en el panel de administración de alertas dlp.</span><span class="sxs-lookup"><span data-stu-id="1e082-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="1e082-119">La **característica de vista previa** de contenido solo está disponible para estas licencias:</span><span class="sxs-lookup"><span data-stu-id="1e082-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="1e082-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="1e082-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="1e082-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="1e082-121">Office 365 (E5)</span></span>
- <span data-ttu-id="1e082-122">Complemento de cumplimiento avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="1e082-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="1e082-123">Microsoft 365 E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="1e082-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="1e082-124">Cumplimiento de Microsft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="1e082-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="1e082-125">Licencias para opciones de configuración de alertas</span><span class="sxs-lookup"><span data-stu-id="1e082-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="1e082-126">Configuración de alerta de evento **único:** las organizaciones que tienen una suscripción A1, F1 o G1 o una suscripción A3 o G3 solo pueden crear directivas de alerta cuando se desencadena una alerta cada vez que se produce una actividad.</span><span class="sxs-lookup"><span data-stu-id="1e082-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="1e082-127">**Configuración de alerta agregada:** para configurar directivas de alerta agregadas basadas en un umbral, debe realizar una de estas configuraciones de licencias:</span><span class="sxs-lookup"><span data-stu-id="1e082-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="1e082-128">Una suscripción A5 o G5</span><span class="sxs-lookup"><span data-stu-id="1e082-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="1e082-129">Una suscripción E1, F1 o G1 o una suscripción A3 o G3 que incluye una de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="1e082-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="1e082-130">Protección contra amenazas avanzada de Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="1e082-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="1e082-131">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1e082-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="1e082-132">Microsoft 365 de complementos de eDiscovery y Audit</span><span class="sxs-lookup"><span data-stu-id="1e082-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="1e082-133">Funciones</span><span class="sxs-lookup"><span data-stu-id="1e082-133">Roles</span></span>


<span data-ttu-id="1e082-134">Si desea ver el panel de administración de alertas DLP o editar las opciones de configuración de alertas en una directiva DLP, debe ser miembro de uno de estos grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="1e082-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="1e082-135">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1e082-135">Compliance Administrator</span></span>
- <span data-ttu-id="1e082-136">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1e082-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="1e082-137">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="1e082-137">Security Administrator</span></span>
- <span data-ttu-id="1e082-138">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="1e082-138">Security Operator</span></span>
- <span data-ttu-id="1e082-139">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="1e082-139">Security Reader</span></span>

<span data-ttu-id="1e082-140">Para obtener acceso al panel de administración de alertas DLP, necesita:</span><span class="sxs-lookup"><span data-stu-id="1e082-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="1e082-141">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="1e082-141">Manage alerts</span></span>

<span data-ttu-id="1e082-142">y cualquiera de estos dos roles:</span><span class="sxs-lookup"><span data-stu-id="1e082-142">and either of these two roles:</span></span>

- <span data-ttu-id="1e082-143">Administración de cumplimiento de DLP</span><span class="sxs-lookup"><span data-stu-id="1e082-143">DLP Compliance Management</span></span>
- <span data-ttu-id="1e082-144">View-Only de cumplimiento dlp</span><span class="sxs-lookup"><span data-stu-id="1e082-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="1e082-145">Para obtener acceso a la característica de vista previa de contenido y a las características de contexto y contenido confidencial coincidentes, debe ser miembro de:</span><span class="sxs-lookup"><span data-stu-id="1e082-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="1e082-146">Grupo de roles visor de contenido del Explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="1e082-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="1e082-147">que tiene el rol de visor de contenido de clasificación de datos asignado previamente.</span><span class="sxs-lookup"><span data-stu-id="1e082-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="1e082-148">Configuración de alerta DLP</span><span class="sxs-lookup"><span data-stu-id="1e082-148">DLP alert configuration</span></span>

<span data-ttu-id="1e082-149">Para obtener información sobre cómo configurar una alerta en la directiva DLP, vea [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span><span class="sxs-lookup"><span data-stu-id="1e082-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="1e082-150">Configuración de alerta de eventos agregados</span><span class="sxs-lookup"><span data-stu-id="1e082-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="1e082-151">Si su organización tiene licencia para [opciones de](#licensing-for-alert-configuration-options)configuración de alerta agregadas, verá estas opciones al crear o editar una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="1e082-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra las opciones de los informes de incidentes para los usuarios que son aptos para opciones de configuración de alerta agregadas." border="false":::

<span data-ttu-id="1e082-153">Esta configuración permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de la directiva o cuando se supera un umbral determinado, en función del número de actividades o en función del volumen de datos exfiltrados.</span><span class="sxs-lookup"><span data-stu-id="1e082-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="1e082-154">Configuración de alerta de evento único</span><span class="sxs-lookup"><span data-stu-id="1e082-154">Single event alert configuration</span></span>

<span data-ttu-id="1e082-155">Si su organización tiene licencia para [opciones](#licensing-for-alert-configuration-options)de configuración de alertas de un solo evento, verá estas opciones al crear o editar una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="1e082-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="1e082-156">Use esta opción para crear una alerta que se genera cada vez que se produce una coincidencia de reglas DLP.</span><span class="sxs-lookup"><span data-stu-id="1e082-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de pantalla que muestra las opciones de los informes de incidentes para los usuarios que son aptos para opciones de configuración de alertas de un solo evento." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="1e082-158">Investigar una alerta DLP</span><span class="sxs-lookup"><span data-stu-id="1e082-158">Investigate a DLP alert</span></span>

<span data-ttu-id="1e082-159">Para trabajar con el panel de administración de alertas DLP:</span><span class="sxs-lookup"><span data-stu-id="1e082-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="1e082-160">En el [centro Microsoft 365 cumplimiento,](https://www.compliance.microsoft.com)vaya a **Prevención de pérdida de datos**.</span><span class="sxs-lookup"><span data-stu-id="1e082-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="1e082-161">Seleccione la **pestaña Alertas** para ver el panel de alertas dlp.</span><span class="sxs-lookup"><span data-stu-id="1e082-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="1e082-162">Seleccione una alerta para ver los detalles:</span><span class="sxs-lookup"><span data-stu-id="1e082-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra detalles de alertas en el panel de administración de alertas DLP." border="false":::

4. <span data-ttu-id="1e082-164">Seleccione la **pestaña Eventos** para ver todos los eventos asociados con la alerta.</span><span class="sxs-lookup"><span data-stu-id="1e082-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="1e082-165">Puede elegir un evento en particular para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="1e082-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="1e082-166">Para obtener una lista de algunos de los detalles de eventos disponibles, vea [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span><span class="sxs-lookup"><span data-stu-id="1e082-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="1e082-167">Seleccione **Detalles** para abrir la **página Información** general de la alerta.</span><span class="sxs-lookup"><span data-stu-id="1e082-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="1e082-168">La página de información general proporciona un resumen:</span><span class="sxs-lookup"><span data-stu-id="1e082-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="1e082-169">de lo que ocurrió</span><span class="sxs-lookup"><span data-stu-id="1e082-169">of what happened</span></span>
    1. <span data-ttu-id="1e082-170">quién realizó las acciones que provocaron la coincidencia de la directiva</span><span class="sxs-lookup"><span data-stu-id="1e082-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="1e082-171">información sobre la directiva coincidente y más</span><span class="sxs-lookup"><span data-stu-id="1e082-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="1e082-172">Elija la **pestaña Eventos** para obtener acceso a:</span><span class="sxs-lookup"><span data-stu-id="1e082-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="1e082-173">contenido implicado</span><span class="sxs-lookup"><span data-stu-id="1e082-173">content involved</span></span>
    1. <span data-ttu-id="1e082-174">tipos de información confidencial coincidentes</span><span class="sxs-lookup"><span data-stu-id="1e082-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="1e082-175">metadatos</span><span class="sxs-lookup"><span data-stu-id="1e082-175">metadata</span></span>

7. <span data-ttu-id="1e082-176">Seleccione la **pestaña Tipos de información** confidencial para ver detalles sobre los tipos de información confidencial detectados en el contenido.</span><span class="sxs-lookup"><span data-stu-id="1e082-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="1e082-177">Los detalles incluyen confianza, recuento y el contenido que coincide con el tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="1e082-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="1e082-178">Después de investigar la alerta, vuelva a la pestaña Información general, donde puede administrar el triage y administrar la eliminación de la alerta y agregar comentarios. </span><span class="sxs-lookup"><span data-stu-id="1e082-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="1e082-179">Para ver el historial de administración de flujos de trabajo, elija **Registro de administración**.</span><span class="sxs-lookup"><span data-stu-id="1e082-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="1e082-180">Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **Resuelto**.</span><span class="sxs-lookup"><span data-stu-id="1e082-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e082-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e082-181">See also</span></span>

- [<span data-ttu-id="1e082-182">Obtenga información sobre las alertas de prevención de pérdida de datos y el panel de alertas</span><span class="sxs-lookup"><span data-stu-id="1e082-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="1e082-183">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="1e082-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)