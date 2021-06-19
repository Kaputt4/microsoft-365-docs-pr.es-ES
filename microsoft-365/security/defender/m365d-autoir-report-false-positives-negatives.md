---
title: Dirección de falsos positivos o falsos negativos en Microsoft 365 Defender
description: ¿Se ha detectado algo perdido o incorrecto por AIR en Microsoft 365 Defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022539"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="447f5-105">Dirección de falsos positivos o falsos negativos en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="447f5-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="447f5-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="447f5-106">**Applies to:**</span></span>
- <span data-ttu-id="447f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="447f5-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="447f5-108">En ocasiones, se pueden producir falsos positivos o negativos con cualquier solución de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="447f5-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="447f5-109">Si [las capacidades automatizadas](m365d-autoir.md) de investigación y respuesta Microsoft 365 Defender detectan o detectan algo incorrectamente, hay pasos que el equipo de operaciones de seguridad puede seguir:</span><span class="sxs-lookup"><span data-stu-id="447f5-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="447f5-110">Notificar un falso positivo/negativo a Microsoft</span><span class="sxs-lookup"><span data-stu-id="447f5-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="447f5-111">[Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="447f5-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="447f5-112">Deshacer acciones de corrección realizadas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="447f5-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="447f5-113">En las secciones siguientes se describe cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="447f5-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="447f5-114">Notificar un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="447f5-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="447f5-115">Elemento perdido o detectado incorrectamente</span><span class="sxs-lookup"><span data-stu-id="447f5-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="447f5-116">Servicio</span><span class="sxs-lookup"><span data-stu-id="447f5-116">Service</span></span>  |<span data-ttu-id="447f5-117">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="447f5-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="447f5-118">- Mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="447f5-118">- Email message</span></span> <br/><span data-ttu-id="447f5-119">- Datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="447f5-119">- Email attachment</span></span> <br/><span data-ttu-id="447f5-120">- DIRECCIÓN URL en un mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="447f5-120">- URL in an email message</span></span><br/><span data-ttu-id="447f5-121">- DIRECCIÓN URL en un Office archivo</span><span class="sxs-lookup"><span data-stu-id="447f5-121">- URL in an Office file</span></span>      |[<span data-ttu-id="447f5-122">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="447f5-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="447f5-123">Enviar correo no deseado, phishing, direcciones URL y archivos sospechosos a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="447f5-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="447f5-124">Archivo o aplicación en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="447f5-124">File or app on a device</span></span>    |[<span data-ttu-id="447f5-125">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="447f5-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="447f5-126">Enviar un archivo a Microsoft para análisis de malware</span><span class="sxs-lookup"><span data-stu-id="447f5-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="447f5-127">Ajustar una alerta para evitar que los falsos positivos se repitan</span><span class="sxs-lookup"><span data-stu-id="447f5-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="447f5-128">Escenario</span><span class="sxs-lookup"><span data-stu-id="447f5-128">Scenario</span></span> |<span data-ttu-id="447f5-129">Servicio</span><span class="sxs-lookup"><span data-stu-id="447f5-129">Service</span></span> |<span data-ttu-id="447f5-130">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="447f5-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="447f5-131">- Una alerta se desencadena por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="447f5-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="447f5-132">- Una alerta es inexacta</span><span class="sxs-lookup"><span data-stu-id="447f5-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="447f5-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="447f5-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="447f5-134">o</span><span class="sxs-lookup"><span data-stu-id="447f5-134">or</span></span> <br/>[<span data-ttu-id="447f5-135">Protección contra amenazas de Azure</span><span class="sxs-lookup"><span data-stu-id="447f5-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="447f5-136">Administrar alertas en el portal Cloud App Security web</span><span class="sxs-lookup"><span data-stu-id="447f5-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="447f5-137">Un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro</span><span class="sxs-lookup"><span data-stu-id="447f5-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="447f5-138">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="447f5-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="447f5-139">Crear un indicador personalizado con una acción "Permitir"</span><span class="sxs-lookup"><span data-stu-id="447f5-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="447f5-140">Deshacer una acción de corrección que se ha realizado en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="447f5-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="447f5-141">Si se ha realizado una acción de corrección en una entidad (como un dispositivo o un mensaje de correo electrónico) y la entidad afectada no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el Centro de acciones [.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="447f5-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="447f5-142">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="447f5-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="447f5-143">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="447f5-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="447f5-144">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="447f5-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="447f5-145">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="447f5-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="447f5-146">En el panel desplegable, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="447f5-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="447f5-147">Vea [Deshacer acciones completadas](m365d-autoir-actions.md#undo-completed-actions).</span><span class="sxs-lookup"><span data-stu-id="447f5-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="447f5-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="447f5-148">See also</span></span>

- [<span data-ttu-id="447f5-149">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="447f5-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="447f5-150">Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="447f5-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
