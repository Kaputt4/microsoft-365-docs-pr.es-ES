---
title: Comprobar el estado del servicio de punto de conexión de Microsoft Defender
description: Compruebe el estado del servicio de punto de conexión de Microsoft Defender, vea si el servicio está experimentando problemas y revise los problemas anteriores que se han resuelto.
keywords: panel, servicio, problemas, estado del servicio, estado actual, historial de estado, resumen de impacto, causa raíz preliminar, resolución, tiempo de resolución, tiempo de resolución esperado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687630"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="b4979-104">Comprobar el estado del servicio de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b4979-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b4979-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b4979-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4979-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b4979-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="b4979-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b4979-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b4979-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b4979-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="b4979-109">**El estado del** servicio proporciona información sobre el estado actual del servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b4979-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="b4979-110">Podrá comprobar si el estado del servicio es correcto o si hay problemas actuales.</span><span class="sxs-lookup"><span data-stu-id="b4979-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="b4979-111">Si hay problemas, verá información como cuándo se detectó el problema, cuál es la causa raíz preliminar y el tiempo de resolución esperado.</span><span class="sxs-lookup"><span data-stu-id="b4979-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="b4979-112">También verá información sobre problemas históricos que se han resuelto y detalles como la fecha y hora en que se resolvió el problema.</span><span class="sxs-lookup"><span data-stu-id="b4979-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="b4979-113">Cuando no haya ningún problema en el servicio, verá un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="b4979-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="b4979-114">Puede ver detalles sobre el estado del  servicio haciendo clic en  el icono del panel operaciones de seguridad o seleccionando el menú Estado del servicio en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="b4979-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="b4979-115">La **página Detalles del** estado del servicio tiene las siguientes pestañas:</span><span class="sxs-lookup"><span data-stu-id="b4979-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="b4979-116">**Estado actual**</span><span class="sxs-lookup"><span data-stu-id="b4979-116">**Current status**</span></span>
- <span data-ttu-id="b4979-117">**Historial de estado**</span><span class="sxs-lookup"><span data-stu-id="b4979-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="b4979-118">Estado actual</span><span class="sxs-lookup"><span data-stu-id="b4979-118">Current status</span></span>
<span data-ttu-id="b4979-119">La **pestaña Estado actual** muestra el estado actual del servicio Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="b4979-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="b4979-120">Cuando el servicio se ejecuta sin problemas, se muestra un estado de servicio correcto.</span><span class="sxs-lookup"><span data-stu-id="b4979-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="b4979-121">Si se ven problemas, se muestran los siguientes detalles del servicio para ayudarle a obtener una mejor información sobre el problema:</span><span class="sxs-lookup"><span data-stu-id="b4979-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="b4979-122">Fecha y hora en que se detectó el problema</span><span class="sxs-lookup"><span data-stu-id="b4979-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="b4979-123">Una breve descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b4979-123">A short description of the issue</span></span>
- <span data-ttu-id="b4979-124">Tiempo de actualización</span><span class="sxs-lookup"><span data-stu-id="b4979-124">Update time</span></span>
- <span data-ttu-id="b4979-125">Resumen del impacto</span><span class="sxs-lookup"><span data-stu-id="b4979-125">Summary of impact</span></span>
- <span data-ttu-id="b4979-126">Causa raíz preliminar</span><span class="sxs-lookup"><span data-stu-id="b4979-126">Preliminary root cause</span></span>
- <span data-ttu-id="b4979-127">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b4979-127">Next steps</span></span>
- <span data-ttu-id="b4979-128">Tiempo de resolución esperado</span><span class="sxs-lookup"><span data-stu-id="b4979-128">Expected resolution time</span></span>

<span data-ttu-id="b4979-129">Las actualizaciones sobre el progreso de un problema se reflejan en la página a medida que se resuelve el problema.</span><span class="sxs-lookup"><span data-stu-id="b4979-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="b4979-130">Verá actualizaciones sobre la información, como una estimación actualizada del tiempo de resolución o los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="b4979-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="b4979-131">Cuando se resuelve un problema, se registra en la **pestaña Historial de** estado.</span><span class="sxs-lookup"><span data-stu-id="b4979-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="b4979-132">Historial de estado</span><span class="sxs-lookup"><span data-stu-id="b4979-132">Status history</span></span>
<span data-ttu-id="b4979-133">La **pestaña Historial de** estado refleja todos los problemas históricos que se han visto y resuelto.</span><span class="sxs-lookup"><span data-stu-id="b4979-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="b4979-134">Verá los detalles de los problemas resueltos junto con la otra información que se incluyeron mientras se estaba resolviendo.</span><span class="sxs-lookup"><span data-stu-id="b4979-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="b4979-135">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="b4979-135">Related topic</span></span>
- [<span data-ttu-id="b4979-136">Ver el panel de operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="b4979-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
