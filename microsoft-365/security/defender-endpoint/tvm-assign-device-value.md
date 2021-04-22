---
title: 'Asignar valor de dispositivo: administración de amenazas y vulnerabilidades'
description: Aprende a asignar un valor bajo, normal o alto a un dispositivo para ayudarte a diferenciar las prioridades de los activos.
keywords: Valor del dispositivo de Microsoft Defender para endpoint, valor del dispositivo de administración de amenazas y vulnerabilidades, dispositivos de alto valor, puntuación de exposición al valor del dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935202"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="7e8c1-104">Asignar valor de dispositivo: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="7e8c1-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7e8c1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7e8c1-105">**Applies to:**</span></span>

- [<span data-ttu-id="7e8c1-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7e8c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7e8c1-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="7e8c1-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7e8c1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e8c1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7e8c1-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="7e8c1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7e8c1-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7e8c1-111">La definición del valor de un dispositivo te ayuda a diferenciar entre las prioridades de los activos.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="7e8c1-112">El valor del dispositivo se usa para incorporar el apetito de riesgo de un activo individual en el cálculo de la puntuación de exposición a la administración de vulnerabilidades y amenazas.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="7e8c1-113">Los dispositivos asignados como "valor alto" recibirán más peso.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="7e8c1-114">También puedes usar la [API de valor de dispositivo establecida.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="7e8c1-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="7e8c1-115">Opciones de valor del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7e8c1-115">Device value options:</span></span>

- <span data-ttu-id="7e8c1-116">Bajo</span><span class="sxs-lookup"><span data-stu-id="7e8c1-116">Low</span></span>
- <span data-ttu-id="7e8c1-117">Normal (predeterminada)</span><span class="sxs-lookup"><span data-stu-id="7e8c1-117">Normal (Default)</span></span>
- <span data-ttu-id="7e8c1-118">Alto</span><span class="sxs-lookup"><span data-stu-id="7e8c1-118">High</span></span>

<span data-ttu-id="7e8c1-119">Ejemplos de dispositivos a los que se debe asignar un valor alto:</span><span class="sxs-lookup"><span data-stu-id="7e8c1-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="7e8c1-120">Controladores de dominio, Active Directory</span><span class="sxs-lookup"><span data-stu-id="7e8c1-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="7e8c1-121">Dispositivos orientados a Internet</span><span class="sxs-lookup"><span data-stu-id="7e8c1-121">Internet facing devices</span></span>
- <span data-ttu-id="7e8c1-122">Dispositivos VIP</span><span class="sxs-lookup"><span data-stu-id="7e8c1-122">VIP devices</span></span>
- <span data-ttu-id="7e8c1-123">Dispositivos que hospedan servicios de producción internos/externos</span><span class="sxs-lookup"><span data-stu-id="7e8c1-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="7e8c1-124">Elegir valor de dispositivo</span><span class="sxs-lookup"><span data-stu-id="7e8c1-124">Choose device value</span></span>

1. <span data-ttu-id="7e8c1-125">Navega a cualquier página de dispositivo, el lugar más fácil es desde el inventario de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="7e8c1-126">Selecciona **Valor de dispositivo** entre tres puntos junto a la barra de acciones en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Ejemplo del desplegable de valores del dispositivo.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="7e8c1-128">Aparecerá un flyout con el valor del dispositivo actual y lo que significa.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="7e8c1-129">Revisa el valor del dispositivo y elige el que mejor se adapte a tu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="7e8c1-130">![Ejemplo del menú desplegable del valor del dispositivo.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="7e8c1-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="7e8c1-131">Cómo afecta el valor del dispositivo a la puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="7e8c1-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="7e8c1-132">La puntuación de exposición es un promedio ponderado en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="7e8c1-133">Si tienes grupos de dispositivos, también puedes filtrar la puntuación por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="7e8c1-134">Los dispositivos normales tienen un peso de 1</span><span class="sxs-lookup"><span data-stu-id="7e8c1-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="7e8c1-135">Los dispositivos de bajo valor tienen un peso de 0,75</span><span class="sxs-lookup"><span data-stu-id="7e8c1-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="7e8c1-136">Los dispositivos de alto valor tienen un peso de NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="7e8c1-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="7e8c1-137">Si tienes 100 dispositivos, cada dispositivo de alto valor tendrá un peso de 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="7e8c1-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e8c1-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7e8c1-138">Related topics</span></span>

- [<span data-ttu-id="7e8c1-139">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="7e8c1-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7e8c1-140">Puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="7e8c1-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="7e8c1-141">API</span><span class="sxs-lookup"><span data-stu-id="7e8c1-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)