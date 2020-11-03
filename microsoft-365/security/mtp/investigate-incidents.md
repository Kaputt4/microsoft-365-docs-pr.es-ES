---
title: Investigar incidentes en Microsoft 365 defender
description: Analizar incidentes relacionados con dispositivos, usuarios y buzones de correo.
keywords: incidente, incidentes, equipos, dispositivos, usuarios, identidades, correo, correo electrónico, buzón, investigación, gráfico, evidencia
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846753"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e70d4-104">Investigar incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e70d4-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e70d4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e70d4-105">**Applies to:**</span></span>

- <span data-ttu-id="e70d4-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e70d4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e70d4-107">Microsoft 365 defender agrega todas las alertas, los activos, las investigaciones y las evidencias relacionadas desde los dispositivos, usuarios y buzones de correo para ofrecer una visión completa de la amplitud de un ataque.</span><span class="sxs-lookup"><span data-stu-id="e70d4-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="e70d4-108">Investigue las alertas que afectan a la red, entienda lo que significa y intercale la evidencia asociada con los incidentes para que pueda diseñar un plan de corrección eficaz.</span><span class="sxs-lookup"><span data-stu-id="e70d4-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="e70d4-109">Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="e70d4-109">Investigate an incident</span></span>

1. <span data-ttu-id="e70d4-110">Seleccione un incidente en la cola incidentes.</span><span class="sxs-lookup"><span data-stu-id="e70d4-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="e70d4-111">Se abre un panel lateral que ofrece una vista previa de información importante, como el estado, la gravedad, las categorías y las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="e70d4-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Imagen del panel lateral del incidente](../../media/incident-side-panel.png)

2. <span data-ttu-id="e70d4-113">Seleccione **abrir página de incidente**.</span><span class="sxs-lookup"><span data-stu-id="e70d4-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="e70d4-114">Se abrirá la página incidente, en la que encontrará más información sobre incidentes, comentarios y acciones, pestañas (información general, alertas, dispositivos, usuarios, investigaciones, evidencia).</span><span class="sxs-lookup"><span data-stu-id="e70d4-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="e70d4-115">Revise las alertas, los dispositivos, los usuarios y otras entidades relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="e70d4-116">Información general del incidente</span><span class="sxs-lookup"><span data-stu-id="e70d4-116">Incident overview</span></span>

<span data-ttu-id="e70d4-117">En la página de información general encontrará un resumen de las instantáneas en las principales cosas que debe tener en cuenta al incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Imagen de la página información general de incidentes](../../media/incidents-overview.png)

<span data-ttu-id="e70d4-119">Las categorías de ataque le proporcionan una vista visual y numérica de la evolución del ataque en la cadena de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e70d4-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="e70d4-120">Como con otros productos de seguridad de Microsoft, Microsoft 365 defender está alineado con el marco [Mitre ATT&CK &trade; ](https://attack.mitre.org/) .</span><span class="sxs-lookup"><span data-stu-id="e70d4-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="e70d4-121">La sección de ámbito ofrece una lista de los activos que se han visto afectados y que forman parte de este incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="e70d4-122">Si hay información específica sobre este activo, como el nivel de riesgo, la prioridad de investigación, así como cualquier etiqueta en los activos, esto también se mostrará en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e70d4-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="e70d4-123">La escala de tiempo de las alertas proporciona una vista rápida al orden cronológico en el que se han producido las alertas, así como los motivos por los que estos avisos se relacionan con este incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="e70d4-124">Por último, la sección de evidencia ofrece un resumen de cuántos artefactos diferentes se incluyeron en el incidente y su estado de corrección, por lo que puede identificar de inmediato si se necesita alguna acción al final.</span><span class="sxs-lookup"><span data-stu-id="e70d4-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="e70d4-125">Esta descripción general puede ayudar en la clasificación inicial del incidente al proporcionar información sobre las principales características del incidente que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="e70d4-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="e70d4-126">Alertas</span><span class="sxs-lookup"><span data-stu-id="e70d4-126">Alerts</span></span>

<span data-ttu-id="e70d4-127">Puede ver todas las alertas relacionadas con el incidente y otra información sobre ellos, como la gravedad, las entidades involucradas en la alerta, el origen de las alertas (Microsoft defender for Identity, Microsoft defender for Endpoint, Microsoft defender para Office 365) y el motivo por el que se vincularon entre sí.</span><span class="sxs-lookup"><span data-stu-id="e70d4-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Imagen de la página de alertas de incidente](../../media/incident-alerts.png)

<span data-ttu-id="e70d4-129">De forma predeterminada, los avisos se ordenan cronológicamente, para que pueda ver en primer lugar cómo se ha producido el ataque a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="e70d4-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="e70d4-130">Al hacer clic en cada alerta le conducirá a la página de alerta relevante donde puede realizar una investigación exhaustiva de esa alerta.</span><span class="sxs-lookup"><span data-stu-id="e70d4-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="e70d4-131">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="e70d4-131">Devices</span></span>

<span data-ttu-id="e70d4-132">En la pestaña dispositivos se muestran todos los dispositivos en los que se ven las alertas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="e70d4-133">Al hacer clic en el nombre del equipo en el que se realizó el ataque, es dirigido a la página de su equipo, donde puede ver las alertas que se activaron y los eventos relacionados que se proporcionan para facilitar la investigación.</span><span class="sxs-lookup"><span data-stu-id="e70d4-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Imagen de la pestaña equipos de un incidente](../../media/incident-machines.png)

<span data-ttu-id="e70d4-135">Seleccionar la pestaña escala de tiempo permite desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos que se observan en el equipo en orden cronológico, intercalados con las alertas iniciadas.</span><span class="sxs-lookup"><span data-stu-id="e70d4-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="e70d4-136">Usuarios</span><span class="sxs-lookup"><span data-stu-id="e70d4-136">Users</span></span>

<span data-ttu-id="e70d4-137">Vea los usuarios que se han identificado como parte de un incidente determinado o que están relacionados con él.</span><span class="sxs-lookup"><span data-stu-id="e70d4-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="e70d4-138">Al hacer clic en el nombre de usuario, se accede a la página de seguridad de la aplicación en la nube del usuario, donde se pueden realizar más investigaciones.</span><span class="sxs-lookup"><span data-stu-id="e70d4-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Imagen de la pestaña usuarios de un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="e70d4-140">Buzones</span><span class="sxs-lookup"><span data-stu-id="e70d4-140">Mailboxes</span></span>

<span data-ttu-id="e70d4-141">Investigue los buzones que se han identificado como parte de un incidente o relacionados con él.</span><span class="sxs-lookup"><span data-stu-id="e70d4-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="e70d4-142">Para hacer más trabajo de investigación, al seleccionar la alerta relacionada con el correo se abrirá Microsoft defender para Office 365, donde puede realizar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="e70d4-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Imagen de la pestaña buzón de un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="e70d4-144">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="e70d4-144">Investigations</span></span>

<span data-ttu-id="e70d4-145">Seleccione **investigaciones** para ver todas las investigaciones automatizadas desencadenadas por las alertas de este incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="e70d4-146">Las investigaciones realizarán acciones de corrección o esperarán la aprobación de analistas de acciones, en función de cómo configuró las investigaciones automatizadas para que se ejecuten en Microsoft defender para Endpoint y defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e70d4-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Imagen de la pestaña investigaciones de un incidente](../../media/incident-investigations.png)

<span data-ttu-id="e70d4-148">Seleccione una investigación para ir a la página de detalles de la investigación para obtener toda la información sobre la investigación y el estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="e70d4-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="e70d4-149">Si hay acciones pendientes de aprobación como parte de la investigación, aparecerán en la ficha acciones pendientes. Emprender acciones como parte de la corrección de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e70d4-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="e70d4-150">Evidencia</span><span class="sxs-lookup"><span data-stu-id="e70d4-150">Evidence</span></span>

<span data-ttu-id="e70d4-151">Microsoft 365 defender investiga automáticamente todos los eventos y las entidades sospechosas admitidas por los incidentes en las alertas, lo que proporciona una respuesta automática e información sobre los archivos, procesos, servicios, mensajes de correo electrónico y mucho más importantes.</span><span class="sxs-lookup"><span data-stu-id="e70d4-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="e70d4-152">Esto permite detectar y bloquear rápidamente posibles amenazas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="e70d4-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Imagen de la pestaña evidencia de un incidente](../../media/incident-evidence.png)

<span data-ttu-id="e70d4-154">Cada una de las entidades analizadas se marcará con un veredicto (malintencionada, sospechosa, limpia), así como un estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="e70d4-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="e70d4-155">Esto le ayuda a comprender el estado de corrección de todo el incidente y cuáles son los siguientes pasos a seguir para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="e70d4-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e70d4-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e70d4-156">Related topics</span></span>

- [<span data-ttu-id="e70d4-157">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="e70d4-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e70d4-158">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="e70d4-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e70d4-159">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="e70d4-159">Manage incidents</span></span>](manage-incidents.md)

