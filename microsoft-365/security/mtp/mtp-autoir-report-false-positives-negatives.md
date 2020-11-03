---
title: Controlar falsos positivos o falsos negativos en AIR en Microsoft 365 defender
description: ¿Perdió o se detectó un error por aire en Microsoft 365 defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
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
ms.openlocfilehash: 92ad4a96665a5355bce7e3546f8c52779f770927
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843737"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="5fb7e-105">Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="5fb7e-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5fb7e-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5fb7e-106">**Applies to:**</span></span>
- <span data-ttu-id="5fb7e-107">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="5fb7e-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="5fb7e-108">¿Las [capacidades automatizadas de investigación y respuesta](mtp-autoir.md) en Microsoft 365 defender pierden o detectan algún problema?</span><span class="sxs-lookup"><span data-stu-id="5fb7e-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="5fb7e-109">Hay pasos que puede llevar a cabo para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="5fb7e-110">Puede:</span><span class="sxs-lookup"><span data-stu-id="5fb7e-110">You can:</span></span>

- <span data-ttu-id="5fb7e-111">[Informar de un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="5fb7e-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="5fb7e-112">[Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y</span><span class="sxs-lookup"><span data-stu-id="5fb7e-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="5fb7e-113">[Deshacer las acciones de corrección que se tomaron en los dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="5fb7e-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="5fb7e-114">Use este artículo como guía.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="5fb7e-115">Informar de un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="5fb7e-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="5fb7e-116">El elemento perdió o no se detectó correctamente</span><span class="sxs-lookup"><span data-stu-id="5fb7e-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="5fb7e-117">Servicio</span><span class="sxs-lookup"><span data-stu-id="5fb7e-117">Service</span></span>  |<span data-ttu-id="5fb7e-118">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="5fb7e-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5fb7e-119">-Mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5fb7e-119">- Email message</span></span> <br/><span data-ttu-id="5fb7e-120">-Datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5fb7e-120">- Email attachment</span></span> <br/><span data-ttu-id="5fb7e-121">-URL en un mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5fb7e-121">- URL in an email message</span></span><br/><span data-ttu-id="5fb7e-122">-URL en un archivo de Office</span><span class="sxs-lookup"><span data-stu-id="5fb7e-122">- URL in an Office file</span></span>      |[<span data-ttu-id="5fb7e-123">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5fb7e-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="5fb7e-124">Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="5fb7e-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="5fb7e-125">Archivo o aplicación en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="5fb7e-125">File or app on a device</span></span>    |[<span data-ttu-id="5fb7e-126">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5fb7e-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="5fb7e-127">Enviar un archivo a Microsoft para el análisis de malware</span><span class="sxs-lookup"><span data-stu-id="5fb7e-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="5fb7e-128">Ajustar una alerta para evitar que se repitan falsos positivos</span><span class="sxs-lookup"><span data-stu-id="5fb7e-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="5fb7e-129">Escenario</span><span class="sxs-lookup"><span data-stu-id="5fb7e-129">Scenario</span></span> |<span data-ttu-id="5fb7e-130">Servicio</span><span class="sxs-lookup"><span data-stu-id="5fb7e-130">Service</span></span> |<span data-ttu-id="5fb7e-131">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="5fb7e-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="5fb7e-132">-El uso legítimo desencadena una alerta</span><span class="sxs-lookup"><span data-stu-id="5fb7e-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="5fb7e-133">-Una alerta no es precisa</span><span class="sxs-lookup"><span data-stu-id="5fb7e-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="5fb7e-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5fb7e-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="5fb7e-135">o</span><span class="sxs-lookup"><span data-stu-id="5fb7e-135">or</span></span> <br/>[<span data-ttu-id="5fb7e-136">Detección de amenazas avanzadas de Azure</span><span class="sxs-lookup"><span data-stu-id="5fb7e-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="5fb7e-137">Administrar alertas en Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="5fb7e-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="5fb7e-138">Un archivo, una dirección IP, una dirección URL o un dominio se trata como malware en un dispositivo, aunque sea seguro</span><span class="sxs-lookup"><span data-stu-id="5fb7e-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="5fb7e-139">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5fb7e-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="5fb7e-140">Crear un indicador personalizado con una acción "permitir"</span><span class="sxs-lookup"><span data-stu-id="5fb7e-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="5fb7e-141">Deshacer una acción de corrección que se ha realizado en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="5fb7e-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="5fb7e-142">Si se realizó una acción de corrección en un dispositivo (como un dispositivo de Windows 10) y el elemento realmente no es una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el [centro de actividades](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="5fb7e-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fb7e-143">Asegúrese de que tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de intentar realizar la siguiente tarea.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="5fb7e-144">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="5fb7e-145">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="5fb7e-146">En la ficha **historial** , seleccione la acción que desea deshacer.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="5fb7e-147">Se abrirá un control flotante.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="5fb7e-148">Use filtros para restringir la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="5fb7e-149">En el control flotante del elemento seleccionado, seleccione **abrir página de investigación**.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="5fb7e-150">En la vista detalles de la investigación, seleccione la ficha **acciones** .</span><span class="sxs-lookup"><span data-stu-id="5fb7e-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="5fb7e-151">Seleccione un elemento que tenga el estado **completado** y busque un vínculo, como **aprobado** , en la columna **decisiones** .</span><span class="sxs-lookup"><span data-stu-id="5fb7e-151">Select an item that has status of **Completed** , and look for a link, such as **Approved** , in the **Decisions** column.</span></span> <span data-ttu-id="5fb7e-152">Se abrirá un control flotante con más detalles sobre la acción.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="5fb7e-153">Para deshacer la acción, seleccione **eliminar corrección**.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fb7e-154">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5fb7e-154">See also</span></span>

- [<span data-ttu-id="5fb7e-155">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="5fb7e-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="5fb7e-156">Buscar de forma proactiva amenazas con búsqueda avanzada en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="5fb7e-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
