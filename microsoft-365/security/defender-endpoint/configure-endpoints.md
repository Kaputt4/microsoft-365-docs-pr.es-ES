---
title: Herramientas y métodos de incorporación para dispositivos Windows 10
description: Incorporar Windows 10 dispositivos para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: Incorporación Windows 10, directiva de grupo, administrador de configuración de extremo, administración de dispositivos móviles, script local, gp, sccm, mdm, intune
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892834"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="8944e-104">Herramientas y métodos de incorporación para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="8944e-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8944e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8944e-105">**Applies to:**</span></span>
- [<span data-ttu-id="8944e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8944e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8944e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8944e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="8944e-108">Microsoft 365 Prevención de pérdida de datos de extremo (DLP)</span><span class="sxs-lookup"><span data-stu-id="8944e-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="8944e-109">Microsoft 365 Administración de riesgos de Insider</span><span class="sxs-lookup"><span data-stu-id="8944e-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="8944e-110">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8944e-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8944e-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8944e-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8944e-112">Los dispositivos de la organización deben configurarse para que el servicio Defender for Endpoint pueda obtener datos de sensores de ellos.</span><span class="sxs-lookup"><span data-stu-id="8944e-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="8944e-113">Existen varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="8944e-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="8944e-114">Se admiten las siguientes herramientas y métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="8944e-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="8944e-115">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8944e-115">Group Policy</span></span>
- <span data-ttu-id="8944e-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8944e-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="8944e-117">Administración de dispositivos móviles (Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="8944e-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="8944e-118">Script local</span><span class="sxs-lookup"><span data-stu-id="8944e-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8944e-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8944e-119">In this section</span></span>
<span data-ttu-id="8944e-120">Tema</span><span class="sxs-lookup"><span data-stu-id="8944e-120">Topic</span></span> | <span data-ttu-id="8944e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8944e-121">Description</span></span>
:---|:---
[<span data-ttu-id="8944e-122">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8944e-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="8944e-123">Use la directiva de grupo para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8944e-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="8944e-124">Incorporar Windows dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8944e-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="8944e-125">Puede usar Microsoft Endpoint Manager (rama actual) versión 1606 o Microsoft Endpoint Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8944e-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="8944e-126">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="8944e-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="8944e-127">Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8944e-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="8944e-128">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="8944e-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="8944e-129">Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="8944e-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="8944e-130">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="8944e-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="8944e-131">Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="8944e-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="8944e-132">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8944e-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8944e-133">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8944e-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
