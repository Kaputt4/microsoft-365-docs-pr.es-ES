---
title: Introducción a las API de Microsoft 365 Defender
description: Más información sobre las API disponibles en Microsoft 365 Defender
keywords: api, api, información general, incidente, incidentes, búsqueda de amenazas, microsoft 365 defender
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
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931007"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="673fb-104">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="673fb-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="673fb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="673fb-105">**Applies to:**</span></span>

- <span data-ttu-id="673fb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="673fb-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="673fb-107">Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="673fb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="673fb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="673fb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="673fb-109">Microsoft 365 Defender se basa en una plataforma lista para la integración.</span><span class="sxs-lookup"><span data-stu-id="673fb-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="673fb-110">Use las API de Microsoft 365 Defender para automatizar flujos de trabajo basados en las tablas de incidentes compartidos y búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="673fb-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="673fb-111">**[Cola de incidentes combinados:](api-incident.md)** céntrate en lo que es fundamental al agrupar el ámbito de ataque completo y todos los activos afectados en la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="673fb-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="673fb-112">**[Búsqueda](api-advanced-hunting.md)** de amenazas entre productos: aproveche los conocimientos organizativos de su equipo de seguridad para buscar signos de peligro mediante la creación de sus propias consultas personalizadas para realizar un control de los datos sin procesar recopilados en varios productos de protección.</span><span class="sxs-lookup"><span data-stu-id="673fb-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="673fb-113">Junto con estas API específicas de Microsoft 365 Defender, [](api-articles.md) cada uno de nuestros otros productos de seguridad expone API adicionales para ayudarle a aprovechar sus capacidades únicas.</span><span class="sxs-lookup"><span data-stu-id="673fb-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="673fb-114">Más información</span><span class="sxs-lookup"><span data-stu-id="673fb-114">Learn more</span></span>

| <span data-ttu-id="673fb-115">**Comprender cómo obtener acceso a las API**</span><span class="sxs-lookup"><span data-stu-id="673fb-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="673fb-116">Más información sobre las cuotas de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="673fb-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="673fb-117">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="673fb-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="673fb-118">**Crear aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="673fb-118">**Build apps**</span></span> |
| [<span data-ttu-id="673fb-119">Crear una aplicación "Hola a todos"</span><span class="sxs-lookup"><span data-stu-id="673fb-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="673fb-120">Crear una aplicación para acceder a las API de Microsoft 365 Defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="673fb-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="673fb-121">Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="673fb-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="673fb-122">Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="673fb-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="673fb-123">**Solucionar problemas y mantener las aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="673fb-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="673fb-124">Comprender los códigos de error de la API</span><span class="sxs-lookup"><span data-stu-id="673fb-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="673fb-125">Administrar secretos en las aplicaciones con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="673fb-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="673fb-126">Implementar la autorización de OAuth 2.0 para el inicio de sesión del usuario</span><span class="sxs-lookup"><span data-stu-id="673fb-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
