---
title: Solucionar problemas con herramientas de informes para Microsoft Defender AV
description: Identificar y resolver problemas comunes al intentar informar sobre el estado de protección antivirus de Microsoft Defender en Update Compliance
keywords: troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1a1c807c86aa95148300298484319001b59963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691591"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="0c5a9-104">Solucionar problemas de informes de Antivirus de Microsoft Defender en Cumplimiento de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0c5a9-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0c5a9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0c5a9-105">**Applies to:**</span></span>

- [<span data-ttu-id="0c5a9-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0c5a9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="0c5a9-107">El 31 de marzo de 2020, se quitará la característica de informes de Antivirus de Microsoft Defender de Update Compliance.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="0c5a9-108">Puede seguir definiendo y revisando directivas de cumplimiento de seguridad con [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)lo que permite un control más preciso sobre las características y actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="0c5a9-109">Puede usar Antivirus de Microsoft Defender con cumplimiento de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="0c5a9-110">Verás el estado de las licencias E3, B, F1, VL y Pro.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="0c5a9-111">Sin embargo, para las licencias de E5, debe usar [el portal de Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="0c5a9-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="0c5a9-112">Para obtener más información sobre las opciones de licencias, consulta [Opciones de licencias de productos de Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="0c5a9-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="0c5a9-113">Cuando usas El cumplimiento de Windows Analytics Update para obtener informes sobre el estado de protección de los [dispositivos](/windows/deployment/update/update-compliance-using#wdav-assessment) o puntos de conexión de la red que usan Antivirus de Microsoft Defender, es posible que encuentres problemas o problemas.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="0c5a9-114">Normalmente, los indicadores más comunes de un problema son:</span><span class="sxs-lookup"><span data-stu-id="0c5a9-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="0c5a9-115">Solo ves un número o subconjunto pequeño de todos los dispositivos que esperabas ver</span><span class="sxs-lookup"><span data-stu-id="0c5a9-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="0c5a9-116">No ve ningún dispositivo en absoluto</span><span class="sxs-lookup"><span data-stu-id="0c5a9-116">You do not see any devices at all</span></span>
- <span data-ttu-id="0c5a9-117">Los informes y la información que ve están obsoletos (con más de unos días)</span><span class="sxs-lookup"><span data-stu-id="0c5a9-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="0c5a9-118">Para obtener códigos de error comunes e IDs de eventos relacionados con el servicio antivirus de Microsoft Defender que no están relacionados con el cumplimiento de actualizaciones, vea [Eventos de Antivirus de Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="0c5a9-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="0c5a9-119">Hay tres pasos para solucionar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="0c5a9-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="0c5a9-120">Confirmar que ha cumplido todos los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c5a9-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="0c5a9-121">Comprobar la conectividad con el servicio Windows Defender basado en la nube</span><span class="sxs-lookup"><span data-stu-id="0c5a9-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="0c5a9-122">Enviar registros de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="0c5a9-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="0c5a9-123">Normalmente, los dispositivos tardan 3 días en aparecer en Update Compliance.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="0c5a9-124">Confirmar requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c5a9-124">Confirm prerequisites</span></span>

<span data-ttu-id="0c5a9-125">Para que los dispositivos se muestren correctamente en Update Compliance, debes cumplir ciertos requisitos previos tanto para el servicio de cumplimiento de actualizaciones como para Antivirus de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="0c5a9-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="0c5a9-126">Los puntos de conexión usan Antivirus de Microsoft Defender como única aplicación de protección antivirus.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="0c5a9-127">[El uso de cualquier otra aplicación antivirus hará](microsoft-defender-antivirus-compatibility.md) que el ANTIVIRUS de Microsoft Defender se deshabilite y el extremo no se notirá en Cumplimiento de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="0c5a9-128">[La protección entregada en la nube está habilitada.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0c5a9-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="0c5a9-129">Los puntos de conexión [pueden conectarse a la nube av de Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="0c5a9-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="0c5a9-130">Si el punto de conexión ejecuta Windows 10 versión 1607 o anterior, los datos de diagnóstico de [Windows 10](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)deben establecerse en el nivel mejorado .</span><span class="sxs-lookup"><span data-stu-id="0c5a9-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="0c5a9-131">Han pasado 3 días desde que se han cumplido todos los requisitos</span><span class="sxs-lookup"><span data-stu-id="0c5a9-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="0c5a9-132">"Puede usar antivirus de Microsoft Defender con cumplimiento de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="0c5a9-133">Verás el estado de las licencias E3, B, F1, VL y Pro.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="0c5a9-134">Sin embargo, para las licencias de E5, debe usar el portal de Microsoft Defender para endpoint ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) .</span><span class="sxs-lookup"><span data-stu-id="0c5a9-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="0c5a9-135">Para obtener más información sobre las opciones de licencias, consulta Opciones de licencias de productos de Windows 10"</span><span class="sxs-lookup"><span data-stu-id="0c5a9-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="0c5a9-136">Si se han cumplido todos los requisitos previos anteriores, es posible que deba continuar con el siguiente paso para recopilar información de diagnóstico y enviarla a nosotros.</span><span class="sxs-lookup"><span data-stu-id="0c5a9-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0c5a9-137">Recopilar datos de diagnóstico para la solución de problemas de cumplimiento de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0c5a9-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="0c5a9-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c5a9-138">Related topics</span></span>

- [<span data-ttu-id="0c5a9-139">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="0c5a9-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="0c5a9-140">Implementar antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0c5a9-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)