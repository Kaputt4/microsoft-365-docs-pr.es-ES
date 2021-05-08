---
title: Cómo notificar falsos positivos o falsos negativos después de una investigación automatizada en Microsoft Defender para Office 365
description: ¿Se ha detectado algo perdido o incorrecto por AIR en Microsoft Defender para Office 365? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275089"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="2667f-105">Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="2667f-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2667f-106">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="2667f-106">**Applies to**</span></span>
- [<span data-ttu-id="2667f-107">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2667f-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2667f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2667f-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2667f-109">Si las capacidades de investigación y respuesta [automatizadas (AIR)](automated-investigation-response-office.md) en Office 365 detectaron o detectaron algo incorrectamente, hay pasos que el equipo de operaciones de seguridad puede llevar a cabo para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="2667f-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="2667f-110">Estas acciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="2667f-110">Such actions include:</span></span>

- <span data-ttu-id="2667f-111">[Notificar un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="2667f-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="2667f-112">[Ajustar alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y</span><span class="sxs-lookup"><span data-stu-id="2667f-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="2667f-113">[Deshacer acciones de corrección que se han realizado](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="2667f-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="2667f-114">Use este artículo como guía.</span><span class="sxs-lookup"><span data-stu-id="2667f-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="2667f-115">Notificar un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="2667f-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="2667f-116">Si AIR en Microsoft Defender para Office 365 perdió un mensaje de correo electrónico, un archivo adjunto de correo electrónico, una dirección URL en un mensaje de correo electrónico o una dirección URL en un archivo Office, puede enviar correo no deseado [sospechoso, phish,](admin-submission.md)direcciones URL y archivos a Microsoft para examinar Office 365 .</span><span class="sxs-lookup"><span data-stu-id="2667f-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="2667f-117">También puede enviar [un archivo a Microsoft para el análisis de malware.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="2667f-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="2667f-118">Ajustar una alerta para evitar que los falsos positivos se repitan</span><span class="sxs-lookup"><span data-stu-id="2667f-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="2667f-119">Si una alerta se desencadena mediante un uso legítimo o la alerta es inexacta, puede administrar alertas [en el portal Cloud App Security](/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="2667f-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="2667f-120">Si tu organización usa [Microsoft Defender](/windows/security/threat-protection) para endpoint además de Office 365 y un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro, puedes crear un indicador personalizado con una acción ["Permitir"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)para el dispositivo .</span><span class="sxs-lookup"><span data-stu-id="2667f-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="2667f-121">Deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="2667f-121">Undo a remediation action</span></span>

<span data-ttu-id="2667f-122">En la mayoría de los casos, si se ha realizado una acción de corrección en un mensaje de correo electrónico, datos adjuntos de correo electrónico o una dirección URL, y el elemento en realidad no es una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección y tomar medidas para evitar que el falso positivo se repita.</span><span class="sxs-lookup"><span data-stu-id="2667f-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="2667f-123">Puede usar el Explorador [de amenazas](#undo-an-action-using-threat-explorer) o la pestaña Acciones para una [investigación para](#undo-an-action-in-the-action-center) deshacer una acción.</span><span class="sxs-lookup"><span data-stu-id="2667f-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2667f-124">Asegúrese de que tiene los permisos necesarios antes de intentar realizar las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="2667f-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="2667f-125">Deshacer una acción con el Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="2667f-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="2667f-126">Con el Explorador de amenazas, el equipo de operaciones de seguridad puede encontrar un correo electrónico afectado por una acción y potencialmente deshacer la acción.</span><span class="sxs-lookup"><span data-stu-id="2667f-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="2667f-127">Escenario</span><span class="sxs-lookup"><span data-stu-id="2667f-127">Scenario</span></span>|<span data-ttu-id="2667f-128">Opciones de deshacer</span><span class="sxs-lookup"><span data-stu-id="2667f-128">Undo Options</span></span>|<span data-ttu-id="2667f-129">Más información</span><span class="sxs-lookup"><span data-stu-id="2667f-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="2667f-130">Un mensaje de correo electrónico se enrutó a la carpeta correo no deseado de un usuario</span><span class="sxs-lookup"><span data-stu-id="2667f-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="2667f-131">- Mover el mensaje a la carpeta Elementos eliminados del usuario</span><span class="sxs-lookup"><span data-stu-id="2667f-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="2667f-132">- Mover el mensaje a la Bandeja de entrada del usuario</span><span class="sxs-lookup"><span data-stu-id="2667f-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="2667f-133">- Eliminar el mensaje</span><span class="sxs-lookup"><span data-stu-id="2667f-133">- Delete the message</span></span>|[<span data-ttu-id="2667f-134">Busque e investigue el correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="2667f-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="2667f-135">Se ha puesto en cuarentena un mensaje de correo electrónico o un archivo</span><span class="sxs-lookup"><span data-stu-id="2667f-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="2667f-136">- Liberar el correo electrónico o el archivo</span><span class="sxs-lookup"><span data-stu-id="2667f-136">- Release the email or file</span></span><br/><span data-ttu-id="2667f-137">- Eliminar el correo electrónico o el archivo</span><span class="sxs-lookup"><span data-stu-id="2667f-137">- Delete the email or file</span></span>|[<span data-ttu-id="2667f-138">Administrar mensajes en cuarentena como administrador</span><span class="sxs-lookup"><span data-stu-id="2667f-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="2667f-139">Deshacer una acción en el Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="2667f-139">Undo an action in the Action center</span></span>

<span data-ttu-id="2667f-140">En el Centro de acciones, puede ver las acciones de corrección que se realizaron y potencialmente deshacer la acción.</span><span class="sxs-lookup"><span data-stu-id="2667f-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="2667f-141">Vaya al centro Microsoft 365 de seguridad ( <https://security.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="2667f-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="2667f-142">En el panel de navegación, seleccione **Centro de acciones**.</span><span class="sxs-lookup"><span data-stu-id="2667f-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="2667f-143">Seleccione la **pestaña** Historial para ver la lista de acciones completadas.</span><span class="sxs-lookup"><span data-stu-id="2667f-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="2667f-144">Seleccione un elemento.</span><span class="sxs-lookup"><span data-stu-id="2667f-144">Select an item.</span></span> <span data-ttu-id="2667f-145">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="2667f-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="2667f-146">En el panel desplegable, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="2667f-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="2667f-147">(Solo las acciones que se pueden deshacer tendrán **un botón Deshacer).**</span><span class="sxs-lookup"><span data-stu-id="2667f-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="2667f-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="2667f-148">See also</span></span>

- [<span data-ttu-id="2667f-149">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2667f-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2667f-150">Investigaciones automatizadas en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2667f-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
