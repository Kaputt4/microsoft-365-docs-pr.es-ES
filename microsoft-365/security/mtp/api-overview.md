---
title: Información general de las API de Microsoft 365 defender
description: Obtenga información sobre las API disponibles en Microsoft 365 defender
keywords: API, API, información general, incidentes, incidentes, caza de amenazas, Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719195"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="7a3af-104">Información general de las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7a3af-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7a3af-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7a3af-105">**Applies to:**</span></span>

- <span data-ttu-id="7a3af-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a3af-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a3af-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="7a3af-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7a3af-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="7a3af-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7a3af-109">Microsoft 365 defender se basa en una plataforma preparada para la integración.</span><span class="sxs-lookup"><span data-stu-id="7a3af-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="7a3af-110">Use las API de Microsoft 365 defender para automatizar los flujos de trabajo en función de las tablas de incidentes compartidos y de caza avanzada.</span><span class="sxs-lookup"><span data-stu-id="7a3af-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="7a3af-111">**[Cola de incidentes combinados](api-incident.md)** : céntrese en lo que resulta fundamental al agrupar el ámbito completo de los ataques y todos los activos afectados en la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="7a3af-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="7a3af-112">**[Búsqueda de amenazas entre productos](api-advanced-hunting.md)** : aproveche el conocimiento de la organización del equipo de seguridad para buscar síntomas de compromiso mediante la creación de sus propias consultas personalizadas para Sift sobre los datos sin procesar recopilados en varios productos de protección.</span><span class="sxs-lookup"><span data-stu-id="7a3af-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="7a3af-113">Junto con estas API específicas de Microsoft 365 defender, cada uno de nuestros otros productos de seguridad expone [API adicionales](api-articles.md) para ayudarle a aprovechar sus capacidades únicas.</span><span class="sxs-lookup"><span data-stu-id="7a3af-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="7a3af-114">Más información</span><span class="sxs-lookup"><span data-stu-id="7a3af-114">Learn more</span></span>

| <span data-ttu-id="7a3af-115">**Información sobre cómo obtener acceso a las API**</span><span class="sxs-lookup"><span data-stu-id="7a3af-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="7a3af-116">Obtenga más información sobre las cuotas de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="7a3af-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="7a3af-117">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7a3af-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="7a3af-118">**Crear aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="7a3af-118">**Build apps**</span></span> |
| [<span data-ttu-id="7a3af-119">Crear una aplicación "Hola a todos"</span><span class="sxs-lookup"><span data-stu-id="7a3af-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="7a3af-120">Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="7a3af-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="7a3af-121">Crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="7a3af-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="7a3af-122">Crear una aplicación con acceso de socio multiinquilino a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7a3af-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="7a3af-123">**Solucionar problemas y mantener las aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="7a3af-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="7a3af-124">Descripción de los códigos de error de la API</span><span class="sxs-lookup"><span data-stu-id="7a3af-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="7a3af-125">Administrar secretos en las aplicaciones con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="7a3af-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="7a3af-126">Implementar la autorización de OAuth 2,0 para el inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="7a3af-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
