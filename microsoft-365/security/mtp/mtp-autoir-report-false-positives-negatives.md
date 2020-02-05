---
title: Cómo informar de falsos positivos o falsos negativos en AIR en la protección contra amenazas de Microsoft
description: ¿Perdió o se detectó un error por aire en la protección contra amenazas de Microsoft? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 1177f552652e728928a2b1d322b4ce0217415509
ms.sourcegitcommit: ca2209d9176f99048d0a7adc20261029ca23dcbd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "41774196"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="2e2b7-105">Cómo informar de falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="2e2b7-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="2e2b7-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2e2b7-106">**Applies to:**</span></span>
- <span data-ttu-id="2e2b7-107">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e2b7-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2e2b7-108">¿Las [capacidades automatizadas de investigación y respuesta](mtp-autoir.md) en Microsoft Threat Protection no se han detectado o no detectan nada correctamente?</span><span class="sxs-lookup"><span data-stu-id="2e2b7-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="2e2b7-109">Hay pasos que puede llevar a cabo para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="2e2b7-110">Puede:</span><span class="sxs-lookup"><span data-stu-id="2e2b7-110">You can:</span></span>
- <span data-ttu-id="2e2b7-111">[Informar de un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="2e2b7-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="2e2b7-112">[Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y</span><span class="sxs-lookup"><span data-stu-id="2e2b7-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="2e2b7-113">[Deshacer las acciones de corrección que se tomaron en los dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="2e2b7-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="2e2b7-114">Use este artículo como guía.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="2e2b7-115">Informar de un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="2e2b7-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="2e2b7-116">El elemento perdió o no se detectó correctamente</span><span class="sxs-lookup"><span data-stu-id="2e2b7-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="2e2b7-117">Servicio</span><span class="sxs-lookup"><span data-stu-id="2e2b7-117">Service</span></span>  |<span data-ttu-id="2e2b7-118">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="2e2b7-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2e2b7-119">-Mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2e2b7-119">- Email message</span></span> <br/><span data-ttu-id="2e2b7-120">-Datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2e2b7-120">- Email attachment</span></span> <br/><span data-ttu-id="2e2b7-121">-URL en un mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2e2b7-121">- URL in an email message</span></span><br/><span data-ttu-id="2e2b7-122">-URL en un archivo de Office</span><span class="sxs-lookup"><span data-stu-id="2e2b7-122">- URL in an Office file</span></span>      |[<span data-ttu-id="2e2b7-123">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="2e2b7-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="2e2b7-124">Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para Office 365 Scanning</span><span class="sxs-lookup"><span data-stu-id="2e2b7-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="2e2b7-125">Archivo o aplicación en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="2e2b7-125">File or app on a device</span></span>    |[<span data-ttu-id="2e2b7-126">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2e2b7-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="2e2b7-127">Enviar un archivo a Microsoft para el análisis de malware</span><span class="sxs-lookup"><span data-stu-id="2e2b7-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="2e2b7-128">Ajustar una alerta para evitar que se repitan falsos positivos</span><span class="sxs-lookup"><span data-stu-id="2e2b7-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="2e2b7-129">Escenario</span><span class="sxs-lookup"><span data-stu-id="2e2b7-129">Scenario</span></span> |<span data-ttu-id="2e2b7-130">Servicio</span><span class="sxs-lookup"><span data-stu-id="2e2b7-130">Service</span></span> |<span data-ttu-id="2e2b7-131">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="2e2b7-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="2e2b7-132">-El uso legítimo desencadena una alerta</span><span class="sxs-lookup"><span data-stu-id="2e2b7-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="2e2b7-133">-Una alerta no es precisa</span><span class="sxs-lookup"><span data-stu-id="2e2b7-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="2e2b7-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2e2b7-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="2e2b7-135">o</span><span class="sxs-lookup"><span data-stu-id="2e2b7-135">or</span></span> <br/>[<span data-ttu-id="2e2b7-136">Detección de amenazas avanzadas de Azure</span><span class="sxs-lookup"><span data-stu-id="2e2b7-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="2e2b7-137">Administrar alertas en Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="2e2b7-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="2e2b7-138">Un archivo, una dirección IP, una dirección URL o un dominio se trata como malware en un dispositivo, aunque sea seguro</span><span class="sxs-lookup"><span data-stu-id="2e2b7-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="2e2b7-139">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2e2b7-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="2e2b7-140">Crear un indicador personalizado con una acción "permitir"</span><span class="sxs-lookup"><span data-stu-id="2e2b7-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="2e2b7-141">Deshacer una acción de corrección que se ha realizado en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="2e2b7-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="2e2b7-142">Si se realizó una acción de corrección en un dispositivo (como un dispositivo de Windows 10) y el elemento está realmente limpio, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el [centro de actividades](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="2e2b7-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e2b7-143">Asegúrese de que tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de intentar realizar la siguiente tarea.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="2e2b7-144">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="2e2b7-145">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="2e2b7-146">En la ficha **historial** , seleccione la acción que desea deshacer.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="2e2b7-147">Se abrirá un control flotante.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="2e2b7-148">Use filtros para restringir la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="2e2b7-149">En el control flotante del elemento seleccionado, seleccione **abrir página de investigación**.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="2e2b7-150">En la vista detalles de la investigación, seleccione la ficha **acciones** .</span><span class="sxs-lookup"><span data-stu-id="2e2b7-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="2e2b7-151">Seleccione un elemento que tenga el estado **completado**y busque un vínculo, como **aprobado**, en la columna **decisiones** .</span><span class="sxs-lookup"><span data-stu-id="2e2b7-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="2e2b7-152">Se abrirá un control flotante con más detalles sobre la acción.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="2e2b7-153">Para deshacer la acción, seleccione **eliminar corrección**.</span><span class="sxs-lookup"><span data-stu-id="2e2b7-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2e2b7-154">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="2e2b7-154">Related articles</span></span>

- [<span data-ttu-id="2e2b7-155">Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="2e2b7-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="2e2b7-156">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="2e2b7-156">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="2e2b7-157">Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e2b7-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
