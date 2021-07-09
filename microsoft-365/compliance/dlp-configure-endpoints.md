---
title: Métodos y herramientas de incorporación para Windows 10 dispositivos
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
description: Incorporar Windows 10 dispositivos para que puedan enviar datos de sensor a las Microsoft 365 de cumplimiento normativo
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341705"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="d5d46-103">Herramientas y métodos de incorporación para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="d5d46-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="d5d46-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d5d46-104">**Applies to:**</span></span>
- [<span data-ttu-id="d5d46-105">Microsoft 365 Prevención de pérdida de datos de extremo (DLP)</span><span class="sxs-lookup"><span data-stu-id="d5d46-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="d5d46-106">Los dispositivos de la organización deben configurarse para que Microsoft 365 servicio de prevención de pérdida de datos de punto de conexión pueda obtener datos de sensores de ellos.</span><span class="sxs-lookup"><span data-stu-id="d5d46-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="d5d46-107">Existen varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="d5d46-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="d5d46-108">Se admiten las siguientes herramientas y métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="d5d46-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="d5d46-109">directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d5d46-109">group policy</span></span>
- <span data-ttu-id="d5d46-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d5d46-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="d5d46-111">Administración de dispositivos móviles (Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="d5d46-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="d5d46-112">script local</span><span class="sxs-lookup"><span data-stu-id="d5d46-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d5d46-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5d46-113">In this section</span></span>
<span data-ttu-id="d5d46-114">Tema</span><span class="sxs-lookup"><span data-stu-id="d5d46-114">Topic</span></span> | <span data-ttu-id="d5d46-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5d46-115">Description</span></span>
:---|:---
[<span data-ttu-id="d5d46-116">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d5d46-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="d5d46-117">Use la directiva de grupo para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5d46-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="d5d46-118">Incorporar Windows dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d5d46-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="d5d46-119">Puede usar Microsoft Endpoint Configuration Manager (rama actual) versión 1606 o Microsoft Endpoint Configuration Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5d46-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="d5d46-120">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="d5d46-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="d5d46-121">Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5d46-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="d5d46-122">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="d5d46-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="d5d46-123">Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="d5d46-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="d5d46-124">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="d5d46-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="d5d46-125">Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="d5d46-125">Learn how to use the configuration package to configure VDI devices.</span></span>