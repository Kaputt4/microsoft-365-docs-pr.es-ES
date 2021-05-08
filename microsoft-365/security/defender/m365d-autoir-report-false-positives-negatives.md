---
title: Dirección de falsos positivos o falsos negativos en Microsoft 365 Defender
description: ¿Se ha detectado algo incorrecto o perdido por AIR en Microsoft 365 Defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
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
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269585"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="83209-105">Dirección de falsos positivos o falsos negativos en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83209-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="83209-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="83209-106">**Applies to:**</span></span>
- <span data-ttu-id="83209-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83209-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="83209-108">En ocasiones, se pueden producir falsos positivos o negativos con cualquier solución de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="83209-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="83209-109">Si [las capacidades automatizadas](m365d-autoir.md) de investigación y respuesta en Microsoft 365 Defender no se detectaron o detectaron incorrectamente algo, hay pasos que el equipo de operaciones de seguridad puede seguir:</span><span class="sxs-lookup"><span data-stu-id="83209-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="83209-110">Notificar un falso positivo/negativo a Microsoft</span><span class="sxs-lookup"><span data-stu-id="83209-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="83209-111">[Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="83209-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="83209-112">Deshacer acciones de corrección realizadas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="83209-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="83209-113">En las secciones siguientes se describe cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="83209-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="83209-114">Notificar un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="83209-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="83209-115">Elemento perdido o detectado incorrectamente</span><span class="sxs-lookup"><span data-stu-id="83209-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="83209-116">Servicio</span><span class="sxs-lookup"><span data-stu-id="83209-116">Service</span></span>  |<span data-ttu-id="83209-117">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="83209-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="83209-118">- Mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="83209-118">- Email message</span></span> <br/><span data-ttu-id="83209-119">- Datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="83209-119">- Email attachment</span></span> <br/><span data-ttu-id="83209-120">- DIRECCIÓN URL en un mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="83209-120">- URL in an email message</span></span><br/><span data-ttu-id="83209-121">- DIRECCIÓN URL en un archivo de Office</span><span class="sxs-lookup"><span data-stu-id="83209-121">- URL in an Office file</span></span>      |[<span data-ttu-id="83209-122">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="83209-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="83209-123">Enviar correo no deseado, phishing, direcciones URL y archivos sospechosos a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="83209-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="83209-124">Archivo o aplicación en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="83209-124">File or app on a device</span></span>    |[<span data-ttu-id="83209-125">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="83209-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="83209-126">Enviar un archivo a Microsoft para análisis de malware</span><span class="sxs-lookup"><span data-stu-id="83209-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="83209-127">Ajustar una alerta para evitar que los falsos positivos se repitan</span><span class="sxs-lookup"><span data-stu-id="83209-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="83209-128">Escenario</span><span class="sxs-lookup"><span data-stu-id="83209-128">Scenario</span></span> |<span data-ttu-id="83209-129">Servicio</span><span class="sxs-lookup"><span data-stu-id="83209-129">Service</span></span> |<span data-ttu-id="83209-130">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="83209-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="83209-131">- Una alerta se desencadena por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="83209-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="83209-132">- Una alerta es inexacta</span><span class="sxs-lookup"><span data-stu-id="83209-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="83209-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="83209-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="83209-134">o</span><span class="sxs-lookup"><span data-stu-id="83209-134">or</span></span> <br/>[<span data-ttu-id="83209-135">Protección contra amenazas de Azure</span><span class="sxs-lookup"><span data-stu-id="83209-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="83209-136">Administrar alertas en el portal de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="83209-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="83209-137">Un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro</span><span class="sxs-lookup"><span data-stu-id="83209-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="83209-138">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="83209-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="83209-139">Crear un indicador personalizado con una acción "Permitir"</span><span class="sxs-lookup"><span data-stu-id="83209-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="83209-140">Deshacer una acción de corrección que se ha realizado en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="83209-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="83209-141">Si se ha realizado una acción de corrección en una entidad (como un dispositivo o un mensaje de correo electrónico) y la entidad afectada no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el Centro de acciones [.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="83209-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="83209-142">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="83209-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="83209-143">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="83209-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="83209-144">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="83209-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="83209-145">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="83209-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="83209-146">En el panel desplegable, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="83209-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="83209-147">Vea [Deshacer acciones completadas](m365d-autoir-actions.md#undo-completed-actions).</span><span class="sxs-lookup"><span data-stu-id="83209-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="83209-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="83209-148">See also</span></span>

- [<span data-ttu-id="83209-149">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="83209-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="83209-150">Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83209-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="83209-151">Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="83209-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)