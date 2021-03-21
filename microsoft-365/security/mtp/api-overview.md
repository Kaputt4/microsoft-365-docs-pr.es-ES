---
title: Introducción a las API de Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922191"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="d951d-104">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d951d-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d951d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d951d-105">**Applies to:**</span></span>

- <span data-ttu-id="d951d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d951d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d951d-107">Parte de la información está relacionada con el producto predefinido que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="d951d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d951d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d951d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d951d-109">Microsoft 365 Defender se basa en una plataforma lista para la integración.</span><span class="sxs-lookup"><span data-stu-id="d951d-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="d951d-110">Usa las API de Microsoft 365 Defender para automatizar flujos de trabajo basados en el incidente compartido y las tablas avanzadas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d951d-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="d951d-111">**[Cola de incidentes combinados:](api-incident.md)** céntrate en lo que es fundamental al agrupar el ámbito de ataque completo y todos los activos afectados en la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="d951d-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="d951d-112">**[Búsqueda](api-advanced-hunting.md)** de amenazas entre productos: aproveche los conocimientos organizativos de su equipo de seguridad para buscar signos de peligro, mediante la creación de sus propias consultas personalizadas para realizar un control de los datos sin procesar recopilados en varios productos de protección.</span><span class="sxs-lookup"><span data-stu-id="d951d-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="d951d-113">Junto con estas API específicas de Microsoft 365 Defender, [](api-articles.md) cada uno de nuestros otros productos de seguridad expone API adicionales para ayudarle a aprovechar sus capacidades únicas.</span><span class="sxs-lookup"><span data-stu-id="d951d-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d951d-114">Más información</span><span class="sxs-lookup"><span data-stu-id="d951d-114">Learn more</span></span>

| <span data-ttu-id="d951d-115">**Comprender cómo obtener acceso a las API**</span><span class="sxs-lookup"><span data-stu-id="d951d-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="d951d-116">Más información sobre las cuotas de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="d951d-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="d951d-117">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d951d-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="d951d-118">**Crear aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="d951d-118">**Build apps**</span></span> |
| [<span data-ttu-id="d951d-119">Crear una aplicación "Hello world"</span><span class="sxs-lookup"><span data-stu-id="d951d-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="d951d-120">Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="d951d-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="d951d-121">Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="d951d-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="d951d-122">Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d951d-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="d951d-123">**Solucionar problemas y mantener las aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="d951d-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="d951d-124">Comprender los códigos de error de la API</span><span class="sxs-lookup"><span data-stu-id="d951d-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="d951d-125">Administrar secretos en las aplicaciones con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d951d-125">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="d951d-126">Implementar la autorización de OAuth 2.0 para el inicio de sesión del usuario</span><span class="sxs-lookup"><span data-stu-id="d951d-126">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |