---
title: Herramientas y métodos de incorporación para dispositivos Windows 10 (versión preliminar)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Dispositivos de Windows 10 incorporados para que puedan enviar datos del sensor a las soluciones de cumplimiento de Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769647"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="4ce4e-103">Herramientas y métodos de incorporación para dispositivos Windows 10 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4ce4e-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="4ce4e-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4ce4e-104">**Applies to:**</span></span>
- [<span data-ttu-id="4ce4e-105">Prevención de pérdida de datos (DLP) de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ce4e-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="4ce4e-106">Los dispositivos de la organización deben configurarse para que el servicio de prevención de pérdida de datos de extremos de Microsoft 365 pueda obtener datos de los sensores.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="4ce4e-107">Hay varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="4ce4e-108">Se admiten las siguientes herramientas y métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="4ce4e-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="4ce4e-109">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="4ce4e-109">group policy</span></span>
- <span data-ttu-id="4ce4e-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4ce4e-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="4ce4e-111">Administración de dispositivos móviles (incluido Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="4ce4e-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="4ce4e-112">script local</span><span class="sxs-lookup"><span data-stu-id="4ce4e-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4ce4e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ce4e-113">In this section</span></span>
<span data-ttu-id="4ce4e-114">Tema</span><span class="sxs-lookup"><span data-stu-id="4ce4e-114">Topic</span></span> | <span data-ttu-id="4ce4e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ce4e-115">Description</span></span>
:---|:---
[<span data-ttu-id="4ce4e-116">Dispositivos de Windows 10 incorporados mediante la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="4ce4e-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="4ce4e-117">Use la Directiva de grupo para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="4ce4e-118">Dispositivos Windows incorporados mediante el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ce4e-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="4ce4e-119">Puede usar usar Microsoft Endpoint Configuration Manager (rama actual) versión 1606 o Microsoft Endpoint Configuration Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="4ce4e-120">Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="4ce4e-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="4ce4e-121">Use las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="4ce4e-122">Dispositivos de Windows 10 incorporados que usan un script local</span><span class="sxs-lookup"><span data-stu-id="4ce4e-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="4ce4e-123">Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="4ce4e-124">Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados</span><span class="sxs-lookup"><span data-stu-id="4ce4e-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="4ce4e-125">Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="4ce4e-125">Learn how to use the configuration package to configure VDI devices.</span></span>
