---
title: Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft
description: Obtener información general sobre las acciones de corrección que siguen las investigaciones automatizadas en protección contra amenazas de Microsoft
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502942"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="c0cac-104">Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0cac-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="c0cac-105">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="c0cac-105">**Applies to:**</span></span>
- <span data-ttu-id="c0cac-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0cac-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="c0cac-107">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="c0cac-107">Remediation actions</span></span>

<span data-ttu-id="c0cac-108">Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos.</span><span class="sxs-lookup"><span data-stu-id="c0cac-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="c0cac-109">Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="c0cac-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="c0cac-110">Otras acciones de corrección se realizan en el contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0cac-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="c0cac-111">Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="c0cac-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="c0cac-112">En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c0cac-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="c0cac-113">Acciones de corrección de dispositivo (extremo)</span><span class="sxs-lookup"><span data-stu-id="c0cac-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="c0cac-114">Acciones de corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c0cac-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="c0cac-115">-Recopilar un paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="c0cac-115">- Collect investigation package</span></span> <br/><span data-ttu-id="c0cac-116">-Isolater dispositivo (esta acción se puede deshacer)</span><span class="sxs-lookup"><span data-stu-id="c0cac-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="c0cac-117">-Máquina desincorpora</span><span class="sxs-lookup"><span data-stu-id="c0cac-117">- Offboard machine</span></span> <br/><span data-ttu-id="c0cac-118">-Liberar la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="c0cac-118">- Release code execution</span></span> <br/><span data-ttu-id="c0cac-119">-Liberar de cuarentena</span><span class="sxs-lookup"><span data-stu-id="c0cac-119">- Release from quarantine</span></span> <br/><span data-ttu-id="c0cac-120">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="c0cac-120">- Request sample</span></span> <br/><span data-ttu-id="c0cac-121">-Restringir la ejecución de código (esta acción se puede deshacer)</span><span class="sxs-lookup"><span data-stu-id="c0cac-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="c0cac-122">-Ejecutar detección de virus</span><span class="sxs-lookup"><span data-stu-id="c0cac-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="c0cac-123">-Detener y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="c0cac-123">- Stop and quarantine</span></span>      |<span data-ttu-id="c0cac-124">-Bloquear dirección URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="c0cac-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="c0cac-125">-Eliminación temporal de mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="c0cac-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="c0cac-126">-Correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="c0cac-126">- Quarantine email</span></span><br/><span data-ttu-id="c0cac-127">-Poner en cuarentena un archivo adjunto de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c0cac-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="c0cac-128">-Desactivar el reenvío externo de correo</span><span class="sxs-lookup"><span data-stu-id="c0cac-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="c0cac-129">Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="c0cac-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="c0cac-130">Las acciones de corrección siguen las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="c0cac-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="c0cac-131">Cuando una investigación automatizada se completa, se llega a un veredicto para cada evidencia involucrada, y se identifican las acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="c0cac-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="c0cac-132">En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación.</span><span class="sxs-lookup"><span data-stu-id="c0cac-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="c0cac-133">En la tabla siguiente se muestran los posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="c0cac-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="c0cac-134">Veredicto</span><span class="sxs-lookup"><span data-stu-id="c0cac-134">Verdict</span></span>    |<span data-ttu-id="c0cac-135">Área</span><span class="sxs-lookup"><span data-stu-id="c0cac-135">Area</span></span>    |<span data-ttu-id="c0cac-136">Resultados</span><span class="sxs-lookup"><span data-stu-id="c0cac-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="c0cac-137">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="c0cac-137">Malicious</span></span>    |<span data-ttu-id="c0cac-138">Dispositivos (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="c0cac-138">Devices (endpoints)</span></span>    |<span data-ttu-id="c0cac-139">Las acciones de corrección se toman automáticamente</span><span class="sxs-lookup"><span data-stu-id="c0cac-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="c0cac-140">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="c0cac-140">Malicious</span></span>    |<span data-ttu-id="c0cac-141">Contenido de correo electrónico (URL y datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="c0cac-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="c0cac-142">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="c0cac-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="c0cac-143">Sospechoso</span><span class="sxs-lookup"><span data-stu-id="c0cac-143">Suspicious</span></span>    |<span data-ttu-id="c0cac-144">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c0cac-144">Devices or email content</span></span> |<span data-ttu-id="c0cac-145">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="c0cac-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="c0cac-146">No se encontraron amenazas</span><span class="sxs-lookup"><span data-stu-id="c0cac-146">No threats found</span></span>    |<span data-ttu-id="c0cac-147">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c0cac-147">Devices or email content</span></span>    |<span data-ttu-id="c0cac-148">No es necesario realizar ninguna acción correctiva</span><span class="sxs-lookup"><span data-stu-id="c0cac-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="c0cac-149">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="c0cac-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="c0cac-150">Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="c0cac-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="c0cac-151">[Informar de falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="c0cac-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0cac-152">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="c0cac-152">Next steps</span></span>

- [<span data-ttu-id="c0cac-153">Aprobar o rechazar acciones</span><span class="sxs-lookup"><span data-stu-id="c0cac-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="c0cac-154">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="c0cac-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
