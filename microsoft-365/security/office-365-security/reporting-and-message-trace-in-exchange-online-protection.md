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
description: Microsoft Exchange Online Protection (EOP) ofrece muchos informes distintos que le permitirán averiguar el estado general y el mantenimiento de la organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento normativo. La tabla siguiente describe los informes y las herramientas de solución de problemas disponibles para los administradores de EOP.
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598557"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="83ab8-105">Informes y seguimiento de mensajes en Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="83ab8-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="83ab8-106">Microsoft Exchange Online Protection (EOP) ofrece muchos informes distintos que le permitirán averiguar el estado general y el mantenimiento de la organización.</span><span class="sxs-lookup"><span data-stu-id="83ab8-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="83ab8-107">También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="83ab8-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="83ab8-108">Informes de uso</span><span class="sxs-lookup"><span data-stu-id="83ab8-108">Usage reports</span></span>

<span data-ttu-id="83ab8-109">**Office 365 actividad de grupos**: ver información sobre el número de grupos de Office 365 que se crean y usan.</span><span class="sxs-lookup"><span data-stu-id="83ab8-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="83ab8-110">**Actividad de correo electrónico**: ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="83ab8-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="83ab8-111">**Uso de la aplicación de correo electrónico**: ver información sobre las aplicaciones de correo electrónico que se usan.</span><span class="sxs-lookup"><span data-stu-id="83ab8-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="83ab8-112">Esto incluye el número total de conexiones de cada aplicación y las versiones de Outlook que se conectan.</span><span class="sxs-lookup"><span data-stu-id="83ab8-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="83ab8-113">**Uso de buzón de correo**: ver información sobre el almacenamiento usado, el consumo de cuotas, el recuento de elementos y la última actividad (actividad de envío o lectura) para los buzones.</span><span class="sxs-lookup"><span data-stu-id="83ab8-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="83ab8-114">Consulte los siguientes recursos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="83ab8-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="83ab8-115">Office 365 Reports en el centro de administración: Office 365 grupos</span><span class="sxs-lookup"><span data-stu-id="83ab8-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="83ab8-116">Office 365 Reports en el centro de administración: actividad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="83ab8-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="83ab8-117">Office 365 Reports en el centro de administración: uso de aplicaciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="83ab8-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="83ab8-118">Office 365 Reports en el centro de administración: uso de buzones</span><span class="sxs-lookup"><span data-stu-id="83ab8-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="83ab8-119">Informes de cumplimiento de & de seguridad en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83ab8-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="83ab8-120">Estos informes mejorados proporcionan una experiencia de creación de informes interactiva para los administradores de EOP, que incluye información de Resumen y la capacidad de profundizar para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="83ab8-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="83ab8-121">**Protección contra amenazas avanzada (ATP)**: ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de ATP.</span><span class="sxs-lookup"><span data-stu-id="83ab8-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="83ab8-122">**EOP**: ver información sobre las detecciones de malware, el correo falsificado, las detecciones de correo no deseado y el flujo de correo hacia y desde la organización.</span><span class="sxs-lookup"><span data-stu-id="83ab8-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="83ab8-123">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="83ab8-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="83ab8-124">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="83ab8-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="83ab8-125">Cree mediante programación informes que estén disponibles en el centro de administración de Microsoft 365 mediante Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="83ab8-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="83ab8-126">Vea los temas secundarios de [trabajar con los informes de uso de Office 365 en Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="83ab8-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="83ab8-127">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="83ab8-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="83ab8-128">Crear informes mediante programación.</span><span class="sxs-lookup"><span data-stu-id="83ab8-128">Programmatically create reports.</span></span> <span data-ttu-id="83ab8-129">Vea [información general de Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="83ab8-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="83ab8-130">Seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="83ab8-130">Message trace</span></span>

<span data-ttu-id="83ab8-131">Sigue los mensajes de correo electrónico mientras viajan a través de EOP.</span><span class="sxs-lookup"><span data-stu-id="83ab8-131">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="83ab8-132">Puede determinar si un mensaje de correo electrónico se ha recibido, rechazado, aplazado o entregado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="83ab8-132">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="83ab8-133">También muestra las acciones que se tomaron en el mensaje antes de que alcanzara su estado final.</span><span class="sxs-lookup"><span data-stu-id="83ab8-133">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="83ab8-134">Puede usar esta información para responder de forma eficaz a las preguntas del usuario, solucionar problemas del flujo de correo, validar los cambios en la Directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="83ab8-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="83ab8-135">Consulte [seguimiento de un mensaje de correo electrónico](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="83ab8-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="83ab8-136">Registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="83ab8-136">Audit logging</span></span>

<span data-ttu-id="83ab8-137">Realiza un seguimiento de los cambios específicos realizados por los administradores en la organización.</span><span class="sxs-lookup"><span data-stu-id="83ab8-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="83ab8-138">Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con el cumplimiento o la seguridad.</span><span class="sxs-lookup"><span data-stu-id="83ab8-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="83ab8-139">Vea [Auditing Reports in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="83ab8-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="83ab8-140">Informes, disponibilidad y latencia de los datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="83ab8-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="83ab8-141">En la tabla siguiente se describe cuándo están disponibles los informes y los datos de seguimiento de mensajes de EOP y durante cuánto tiempo.</span><span class="sxs-lookup"><span data-stu-id="83ab8-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="83ab8-142">**Tipo de informe**</span><span class="sxs-lookup"><span data-stu-id="83ab8-142">**Report type**</span></span>|<span data-ttu-id="83ab8-143">**Datos disponibles (período retrospectivo)**</span><span class="sxs-lookup"><span data-stu-id="83ab8-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="83ab8-144">**Latencia**</span><span class="sxs-lookup"><span data-stu-id="83ab8-144">**Latency**</span></span>|
|<span data-ttu-id="83ab8-145">Informes de Resumen de protección de correo</span><span class="sxs-lookup"><span data-stu-id="83ab8-145">Mail protection summary reports</span></span>|<span data-ttu-id="83ab8-146">90 días</span><span class="sxs-lookup"><span data-stu-id="83ab8-146">90 days</span></span>|<span data-ttu-id="83ab8-p108">La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="83ab8-p108">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="83ab8-149">Informes de detalles de protección de correo</span><span class="sxs-lookup"><span data-stu-id="83ab8-149">Mail protection detail reports</span></span>|<span data-ttu-id="83ab8-150">90 días</span><span class="sxs-lookup"><span data-stu-id="83ab8-150">90 days</span></span>|<span data-ttu-id="83ab8-p109">Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="83ab8-p109">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="83ab8-153">Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="83ab8-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="83ab8-154">Datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="83ab8-154">Message trace data</span></span>|<span data-ttu-id="83ab8-155">90 días</span><span class="sxs-lookup"><span data-stu-id="83ab8-155">90 days</span></span>|<span data-ttu-id="83ab8-156">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="83ab8-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="83ab8-157">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="83ab8-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="83ab8-158">La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del centro de administración de Microsoft 365 o de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="83ab8-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
