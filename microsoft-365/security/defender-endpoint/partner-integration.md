---
title: Escenarios y oportunidades de socio de Microsoft Defender para puntos de conexión
ms.reviewer: ''
description: Obtenga información sobre cómo ampliar las ofertas de seguridad existentes sobre el marco abierto y un amplio conjunto de API para crear extensiones e integraciones con Microsoft Defender para endpoint
keywords: API, partner, extend, open framework, apis, extensions, integrations, detection, management, response, vulnerabilities, intelligence
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
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861114"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="ca314-104">Escenarios y oportunidades de socio de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="ca314-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca314-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ca314-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca314-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ca314-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ca314-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca314-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ca314-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ca314-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ca314-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ca314-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="ca314-110">Los partners pueden ampliar fácilmente sus ofertas de seguridad existentes sobre el marco abierto y un amplio y completo conjunto de API para crear extensiones e integraciones con Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ca314-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="ca314-111">Las API abarcan áreas funcionales como detección, administración, respuesta, vulnerabilidades y casos de uso de toda la inteligencia.</span><span class="sxs-lookup"><span data-stu-id="ca314-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="ca314-112">En función del caso de uso y la necesidad, los partners pueden transmitir o consultar datos desde Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="ca314-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="ca314-113">Escenario 1: Correlación de alertas externas e Investigación y corrección automatizadas</span><span class="sxs-lookup"><span data-stu-id="ca314-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="ca314-114">Defender for Endpoint ofrece capacidades únicas de investigación y corrección automatizadas para impulsar la respuesta a incidentes a escala.</span><span class="sxs-lookup"><span data-stu-id="ca314-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="ca314-115">La integración de la capacidad automatizada de investigación y respuesta con otras soluciones, como productos de seguridad de red u otros productos de seguridad de puntos de conexión, ayudará a abordar las alertas.</span><span class="sxs-lookup"><span data-stu-id="ca314-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="ca314-116">La integración también minimiza las complejidades que rodean la correlación de señal de dispositivo y red, lo que a la vez abate eficazmente las acciones de investigación y corrección de amenazas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ca314-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="ca314-117">Defender para endpoint agrega compatibilidad para este escenario en los siguientes formularios:</span><span class="sxs-lookup"><span data-stu-id="ca314-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="ca314-118">Las alertas externas se pueden insertar en Defender para Endpoint y presentarse en paralelo con alertas adicionales basadas en dispositivos de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="ca314-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="ca314-119">Esta vista proporciona el contexto completo de la alerta, con el proceso real y la historia completa de ataque.</span><span class="sxs-lookup"><span data-stu-id="ca314-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="ca314-120">Una vez generada una alerta, la señal se comparte en todos los puntos de conexión protegidos de Defender for Endpoint en la empresa.</span><span class="sxs-lookup"><span data-stu-id="ca314-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="ca314-121">Defender for Endpoint toma una respuesta inmediata automatizada o asistida por el operador para abordar la alerta.</span><span class="sxs-lookup"><span data-stu-id="ca314-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="ca314-122">Escenario 2: Integración de la orquestación de seguridad y la respuesta de automatización (SOAR)</span><span class="sxs-lookup"><span data-stu-id="ca314-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="ca314-123">Las soluciones de orquestación pueden ayudar a crear libros de reproducción e integrar el modelo de datos enriquecido y las acciones que exponen las API de Defender for Endpoint para orquestar respuestas, como la consulta de datos del dispositivo, desencadenar el aislamiento de dispositivos, bloquear/permitir, resolver alertas y otras.</span><span class="sxs-lookup"><span data-stu-id="ca314-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="ca314-124">Escenario 3: Coincidencia de indicadores</span><span class="sxs-lookup"><span data-stu-id="ca314-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="ca314-125">El indicador de coincidencia de puntos de conexión (IoCs) es una característica esencial en cada solución de protección de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca314-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="ca314-126">Esta funcionalidad está disponible en Defender for Endpoint y permite establecer una lista de indicadores para la prevención, detección y exclusión de entidades.</span><span class="sxs-lookup"><span data-stu-id="ca314-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="ca314-127">Se puede definir la acción que se debe realizar, así como la duración de cuándo aplicar la acción.</span><span class="sxs-lookup"><span data-stu-id="ca314-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="ca314-128">Los escenarios anteriores sirven como ejemplos de la extensibilidad de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="ca314-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="ca314-129">No se limita a los ejemplos y le animamos a aprovechar el marco abierto para descubrir y explorar otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="ca314-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="ca314-130">Siga los pasos descritos en Convertirse en un partner de [Microsoft Defender para endpoint](get-started-partner-integration.md) para integrar la solución en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="ca314-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="ca314-131">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="ca314-131">Related topic</span></span>
- [<span data-ttu-id="ca314-132">Introducción a la administración y las API</span><span class="sxs-lookup"><span data-stu-id="ca314-132">Overview of management and APIs</span></span>](management-apis.md)
