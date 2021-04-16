---
title: Introducción a la administración y las API
ms.reviewer: ''
description: Obtenga información sobre las herramientas de administración y las categorías de API en Microsoft Defender para endpoint
keywords: incorporación, api, siem, rbac, access, portal, integration, investigation, response, entities, entity, user context, application context, streaming
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
ms.openlocfilehash: 9e54fb5f2105f0a77c4b63e8d880135005c17168
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862096"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="aa1de-104">Introducción a la administración y las API</span><span class="sxs-lookup"><span data-stu-id="aa1de-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa1de-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="aa1de-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa1de-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="aa1de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa1de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa1de-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa1de-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aa1de-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa1de-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="aa1de-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="aa1de-110">Defender for Endpoint admite una amplia variedad de opciones para garantizar que los clientes puedan adoptar fácilmente la plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa1de-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="aa1de-111">Reconociendo que los entornos y estructuras de los clientes pueden variar, Defender for Endpoint se creó con flexibilidad y control pormenorizado para adaptarse a los distintos requisitos del cliente.</span><span class="sxs-lookup"><span data-stu-id="aa1de-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="aa1de-112">Incorporación de puntos de conexión y acceso al portal</span><span class="sxs-lookup"><span data-stu-id="aa1de-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="aa1de-113">La incorporación de dispositivos está totalmente integrada en Microsoft Endpoint Manager y Microsoft Intune para dispositivos cliente y Azure Security Center para dispositivos de servidor, lo que proporciona una experiencia completa de extremo a extremo de configuración, implementación y supervisión.</span><span class="sxs-lookup"><span data-stu-id="aa1de-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Security Center for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="aa1de-114">Además, Microsoft Defender para endpoint admite la directiva de grupo y otras herramientas de terceros usadas para la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa1de-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="aa1de-115">Defender for Endpoint proporciona un control preciso sobre lo que los usuarios con acceso al portal pueden ver y hacer a través de la flexibilidad del control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="aa1de-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="aa1de-116">El modelo RBAC admite todos los sabores de la estructura de los equipos de seguridad:</span><span class="sxs-lookup"><span data-stu-id="aa1de-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="aa1de-117">Organizaciones distribuidas globalmente y equipos de seguridad</span><span class="sxs-lookup"><span data-stu-id="aa1de-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="aa1de-118">Equipos de operaciones de seguridad de modelos en niveles</span><span class="sxs-lookup"><span data-stu-id="aa1de-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="aa1de-119">Divisiones totalmente segregadas con equipos de operaciones de seguridad global centralizados únicos</span><span class="sxs-lookup"><span data-stu-id="aa1de-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="aa1de-120">API disponibles</span><span class="sxs-lookup"><span data-stu-id="aa1de-120">Available APIs</span></span>
<span data-ttu-id="aa1de-121">La solución de Microsoft Defender para endpoint se basa en una plataforma lista para la integración.</span><span class="sxs-lookup"><span data-stu-id="aa1de-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="aa1de-122">Defender for Endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="aa1de-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="aa1de-123">Estas API le permitirán automatizar flujos de trabajo e innovar en función de las capacidades de Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="aa1de-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Imagen de la API e integración disponibles en Microsoft Defender para endpoint](images/mdatp-apis.png)  

<span data-ttu-id="aa1de-125">Las API de Defender for Endpoint se pueden agrupar en tres:</span><span class="sxs-lookup"><span data-stu-id="aa1de-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="aa1de-126">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="aa1de-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="aa1de-127">API de streaming de datos sin procesar</span><span class="sxs-lookup"><span data-stu-id="aa1de-127">Raw data streaming API</span></span>
- <span data-ttu-id="aa1de-128">Integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="aa1de-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="aa1de-129">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="aa1de-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="aa1de-130">Defender for Endpoint ofrece un modelo de API en capas que expone datos y capacidades en un modelo estructurado, claro y fácil de usar, expuesto a través de un modelo estándar de autenticación y autorización basado en Azure AD que permite el acceso en contexto de usuarios o aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="aa1de-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="aa1de-131">El modelo de API se diseñó para exponer entidades y funcionalidades de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="aa1de-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="aa1de-132">Vea este vídeo para obtener una introducción rápida a las API de Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="aa1de-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="aa1de-133">La **API** de investigación expone la riqueza de Defender para endpoint: expone entidades calculadas o "perfiladas" (por ejemplo, dispositivo, usuario y archivo) y eventos discretos (por ejemplo, creación de procesos y creación de archivos) que normalmente describen un comportamiento relacionado con una entidad, lo que habilita el acceso a los datos a través de interfaces de investigación que permiten un acceso basado en consultas a los datos.</span><span class="sxs-lookup"><span data-stu-id="aa1de-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="aa1de-134">Para obtener más información, vea [Supported API](exposed-apis-list.md).</span><span class="sxs-lookup"><span data-stu-id="aa1de-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="aa1de-135">La **API** de respuesta expone la capacidad de realizar acciones en el servicio y en los dispositivos, lo que permite a los clientes ingerir indicadores, administrar la configuración, el estado de alerta, así como realizar acciones de respuesta en dispositivos mediante programación, como aislar dispositivos de la red, archivos de cuarentena y otros.</span><span class="sxs-lookup"><span data-stu-id="aa1de-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="aa1de-136">API de streaming de datos sin procesar</span><span class="sxs-lookup"><span data-stu-id="aa1de-136">Raw data streaming API</span></span> 
<span data-ttu-id="aa1de-137">La API de streaming de datos sin procesar de Defender for Endpoint ofrece a los clientes la capacidad de enviar eventos y alertas en tiempo real desde sus instancias a medida que se producen en un único flujo de datos, lo que proporciona un mecanismo de entrega de baja latencia y alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="aa1de-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="aa1de-138">La información del evento Defender for Endpoint se inserta directamente en Azure Storage para la retención de datos a largo plazo, o en Azure Event Hubs para su consumo por parte de servicios de visualización o motores de procesamiento de datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="aa1de-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="aa1de-139">Para obtener más información, vea [Raw data streaming API](raw-data-export.md).</span><span class="sxs-lookup"><span data-stu-id="aa1de-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="aa1de-140">SIEM API</span><span class="sxs-lookup"><span data-stu-id="aa1de-140">SIEM API</span></span>
<span data-ttu-id="aa1de-141">Al habilitar la integración de la información de seguridad y la administración de eventos (SIEM), permite extraer detecciones del Centro de seguridad de Microsoft Defender mediante la solución SIEM o mediante la conexión directa a la API rest de detecciones.</span><span class="sxs-lookup"><span data-stu-id="aa1de-141">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="aa1de-142">Esto activa la sección detalles de acceso al conector SIEM con valores rellenados previamente y se crea una aplicación en el inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="aa1de-142">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="aa1de-143">Para obtener más información, vea [Integración siem](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="aa1de-143">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa1de-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aa1de-144">Related topics</span></span>
- [<span data-ttu-id="aa1de-145">Obtener acceso a las API de Microsoft Defender para puntos de conexión </span><span class="sxs-lookup"><span data-stu-id="aa1de-145">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="aa1de-146">API compatibles</span><span class="sxs-lookup"><span data-stu-id="aa1de-146">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="aa1de-147">Oportunidades para asociados técnicos</span><span class="sxs-lookup"><span data-stu-id="aa1de-147">Technical partner opportunities</span></span>](partner-integration.md)

