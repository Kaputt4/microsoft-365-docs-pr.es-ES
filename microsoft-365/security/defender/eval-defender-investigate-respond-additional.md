---
title: Pruebe Microsoft 365 Defender de respuesta a incidentes en un entorno piloto, priorizar y administrar incidentes, configurar la investigación y respuesta automatizadas y usar la búsqueda avanzada
description: Pruebe las capacidades de respuesta a incidentes en Microsoft 365 Defender priorizar y administrar incidentes, automatizar investigaciones y usar la búsqueda avanzada en la detección de amenazas.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, laboratorio de evaluación de Microsoft 365 Defender Microsoft 365 Defender, piloto, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458594"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a><span data-ttu-id="29831-104">Pruebe Microsoft 365 Defender de respuesta a incidentes en un entorno piloto</span><span class="sxs-lookup"><span data-stu-id="29831-104">Try Microsoft 365 Defender incident response capabilities in a pilot environment</span></span>

<span data-ttu-id="29831-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="29831-105">**Applies to:**</span></span>
- <span data-ttu-id="29831-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29831-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="29831-107">Este artículo es [el paso 2 de 2](eval-defender-investigate-respond.md) en el proceso de realizar una investigación y respuesta de un incidente en Microsoft 365 Defender un entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="29831-107">This article is [Step 2 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="29831-108">Para obtener más información acerca de este proceso, vea el [artículo de introducción.](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="29831-108">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="29831-109">Una vez que haya realizado una respuesta [a incidentes para](eval-defender-investigate-respond-simulate-attack.md)un ataque simulado, estas son algunas Microsoft 365 Defender capacidades para explorar:</span><span class="sxs-lookup"><span data-stu-id="29831-109">Once you have performed an [incident response for a simulated attack](eval-defender-investigate-respond-simulate-attack.md), here are some Microsoft 365 Defender capabilities to explore:</span></span>

|<span data-ttu-id="29831-110">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="29831-110">Capability</span></span> |<span data-ttu-id="29831-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="29831-111">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="29831-112">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="29831-112">Prioritize incidents</span></span>](#prioritize-incidents) | <span data-ttu-id="29831-113">Use el filtrado y ordenación de la cola de incidentes para determinar qué incidentes se deben solucionar a continuación.</span><span class="sxs-lookup"><span data-stu-id="29831-113">Use filtering and sorting of the incidents queue to determine which incidents to address next.</span></span> |
| [<span data-ttu-id="29831-114">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="29831-114">Manage incidents</span></span>](#manage-incidents) | <span data-ttu-id="29831-115">Modifique las propiedades de incidentes para garantizar la asignación correcta, agregar etiquetas y comentarios y resolver un incidente.</span><span class="sxs-lookup"><span data-stu-id="29831-115">Modify incident properties to ensure correct assignment, add tags and comments, and to resolve an incident.</span></span> |
| [<span data-ttu-id="29831-116">Investigación y respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="29831-116">Automated investigation and response</span></span>](#examine-automated-investigation-and-response-with-the-action-center) | <span data-ttu-id="29831-117">Capacidades de investigación y respuesta automatizadas (AIR) que pueden ayudar a su equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz.</span><span class="sxs-lookup"><span data-stu-id="29831-117">Automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span> <span data-ttu-id="29831-118">El Centro de acciones es una experiencia de "panel único de cristal" para las tareas de incidentes y alertas, como la aprobación de acciones de corrección pendientes.</span><span class="sxs-lookup"><span data-stu-id="29831-118">The Action center is a "single pane of glass" experience for incident and alert tasks such as approving pending remediation actions.</span></span> |
| [<span data-ttu-id="29831-119">Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="29831-119">Advanced hunting</span></span>](#advanced-hunting) | <span data-ttu-id="29831-120">Una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar proactivamente los eventos de la red y localizar indicadores y entidades de amenazas.</span><span class="sxs-lookup"><span data-stu-id="29831-120">A query-based threat-hunting tool that lets you proactively inspect events in your network and locate threat indicators and entities.</span></span> <span data-ttu-id="29831-121">También se usa la búsqueda avanzada durante la investigación y la corrección de un incidente.</span><span class="sxs-lookup"><span data-stu-id="29831-121">You also use advanced hunting during the investigation and remediation of an incident.</span></span> |
||||

## <a name="prioritize-incidents"></a><span data-ttu-id="29831-122">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="29831-122">Prioritize incidents</span></span>

<span data-ttu-id="29831-123">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="29831-123">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="29831-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29831-124">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="29831-126">La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="29831-126">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="29831-127">Para examinar la lista de incidentes y priorizar su importancia para la asignación e investigación, puede:</span><span class="sxs-lookup"><span data-stu-id="29831-127">To examine the list of incidents and prioritize their importance for assignment and investigation, you can:</span></span> 

- <span data-ttu-id="29831-128">Configure columnas personalizables (seleccione **Elegir columnas**) para darle visibilidad a las distintas características del incidente o las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="29831-128">Configure customizable columns (select **Choose columns**) to give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="29831-129">Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.</span><span class="sxs-lookup"><span data-stu-id="29831-129">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

- <span data-ttu-id="29831-130">Use el filtrado para centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="29831-130">Use filtering to focus on a specific scenario or threat.</span></span> <span data-ttu-id="29831-131">La aplicación de filtros en la cola de incidentes puede ayudar a determinar qué incidentes requieren atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="29831-131">Applying filters on the incident queue can help determine which incidents require immediate attention.</span></span> 

<span data-ttu-id="29831-132">En la cola de incidentes predeterminada, seleccione **Filtros** para ver un panel **Filtros,** desde el que puede especificar un conjunto específico de incidentes.</span><span class="sxs-lookup"><span data-stu-id="29831-132">From the default incident queue, select **Filters** to see a **Filters** pane, from which you can specify a specific set of incidents.</span></span> <span data-ttu-id="29831-133">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="29831-133">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

<span data-ttu-id="29831-135">Para obtener más información, vea [Priorizar incidentes](incident-queue.md).</span><span class="sxs-lookup"><span data-stu-id="29831-135">For more information, see [Prioritize incidents](incident-queue.md).</span></span>

## <a name="manage-incidents"></a><span data-ttu-id="29831-136">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="29831-136">Manage incidents</span></span>

<span data-ttu-id="29831-137">Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente.</span><span class="sxs-lookup"><span data-stu-id="29831-137">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="29831-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29831-138">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Ejemplo del panel Administrar incidentes de un incidente":::

<span data-ttu-id="29831-140">Puede mostrar este panel desde el vínculo **Administrar incidentes** en:</span><span class="sxs-lookup"><span data-stu-id="29831-140">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="29831-141">Panel de propiedades de un incidente en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="29831-141">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="29831-142">**Página de** resumen de un incidente.</span><span class="sxs-lookup"><span data-stu-id="29831-142">**Summary** page of an incident.</span></span>

<span data-ttu-id="29831-143">Estas son las formas en que puede administrar sus incidentes:</span><span class="sxs-lookup"><span data-stu-id="29831-143">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="29831-144">Editar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="29831-144">Edit the incident name</span></span>

  <span data-ttu-id="29831-145">Cambie el nombre asignado de formautomática en función de los procedimientos recomendados del equipo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29831-145">Change the utomatically assigned name based on your security team best practices.</span></span>
  
- <span data-ttu-id="29831-146">Agregar etiquetas de incidente</span><span class="sxs-lookup"><span data-stu-id="29831-146">Add incident tags</span></span>

  <span data-ttu-id="29831-147">Agregue etiquetas que el equipo de seguridad usa para clasificar incidentes, que se pueden filtrar más adelante.</span><span class="sxs-lookup"><span data-stu-id="29831-147">Add tags that your security team uses to classify incidents, which can be later filtered.</span></span>
  
- <span data-ttu-id="29831-148">Asignar el incidente a usted mismo</span><span class="sxs-lookup"><span data-stu-id="29831-148">Assign the incident to yourself</span></span>

  <span data-ttu-id="29831-149">Asígnelo al nombre de la cuenta de usuario, que se puede filtrar más adelante.</span><span class="sxs-lookup"><span data-stu-id="29831-149">Assign it to your user account name, which can be later filtered.</span></span>
  
- <span data-ttu-id="29831-150">Resolver un incidente</span><span class="sxs-lookup"><span data-stu-id="29831-150">Resolve an incident</span></span>

  <span data-ttu-id="29831-151">Cierre el incidente después de que se haya corregido.</span><span class="sxs-lookup"><span data-stu-id="29831-151">Close the incident after it has been remediated.</span></span>
  
- <span data-ttu-id="29831-152">Establecer su clasificación y determinación</span><span class="sxs-lookup"><span data-stu-id="29831-152">Set its classification and determination</span></span>

  <span data-ttu-id="29831-153">Clasificar y seleccionar el tipo de amenaza al resolver un incidente.</span><span class="sxs-lookup"><span data-stu-id="29831-153">Classify and select the threat type when you resolve an incident.</span></span>
  
- <span data-ttu-id="29831-154">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="29831-154">Add comments</span></span>

  <span data-ttu-id="29831-155">Use comentarios para el progreso, las notas u otra información basada en los procedimientos recomendados del equipo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29831-155">Use comments for progress, notes, or other information based on your security team best practices.</span></span> <span data-ttu-id="29831-156">El historial de comentarios completo está disponible en la **opción Comentarios e** historial de la página de detalles de un incidente.</span><span class="sxs-lookup"><span data-stu-id="29831-156">The full comment history is available from the **Comments and history** option in the details page of an incident.</span></span>

<span data-ttu-id="29831-157">Para obtener más información, vea [Manage incidents](manage-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="29831-157">For more information, see [Manage incidents](manage-incidents.md).</span></span>

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a><span data-ttu-id="29831-158">Examinar la investigación automatizada y la respuesta con el Centro de acción</span><span class="sxs-lookup"><span data-stu-id="29831-158">Examine automated investigation and response with the Action center</span></span>

<span data-ttu-id="29831-159">En función de cómo se configuren las capacidades automatizadas de investigación y respuesta para su organización, las acciones de corrección se toman automáticamente o solo tras la aprobación del equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29831-159">Depending on how automated investigation and response capabilities are configured for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="29831-160">Todas las acciones, ya sean pendientes o completadas, se enumeran en el Centro de [acciones,](m365d-action-center.md)que enumera las acciones de corrección pendientes y completadas para los dispositivos, el contenido de colaboración & correo electrónico y las identidades en una ubicación.</span><span class="sxs-lookup"><span data-stu-id="29831-160">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md), which lists pending and completed remediation actions for your devices, email & collaboration content, and identities in one location.</span></span>

<span data-ttu-id="29831-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29831-161">Here's an example.</span></span>

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificado en Microsoft 365 Defender":::

<span data-ttu-id="29831-163">En el Centro de acciones, puede seleccionar acciones pendientes y, a continuación, aprobarlas o rechazarlas en el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="29831-163">From the Action center, you can select pending actions and then approve or reject them in the flyout pane.</span></span> <span data-ttu-id="29831-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29831-164">Here's an example.</span></span>

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Aprobar o rechazar una acción":::

<span data-ttu-id="29831-166">Aprobar (o rechazar) acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="29831-166">Approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span>

<span data-ttu-id="29831-167">Para obtener más información, vea [Automated investigation and response](m365d-autoir.md) y Action [Center](m365d-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="29831-167">For more information, see [Automated investigation and response](m365d-autoir.md) and [Action center](m365d-action-center.md).</span></span>

## <a name="advanced-hunting"></a><span data-ttu-id="29831-168">Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="29831-168">Advanced hunting</span></span>

> [!NOTE]
> <span data-ttu-id="29831-169">Antes de ayudarle a través de la simulación de búsqueda avanzada, vea el siguiente vídeo para comprender los conceptos avanzados de búsqueda, vea dónde puede encontrarlo en el portal y sepa cómo puede ayudarle en sus operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29831-169">Before we walk you through the advanced hunting simulation, watch the following video to understand advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


<span data-ttu-id="29831-170">Si la simulación de ataque de [PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) sin archivos opcional era un ataque real que ya había alcanzado la fase de acceso a credenciales, puede usar la búsqueda avanzada en cualquier momento de la investigación para buscar proactivamente en eventos y registros de la red con lo que ya sabe de las alertas generadas y las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="29831-170">If the [optional fileless PowerShell attack simulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) were a real attack that had already reached the credential access stage, you can use advanced hunting at any point in the investigation to proactively search through events and records in the network using what you already know from the generated alerts and affected entities.</span></span> <span data-ttu-id="29831-171">Por ejemplo, puede consultar cualquier conexión a la dirección IP externa en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="29831-171">For instance, you can query for any connections to the external IP address in the past 30 days.</span></span>

### <a name="hunting-environment-requirements"></a><span data-ttu-id="29831-172">Requisitos del entorno de búsqueda</span><span class="sxs-lookup"><span data-stu-id="29831-172">Hunting environment requirements</span></span>

<span data-ttu-id="29831-173">Hay un único buzón interno y un dispositivo necesarios para esta simulación.</span><span class="sxs-lookup"><span data-stu-id="29831-173">There's a single internal mailbox and device required for this simulation.</span></span> <span data-ttu-id="29831-174">También necesitará una cuenta de correo electrónico externa para enviar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="29831-174">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="29831-175">Compruebe que el espacio empresarial [ha habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span><span class="sxs-lookup"><span data-stu-id="29831-175">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="29831-176">Identificar un buzón de destino que se usará para recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="29831-176">Identify a target mailbox to be used for receiving email.</span></span>

   - <span data-ttu-id="29831-177">Microsoft Defender debe supervisar este buzón Office 365</span><span class="sxs-lookup"><span data-stu-id="29831-177">This mailbox must be monitored by Microsoft Defender for Office 365</span></span>

   - <span data-ttu-id="29831-178">El dispositivo del requisito 3 debe tener acceso a este buzón</span><span class="sxs-lookup"><span data-stu-id="29831-178">The device from requirement 3 needs to access this mailbox</span></span>

3. <span data-ttu-id="29831-179">Configurar un dispositivo de prueba:</span><span class="sxs-lookup"><span data-stu-id="29831-179">Configure a test device:</span></span>

    <span data-ttu-id="29831-180">a.</span><span class="sxs-lookup"><span data-stu-id="29831-180">a.</span></span> <span data-ttu-id="29831-181">Asegúrese de que está usando Windows 10 versión 1903 o posterior.</span><span class="sxs-lookup"><span data-stu-id="29831-181">Make sure you are using Windows 10 version 1903 or later version.</span></span>

    <span data-ttu-id="29831-182">b.</span><span class="sxs-lookup"><span data-stu-id="29831-182">b.</span></span> <span data-ttu-id="29831-183">Une el dispositivo de prueba al dominio de prueba.</span><span class="sxs-lookup"><span data-stu-id="29831-183">Join the test device to the test domain.</span></span>

    <span data-ttu-id="29831-184">c.</span><span class="sxs-lookup"><span data-stu-id="29831-184">c.</span></span> <span data-ttu-id="29831-185">[Active la Antivirus de Windows Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="29831-185">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="29831-186">Si tiene problemas para habilitar Antivirus de Windows Defender, consulte [este tema de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="29831-186">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

    <span data-ttu-id="29831-187">d.</span><span class="sxs-lookup"><span data-stu-id="29831-187">d.</span></span> <span data-ttu-id="29831-188">[Incorporación a Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="29831-188">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="29831-189">Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="29831-189">Run the simulation</span></span>

1. <span data-ttu-id="29831-190">Desde una cuenta de correo electrónico externa, envíe un correo electrónico al buzón identificado en el paso 2 de la sección de requisitos del entorno de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="29831-190">From an external email account, send an email to the mailbox identified in step 2 of the hunting environment requirements section.</span></span> <span data-ttu-id="29831-191">Incluya datos adjuntos que se permitirán a través de las directivas de filtro de correo electrónico existentes.</span><span class="sxs-lookup"><span data-stu-id="29831-191">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="29831-192">Este archivo no necesita ser malintencionado ni ejecutable.</span><span class="sxs-lookup"><span data-stu-id="29831-192">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="29831-193">Los tipos de archivo <i>sugeridos.pdf</i>, <i>.exe</i> (si está permitido) o un tipo de documento Office como un archivo de Word.</span><span class="sxs-lookup"><span data-stu-id="29831-193">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or an Office document type such as a Word file.</span></span>

2. <span data-ttu-id="29831-194">Abra el correo electrónico enviado desde el dispositivo configurado como se define en el paso 3 de la sección de requisitos del entorno de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="29831-194">Open the sent email from the device configured as defined in step 3 of the hunting environment requirements section.</span></span> <span data-ttu-id="29831-195">Abra los datos adjuntos o guarde el archivo en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29831-195">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="29831-196">Ir a buscar</span><span class="sxs-lookup"><span data-stu-id="29831-196">Go hunting</span></span>

1. <span data-ttu-id="29831-197">Abra el [portal Microsoft 365 Defender](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="29831-197">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="29831-198">En el panel de navegación, seleccione **Buscar > Búsqueda avanzada.**</span><span class="sxs-lookup"><span data-stu-id="29831-198">From the navigation pane, select **Hunting > Advanced hunting**.</span></span>

3. <span data-ttu-id="29831-199">Cree una consulta que comience recopilando eventos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="29831-199">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="29831-200">Seleccione **Consulta > Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="29831-200">Select **Query > New**.</span></span>

   1. <span data-ttu-id="29831-201">En los **grupos de** correo electrónico en **Búsqueda avanzada,** haga doble clic en **EmailEvents**.</span><span class="sxs-lookup"><span data-stu-id="29831-201">In the **Email** groups under **Advanced hunting**, double-click **EmailEvents**.</span></span> <span data-ttu-id="29831-202">Debería verlo en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="29831-202">You should see this in the query window.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="29831-203">Cambie el período de tiempo de la consulta a las últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="29831-203">Change the time frame of the query to the last 24 hours.</span></span> <span data-ttu-id="29831-204">Suponiendo que el correo electrónico que envió al realizar la simulación anterior fue en las últimas 24 horas, cambie el período de tiempo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="29831-204">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame as needed.</span></span>

   1. <span data-ttu-id="29831-205">Seleccione **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="29831-205">Select **Run query**.</span></span> <span data-ttu-id="29831-206">Es posible que tenga resultados diferentes en función del entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="29831-206">You may have differing results depending on your pilot environment.</span></span>

      > [!NOTE]
      > <span data-ttu-id="29831-207">Consulta el siguiente paso para filtrar opciones para limitar la devolución de datos.</span><span class="sxs-lookup"><span data-stu-id="29831-207">See the next step for filtering options to limit data return.</span></span>

      ![Ejemplo de los resultados avanzados de la consulta de búsqueda](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="29831-209">La búsqueda avanzada muestra los resultados de la consulta como datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="29831-209">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="29831-210">También puede optar por ver los datos en otros tipos de formato, como gráficos.</span><span class="sxs-lookup"><span data-stu-id="29831-210">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="29831-211">Vea los resultados y vea si puede identificar el correo electrónico que abrió.</span><span class="sxs-lookup"><span data-stu-id="29831-211">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="29831-212">El mensaje puede tardar hasta dos horas en aparecer en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="29831-212">It may take up to two hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="29831-213">Para restringir los resultados, puede agregar la condición **where** a la consulta para buscar solo correos electrónicos que tengan "yahoo.com" como senderMailFromDomain.</span><span class="sxs-lookup"><span data-stu-id="29831-213">To narrow down the results, you can add the **where** condition to your query to only look for emails that have "yahoo.com" as their SenderMailFromDomain.</span></span> <span data-ttu-id="29831-214">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="29831-214">Here is an example.</span></span>

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="29831-215">Haga clic en las filas resultantes de la consulta para poder inspeccionar el registro.</span><span class="sxs-lookup"><span data-stu-id="29831-215">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![Ejemplo del panel lateral del registro de inspección que se abre cuando se selecciona un resultado de búsqueda avanzada](../../media/mtp/fig21.png)

4. <span data-ttu-id="29831-217">Ahora que ha comprobado que puede ver el correo electrónico, agregue un filtro para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="29831-217">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="29831-218">Céntrate en todos los correos electrónicos con datos adjuntos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="29831-218">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="29831-219">Para esta simulación, céntrate en los correos electrónicos entrantes, no en los que se envían desde el entorno.</span><span class="sxs-lookup"><span data-stu-id="29831-219">For this simulation, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="29831-220">Quite los filtros que haya agregado para buscar el mensaje y agregar "| donde **AttachmentCount > 0** y **EmailDirection**  ==  **"Inbound""**</span><span class="sxs-lookup"><span data-stu-id="29831-220">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="29831-221">La siguiente consulta le mostrará el resultado con una lista más corta que la consulta inicial para todos los eventos de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="29831-221">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="29831-222">A continuación, incluya la información sobre los datos adjuntos (como: nombre de archivo, hashes) en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="29831-222">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="29831-223">Para ello, únase a la **tabla EmailAttachmentInfo.**</span><span class="sxs-lookup"><span data-stu-id="29831-223">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="29831-224">Los campos comunes que se usan para unirse, en este caso son **NetworkMessageId** y **RecipientObjectId**.</span><span class="sxs-lookup"><span data-stu-id="29831-224">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="29831-225">La siguiente consulta también incluye una línea adicional "| **project-rename EmailTimestamp=Timestamp**" que le ayudará a identificar qué marca de tiempo estaba relacionada con el correo electrónico y las marcas de tiempo relacionadas con las acciones de archivo que agregará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="29831-225">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="29831-226">A continuación, use el valor **SHA256** de la **tabla EmailAttachmentInfo** para buscar **DeviceFileEvents** (acciones de archivo que se han producido en el extremo) para ese hash.</span><span class="sxs-lookup"><span data-stu-id="29831-226">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="29831-227">El campo común aquí será el hash SHA256 para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="29831-227">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="29831-228">La tabla resultante ahora incluye detalles del punto de conexión (Microsoft Defender para endpoint), como el nombre del dispositivo, qué acción se hizo (en este caso, filtrada para incluir solo eventos FileCreated) y dónde se almacenaba el archivo.</span><span class="sxs-lookup"><span data-stu-id="29831-228">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="29831-229">También se incluirá el nombre de cuenta asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="29831-229">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="29831-230">Ahora ha creado una consulta que identificará todos los correos electrónicos entrantes en los que el usuario abrió o guardó los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="29831-230">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="29831-231">También puede refinar esta consulta para filtrar para dominios de remitente específicos, tamaños de archivo, tipos de archivo, entre otros.</span><span class="sxs-lookup"><span data-stu-id="29831-231">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="29831-232">Las funciones son un tipo especial de unión, lo que te permite extraer más datos de TI sobre un archivo como su prevalencia, la información del firmante y el emisor, etc. Para obtener más detalles sobre el archivo, use el enriquecimiento de la función **FileProfile():**</span><span class="sxs-lookup"><span data-stu-id="29831-232">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="29831-233">Crear una detección</span><span class="sxs-lookup"><span data-stu-id="29831-233">Create a detection</span></span>

<span data-ttu-id="29831-234">Una vez que haya creado una consulta que  identifique la información que le gustaría recibir alerta sobre si se producirían en el futuro, puede crear una detección personalizada a partir de la consulta.</span><span class="sxs-lookup"><span data-stu-id="29831-234">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="29831-235">Las detecciones personalizadas ejecutarán la consulta según la frecuencia que establezca y los resultados de las consultas crearán alertas de seguridad, en función de los activos afectados que elija.</span><span class="sxs-lookup"><span data-stu-id="29831-235">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="29831-236">Estas alertas se correlacionarán con incidentes y se pueden triager como cualquier otra alerta de seguridad generada por uno de los productos.</span><span class="sxs-lookup"><span data-stu-id="29831-236">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="29831-237">En la página de consulta, quite las líneas 7 y 8 que se agregaron en el paso 7 de las instrucciones Ir a buscar y haga clic en **Crear regla de detección.**</span><span class="sxs-lookup"><span data-stu-id="29831-237">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![Ejemplo de dónde puede hacer clic en Crear regla de detección en la página de búsqueda avanzada](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="29831-239">Si hace clic en **Crear regla de detección** y tiene errores de sintaxis en la consulta, la regla de detección no se guardará.</span><span class="sxs-lookup"><span data-stu-id="29831-239">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="29831-240">Compruebe doblemente la consulta para asegurarse de que no hay errores.</span><span class="sxs-lookup"><span data-stu-id="29831-240">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="29831-241">Rellene los campos requeridos con la información que permitirá al equipo de seguridad comprender la alerta, por qué se generó y qué acciones espera que lleve a cabo.</span><span class="sxs-lookup"><span data-stu-id="29831-241">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![Ejemplo de la página crear regla de detección donde puede definir los detalles de la alerta](../../media/mtp/fig23.png)

   <span data-ttu-id="29831-243">Asegúrese de rellenar los campos con claridad para ayudar a dar al siguiente usuario una decisión fundamentada sobre esta alerta de regla de detección</span><span class="sxs-lookup"><span data-stu-id="29831-243">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="29831-244">Seleccione las entidades que se verán afectadas en esta alerta.</span><span class="sxs-lookup"><span data-stu-id="29831-244">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="29831-245">En este caso, seleccione **Dispositivo** y **buzón**.</span><span class="sxs-lookup"><span data-stu-id="29831-245">In this case, select **Device** and **Mailbox**.</span></span>

   ![Ejemplo de la página crear regla de detección donde puede elegir los parámetros de las entidades afectadas](../../media/mtp/fig24.png)

4. <span data-ttu-id="29831-247">Determine qué acciones deben tener lugar si se desencadena la alerta.</span><span class="sxs-lookup"><span data-stu-id="29831-247">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="29831-248">En este caso, ejecute un examen antivirus, aunque se podrían realizar otras acciones.</span><span class="sxs-lookup"><span data-stu-id="29831-248">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![Ejemplo de la página crear regla de detección en la que puede ejecutar un examen antivirus cuando se desencadena una alerta para ayudar a solucionar amenazas](../../media/mtp/fig25.png)

5. <span data-ttu-id="29831-250">Seleccione el ámbito de la regla de alerta.</span><span class="sxs-lookup"><span data-stu-id="29831-250">Select the scope for the alert rule.</span></span> <span data-ttu-id="29831-251">Dado que esta consulta implica dispositivos, los grupos de dispositivos son relevantes en esta detección personalizada según el contexto de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="29831-251">Since this query involves devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="29831-252">Al crear una detección personalizada que no incluya dispositivos como entidades afectadas, el ámbito no se aplica.</span><span class="sxs-lookup"><span data-stu-id="29831-252">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![Ejemplo de la página crear regla de detección donde puede establecer el ámbito de la regla de alerta administra las expectativas de los resultados que verá](../../media/mtp/fig26.png)

   <span data-ttu-id="29831-254">Para este piloto, es posible que quieras limitar esta regla a un subconjunto de dispositivos de prueba en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="29831-254">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="29831-255">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="29831-255">Select **Create**.</span></span> <span data-ttu-id="29831-256">A continuación, **seleccione Reglas de detección personalizadas** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="29831-256">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![Ejemplo de la opción Reglas de detección personalizadas en el menú](../../media/mtp/fig27a.png)

   ![Ejemplo de la página de reglas de detección que muestra los detalles de regla y ejecución](../../media/mtp/fig27b.png)

   <span data-ttu-id="29831-259">En esta página, puede seleccionar la regla de detección, que abrirá una página de detalles.</span><span class="sxs-lookup"><span data-stu-id="29831-259">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![Ejemplo de la página de datos adjuntos de correo electrónico donde puede ver el estado de la ejecución de la regla, alertas y acciones desencadenadas, editar la detección, y así sucesivamente](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a><span data-ttu-id="29831-261">Formación de expertos sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="29831-261">Expert training on advanced hunting</span></span>

<span data-ttu-id="29831-262">**El seguimiento del adversario es** una serie de difusión por web para nuevos analistas de seguridad y expertos en amenazas.</span><span class="sxs-lookup"><span data-stu-id="29831-262">**Tracking the adversary** is a webcast series for new security analysts and seasoned threat hunters.</span></span> <span data-ttu-id="29831-263">Le guía a través de los conceptos básicos de la búsqueda avanzada hasta la creación de sus propias consultas sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="29831-263">It guides you through the basics of advanced hunting all the way to creating your own sophisticated queries.</span></span> 

<span data-ttu-id="29831-264">Consulta [Obtener formación de expertos sobre la búsqueda avanzada](advanced-hunting-expert-training.md) para empezar.</span><span class="sxs-lookup"><span data-stu-id="29831-264">See [Get expert training on advanced hunting](advanced-hunting-expert-training.md) to get started.</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="29831-265">Navegación que puede necesitar</span><span class="sxs-lookup"><span data-stu-id="29831-265">Navigation you may need</span></span>

[<span data-ttu-id="29831-266">Crear el entorno Microsoft 365 Defender evaluación</span><span class="sxs-lookup"><span data-stu-id="29831-266">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
