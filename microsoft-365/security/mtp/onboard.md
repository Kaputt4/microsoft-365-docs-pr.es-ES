---
title: Configurar y administrar las funcionalidades de Microsoft Defender para puntos de conexión
ms.reviewer: ''
description: Configurar y administrar Las capacidades de Microsoft Defender para endpoints, como la reducción de superficie de ataque y la protección de próxima generación
keywords: configurar, administrar, funcionalidades, reducción de superficie de ataque, protección de próxima generación, controles de seguridad, detección y respuesta de puntos de conexión, investigación y corrección automáticas, controles de seguridad, controles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c3bb09820f4a22c8ecb1e49c699db5b6f4cabc68
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928621"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="e4d22-104">Configurar y administrar las funcionalidades de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="e4d22-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e4d22-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e4d22-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4d22-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e4d22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="e4d22-107">Configure y administre todas las funcionalidades de Microsoft Defender para endpoint para obtener la mejor protección de seguridad para su organización.</span><span class="sxs-lookup"><span data-stu-id="e4d22-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="e4d22-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e4d22-108">In this section</span></span> 
<span data-ttu-id="e4d22-109">Tema</span><span class="sxs-lookup"><span data-stu-id="e4d22-109">Topic</span></span> | <span data-ttu-id="e4d22-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4d22-110">Description</span></span> 
:---|:---
[<span data-ttu-id="e4d22-111">Configurar capacidades de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="e4d22-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="e4d22-112">Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, este conjunto de capacidades resiste los ataques y la explotación.</span><span class="sxs-lookup"><span data-stu-id="e4d22-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="e4d22-113">Configurar la protección de próxima generación</span><span class="sxs-lookup"><span data-stu-id="e4d22-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="e4d22-114">Configure la protección de próxima generación para detectar todo tipo de amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="e4d22-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="e4d22-115">Configurar las capacidades de Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="e4d22-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="e4d22-116">Configure y administre cómo le gustaría obtener la inteligencia de amenazas de ciberseguridad de los expertos en amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4d22-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="e4d22-117">Configurar la integración de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4d22-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="e4d22-118">Configure otras soluciones que se integren con Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e4d22-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="e4d22-119">Soporte técnico de api y administración</span><span class="sxs-lookup"><span data-stu-id="e4d22-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="e4d22-120">Extraer alertas a siem o usar api para crear alertas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e4d22-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="e4d22-121">Cree y cree informes de Power BI.</span><span class="sxs-lookup"><span data-stu-id="e4d22-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="e4d22-122">Configurar la configuración del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e4d22-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="e4d22-123">Configure las opciones relacionadas con el portal, como la configuración general, las características avanzadas, habilite la experiencia de vista previa y otras.</span><span class="sxs-lookup"><span data-stu-id="e4d22-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>