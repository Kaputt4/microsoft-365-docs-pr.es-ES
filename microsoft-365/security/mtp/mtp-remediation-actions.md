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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266056"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="865cc-104">Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="865cc-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="865cc-105">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="865cc-105">**Applies to:**</span></span>
- <span data-ttu-id="865cc-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="865cc-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="865cc-107">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="865cc-107">Remediation actions</span></span>

<span data-ttu-id="865cc-108">Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos.</span><span class="sxs-lookup"><span data-stu-id="865cc-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="865cc-109">Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="865cc-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="865cc-110">Otras acciones de corrección se realizan en el contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="865cc-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="865cc-111">Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="865cc-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="865cc-112">En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="865cc-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="865cc-113">Acciones de corrección de dispositivo (extremo)</span><span class="sxs-lookup"><span data-stu-id="865cc-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="865cc-114">Acciones de corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="865cc-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="865cc-115">Poner archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="865cc-115">Quarantine file</span></span><br/><span data-ttu-id="865cc-116">Eliminar clave del registro</span><span class="sxs-lookup"><span data-stu-id="865cc-116">Remove registry key</span></span><br/><span data-ttu-id="865cc-117">Terminar proceso</span><span class="sxs-lookup"><span data-stu-id="865cc-117">Kill process</span></span> <br/><span data-ttu-id="865cc-118">Detener el servicio</span><span class="sxs-lookup"><span data-stu-id="865cc-118">Stop service</span></span> <br/><span data-ttu-id="865cc-119">Deshabilitar controlador</span><span class="sxs-lookup"><span data-stu-id="865cc-119">Disable driver</span></span> <br/><span data-ttu-id="865cc-120">Eliminar tarea programada.</span><span class="sxs-lookup"><span data-stu-id="865cc-120">Remove scheduled task</span></span>      |<span data-ttu-id="865cc-121">Eliminar temporalmente mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="865cc-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="865cc-122">Bloquear URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="865cc-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="865cc-123">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="865cc-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="865cc-124">Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="865cc-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="865cc-125">Veredictos y resultados tras las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="865cc-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="865cc-126">Cuando una investigación automatizada se completa, se llega a un veredicto para cada evidencia involucrada, y se identifican las acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="865cc-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="865cc-127">En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación.</span><span class="sxs-lookup"><span data-stu-id="865cc-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="865cc-128">En la tabla siguiente se muestran los posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="865cc-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="865cc-129">Veredicto</span><span class="sxs-lookup"><span data-stu-id="865cc-129">Verdict</span></span>    |<span data-ttu-id="865cc-130">Área</span><span class="sxs-lookup"><span data-stu-id="865cc-130">Area</span></span>   |<span data-ttu-id="865cc-131">Resultados</span><span class="sxs-lookup"><span data-stu-id="865cc-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="865cc-132">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="865cc-132">Malicious</span></span>  |<span data-ttu-id="865cc-133">Dispositivos (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="865cc-133">Devices (endpoints)</span></span>    |<span data-ttu-id="865cc-134">Las acciones de corrección se toman automáticamente</span><span class="sxs-lookup"><span data-stu-id="865cc-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="865cc-135">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="865cc-135">Malicious</span></span>  |<span data-ttu-id="865cc-136">Contenido de correo electrónico (URL y datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="865cc-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="865cc-137">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="865cc-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="865cc-138">Sospechoso</span><span class="sxs-lookup"><span data-stu-id="865cc-138">Suspicious</span></span> |<span data-ttu-id="865cc-139">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="865cc-139">Devices or email content</span></span> |<span data-ttu-id="865cc-140">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="865cc-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="865cc-141">Limpiar</span><span class="sxs-lookup"><span data-stu-id="865cc-141">Clean</span></span>  |<span data-ttu-id="865cc-142">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="865cc-142">Devices or email content</span></span>   |<span data-ttu-id="865cc-143">No es necesario realizar ninguna acción correctiva</span><span class="sxs-lookup"><span data-stu-id="865cc-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="865cc-144">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="865cc-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="865cc-145">Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="865cc-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="865cc-146">[Informar de falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="865cc-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="865cc-147">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="865cc-147">Next steps</span></span>

- [<span data-ttu-id="865cc-148">Aprobar o rechazar acciones</span><span class="sxs-lookup"><span data-stu-id="865cc-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="865cc-149">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="865cc-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
