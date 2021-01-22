---
title: Controlar falsos positivos o falsos negativos en AIR en Microsoft 365 Defender
description: ¿Se ha detectado algo perdido o detectado incorrectamente por AIR en Microsoft 365 Defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930359"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="7af68-105">Controlar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="7af68-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7af68-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7af68-106">**Applies to:**</span></span>
- <span data-ttu-id="7af68-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7af68-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="7af68-108">¿Las [capacidades automatizadas de](mtp-autoir.md) investigación y respuesta en Microsoft 365 Defender no detectaron o detectaron algo incorrectamente?</span><span class="sxs-lookup"><span data-stu-id="7af68-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="7af68-109">Hay pasos que puede seguir para corregirlo.</span><span class="sxs-lookup"><span data-stu-id="7af68-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="7af68-110">Puede:</span><span class="sxs-lookup"><span data-stu-id="7af68-110">You can:</span></span>

- <span data-ttu-id="7af68-111">[Notificar un falso positivo/negativo a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="7af68-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="7af68-112">[Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y</span><span class="sxs-lookup"><span data-stu-id="7af68-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="7af68-113">[Deshacer acciones de corrección realizadas en dispositivos.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="7af68-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="7af68-114">Use este artículo como guía.</span><span class="sxs-lookup"><span data-stu-id="7af68-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="7af68-115">Notificar un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="7af68-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="7af68-116">Elemento perdido o detectado incorrectamente</span><span class="sxs-lookup"><span data-stu-id="7af68-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="7af68-117">Servicio</span><span class="sxs-lookup"><span data-stu-id="7af68-117">Service</span></span>  |<span data-ttu-id="7af68-118">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="7af68-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7af68-119">- Mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7af68-119">- Email message</span></span> <br/><span data-ttu-id="7af68-120">- Datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7af68-120">- Email attachment</span></span> <br/><span data-ttu-id="7af68-121">- Dirección URL en un mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7af68-121">- URL in an email message</span></span><br/><span data-ttu-id="7af68-122">- Dirección URL en un archivo de Office</span><span class="sxs-lookup"><span data-stu-id="7af68-122">- URL in an Office file</span></span>      |[<span data-ttu-id="7af68-123">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7af68-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="7af68-124">Enviar correos sospechosos de correo no deseado, phishing, direcciones URL y archivos a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="7af68-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="7af68-125">Archivo o aplicación en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="7af68-125">File or app on a device</span></span>    |[<span data-ttu-id="7af68-126">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7af68-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="7af68-127">Enviar un archivo a Microsoft para el análisis de malware</span><span class="sxs-lookup"><span data-stu-id="7af68-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="7af68-128">Ajustar una alerta para evitar que los falsos positivos se repitan</span><span class="sxs-lookup"><span data-stu-id="7af68-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="7af68-129">Escenario</span><span class="sxs-lookup"><span data-stu-id="7af68-129">Scenario</span></span> |<span data-ttu-id="7af68-130">Servicio</span><span class="sxs-lookup"><span data-stu-id="7af68-130">Service</span></span> |<span data-ttu-id="7af68-131">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="7af68-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="7af68-132">- Una alerta se desencadena por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="7af68-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="7af68-133">- Una alerta no es precisa</span><span class="sxs-lookup"><span data-stu-id="7af68-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="7af68-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7af68-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="7af68-135">Otra posibilidad:</span><span class="sxs-lookup"><span data-stu-id="7af68-135">or</span></span> <br/>[<span data-ttu-id="7af68-136">Detección avanzada de amenazas de Azure</span><span class="sxs-lookup"><span data-stu-id="7af68-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="7af68-137">Administrar alertas en el portal de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7af68-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="7af68-138">Un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro</span><span class="sxs-lookup"><span data-stu-id="7af68-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="7af68-139">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7af68-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="7af68-140">Crear un indicador personalizado con una acción "Permitir"</span><span class="sxs-lookup"><span data-stu-id="7af68-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="7af68-141">Deshacer una acción de corrección que se ha realizado en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="7af68-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="7af68-142">Si se ha realizado una acción de corrección en un dispositivo (como un dispositivo windows 10) y el elemento no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el Centro de [actividades.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="7af68-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7af68-143">Asegúrese de que tiene los [permisos necesarios antes](mtp-action-center.md#required-permissions-for-action-center-tasks) de intentar realizar la siguiente tarea.</span><span class="sxs-lookup"><span data-stu-id="7af68-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="7af68-144">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="7af68-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="7af68-145">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="7af68-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="7af68-146">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="7af68-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="7af68-147">Se abrirá un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="7af68-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="7af68-148">Use filtros para restringir la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="7af68-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="7af68-149">En el menú desplegable del elemento seleccionado, seleccione **Abrir página de investigación.**</span><span class="sxs-lookup"><span data-stu-id="7af68-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="7af68-150">En la vista de detalles de la investigación, seleccione la **pestaña** Acciones.</span><span class="sxs-lookup"><span data-stu-id="7af68-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="7af68-151">Seleccione un elemento que tenga el estado **Completado** y busque un vínculo, como **Aprobado,** en la **columna Decisiones.**</span><span class="sxs-lookup"><span data-stu-id="7af68-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="7af68-152">Se abrirá un menú desplegable con más detalles sobre la acción.</span><span class="sxs-lookup"><span data-stu-id="7af68-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="7af68-153">Para deshacer la acción, seleccione **Eliminar corrección.**</span><span class="sxs-lookup"><span data-stu-id="7af68-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af68-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7af68-154">See also</span></span>

- [<span data-ttu-id="7af68-155">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="7af68-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="7af68-156">Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7af68-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
