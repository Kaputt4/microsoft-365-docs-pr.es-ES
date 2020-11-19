---
title: Cómo informar de falsos positivos o falsos negativos tras la investigación automatizada en Microsoft defender para Office 365
description: ¿Perdió o se detectó un error por aire en Microsoft defender para Office 365? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
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
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 27edc44145e7b61768d9caf00a3f308e8561d708
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357404"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="a54aa-105">Cómo informar de falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="a54aa-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a54aa-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a54aa-106">**Applies to:**</span></span>
- <span data-ttu-id="a54aa-107">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a54aa-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a54aa-108">¿Las [capacidades de investigación y respuesta automatizadas (Air) de Office 365](automated-investigation-response-office.md) pierden o detectaron algo erróneamente?</span><span class="sxs-lookup"><span data-stu-id="a54aa-108">Did [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) miss or wrongly detect something?</span></span> <span data-ttu-id="a54aa-109">Hay pasos que puede llevar a cabo para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="a54aa-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="a54aa-110">Puede:</span><span class="sxs-lookup"><span data-stu-id="a54aa-110">You can:</span></span>

- <span data-ttu-id="a54aa-111">[Informar de un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="a54aa-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="a54aa-112">[Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y</span><span class="sxs-lookup"><span data-stu-id="a54aa-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="a54aa-113">[Deshacer las acciones de corrección que se tomaron](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="a54aa-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="a54aa-114">Use este artículo como guía.</span><span class="sxs-lookup"><span data-stu-id="a54aa-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="a54aa-115">Informar de un falso positivo/negativo a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="a54aa-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="a54aa-116">Si el aire de Microsoft defender para Office 365 perdió un mensaje de correo electrónico, un archivo adjunto de correo electrónico, una dirección URL en un mensaje de correo electrónico o una dirección URL en un archivo de Office, puede [Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para la detección de office 365](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a54aa-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="a54aa-117">También puede [Enviar un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="a54aa-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="a54aa-118">Ajustar una alerta para evitar que se repitan falsos positivos</span><span class="sxs-lookup"><span data-stu-id="a54aa-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="a54aa-119">Si una alerta se activa por uso legítimo, o la alerta no es precisa, puede [administrar las alertas en Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="a54aa-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="a54aa-120">Si su organización usa [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection) además de Office 365 y un archivo, una dirección IP, una dirección URL o un dominio se trata como malware en un dispositivo, aunque sea seguro, puede [crear un indicador personalizado con una acción "permitir" para el dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="a54aa-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="a54aa-121">Deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="a54aa-121">Undo a remediation action</span></span>

<span data-ttu-id="a54aa-122">En la mayoría de los casos, si se realizó una acción de corrección en un mensaje de correo electrónico, un archivo adjunto de correo electrónico o una dirección URL, y el elemento no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección y tomar medidas para evitar que el falso positivo se repita.</span><span class="sxs-lookup"><span data-stu-id="a54aa-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="a54aa-123">Puede usar el [Explorador de amenazas](#undo-an-action-using-threat-explorer) o la [ficha acciones para realizar una investigación](#undo-an-action-using-the-actions-tab-for-an-investigation) y deshacer una acción.</span><span class="sxs-lookup"><span data-stu-id="a54aa-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a54aa-124">Asegúrese de que tiene los permisos necesarios antes de intentar realizar las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="a54aa-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="a54aa-125">Deshacer una acción con el explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="a54aa-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="a54aa-126">Con el explorador de amenazas, el equipo de operaciones de seguridad puede encontrar un correo electrónico afectado por una acción y, potencialmente, deshacer la acción.</span><span class="sxs-lookup"><span data-stu-id="a54aa-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="a54aa-127">Escenario</span><span class="sxs-lookup"><span data-stu-id="a54aa-127">Scenario</span></span>|<span data-ttu-id="a54aa-128">Opciones de deshacer</span><span class="sxs-lookup"><span data-stu-id="a54aa-128">Undo Options</span></span>|<span data-ttu-id="a54aa-129">Más información</span><span class="sxs-lookup"><span data-stu-id="a54aa-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="a54aa-130">Un mensaje de correo electrónico se enrutó a la carpeta de correo electrónico no deseado de un usuario</span><span class="sxs-lookup"><span data-stu-id="a54aa-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="a54aa-131">Mover el mensaje a la carpeta elementos eliminados del usuario</span><span class="sxs-lookup"><span data-stu-id="a54aa-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="a54aa-132">Mover el mensaje a la bandeja de entrada del usuario</span><span class="sxs-lookup"><span data-stu-id="a54aa-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="a54aa-133">Eliminar el mensaje</span><span class="sxs-lookup"><span data-stu-id="a54aa-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="a54aa-134">Buscar e investigar correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="a54aa-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="a54aa-135">Un mensaje de correo electrónico o un archivo se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="a54aa-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="a54aa-136">Liberar el correo electrónico o el archivo</span><span class="sxs-lookup"><span data-stu-id="a54aa-136">Release the email or file</span></span></li><li><span data-ttu-id="a54aa-137">Eliminar el correo electrónico o el archivo</span><span class="sxs-lookup"><span data-stu-id="a54aa-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="a54aa-138">Administrar mensajes en cuarentena como administrador</span><span class="sxs-lookup"><span data-stu-id="a54aa-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="a54aa-139">Deshacer una acción con la ficha acciones para una investigación</span><span class="sxs-lookup"><span data-stu-id="a54aa-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="a54aa-140">En el centro de actividades, puede ver las acciones de corrección que se han realizado y, potencialmente, deshacer la acción.</span><span class="sxs-lookup"><span data-stu-id="a54aa-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="a54aa-141">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a54aa-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="a54aa-142">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a54aa-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="a54aa-143">Vaya a investigaciones de **Administración de amenazas**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="a54aa-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="a54aa-144">En la lista de investigaciones, seleccione el icono **abrir en ventana nueva** junto al identificador de un elemento.</span><span class="sxs-lookup"><span data-stu-id="a54aa-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="a54aa-145">Seleccione la ficha **acciones** .</span><span class="sxs-lookup"><span data-stu-id="a54aa-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="a54aa-146">Seleccione un elemento que tenga el estado **completado** y busque un vínculo, como **aprobado**, en la columna **decisión** .</span><span class="sxs-lookup"><span data-stu-id="a54aa-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="a54aa-147">Se abrirá un control flotante con más detalles sobre la acción.</span><span class="sxs-lookup"><span data-stu-id="a54aa-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="a54aa-148">Para deshacer la acción, seleccione **eliminar corrección**.</span><span class="sxs-lookup"><span data-stu-id="a54aa-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a54aa-149">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a54aa-149">Related articles</span></span>

[<span data-ttu-id="a54aa-150">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a54aa-150">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="a54aa-151">AIR en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a54aa-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
