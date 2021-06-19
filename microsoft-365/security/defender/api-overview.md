---
title: Introducción a Microsoft 365 Defender API
description: Obtenga información sobre las API disponibles en Microsoft 365 Defender
keywords: api, apis, overview, incident, incidents, threat hunting, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1ddb6da49e5e9f23aacf73caaeb91302ac9c19c9
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028972"
---
# <a name="overview-of-microsoft-365-defender-apis"></a><span data-ttu-id="8d11a-104">Introducción a Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="8d11a-104">Overview of Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8d11a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8d11a-105">**Applies to:**</span></span>

- <span data-ttu-id="8d11a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d11a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d11a-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="8d11a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8d11a-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="8d11a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8d11a-109">Microsoft 365 Defender se basa en una plataforma lista para la integración.</span><span class="sxs-lookup"><span data-stu-id="8d11a-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="8d11a-110">Use las API Microsoft 365 Defender para automatizar flujos de trabajo basados en el incidente compartido y las tablas avanzadas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8d11a-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="8d11a-111">**[Cola de incidentes combinados:](api-incident.md)** céntrate en lo que es fundamental al agrupar el ámbito de ataque completo y todos los activos afectados en la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="8d11a-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="8d11a-112">**[Búsqueda](api-advanced-hunting.md)** de amenazas entre productos: aproveche los conocimientos organizativos de su equipo de seguridad para buscar signos de peligro, mediante la creación de sus propias consultas personalizadas para realizar un control de los datos sin procesar recopilados en varios productos de protección.</span><span class="sxs-lookup"><span data-stu-id="8d11a-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="8d11a-113">Use la [API de streaming para](../defender-endpoint/raw-data-export.md) enviar alertas y eventos en tiempo real desde instancias a medida que se producen en un único flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8d11a-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="8d11a-114">Junto con estas API Microsoft 365 Defender específicas, cada uno de [](api-articles.md) nuestros otros productos de seguridad expone API adicionales para ayudarle a aprovechar sus capacidades únicas.</span><span class="sxs-lookup"><span data-stu-id="8d11a-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="8d11a-115">La transición al portal unificado no debe afectar a los paneles de PowerBi basados en Microsoft Defender para las API de extremo.</span><span class="sxs-lookup"><span data-stu-id="8d11a-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="8d11a-116">Puede seguir trabajando con las API existentes independientemente de la transición del portal interactivo.</span><span class="sxs-lookup"><span data-stu-id="8d11a-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="8d11a-117">Más información</span><span class="sxs-lookup"><span data-stu-id="8d11a-117">Learn more</span></span>

| <span data-ttu-id="8d11a-118">**Comprender cómo obtener acceso a las API**</span><span class="sxs-lookup"><span data-stu-id="8d11a-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="8d11a-119">Más información sobre las cuotas de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="8d11a-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="8d11a-120">Obtener acceso a Microsoft 365 Defender API de acceso</span><span class="sxs-lookup"><span data-stu-id="8d11a-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="8d11a-121">**Crear aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="8d11a-121">**Build apps**</span></span> |
| [<span data-ttu-id="8d11a-122">Crear una aplicación "Hello world"</span><span class="sxs-lookup"><span data-stu-id="8d11a-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="8d11a-123">Crear una aplicación para obtener acceso Microsoft 365 Defender API en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="8d11a-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="8d11a-124">Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="8d11a-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="8d11a-125">Crear una aplicación con acceso de asociado multiinquilino a Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="8d11a-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="8d11a-126">**Solucionar problemas y mantener las aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="8d11a-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="8d11a-127">Comprender los códigos de error de la API</span><span class="sxs-lookup"><span data-stu-id="8d11a-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="8d11a-128">Administrar secretos en las aplicaciones con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8d11a-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="8d11a-129">Implementar la autorización de OAuth 2.0 para el inicio de sesión del usuario</span><span class="sxs-lookup"><span data-stu-id="8d11a-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |