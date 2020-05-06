---
title: Informes y seguimiento de mensajes en Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: En este artículo, obtendrá información sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 44b4223b4310a2de1d90f99f8a7af23cc6054f94
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034385"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="e756c-103">Informes y seguimiento de mensajes en Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e756c-103">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="e756c-104">Microsoft Exchange Online Protection (EOP) ofrece muchos informes distintos que le permitirán averiguar el estado general y el mantenimiento de la organización.</span><span class="sxs-lookup"><span data-stu-id="e756c-104">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="e756c-105">También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="e756c-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="e756c-106">Informes de uso</span><span class="sxs-lookup"><span data-stu-id="e756c-106">Usage reports</span></span>

<span data-ttu-id="e756c-107">**Actividad de microsoft 365 Groups**: ver información sobre el número de grupos de Microsoft 365 que se crean y usan.</span><span class="sxs-lookup"><span data-stu-id="e756c-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="e756c-108">**Actividad de correo electrónico**: ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="e756c-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="e756c-109">**Uso de la aplicación de correo electrónico**: ver información sobre las aplicaciones de correo electrónico que se usan.</span><span class="sxs-lookup"><span data-stu-id="e756c-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="e756c-110">Esto incluye el número total de conexiones de cada aplicación y las versiones de Outlook que se conectan.</span><span class="sxs-lookup"><span data-stu-id="e756c-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="e756c-111">**Uso de buzón de correo**: ver información sobre el almacenamiento usado, el consumo de cuotas, el recuento de elementos y la última actividad (actividad de envío o lectura) para los buzones.</span><span class="sxs-lookup"><span data-stu-id="e756c-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="e756c-112">Consulte los siguientes recursos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="e756c-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="e756c-113">Informes de Microsoft 365 en el centro de administración (grupos de Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="e756c-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="e756c-114">Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e756c-114">Microsoft 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="e756c-115">Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e756c-115">Microsoft 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="e756c-116">Informes de Microsoft 365 en el centro de administración: uso de buzones</span><span class="sxs-lookup"><span data-stu-id="e756c-116">Microsoft 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e756c-117">Informes de cumplimiento de & de seguridad en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e756c-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e756c-118">Estos informes mejorados proporcionan una experiencia de creación de informes interactiva para los administradores de EOP, que incluye información de Resumen y la capacidad de profundizar para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="e756c-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="e756c-119">**Protección contra amenazas avanzada (ATP)**: ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de ATP.</span><span class="sxs-lookup"><span data-stu-id="e756c-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="e756c-120">**EOP**: ver información sobre las detecciones de malware, el correo falsificado, las detecciones de correo no deseado y el flujo de correo hacia y desde la organización.</span><span class="sxs-lookup"><span data-stu-id="e756c-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="e756c-121">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="e756c-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="e756c-122">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="e756c-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="e756c-123">Cree mediante programación informes que estén disponibles en el centro de administración de Microsoft 365 mediante Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e756c-123">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="e756c-124">Vea los temas secundarios de [trabajar con los informes de uso de Office 365 en Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="e756c-124">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="e756c-125">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="e756c-125">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="e756c-126">Crear informes mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e756c-126">Programmatically create reports.</span></span> <span data-ttu-id="e756c-127">Vea [información general de Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="e756c-127">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="e756c-128">Seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e756c-128">Message trace</span></span>

<span data-ttu-id="e756c-129">Sigue los mensajes de correo electrónico mientras viajan a través de EOP.</span><span class="sxs-lookup"><span data-stu-id="e756c-129">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="e756c-130">Puede determinar si un mensaje de correo electrónico se ha recibido, rechazado, aplazado o entregado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="e756c-130">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="e756c-131">También muestra las acciones que se tomaron en el mensaje antes de que alcanzara su estado final.</span><span class="sxs-lookup"><span data-stu-id="e756c-131">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="e756c-132">Puede usar esta información para responder de forma eficaz a las preguntas del usuario, solucionar problemas del flujo de correo, validar los cambios en la Directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="e756c-132">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="e756c-133">Consulte [seguimiento de un mensaje de correo electrónico](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="e756c-133">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="e756c-134">Registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="e756c-134">Audit logging</span></span>

<span data-ttu-id="e756c-135">Realiza un seguimiento de los cambios específicos realizados por los administradores en la organización.</span><span class="sxs-lookup"><span data-stu-id="e756c-135">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="e756c-136">Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con el cumplimiento o la seguridad.</span><span class="sxs-lookup"><span data-stu-id="e756c-136">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="e756c-137">Vea [Auditing Reports in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e756c-137">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="e756c-138">Informes, disponibilidad y latencia de los datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e756c-138">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="e756c-139">En la tabla siguiente se describe cuándo están disponibles los informes y los datos de seguimiento de mensajes de EOP y durante cuánto tiempo.</span><span class="sxs-lookup"><span data-stu-id="e756c-139">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="e756c-140">**Tipo de informe**</span><span class="sxs-lookup"><span data-stu-id="e756c-140">**Report type**</span></span>|<span data-ttu-id="e756c-141">**Datos disponibles (período retrospectivo)**</span><span class="sxs-lookup"><span data-stu-id="e756c-141">**Data available for (look back period)**</span></span>|<span data-ttu-id="e756c-142">**Latencia**</span><span class="sxs-lookup"><span data-stu-id="e756c-142">**Latency**</span></span>|
|<span data-ttu-id="e756c-143">Informes de Resumen de protección de correo</span><span class="sxs-lookup"><span data-stu-id="e756c-143">Mail protection summary reports</span></span>|<span data-ttu-id="e756c-144">90 días</span><span class="sxs-lookup"><span data-stu-id="e756c-144">90 days</span></span>|<span data-ttu-id="e756c-p107">La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="e756c-p107">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="e756c-147">Informes de detalles de protección de correo</span><span class="sxs-lookup"><span data-stu-id="e756c-147">Mail protection detail reports</span></span>|<span data-ttu-id="e756c-148">90 días</span><span class="sxs-lookup"><span data-stu-id="e756c-148">90 days</span></span>|<span data-ttu-id="e756c-p108">Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="e756c-p108">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="e756c-151">Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="e756c-151">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="e756c-152">Datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e756c-152">Message trace data</span></span>|<span data-ttu-id="e756c-153">90 días</span><span class="sxs-lookup"><span data-stu-id="e756c-153">90 days</span></span>|<span data-ttu-id="e756c-154">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="e756c-154">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="e756c-155">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="e756c-155">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="e756c-156">La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del centro de administración de Microsoft 365 o de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e756c-156">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
