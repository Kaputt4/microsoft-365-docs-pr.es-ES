---
title: Cómo informar de falsos positivos o falsos negativos en AIR en la protección contra amenazas de Microsoft
description: ¿Perdió o se detectó un error por aire en la protección contra amenazas de Microsoft? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260198"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f965d-105">Cómo informar de falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="f965d-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="f965d-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f965d-106">**Applies to:**</span></span>
- <span data-ttu-id="f965d-107">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f965d-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f965d-108">¿Las [capacidades automatizadas de investigación y respuesta](mtp-autoir.md) en Microsoft Threat Protection no se han detectado o no detectan nada correctamente?</span><span class="sxs-lookup"><span data-stu-id="f965d-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="f965d-109">Puede informar a Microsoft o ajustar sus avisos (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="f965d-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="f965d-110">Use la tabla siguiente como guía:</span><span class="sxs-lookup"><span data-stu-id="f965d-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="f965d-111">Item</span><span class="sxs-lookup"><span data-stu-id="f965d-111">Item</span></span>  |<span data-ttu-id="f965d-112">Detectado por</span><span class="sxs-lookup"><span data-stu-id="f965d-112">Detected by</span></span>  |<span data-ttu-id="f965d-113">Cómo notificarlo</span><span class="sxs-lookup"><span data-stu-id="f965d-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f965d-114">Mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f965d-114">Email message</span></span> <br/><span data-ttu-id="f965d-115">Datos adjuntos de correo</span><span class="sxs-lookup"><span data-stu-id="f965d-115">Email attachment</span></span> <br/><span data-ttu-id="f965d-116">Dirección URL en un mensaje de correo electrónico o un archivo de Office</span><span class="sxs-lookup"><span data-stu-id="f965d-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="f965d-117">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="f965d-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="f965d-118">Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para Office 365 Scanning</span><span class="sxs-lookup"><span data-stu-id="f965d-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="f965d-119">Archivo o aplicación en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="f965d-119">File or app on a device</span></span>    |[<span data-ttu-id="f965d-120">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f965d-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="f965d-121">Enviar un archivo a Microsoft para el análisis de malware</span><span class="sxs-lookup"><span data-stu-id="f965d-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="f965d-122">Alerta desencadenada por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="f965d-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="f965d-123">Alerta no precisa</span><span class="sxs-lookup"><span data-stu-id="f965d-123">Inaccurate alert</span></span>    |[<span data-ttu-id="f965d-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f965d-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="f965d-125">o</span><span class="sxs-lookup"><span data-stu-id="f965d-125">or</span></span> <br/>[<span data-ttu-id="f965d-126">Detección de amenazas avanzadas de Azure</span><span class="sxs-lookup"><span data-stu-id="f965d-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="f965d-127">Administrar alertas en Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="f965d-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="f965d-128">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="f965d-128">Next steps</span></span>

- [<span data-ttu-id="f965d-129">Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="f965d-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="f965d-130">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="f965d-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="f965d-131">Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f965d-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
