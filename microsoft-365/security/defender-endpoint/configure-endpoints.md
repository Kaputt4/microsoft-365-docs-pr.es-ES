---
title: Herramientas y métodos de incorporación para dispositivos Windows 10
description: Incorporar dispositivos Windows 10 para que puedan enviar datos del sensor al sensor atp de Microsoft Defender
keywords: Incorporación de dispositivos Windows 10, directiva de grupo, administrador de configuración de extremo, administración de dispositivos móviles, script local, gp, sccm, mdm, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165542"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="00a39-104">Herramientas y métodos de incorporación para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="00a39-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00a39-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="00a39-105">**Applies to:**</span></span>
- [<span data-ttu-id="00a39-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="00a39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="00a39-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00a39-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="00a39-108">Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="00a39-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="00a39-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="00a39-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="00a39-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="00a39-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="00a39-111">Los dispositivos de la organización deben configurarse para que el servicio Defender for Endpoint pueda obtener datos de sensores de ellos.</span><span class="sxs-lookup"><span data-stu-id="00a39-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="00a39-112">Existen varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="00a39-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="00a39-113">Se admiten las siguientes herramientas y métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="00a39-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="00a39-114">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="00a39-114">Group Policy</span></span>
- <span data-ttu-id="00a39-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="00a39-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="00a39-116">Administración de dispositivos móviles (incluido Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="00a39-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="00a39-117">Script local</span><span class="sxs-lookup"><span data-stu-id="00a39-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="00a39-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="00a39-118">In this section</span></span>
<span data-ttu-id="00a39-119">Tema</span><span class="sxs-lookup"><span data-stu-id="00a39-119">Topic</span></span> | <span data-ttu-id="00a39-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="00a39-120">Description</span></span>
:---|:---
[<span data-ttu-id="00a39-121">Incorporación de dispositivos Windows 10 con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="00a39-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="00a39-122">Use la directiva de grupo para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00a39-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="00a39-123">Incorporación de dispositivos Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="00a39-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="00a39-124">Puede usar Microsoft Endpoint Manager (rama actual) versión 1606 o Microsoft Endpoint Manager (rama actual) versión 1602 o versiones anteriores para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00a39-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="00a39-125">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="00a39-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="00a39-126">Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00a39-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="00a39-127">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="00a39-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="00a39-128">Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="00a39-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="00a39-129">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="00a39-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="00a39-130">Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="00a39-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="00a39-131">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="00a39-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="00a39-132">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="00a39-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
