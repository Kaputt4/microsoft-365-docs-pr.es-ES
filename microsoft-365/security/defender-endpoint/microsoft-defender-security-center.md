---
title: Centro de seguridad de Microsoft Defender
description: El Centro de seguridad de Microsoft Defender es el portal donde puede acceder a Microsoft Defender para endpoint.
keywords: windows, defender, security, center, defender, advanced, threat, protection
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 521c24c24ecc46c81f74e0bab28642aaf581274d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069611"
---
# <a name="microsoft-defender-security-center"></a><span data-ttu-id="db114-104">Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db114-104">Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db114-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="db114-105">**Applies to:**</span></span>
- [<span data-ttu-id="db114-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="db114-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="db114-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db114-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="db114-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="db114-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="db114-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="db114-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="db114-110">El Centro de seguridad de Microsoft Defender es el portal donde puede obtener acceso a las funcionalidades de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="db114-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="db114-111">Proporciona a los equipos de operaciones de seguridad empresarial un único panel de experiencia de cristal para ayudar a proteger las redes.</span><span class="sxs-lookup"><span data-stu-id="db114-111">It gives enterprise security operations teams a single pane of glass experience to help secure networks.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="db114-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="db114-112">In this section</span></span>

<span data-ttu-id="db114-113">Tema</span><span class="sxs-lookup"><span data-stu-id="db114-113">Topic</span></span> | <span data-ttu-id="db114-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="db114-114">Description</span></span>
:---|:---
<span data-ttu-id="db114-115">Introducción</span><span class="sxs-lookup"><span data-stu-id="db114-115">Get started</span></span>  |  <span data-ttu-id="db114-116">Obtenga información sobre los requisitos mínimos, valide las licencias y la configuración completa, conozca las características de vista previa, comprenda el almacenamiento y la privacidad de los datos y cómo asignar acceso de usuario al portal.</span><span class="sxs-lookup"><span data-stu-id="db114-116">Learn about the minimum requirements, validate licensing and complete setup, know about preview features, understand data storage and privacy, and how to assign user access to the portal.</span></span>
[<span data-ttu-id="db114-117">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="db114-117">Onboard devices</span></span>](onboard-configure.md) | <span data-ttu-id="db114-118">Obtén información sobre la incorporación de dispositivos cliente, servidor y que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="db114-118">Learn about onboarding client, server, and non-Windows devices.</span></span> <span data-ttu-id="db114-119">Obtenga información sobre cómo ejecutar una prueba de detección, configurar la configuración de proxy y conectividad a Internet y cómo solucionar posibles problemas de incorporación.</span><span class="sxs-lookup"><span data-stu-id="db114-119">Learn how to run a detection test, configure proxy and Internet connectivity settings, and how to troubleshoot potential onboarding issues.</span></span>
[<span data-ttu-id="db114-120">Comprender el portal</span><span class="sxs-lookup"><span data-stu-id="db114-120">Understand the portal</span></span>](use.md) | <span data-ttu-id="db114-121">Comprenda las operaciones de seguridad, puntuación segura y paneles de análisis de amenazas, así como cómo navegar por el portal.</span><span class="sxs-lookup"><span data-stu-id="db114-121">Understand the Security operations, Secure Score, and Threat analytics dashboards as well as how to navigate the portal.</span></span>
<span data-ttu-id="db114-122">Investigar y corregir amenazas</span><span class="sxs-lookup"><span data-stu-id="db114-122">Investigate and remediate threats</span></span> | <span data-ttu-id="db114-123">Investigar alertas, dispositivos y realizar acciones de respuesta para corregir amenazas.</span><span class="sxs-lookup"><span data-stu-id="db114-123">Investigate alerts, devices, and take response actions to remediate threats.</span></span>
<span data-ttu-id="db114-124">Compatibilidad con API y SIEM</span><span class="sxs-lookup"><span data-stu-id="db114-124">API and SIEM support</span></span> | <span data-ttu-id="db114-125">Use las API admitidas para extraer y crear alertas personalizadas o automatizar flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db114-125">Use the supported APIs to pull and create custom alerts, or automate workflows.</span></span> <span data-ttu-id="db114-126">Use las herramientas SIEM compatibles para extraer alertas del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="db114-126">Use the supported SIEM tools to pull alerts from Microsoft Defender Security Center.</span></span>
<span data-ttu-id="db114-127">Reporting</span><span class="sxs-lookup"><span data-stu-id="db114-127">Reporting</span></span> | <span data-ttu-id="db114-128">Cree y cree informes de Power BI con Microsoft Defender para datos de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="db114-128">Create and build Power BI reports using Microsoft Defender for Endpoint data.</span></span>
<span data-ttu-id="db114-129">Comprobar el estado del servicio y el estado del sensor</span><span class="sxs-lookup"><span data-stu-id="db114-129">Check service health and sensor state</span></span> | <span data-ttu-id="db114-130">Compruebe que el servicio se está ejecutando y compruebe el estado del sensor en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="db114-130">Verify that the service is running and check the sensor state on devices.</span></span>
[<span data-ttu-id="db114-131">Configurar la configuración del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db114-131">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="db114-132">Configure la configuración general, active la experiencia de vista previa, las notificaciones y habilite otras características.</span><span class="sxs-lookup"><span data-stu-id="db114-132">Configure general settings, turn on the preview experience, notifications, and enable other features.</span></span>
[<span data-ttu-id="db114-133">Obtener acceso al Centro de la comunidad de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="db114-133">Access the Microsoft Defender for Endpoint Community Center</span></span>](community.md) | <span data-ttu-id="db114-134">Accede al Centro de la comunidad de Microsoft Defender para endpoints para aprender, colaborar y compartir experiencias sobre el producto.</span><span class="sxs-lookup"><span data-stu-id="db114-134">Access the Microsoft Defender for Endpoint Community Center to learn, collaborate, and share experiences about the product.</span></span>
[<span data-ttu-id="db114-135">Solucionar problemas de servicio</span><span class="sxs-lookup"><span data-stu-id="db114-135">Troubleshoot service issues</span></span>](troubleshoot-mdatp.md) | <span data-ttu-id="db114-136">En esta sección se abordan los problemas que pueden surgir al usar el servicio Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="db114-136">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>