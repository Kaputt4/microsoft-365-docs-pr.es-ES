---
title: Mapa de ruta del espacio empresarial para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: La guía básica para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315758"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="d6123-103">Mapa de ruta del espacio empresarial para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6123-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="d6123-104">Su inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización.</span><span class="sxs-lookup"><span data-stu-id="d6123-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="d6123-105">Este inquilino suele estar asociado con uno o más de los nombres de dominio DNS y actúa como un contenedor central para distintas suscripciones y las licencias que se asignan a las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="d6123-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="d6123-106">Cuando se crea un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="d6123-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="d6123-107">También puede tener un inquilino con varias ubicaciones geográficas y mover el espacio empresarial de una ubicación a otra.</span><span class="sxs-lookup"><span data-stu-id="d6123-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="d6123-108">Una configuración de inquilino bien planeada y ejecutada es fundamental para obtenerla lista para los servicios básicos de la red y la identidad.</span><span class="sxs-lookup"><span data-stu-id="d6123-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="d6123-109">Plan</span><span class="sxs-lookup"><span data-stu-id="d6123-109">Plan</span></span>

<span data-ttu-id="d6123-110">Para planear la implementación del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="d6123-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="d6123-111">Comprender las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d6123-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="d6123-112">Aprenda a usar certificados SSL de terceros</span><span class="sxs-lookup"><span data-stu-id="d6123-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="d6123-113">Acceder a las guías de configuración en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6123-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="d6123-114">Comprender las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d6123-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="d6123-115">Planeación del soporte técnico de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="d6123-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="d6123-116">Determinación del uso de la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="d6123-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="d6123-117">Planeación de actualizaciones de Office 2007 y Office 2010</span><span class="sxs-lookup"><span data-stu-id="d6123-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="d6123-118">Comprender el aislamiento de inquilino</span><span class="sxs-lookup"><span data-stu-id="d6123-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="d6123-119">Obtener información detallada sobre Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="d6123-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="d6123-120">Implementar</span><span class="sxs-lookup"><span data-stu-id="d6123-120">Deploy</span></span>

<span data-ttu-id="d6123-121">Para implementar el inquilino, [agregue los dominios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) de la organización.</span><span class="sxs-lookup"><span data-stu-id="d6123-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="d6123-122">Inquilinos con varias ubicaciones geográficas</span><span class="sxs-lookup"><span data-stu-id="d6123-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="d6123-123">Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="d6123-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="d6123-124">[Introducción a](microsoft-365-multi-geo.md) la comprensión, planeación, configuración y administración con Microsoft 365 multi-geo.</span><span class="sxs-lookup"><span data-stu-id="d6123-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="d6123-125">Mover las ubicaciones geográficas de un inquilino</span><span class="sxs-lookup"><span data-stu-id="d6123-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="d6123-126">Microsoft sigue abrir nuevas ubicaciones geográficas del centro de recursos (GEOS) para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6123-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="d6123-127">Estos nuevos GEOS de centro de recursos agregan capacidad y computan recursos para apoyar el crecimiento de la demanda y el uso de los clientes.</span><span class="sxs-lookup"><span data-stu-id="d6123-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="d6123-128">Además, el nuevo centro de datos GEOS ofrece una residencia de datos geográfica para los principales datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="d6123-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="d6123-129">Introducción a la comprensión y solicitud de un movimiento de datos geográficas con [movimiento de datos principales a un nuevo centro de datos de Microsoft 365 geográficamente](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="d6123-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="d6123-130">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d6123-130">Next step</span></span>

<span data-ttu-id="d6123-131">Inicie la planeación del espacio empresarial con [suscripciones, licencias, cuentas e inquilinos](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="d6123-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

