---
title: Configurar y administrar las funcionalidades de Microsoft Defender para puntos de conexión
ms.reviewer: ''
description: Configurar y administrar Las capacidades de Microsoft Defender para puntos de conexión, como la reducción de superficie de ataque y la protección de próxima generación
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861340"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="57439-104">Configurar y administrar las funcionalidades de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="57439-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="57439-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="57439-105">**Applies to:**</span></span>

- [<span data-ttu-id="57439-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="57439-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="57439-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57439-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="57439-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="57439-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57439-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="57439-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="57439-110">Obtenga información sobre cómo configurar y administrar las características de Defender for Endpoint para obtener la mejor protección de seguridad para su organización.</span><span class="sxs-lookup"><span data-stu-id="57439-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="57439-111">Para obtener consejos prácticos sobre cómo conectar nuevos dispositivos en su organización, consulte Incorporación de dispositivos [al servicio de Microsoft Defender para endpoints.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="57439-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="57439-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="57439-112">In this section</span></span>

<span data-ttu-id="57439-113">Tema</span><span class="sxs-lookup"><span data-stu-id="57439-113">Topic</span></span> | <span data-ttu-id="57439-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="57439-114">Description</span></span>
:---|:---
[<span data-ttu-id="57439-115">Configurar la configuración del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="57439-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="57439-116">Configure las opciones relacionadas con el portal, como la configuración general, las características avanzadas o habilite la experiencia de vista previa.</span><span class="sxs-lookup"><span data-stu-id="57439-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="57439-117">Configurar capacidades de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="57439-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="57439-118">Configure las capacidades de reducción de superficie de ataque, para asegurarse de que la configuración se aplica correctamente y de que se establecen técnicas de mitigación de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="57439-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="57439-119">Configurar la protección de última generación</span><span class="sxs-lookup"><span data-stu-id="57439-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="57439-120">Configure la protección de última generación para detectar todo tipo de amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="57439-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="57439-121">Configurar las capacidades de Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="57439-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="57439-122">Configurar y administrar la inteligencia de amenazas de ciberseguridad de Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="57439-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="57439-123">Configurar la integración de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="57439-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="57439-124">Configure otras soluciones que se integren con Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="57439-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="57439-125">Soporte técnico de api y administración</span><span class="sxs-lookup"><span data-stu-id="57439-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="57439-126">Extraer alertas a la información de seguridad y administración de eventos (SIEM) o usar las API para crear alertas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="57439-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="57439-127">Cree y cree informes de Power BI.</span><span class="sxs-lookup"><span data-stu-id="57439-127">Create and build Power BI reports.</span></span>
