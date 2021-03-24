---
title: Configurar y administrar las capacidades de ATP de Microsoft Defender
ms.reviewer: ''
description: Configurar y administrar las capacidades de ATP de Microsoft Defender, como la reducción de superficie de ataque y la protección de próxima generación
keywords: configurar, administrar, funcionalidades, reducción de superficie de ataque, protección de última generación, controles de seguridad, detección y respuesta de puntos de conexión, investigación y corrección automáticas, controles de seguridad, controles
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
ms.openlocfilehash: e2082929cf1fb7f4b55331cf62adcd9b936168d0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069155"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="12267-104">Configurar y administrar las funcionalidades de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="12267-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12267-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="12267-105">**Applies to:**</span></span>
- [<span data-ttu-id="12267-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="12267-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="12267-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12267-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="12267-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="12267-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12267-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="12267-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="12267-110">Configure y administre todas las funcionalidades de Defender for Endpoint para obtener la mejor protección de seguridad para su organización.</span><span class="sxs-lookup"><span data-stu-id="12267-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="12267-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12267-111">In this section</span></span> 
<span data-ttu-id="12267-112">Tema</span><span class="sxs-lookup"><span data-stu-id="12267-112">Topic</span></span> | <span data-ttu-id="12267-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="12267-113">Description</span></span> 
:---|:---
[<span data-ttu-id="12267-114">Configurar capacidades de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="12267-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="12267-115">Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, este conjunto de capacidades resiste los ataques y la explotación.</span><span class="sxs-lookup"><span data-stu-id="12267-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="12267-116">Configurar la protección de última generación</span><span class="sxs-lookup"><span data-stu-id="12267-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="12267-117">Configure la protección de última generación para detectar todo tipo de amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="12267-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="12267-118">Configurar las capacidades de Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="12267-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="12267-119">Configure y administre cómo le gustaría obtener la inteligencia de amenazas de ciberseguridad de los expertos en amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12267-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="12267-120">Configurar la integración de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12267-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="12267-121">Configure otras soluciones que se integren con Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="12267-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="12267-122">Soporte técnico de api y administración</span><span class="sxs-lookup"><span data-stu-id="12267-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="12267-123">Extraer alertas a siem o usar api para crear alertas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="12267-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="12267-124">Cree y cree informes de Power BI.</span><span class="sxs-lookup"><span data-stu-id="12267-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="12267-125">Configurar la configuración del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="12267-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="12267-126">Configure las opciones relacionadas con el portal, como la configuración general, las características avanzadas, habilite la experiencia de vista previa y otras.</span><span class="sxs-lookup"><span data-stu-id="12267-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



