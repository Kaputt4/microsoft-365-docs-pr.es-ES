---
title: Acciones de corrección en Microsoft 365 Defender
description: Obtener información general sobre las acciones de corrección que siguen las investigaciones automatizadas en Microsoft 365 Defender
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fa73756aa9f350793c00a7e4a960c215627b712f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072752"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="75d18-104">Acciones de corrección en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d18-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75d18-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="75d18-105">**Applies to:**</span></span>
- <span data-ttu-id="75d18-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d18-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="75d18-107">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="75d18-107">Remediation actions</span></span>

<span data-ttu-id="75d18-108">Durante y después de una investigación automatizada en Microsoft 365 Defender, las acciones de corrección se identifican para elementos malintencionados o sospechosos.</span><span class="sxs-lookup"><span data-stu-id="75d18-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="75d18-109">Algunos tipos de acciones de corrección se toman en dispositivos, también denominados puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="75d18-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="75d18-110">Otras acciones de corrección se toman en el contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75d18-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="75d18-111">Las investigaciones automatizadas se completan después de que se realicen, aprueben o rechacen las acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="75d18-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75d18-112">Si las acciones de corrección se toman automáticamente o solo tras la aprobación depende de determinadas configuraciones, como el modo en que los niveles de automatización.</span><span class="sxs-lookup"><span data-stu-id="75d18-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="75d18-113">Para obtener más información, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="75d18-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="75d18-114">Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d18-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="75d18-115">Cómo se corrigen las amenazas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="75d18-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="75d18-116">Amenazas y acciones de corrección en el correo & contenido de colaboración</span><span class="sxs-lookup"><span data-stu-id="75d18-116">Threats and remediation actions on email & collaboration content</span></span>](../defender-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="75d18-117">En la tabla siguiente se resumen las acciones de corrección que se admiten actualmente en Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="75d18-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="75d18-118">Acciones de corrección del dispositivo (punto de conexión)</span><span class="sxs-lookup"><span data-stu-id="75d18-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="75d18-119">Acciones de corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="75d18-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="75d18-120">- Recopilar paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="75d18-120">- Collect investigation package</span></span> <br/><span data-ttu-id="75d18-121">- Aislar dispositivo (esta acción se puede deshacer)</span><span class="sxs-lookup"><span data-stu-id="75d18-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="75d18-122">- Máquina offboard</span><span class="sxs-lookup"><span data-stu-id="75d18-122">- Offboard machine</span></span> <br/><span data-ttu-id="75d18-123">- Ejecución de código de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="75d18-123">- Release code execution</span></span> <br/><span data-ttu-id="75d18-124">- Liberar de cuarentena</span><span class="sxs-lookup"><span data-stu-id="75d18-124">- Release from quarantine</span></span> <br/><span data-ttu-id="75d18-125">- Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="75d18-125">- Request sample</span></span> <br/><span data-ttu-id="75d18-126">- Restringir la ejecución de código (esta acción se puede deshacer)</span><span class="sxs-lookup"><span data-stu-id="75d18-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="75d18-127">- Ejecutar examen antivirus</span><span class="sxs-lookup"><span data-stu-id="75d18-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="75d18-128">- Detener y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="75d18-128">- Stop and quarantine</span></span>      |<span data-ttu-id="75d18-129">- Dirección URL de bloqueo (hora de hacer clic)</span><span class="sxs-lookup"><span data-stu-id="75d18-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="75d18-130">- Eliminar mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="75d18-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="75d18-131">- Correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="75d18-131">- Quarantine email</span></span><br/><span data-ttu-id="75d18-132">- Poner en cuarentena datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="75d18-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="75d18-133">- Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="75d18-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="75d18-134">Las acciones de corrección, ya sean pendientes de aprobación o ya completadas, se pueden ver en el [Centro de acciones](m365d-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="75d18-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="75d18-135">Acciones de corrección que siguen investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="75d18-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="75d18-136">Cuando se completa una investigación automatizada, se llega a un veredicto para cada elemento de prueba implicado.</span><span class="sxs-lookup"><span data-stu-id="75d18-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="75d18-137">Según el veredicto, se identifican las acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="75d18-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="75d18-138">En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación.</span><span class="sxs-lookup"><span data-stu-id="75d18-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="75d18-139">Todo depende de cómo se configure [la investigación automatizada y la respuesta](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="75d18-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="75d18-140">En la tabla siguiente se muestran los posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="75d18-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="75d18-141">Veredicto</span><span class="sxs-lookup"><span data-stu-id="75d18-141">Verdict</span></span>    | <span data-ttu-id="75d18-142">Área</span><span class="sxs-lookup"><span data-stu-id="75d18-142">Area</span></span>    | <span data-ttu-id="75d18-143">Resultados</span><span class="sxs-lookup"><span data-stu-id="75d18-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="75d18-144">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="75d18-144">Malicious</span></span>    | <span data-ttu-id="75d18-145">Dispositivos (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="75d18-145">Devices (endpoints)</span></span>    | <span data-ttu-id="75d18-146">Las acciones de corrección se toman automáticamente [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) (suponiendo que los grupos de dispositivos de la organización estén establecidos en **Full - remediar las amenazas automáticamente)**</span><span class="sxs-lookup"><span data-stu-id="75d18-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="75d18-147">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="75d18-147">Malicious</span></span>    | <span data-ttu-id="75d18-148">Contenido de correo electrónico (URL y datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="75d18-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="75d18-149">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="75d18-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="75d18-150">Sospechoso</span><span class="sxs-lookup"><span data-stu-id="75d18-150">Suspicious</span></span>    | <span data-ttu-id="75d18-151">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="75d18-151">Devices or email content</span></span> | <span data-ttu-id="75d18-152">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="75d18-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="75d18-153">No se encontraron amenazas</span><span class="sxs-lookup"><span data-stu-id="75d18-153">No threats found</span></span>    | <span data-ttu-id="75d18-154">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="75d18-154">Devices or email content</span></span>    | <span data-ttu-id="75d18-155">No es necesario realizar ninguna acción correctiva</span><span class="sxs-lookup"><span data-stu-id="75d18-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="75d18-156">Acciones de corrección que se toman manualmente</span><span class="sxs-lookup"><span data-stu-id="75d18-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="75d18-157">Además de las acciones de corrección que siguen investigaciones automatizadas, el equipo de operaciones de seguridad puede realizar determinadas acciones de corrección manualmente.</span><span class="sxs-lookup"><span data-stu-id="75d18-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="75d18-158">Entre ellas se incluyen las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="75d18-158">These include the following actions:</span></span>

- <span data-ttu-id="75d18-159">Acción manual del dispositivo, como aislamiento del dispositivo o cuarentena de archivos.</span><span class="sxs-lookup"><span data-stu-id="75d18-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="75d18-160">Acción de correo electrónico manual, como la eliminación de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75d18-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="75d18-161">[Acción de búsqueda](../defender-endpoint/advanced-hunting-overview.md) avanzada en dispositivos o correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75d18-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="75d18-162">[Acción](../defender-365-security/threat-explorer.md) del explorador en el contenido de correo electrónico, como mover el correo electrónico a correo no deseado, eliminar correo electrónico de forma suave o eliminar correo electrónico de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="75d18-162">[Explorer](../defender-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="75d18-163">Acción [de respuesta en](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) directo manual, como eliminar un archivo, detener un proceso y quitar una tarea programada.</span><span class="sxs-lookup"><span data-stu-id="75d18-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="75d18-164">Acción de respuesta en directo con [Microsoft Defender para](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)API de punto de conexión, como aislar un dispositivo, ejecutar un examen antivirus y obtener información sobre un archivo.</span><span class="sxs-lookup"><span data-stu-id="75d18-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="75d18-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="75d18-165">Next steps</span></span>

- [<span data-ttu-id="75d18-166">Visite el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="75d18-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="75d18-167">Ver y administrar acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="75d18-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="75d18-168">Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="75d18-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
