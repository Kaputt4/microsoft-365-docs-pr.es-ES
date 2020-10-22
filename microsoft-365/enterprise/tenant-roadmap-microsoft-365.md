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
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La guía básica para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656012"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="0555d-103">Mapa de ruta del espacio empresarial para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0555d-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="0555d-104">Su inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización.</span><span class="sxs-lookup"><span data-stu-id="0555d-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="0555d-105">Normalmente, este inquilino está asociado con uno o más de los nombres de dominio DNS y actúa como un contenedor central para distintas suscripciones y las licencias que se asignan a las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="0555d-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="0555d-106">Para obtener más información, vea [suscripciones, licencias, cuentas e inquilinos para las ofertas de la nube de Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="0555d-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="0555d-107">Cuando se crea un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="0555d-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="0555d-108">También puede tener un inquilino con varias ubicaciones geográficas y mover el espacio empresarial de una ubicación a otra.</span><span class="sxs-lookup"><span data-stu-id="0555d-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="0555d-109">Para preparar su inquilino para la identidad, es fundamental planear y ejecutar cuidadosamente la configuración de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="0555d-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="0555d-110">Configurar su inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0555d-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="0555d-111">Una vez que haya comprobado que la red está optimizada para el acceso a Microsoft 365 tanto para trabajadores locales como remotos, las próximas grandes tareas planean y configuran el espacio empresarial de Microsoft 365 para los nombres de dominio DNS, los servicios comunes y para esa infraestructura de identidad que admita el inicio de sesión de usuario seguro.</span><span class="sxs-lookup"><span data-stu-id="0555d-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="0555d-112">Plan</span><span class="sxs-lookup"><span data-stu-id="0555d-112">Plan</span></span>

<span data-ttu-id="0555d-113">Para planear la implementación del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="0555d-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="0555d-114">Comprender las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="0555d-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="0555d-115">Aprenda a usar certificados SSL de terceros</span><span class="sxs-lookup"><span data-stu-id="0555d-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="0555d-116">Comprender las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD</span><span class="sxs-lookup"><span data-stu-id="0555d-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="0555d-117">Planeación del soporte técnico de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="0555d-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="0555d-118">Determinación del uso de la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="0555d-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="0555d-119">Planeación de actualizaciones de Office 2007 y Office 2010</span><span class="sxs-lookup"><span data-stu-id="0555d-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="0555d-120">Comprender el aislamiento de inquilino</span><span class="sxs-lookup"><span data-stu-id="0555d-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="0555d-121">Obtener información detallada sobre Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="0555d-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="0555d-122">Implementar</span><span class="sxs-lookup"><span data-stu-id="0555d-122">Deploy</span></span>

<span data-ttu-id="0555d-123">Para implementar su espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="0555d-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="0555d-124">Agregue los [dominios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para su organización.</span><span class="sxs-lookup"><span data-stu-id="0555d-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="0555d-125">Use las [guías de configuración del centro de administración de Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="0555d-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="0555d-126">Crear la [infraestructura de identidad](identity-roadmap-microsoft-365.md) y [proteger los inicios de sesión de los usuarios](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="0555d-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="0555d-127">Mover las ubicaciones geográficas de un inquilino</span><span class="sxs-lookup"><span data-stu-id="0555d-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="0555d-128">Microsoft sigue abrir nuevas ubicaciones geográficas del centro de recursos (GEOS) para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0555d-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="0555d-129">Estos nuevos GEOS de centro de recursos agregan capacidad y computan recursos para apoyar el crecimiento de la demanda y el uso de los clientes.</span><span class="sxs-lookup"><span data-stu-id="0555d-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="0555d-130">Además, el nuevo centro de datos GEOS ofrece una residencia de datos geográfica para los principales datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="0555d-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="0555d-131">Para obtener más información, vea [mover datos principales a New Microsoft 365 Datacenter GEOS](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="0555d-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="0555d-132">Implementación de Microsoft 365 multigeográfico</span><span class="sxs-lookup"><span data-stu-id="0555d-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="0555d-133">Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="0555d-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="0555d-134">Para obtener más información, vea [Microsoft 365 multi-geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="0555d-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="0555d-135">Administrar varios arrendamientos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0555d-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="0555d-136">Aunque tener un único inquilino para su oganization es ideal, puede ser una de las muchas organizaciones que tienen varios arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="0555d-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="0555d-137">Los motivos para varios inquilinos pueden incluir fusiones y adquisiciones, desear el aislamiento administrativo o tener un descentralizado.</span><span class="sxs-lookup"><span data-stu-id="0555d-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="0555d-138">Si tiene varios arrendamientos de Microsoft 365, consulte estos artículos para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="0555d-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="0555d-139">Colaboración entre inquilinos</span><span class="sxs-lookup"><span data-stu-id="0555d-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="0555d-140">Migración de buzones de inquilinos cruzados</span><span class="sxs-lookup"><span data-stu-id="0555d-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="0555d-141">Migraciones de espacio empresarial a espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="0555d-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="0555d-142">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0555d-142">Next step</span></span>

<span data-ttu-id="0555d-143">Inicie la planeación del espacio empresarial con [suscripciones, licencias, cuentas e inquilinos](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="0555d-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
