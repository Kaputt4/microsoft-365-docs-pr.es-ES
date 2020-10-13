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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 5106ef34f11cb43d74fa993fcdb820d6a5dce86f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429484"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="fae90-104">Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fae90-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fae90-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fae90-105">**Applies to:**</span></span>
- <span data-ttu-id="fae90-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fae90-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="fae90-107">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="fae90-107">Remediation actions</span></span>

<span data-ttu-id="fae90-108">Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos.</span><span class="sxs-lookup"><span data-stu-id="fae90-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="fae90-109">Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="fae90-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="fae90-110">Otras acciones de corrección se realizan en el contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fae90-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="fae90-111">Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="fae90-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="fae90-112">En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="fae90-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="fae90-113">Acciones de corrección de dispositivo (extremo)</span><span class="sxs-lookup"><span data-stu-id="fae90-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="fae90-114">Acciones de corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fae90-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="fae90-115">-Recopilar un paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="fae90-115">- Collect investigation package</span></span> <br/><span data-ttu-id="fae90-116">-Isolater dispositivo (esta acción se puede deshacer)</span><span class="sxs-lookup"><span data-stu-id="fae90-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="fae90-117">-Máquina desincorpora</span><span class="sxs-lookup"><span data-stu-id="fae90-117">- Offboard machine</span></span> <br/><span data-ttu-id="fae90-118">-Liberar la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="fae90-118">- Release code execution</span></span> <br/><span data-ttu-id="fae90-119">-Liberar de cuarentena</span><span class="sxs-lookup"><span data-stu-id="fae90-119">- Release from quarantine</span></span> <br/><span data-ttu-id="fae90-120">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="fae90-120">- Request sample</span></span> <br/><span data-ttu-id="fae90-121">-Restringir la ejecución de código (esta acción se puede deshacer)</span><span class="sxs-lookup"><span data-stu-id="fae90-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="fae90-122">-Ejecutar detección de virus</span><span class="sxs-lookup"><span data-stu-id="fae90-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="fae90-123">-Detener y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="fae90-123">- Stop and quarantine</span></span>      |<span data-ttu-id="fae90-124">-Bloquear dirección URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="fae90-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="fae90-125">-Eliminación temporal de mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="fae90-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="fae90-126">-Correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="fae90-126">- Quarantine email</span></span><br/><span data-ttu-id="fae90-127">-Poner en cuarentena un archivo adjunto de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fae90-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="fae90-128">-Desactivar el reenvío externo de correo</span><span class="sxs-lookup"><span data-stu-id="fae90-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="fae90-129">Las acciones de corrección, ya estén pendientes de aprobación o ya completadas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="fae90-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="fae90-130">Las acciones de corrección siguen las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="fae90-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="fae90-131">Cuando se completa una investigación automatizada, se alcanza un veredicto para cada fragmento de evidencia implicado.</span><span class="sxs-lookup"><span data-stu-id="fae90-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="fae90-132">Según el veredicto, se identifican las acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="fae90-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="fae90-133">En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación.</span><span class="sxs-lookup"><span data-stu-id="fae90-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="fae90-134">Todo depende de cómo [esté configurada la investigación y la respuesta automatizadas](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="fae90-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="fae90-135">En la tabla siguiente se muestran los posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="fae90-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="fae90-136">Veredicto</span><span class="sxs-lookup"><span data-stu-id="fae90-136">Verdict</span></span>    |<span data-ttu-id="fae90-137">Área</span><span class="sxs-lookup"><span data-stu-id="fae90-137">Area</span></span>    |<span data-ttu-id="fae90-138">Resultados</span><span class="sxs-lookup"><span data-stu-id="fae90-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="fae90-139">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="fae90-139">Malicious</span></span>    |<span data-ttu-id="fae90-140">Dispositivos (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="fae90-140">Devices (endpoints)</span></span>    |<span data-ttu-id="fae90-141">Las acciones de corrección se realizan automáticamente (suponiendo que los [grupos de dispositivos](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) de la organización están configurados automáticamente para las amenazas de corrección **completa**)</span><span class="sxs-lookup"><span data-stu-id="fae90-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="fae90-142">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="fae90-142">Malicious</span></span>    |<span data-ttu-id="fae90-143">Contenido de correo electrónico (URL y datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="fae90-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="fae90-144">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="fae90-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="fae90-145">Sospechoso</span><span class="sxs-lookup"><span data-stu-id="fae90-145">Suspicious</span></span>    |<span data-ttu-id="fae90-146">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fae90-146">Devices or email content</span></span> |<span data-ttu-id="fae90-147">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="fae90-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="fae90-148">No se encontraron amenazas</span><span class="sxs-lookup"><span data-stu-id="fae90-148">No threats found</span></span>    |<span data-ttu-id="fae90-149">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fae90-149">Devices or email content</span></span>    |<span data-ttu-id="fae90-150">No es necesario realizar ninguna acción correctiva</span><span class="sxs-lookup"><span data-stu-id="fae90-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="fae90-151">El hecho de que las acciones de corrección se tomen automáticamente o solo tras la aprobación depende de determinadas opciones, como las directivas de grupo de dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="fae90-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="fae90-152">Para obtener más información, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="fae90-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="fae90-153">Configuración de capacidades de investigación y respuesta automatizadas en Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fae90-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="fae90-154">Cómo se corrigen las amenazas en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fae90-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="fae90-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fae90-155">Next steps</span></span>

- [<span data-ttu-id="fae90-156">Visite el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="fae90-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="fae90-157">Aprobar o rechazar acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="fae90-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="fae90-158">Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="fae90-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
