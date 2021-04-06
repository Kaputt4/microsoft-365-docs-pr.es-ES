---
title: Investigar incidentes en Microsoft 365 Defender
description: Analizar incidentes relacionados con dispositivos, usuarios y buzones de correo.
keywords: incidente, incidentes, equipos, dispositivos, usuarios, identidades, correo, correo electrónico, buzón, investigación, gráfico, evidencia
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592101"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5d380-104">Investigar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d380-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5d380-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5d380-105">**Applies to:**</span></span>

- <span data-ttu-id="5d380-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d380-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5d380-107">Microsoft 365 Defender agrega todas las alertas, activos, investigaciones y pruebas relacionadas de todos los dispositivos, usuarios y buzones de correo para darle una visión completa de toda la amplitud de un ataque.</span><span class="sxs-lookup"><span data-stu-id="5d380-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="5d380-108">Investigue las alertas que afectan a la red, entienda lo que significa y intercale la evidencia asociada con los incidentes para que pueda diseñar un plan de corrección eficaz.</span><span class="sxs-lookup"><span data-stu-id="5d380-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="5d380-109">Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="5d380-109">Investigate an incident</span></span>

1. <span data-ttu-id="5d380-110">Seleccione un incidente en la cola incidentes.</span><span class="sxs-lookup"><span data-stu-id="5d380-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="5d380-111">Se abre un panel lateral y proporciona una vista previa de información importante, como el estado, la gravedad, las categorías y las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="5d380-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Imagen del panel lateral del incidente](../../media/incident-side-panel.png)

2. <span data-ttu-id="5d380-113">Seleccione **abrir página de incidente**.</span><span class="sxs-lookup"><span data-stu-id="5d380-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="5d380-114">Se abre la página de incidentes donde encontrará más información sobre incidentes, comentarios y acciones, pestañas (información general, alertas, dispositivos, usuarios, investigaciones, evidencias).</span><span class="sxs-lookup"><span data-stu-id="5d380-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="5d380-115">Revise las alertas, los dispositivos, los usuarios y otras entidades relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="5d380-116">Información general del incidente</span><span class="sxs-lookup"><span data-stu-id="5d380-116">Incident overview</span></span>

<span data-ttu-id="5d380-117">En la página de información general encontrará un resumen de las instantáneas en las principales cosas que debe tener en cuenta al incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Imagen de la página información general de incidentes](../../media/incidents-overview.png)

<span data-ttu-id="5d380-119">Las categorías de ataque te dan una vista visual y numérica de lo avanzado que ha progresado el ataque en la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="5d380-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="5d380-120">Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender se alinea con el marco de [CK &trade;&MITRE ATT.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="5d380-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="5d380-121">La sección de ámbito ofrece una lista de los activos que se han visto afectados y que forman parte de este incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="5d380-122">Si hay información específica sobre este activo, como el nivel de riesgo, la prioridad de investigación, así como cualquier etiqueta en los activos, esto también se mostrará en esta sección.</span><span class="sxs-lookup"><span data-stu-id="5d380-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="5d380-123">La escala de tiempo de las alertas proporciona una vista rápida al orden cronológico en el que se han producido las alertas, así como los motivos por los que estos avisos se relacionan con este incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="5d380-124">Por último, la sección de evidencia ofrece un resumen de cuántos artefactos diferentes se incluyeron en el incidente y su estado de corrección, por lo que puede identificar de inmediato si se necesita alguna acción al final.</span><span class="sxs-lookup"><span data-stu-id="5d380-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="5d380-125">Esta descripción general puede ayudar en la clasificación inicial del incidente al proporcionar información sobre las principales características del incidente que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="5d380-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="5d380-126">Alertas</span><span class="sxs-lookup"><span data-stu-id="5d380-126">Alerts</span></span>

<span data-ttu-id="5d380-127">Puede ver todas las alertas relacionadas con el incidente y otra información sobre ellas, como la gravedad, las entidades que participaron en la alerta, el origen de las alertas (Microsoft Defender para identity, Microsoft Defender para endpoint, Microsoft Defender para Office 365) y el motivo por el que se vincularon.</span><span class="sxs-lookup"><span data-stu-id="5d380-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Imagen de la página de alertas de incidente](../../media/incident-alerts.png)

<span data-ttu-id="5d380-129">De forma predeterminada, los avisos se ordenan cronológicamente, para que pueda ver en primer lugar cómo se ha producido el ataque a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="5d380-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="5d380-130">Al hacer clic en cada alerta, se le dirigirá a la página de alerta relevante donde puede llevar a cabo una investigación en profundidad de esa alerta.</span><span class="sxs-lookup"><span data-stu-id="5d380-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="5d380-131">Obtenga información sobre cómo usar las páginas de alertas y la cola de alertas unificada en [Investigar alertas](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="5d380-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="5d380-132">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="5d380-132">Devices</span></span>

<span data-ttu-id="5d380-133">En la pestaña dispositivos se muestran todos los dispositivos en los que se ven las alertas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="5d380-134">Al hacer clic en el nombre del equipo en el que se realizó el ataque, es dirigido a la página de su equipo, donde puede ver las alertas que se activaron y los eventos relacionados que se proporcionan para facilitar la investigación.</span><span class="sxs-lookup"><span data-stu-id="5d380-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Imagen de la pestaña equipos de un incidente](../../media/incident-machines.png)

<span data-ttu-id="5d380-136">Seleccionar la pestaña escala de tiempo permite desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos que se observan en el equipo en orden cronológico, intercalados con las alertas iniciadas.</span><span class="sxs-lookup"><span data-stu-id="5d380-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="5d380-137">Puedes realizar exámenes a petición en una página de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d380-137">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="5d380-138">En el Centro de seguridad de Microsoft 365, elija **Inventario de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5d380-138">In the Microsoft 365 security center, choose **Device inventory**.</span></span> <span data-ttu-id="5d380-139">Selecciona un dispositivo que tenga alertas y, a continuación, ejecuta un examen antivirus.</span><span class="sxs-lookup"><span data-stu-id="5d380-139">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="5d380-140">Las acciones, como los exámenes antivirus, se realiza un seguimiento y están visibles en la **página Inventario de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5d380-140">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="5d380-141">Para obtener más información, consulta [Ejecutar el examen de Antivirus de Microsoft Defender en dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="5d380-141">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>


## <a name="users"></a><span data-ttu-id="5d380-142">Usuarios</span><span class="sxs-lookup"><span data-stu-id="5d380-142">Users</span></span>

<span data-ttu-id="5d380-143">Vea los usuarios que se han identificado como parte de un incidente determinado o que están relacionados con él.</span><span class="sxs-lookup"><span data-stu-id="5d380-143">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="5d380-144">Al hacer clic en el nombre de usuario, se accede a la página de seguridad de la aplicación en la nube del usuario, donde se pueden realizar más investigaciones.</span><span class="sxs-lookup"><span data-stu-id="5d380-144">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Imagen de la pestaña usuarios de un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="5d380-146">Buzones</span><span class="sxs-lookup"><span data-stu-id="5d380-146">Mailboxes</span></span>

<span data-ttu-id="5d380-147">Investigue los buzones que se han identificado como parte de un incidente o relacionados con él.</span><span class="sxs-lookup"><span data-stu-id="5d380-147">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="5d380-148">Para realizar más tareas de investigación, al seleccionar la alerta relacionada con el correo se abrirá Microsoft Defender para Office 365, donde puede realizar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="5d380-148">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Imagen de la pestaña buzón de un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="5d380-150">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="5d380-150">Investigations</span></span>

<span data-ttu-id="5d380-151">Seleccione **Investigaciones para** ver todas las investigaciones automatizadas desencadenadas por alertas en este incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-151">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="5d380-152">Las investigaciones realizarán acciones de corrección o esperarán a que el analista apruebe las acciones, según cómo haya configurado las investigaciones automatizadas para que se ejecuten en Microsoft Defender para Endpoint y Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d380-152">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Imagen de la pestaña investigaciones de un incidente](../../media/incident-investigations.png)

<span data-ttu-id="5d380-154">Seleccione una investigación para ir a la página de detalles de la investigación para obtener toda la información sobre la investigación y el estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="5d380-154">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="5d380-155">Si hay acciones pendientes para su aprobación como parte de la investigación, aparecerán en la pestaña Acciones pendientes. Tome medidas como parte de la corrección de incidentes.</span><span class="sxs-lookup"><span data-stu-id="5d380-155">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="5d380-156">Evidencia</span><span class="sxs-lookup"><span data-stu-id="5d380-156">Evidence</span></span>

<span data-ttu-id="5d380-157">Microsoft 365 Defender investiga automáticamente todos los eventos admitidos por los incidentes y las entidades sospechosas de las alertas, lo que proporciona una respuesta automática e información sobre los archivos, procesos, servicios, correos electrónicos y mucho más importantes.</span><span class="sxs-lookup"><span data-stu-id="5d380-157">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="5d380-158">Esto permite detectar y bloquear rápidamente posibles amenazas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="5d380-158">This helps quickly detect and block potential threats in the incident.</span></span>

![Imagen de la pestaña evidencia de un incidente](../../media/incident-evidence.png)

<span data-ttu-id="5d380-160">Cada una de las entidades analizadas se marcará con un veredicto (malintencionada, sospechosa, limpia), así como un estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="5d380-160">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="5d380-161">Esto le ayuda a comprender el estado de corrección de todo el incidente y cuáles son los siguientes pasos a seguir para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="5d380-161">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d380-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d380-162">Related topics</span></span>

- [<span data-ttu-id="5d380-163">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="5d380-163">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5d380-164">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="5d380-164">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="5d380-165">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="5d380-165">Manage incidents</span></span>](manage-incidents.md)

