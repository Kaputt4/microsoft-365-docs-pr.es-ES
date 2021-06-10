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
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online protección contra errores (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 079e2b359f28b0b6bc3d7eac86e69060c65ea250
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841443"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="42bc8-103">Informes y seguimiento de mensajes en EOP</span><span class="sxs-lookup"><span data-stu-id="42bc8-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="42bc8-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="42bc8-104">**Applies to**</span></span>
- [<span data-ttu-id="42bc8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="42bc8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="42bc8-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="42bc8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="42bc8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42bc8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="42bc8-108">En Microsoft 365 organizaciones con buzones en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el estado de su organización.</span><span class="sxs-lookup"><span data-stu-id="42bc8-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="42bc8-109">También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="42bc8-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="42bc8-110">Informes de uso</span><span class="sxs-lookup"><span data-stu-id="42bc8-110">Usage reports</span></span>

<span data-ttu-id="42bc8-111">**Microsoft 365 de grupos:** ver información sobre el número de grupos Microsoft 365 que se crean y usan.</span><span class="sxs-lookup"><span data-stu-id="42bc8-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="42bc8-112">**Actividad de correo** electrónico: vea información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="42bc8-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="42bc8-113">**Uso de la aplicación de** correo electrónico: ver información sobre las aplicaciones de correo electrónico que se usan.</span><span class="sxs-lookup"><span data-stu-id="42bc8-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="42bc8-114">Esto incluye el número total de conexiones para cada aplicación y las versiones de Outlook que se conectan.</span><span class="sxs-lookup"><span data-stu-id="42bc8-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="42bc8-115">**Uso del** buzón: ver información sobre el almacenamiento usado, el consumo de cuota, el recuento de elementos y la última actividad (actividad de envío o lectura) de los buzones.</span><span class="sxs-lookup"><span data-stu-id="42bc8-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="42bc8-116">Consulte los siguientes recursos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="42bc8-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="42bc8-117">Microsoft 365 Informes en el Centro de administración: Microsoft 365 grupos</span><span class="sxs-lookup"><span data-stu-id="42bc8-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)
- [<span data-ttu-id="42bc8-118">Microsoft 365 Informes en el Centro de administración: actividad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="42bc8-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)
- [<span data-ttu-id="42bc8-119">Microsoft 365 Informes en el Centro de administración: uso de aplicaciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="42bc8-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)
- [<span data-ttu-id="42bc8-120">Microsoft 365 Informes en el Centro de administración: uso del buzón</span><span class="sxs-lookup"><span data-stu-id="42bc8-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="42bc8-121">Informes de & cumplimiento normativo en el Centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="42bc8-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="42bc8-122">Estos informes mejorados proporcionan una experiencia interactiva de informes para los administradores de EOP, que incluye información de resumen y la capacidad de explorar más detalles.</span><span class="sxs-lookup"><span data-stu-id="42bc8-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="42bc8-123">**Defender para Office 365:** ver información sobre Caja fuerte vínculos y Caja fuerte adjuntos que forman parte de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="42bc8-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="42bc8-124">**EOP:** ver información sobre detecciones de malware, correo suplantado, detecciones de correo no deseado y flujo de correo desde y hacia su organización.</span><span class="sxs-lookup"><span data-stu-id="42bc8-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="42bc8-125">Ver informes de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="42bc8-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="42bc8-126">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="42bc8-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="42bc8-127">Cree informes disponibles en el Centro de administración mediante programación mediante Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="42bc8-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="42bc8-128">Para obtener más información, vea [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph](/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="42bc8-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="42bc8-129">Seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="42bc8-129">Message trace</span></span>

<span data-ttu-id="42bc8-130">Sigue los mensajes de correo electrónico mientras viajan a través de EOP.</span><span class="sxs-lookup"><span data-stu-id="42bc8-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="42bc8-131">Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="42bc8-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="42bc8-132">También muestra qué acciones se realizaron en el mensaje antes de alcanzar su estado final.</span><span class="sxs-lookup"><span data-stu-id="42bc8-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="42bc8-133">Puede usar esta información para responder eficazmente a las preguntas del usuario, solucionar problemas de flujo de correo, validar los cambios de directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener asistencia.</span><span class="sxs-lookup"><span data-stu-id="42bc8-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="42bc8-134">Consulte [Seguimiento de mensajes en el Centro de seguridad & cumplimiento](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="42bc8-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="42bc8-135">Registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="42bc8-135">Audit logging</span></span>

<span data-ttu-id="42bc8-136">Realiza un seguimiento de los cambios específicos realizados por los administradores en su organización.</span><span class="sxs-lookup"><span data-stu-id="42bc8-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="42bc8-137">Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con la seguridad o el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="42bc8-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="42bc8-138">Vea [Informes de auditoría en Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span><span class="sxs-lookup"><span data-stu-id="42bc8-138">See [Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="42bc8-139">Informes, disponibilidad y latencia de los datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="42bc8-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="42bc8-140">En la tabla siguiente se describe cuándo los datos de seguimiento de mensajes y informes de EOP están disponibles y durante cuánto tiempo.</span><span class="sxs-lookup"><span data-stu-id="42bc8-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="42bc8-141">Tipo de informe</span><span class="sxs-lookup"><span data-stu-id="42bc8-141">Report type</span></span>|<span data-ttu-id="42bc8-142">Datos disponibles (período retrospectivo)</span><span class="sxs-lookup"><span data-stu-id="42bc8-142">Data available for (look back period)</span></span>|<span data-ttu-id="42bc8-143">Latencia</span><span class="sxs-lookup"><span data-stu-id="42bc8-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="42bc8-144">Informes de resumen de protección de correo</span><span class="sxs-lookup"><span data-stu-id="42bc8-144">Mail protection summary reports</span></span>|<span data-ttu-id="42bc8-145">90 días</span><span class="sxs-lookup"><span data-stu-id="42bc8-145">90 days</span></span>|<span data-ttu-id="42bc8-p106">La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="42bc8-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="42bc8-148">Informes de detalles de protección de correo</span><span class="sxs-lookup"><span data-stu-id="42bc8-148">Mail protection detail reports</span></span>|<span data-ttu-id="42bc8-149">90 días</span><span class="sxs-lookup"><span data-stu-id="42bc8-149">90 days</span></span>|<span data-ttu-id="42bc8-p107">Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="42bc8-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="42bc8-152">Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="42bc8-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="42bc8-153">Datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="42bc8-153">Message trace data</span></span>|<span data-ttu-id="42bc8-154">90 días</span><span class="sxs-lookup"><span data-stu-id="42bc8-154">90 days</span></span>|<span data-ttu-id="42bc8-155">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="42bc8-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="42bc8-156">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="42bc8-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="42bc8-157">La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del Centro de administración o powerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="42bc8-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
