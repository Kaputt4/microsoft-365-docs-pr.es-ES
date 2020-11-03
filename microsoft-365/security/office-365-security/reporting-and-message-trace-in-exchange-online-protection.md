---
title: Creación de informes y seguimiento de mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: En este artículo, obtendrá información sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 9a8eb8e35ef73eb27604eef4bf701982b1d51710
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845557"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="6c7c3-103">Informes y seguimiento de mensajes en EOP</span><span class="sxs-lookup"><span data-stu-id="6c7c3-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6c7c3-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el mantenimiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="6c7c3-105">También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="6c7c3-106">Informes de uso</span><span class="sxs-lookup"><span data-stu-id="6c7c3-106">Usage reports</span></span>

<span data-ttu-id="6c7c3-107">**Actividad de microsoft 365 Groups** : ver información sobre el número de grupos de Microsoft 365 que se crean y usan.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-107">**Microsoft 365 groups activity** : View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="6c7c3-108">**Actividad de correo electrónico** : ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-108">**Email activity** : View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="6c7c3-109">**Uso de la aplicación de correo electrónico** : ver información sobre las aplicaciones de correo electrónico que se usan.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-109">**Email app usage** : View information about the email apps that are used.</span></span> <span data-ttu-id="6c7c3-110">Esto incluye el número total de conexiones de cada aplicación y las versiones de Outlook que se conectan.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="6c7c3-111">**Uso de buzón de correo** : ver información sobre el almacenamiento usado, el consumo de cuotas, el recuento de elementos y la última actividad (actividad de envío o lectura) para los buzones.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-111">**Mailbox usage** : View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="6c7c3-112">Consulte los siguientes recursos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="6c7c3-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="6c7c3-113">Informes de Microsoft 365 en el centro de administración (grupos de Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="6c7c3-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="6c7c3-114">Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6c7c3-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="6c7c3-115">Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6c7c3-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="6c7c3-116">Informes de Microsoft 365 en el centro de administración: uso de buzones</span><span class="sxs-lookup"><span data-stu-id="6c7c3-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6c7c3-117">Informes de cumplimiento de & de seguridad en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c7c3-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6c7c3-118">Estos informes mejorados proporcionan una experiencia de creación de informes interactiva para los administradores de EOP, que incluye información de Resumen y la capacidad de profundizar para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="6c7c3-119">**Defender para office 365** : ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-119">**Defender for Office 365** : View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="6c7c3-120">**EOP** : ver información sobre las detecciones de malware, el correo falsificado, las detecciones de correo no deseado y el flujo de correo hacia y desde la organización.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-120">**EOP** : View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="6c7c3-121">Ver informes para defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6c7c3-121">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="6c7c3-122">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="6c7c3-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="6c7c3-123">Cree mediante programación informes que estén disponibles en el centro de administración mediante Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="6c7c3-124">Para obtener más información, vea [información general de Microsoft Graph](https://docs.microsoft.com/graph/overview) y [trabajar con los informes de uso de Office 365 en Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="6c7c3-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="6c7c3-125">Seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="6c7c3-125">Message trace</span></span>

<span data-ttu-id="6c7c3-126">Sigue los mensajes de correo electrónico mientras viajan a través de EOP.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="6c7c3-127">Puede determinar si un mensaje de correo electrónico se ha recibido, rechazado, aplazado o entregado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="6c7c3-128">También muestra las acciones que se tomaron en el mensaje antes de que alcanzara su estado final.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="6c7c3-129">Puede usar esta información para responder de forma eficaz a las preguntas del usuario, solucionar problemas del flujo de correo, validar los cambios en la Directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="6c7c3-130">Consulte [seguimiento de mensajes en el centro de seguridad & cumplimiento](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="6c7c3-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="6c7c3-131">Registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="6c7c3-131">Audit logging</span></span>

<span data-ttu-id="6c7c3-132">Realiza un seguimiento de los cambios específicos realizados por los administradores en la organización.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="6c7c3-133">Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con el cumplimiento o la seguridad.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="6c7c3-134">Vea [Auditing Reports in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6c7c3-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="6c7c3-135">Informes, disponibilidad y latencia de los datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="6c7c3-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="6c7c3-136">En la tabla siguiente se describe cuándo están disponibles los informes y los datos de seguimiento de mensajes de EOP y durante cuánto tiempo.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="6c7c3-137">Tipo de informe</span><span class="sxs-lookup"><span data-stu-id="6c7c3-137">Report type</span></span>|<span data-ttu-id="6c7c3-138">Datos disponibles (período retrospectivo)</span><span class="sxs-lookup"><span data-stu-id="6c7c3-138">Data available for (look back period)</span></span>|<span data-ttu-id="6c7c3-139">Latencia</span><span class="sxs-lookup"><span data-stu-id="6c7c3-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="6c7c3-140">Informes de Resumen de protección de correo</span><span class="sxs-lookup"><span data-stu-id="6c7c3-140">Mail protection summary reports</span></span>|<span data-ttu-id="6c7c3-141">90 días</span><span class="sxs-lookup"><span data-stu-id="6c7c3-141">90 days</span></span>|<span data-ttu-id="6c7c3-p106">La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="6c7c3-144">Informes de detalles de protección de correo</span><span class="sxs-lookup"><span data-stu-id="6c7c3-144">Mail protection detail reports</span></span>|<span data-ttu-id="6c7c3-145">90 días</span><span class="sxs-lookup"><span data-stu-id="6c7c3-145">90 days</span></span>|<span data-ttu-id="6c7c3-p107">Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="6c7c3-148">Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="6c7c3-149">Datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="6c7c3-149">Message trace data</span></span>|<span data-ttu-id="6c7c3-150">90 días</span><span class="sxs-lookup"><span data-stu-id="6c7c3-150">90 days</span></span>|<span data-ttu-id="6c7c3-151">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="6c7c3-152">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="6c7c3-153">La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del centro de administración o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
