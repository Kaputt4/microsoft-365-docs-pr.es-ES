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
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955596"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="3ebb7-104">Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ebb7-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="3ebb7-105">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="3ebb7-105">**Applies to:**</span></span>
- <span data-ttu-id="3ebb7-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ebb7-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="3ebb7-107">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="3ebb7-107">Remediation actions</span></span>

<span data-ttu-id="3ebb7-108">Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="3ebb7-109">Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="3ebb7-110">Otras acciones de corrección se realizan en el contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="3ebb7-111">Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="3ebb7-112">En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3ebb7-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="3ebb7-113">Acciones de corrección de dispositivo (extremo)</span><span class="sxs-lookup"><span data-stu-id="3ebb7-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="3ebb7-114">Acciones de corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3ebb7-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="3ebb7-115">Poner archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="3ebb7-115">Quarantine file</span></span><br/><span data-ttu-id="3ebb7-116">Eliminar clave del registro</span><span class="sxs-lookup"><span data-stu-id="3ebb7-116">Remove registry key</span></span><br/><span data-ttu-id="3ebb7-117">Terminar proceso</span><span class="sxs-lookup"><span data-stu-id="3ebb7-117">Kill process</span></span> <br/><span data-ttu-id="3ebb7-118">Detener el servicio</span><span class="sxs-lookup"><span data-stu-id="3ebb7-118">Stop service</span></span> <br/><span data-ttu-id="3ebb7-119">Deshabilitar controlador</span><span class="sxs-lookup"><span data-stu-id="3ebb7-119">Disable driver</span></span> <br/><span data-ttu-id="3ebb7-120">Eliminar tarea programada.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-120">Remove scheduled task</span></span>      |<span data-ttu-id="3ebb7-121">Eliminar temporalmente mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="3ebb7-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="3ebb7-122">Bloquear URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="3ebb7-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="3ebb7-123">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="3ebb7-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="3ebb7-124">Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="3ebb7-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="3ebb7-125">Las acciones de corrección siguen las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="3ebb7-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="3ebb7-126">Cuando una investigación automatizada se completa, se llega a un veredicto para cada evidencia involucrada, y se identifican las acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="3ebb7-127">En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="3ebb7-128">En la tabla siguiente se muestran los posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="3ebb7-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="3ebb7-129">Veredicto</span><span class="sxs-lookup"><span data-stu-id="3ebb7-129">Verdict</span></span>    |<span data-ttu-id="3ebb7-130">Área</span><span class="sxs-lookup"><span data-stu-id="3ebb7-130">Area</span></span>    |<span data-ttu-id="3ebb7-131">Resultados</span><span class="sxs-lookup"><span data-stu-id="3ebb7-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="3ebb7-132">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="3ebb7-132">Malicious</span></span>    |<span data-ttu-id="3ebb7-133">Dispositivos (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="3ebb7-133">Devices (endpoints)</span></span>    |<span data-ttu-id="3ebb7-134">Las acciones de corrección se toman automáticamente</span><span class="sxs-lookup"><span data-stu-id="3ebb7-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="3ebb7-135">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="3ebb7-135">Malicious</span></span>    |<span data-ttu-id="3ebb7-136">Contenido de correo electrónico (URL y datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="3ebb7-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="3ebb7-137">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="3ebb7-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="3ebb7-138">Sospechoso</span><span class="sxs-lookup"><span data-stu-id="3ebb7-138">Suspicious</span></span>    |<span data-ttu-id="3ebb7-139">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3ebb7-139">Devices or email content</span></span> |<span data-ttu-id="3ebb7-140">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="3ebb7-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="3ebb7-141">No se encontraron amenazas</span><span class="sxs-lookup"><span data-stu-id="3ebb7-141">No threats found</span></span>    |<span data-ttu-id="3ebb7-142">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3ebb7-142">Devices or email content</span></span>    |<span data-ttu-id="3ebb7-143">No es necesario realizar ninguna acción correctiva</span><span class="sxs-lookup"><span data-stu-id="3ebb7-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="3ebb7-144">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="3ebb7-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="3ebb7-145">Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="3ebb7-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="3ebb7-146">[Informar de falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="3ebb7-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ebb7-147">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="3ebb7-147">Next steps</span></span>

- [<span data-ttu-id="3ebb7-148">Aprobar o rechazar acciones</span><span class="sxs-lookup"><span data-stu-id="3ebb7-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="3ebb7-149">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="3ebb7-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
