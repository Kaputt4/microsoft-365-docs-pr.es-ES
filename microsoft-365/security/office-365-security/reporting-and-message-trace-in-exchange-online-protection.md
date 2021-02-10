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
description: En este artículo, aprenderá sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86c9eb0ee050c4c1a40ef7f29ea3d01dc202be9a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166680"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="5d6e3-103">Informes y seguimiento de mensajes en EOP</span><span class="sxs-lookup"><span data-stu-id="5d6e3-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d6e3-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="5d6e3-104">**Applies to**</span></span>
- [<span data-ttu-id="5d6e3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5d6e3-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="5d6e3-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5d6e3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="5d6e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d6e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5d6e3-108">En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el estado de su organización.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="5d6e3-109">También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="5d6e3-110">Informes de uso</span><span class="sxs-lookup"><span data-stu-id="5d6e3-110">Usage reports</span></span>

<span data-ttu-id="5d6e3-111">**Actividad de grupos de Microsoft 365:** ver información sobre el número de grupos de Microsoft 365 que se crean y usan.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="5d6e3-112">**Actividad de correo** electrónico: ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="5d6e3-113">**Uso de la aplicación de** correo electrónico: ver información sobre las aplicaciones de correo electrónico que se usan.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="5d6e3-114">Esto incluye el número total de conexiones para cada aplicación y las versiones de Outlook que se conectan.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="5d6e3-115">**Uso del buzón:** ver información sobre el almacenamiento usado, el consumo de cuota, el recuento de elementos y la última actividad (actividad de envío o lectura) de los buzones.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="5d6e3-116">Consulte los siguientes recursos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="5d6e3-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="5d6e3-117">Informes de Microsoft 365 en el centro de administración: grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5d6e3-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="5d6e3-118">Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5d6e3-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="5d6e3-119">Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5d6e3-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="5d6e3-120">Informes de Microsoft 365 en el centro de administración: uso del buzón</span><span class="sxs-lookup"><span data-stu-id="5d6e3-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5d6e3-121">Informes de & cumplimiento normativo en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5d6e3-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5d6e3-122">Estos informes mejorados proporcionan una experiencia interactiva de informes para los administradores de EOP, que incluye información resumida y la capacidad de explorar en profundidad para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="5d6e3-123">**Defender para Office 365:** ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="5d6e3-124">**EOP:** ver información sobre detecciones de malware, correo suplantado, detecciones de correo no deseado y flujo de correo hacia y desde su organización.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="5d6e3-125">Ver informes de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5d6e3-125">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="5d6e3-126">Informes personalizados con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5d6e3-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="5d6e3-127">Cree mediante programación informes que estén disponibles en el centro de administración mediante Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="5d6e3-128">Para obtener más información, vea [Información general sobre Microsoft Graph](https://docs.microsoft.com/graph/overview) y trabajar con informes de uso de Office [365 en Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="5d6e3-128">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="5d6e3-129">Seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="5d6e3-129">Message trace</span></span>

<span data-ttu-id="5d6e3-130">Sigue los mensajes de correo electrónico mientras viajan a través de EOP.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="5d6e3-131">Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="5d6e3-132">También muestra las acciones que se realizaron en el mensaje antes de alcanzar su estado final.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5d6e3-133">Puede usar esta información para responder eficazmente a las preguntas del usuario, solucionar problemas de flujo de correo, validar los cambios de directiva y mitigar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="5d6e3-134">Consulte [Seguimiento de mensajes en el Centro de seguridad & cumplimiento.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="5d6e3-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="5d6e3-135">Registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="5d6e3-135">Audit logging</span></span>

<span data-ttu-id="5d6e3-136">Realiza un seguimiento de los cambios específicos realizados por los administradores en su organización.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="5d6e3-137">Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con la seguridad o el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="5d6e3-138">Vea [Informes de auditoría en EOP.](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="5d6e3-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="5d6e3-139">Informes, disponibilidad y latencia de los datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="5d6e3-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="5d6e3-140">En la tabla siguiente se describe cuándo están disponibles los datos de informes y seguimiento de mensajes de EOP y durante cuánto tiempo.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="5d6e3-141">Tipo de informe</span><span class="sxs-lookup"><span data-stu-id="5d6e3-141">Report type</span></span>|<span data-ttu-id="5d6e3-142">Datos disponibles (período retrospectivo)</span><span class="sxs-lookup"><span data-stu-id="5d6e3-142">Data available for (look back period)</span></span>|<span data-ttu-id="5d6e3-143">Latencia</span><span class="sxs-lookup"><span data-stu-id="5d6e3-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="5d6e3-144">Informes de resumen de protección de correo</span><span class="sxs-lookup"><span data-stu-id="5d6e3-144">Mail protection summary reports</span></span>|<span data-ttu-id="5d6e3-145">90 días</span><span class="sxs-lookup"><span data-stu-id="5d6e3-145">90 days</span></span>|<span data-ttu-id="5d6e3-p106">La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="5d6e3-148">Informes de detalles de protección de correo</span><span class="sxs-lookup"><span data-stu-id="5d6e3-148">Mail protection detail reports</span></span>|<span data-ttu-id="5d6e3-149">90 días</span><span class="sxs-lookup"><span data-stu-id="5d6e3-149">90 days</span></span>|<span data-ttu-id="5d6e3-p107">Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="5d6e3-152">Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="5d6e3-153">Datos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="5d6e3-153">Message trace data</span></span>|<span data-ttu-id="5d6e3-154">90 días</span><span class="sxs-lookup"><span data-stu-id="5d6e3-154">90 days</span></span>|<span data-ttu-id="5d6e3-155">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="5d6e3-156">Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="5d6e3-157">La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del Centro de administración o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="5d6e3-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
