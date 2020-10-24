---
title: Mapa de ruta del espacio empresarial para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La guía básica para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: 038d9b0d94b84d184f0d9d9b250d0ee4d2c19de9
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753971"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="a1600-103">Mapa de ruta del espacio empresarial para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1600-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="a1600-104">Su inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización.</span><span class="sxs-lookup"><span data-stu-id="a1600-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="a1600-105">Normalmente, este inquilino está asociado con uno o más de los nombres de dominio DNS públicos y actúa como un contenedor central y aislado para las distintas suscripciones y las licencias que se asignan a las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1600-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="a1600-106">Para obtener más información, vea [suscripciones, licencias, cuentas e inquilinos para las ofertas de la nube de Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="a1600-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="a1600-107">Cuando se crea un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="a1600-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="a1600-108">También puede tener un inquilino con varias ubicaciones geográficas y mover el espacio empresarial de una ubicación a otra.</span><span class="sxs-lookup"><span data-stu-id="a1600-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="a1600-109">Para preparar al inquilino para el usuario, los grupos, las licencias y las aplicaciones en la nube, es fundamental planear y ejecutar cuidadosamente la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a1600-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="a1600-110">Configurar su inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1600-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="a1600-111">Una vez que haya comprobado que la red está optimizada para el acceso a Microsoft 365 tanto para trabajadores locales como remotos, las próximas grandes tareas planean y configuran el espacio empresarial de Microsoft 365 para los nombres de dominio DNS, los servicios comunes y para esa infraestructura de identidad que admita el inicio de sesión de usuario seguro.</span><span class="sxs-lookup"><span data-stu-id="a1600-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="a1600-112">Planear</span><span class="sxs-lookup"><span data-stu-id="a1600-112">Plan</span></span>

<span data-ttu-id="a1600-113">Para planear la implementación del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="a1600-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="a1600-114">Comprender las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a1600-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="a1600-115">Aprenda a usar certificados SSL de terceros</span><span class="sxs-lookup"><span data-stu-id="a1600-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="a1600-116">Comprender las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD</span><span class="sxs-lookup"><span data-stu-id="a1600-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="a1600-117">Planeación del soporte técnico de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="a1600-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="a1600-118">Determinación del uso de la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="a1600-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="a1600-119">Planeación de actualizaciones de Office 2007 y Office 2010</span><span class="sxs-lookup"><span data-stu-id="a1600-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="a1600-120">Comprender el aislamiento de inquilino</span><span class="sxs-lookup"><span data-stu-id="a1600-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="a1600-121">Implementar</span><span class="sxs-lookup"><span data-stu-id="a1600-121">Deploy</span></span>

<span data-ttu-id="a1600-122">Para implementar su espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="a1600-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="a1600-123">Agregue los [dominios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para su organización.</span><span class="sxs-lookup"><span data-stu-id="a1600-123">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="a1600-124">Use las [guías de configuración del centro de administración de Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="a1600-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="a1600-125">Crear la [infraestructura de identidad](identity-roadmap-microsoft-365.md) y [proteger los inicios de sesión de los usuarios](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="a1600-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="a1600-126">Mover las ubicaciones geográficas de un inquilino</span><span class="sxs-lookup"><span data-stu-id="a1600-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="a1600-127">Microsoft sigue abrir nuevas ubicaciones geográficas del centro de recursos (GEOS) para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1600-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="a1600-128">Estos nuevos GEOS de centro de recursos agregan capacidad y computan recursos para apoyar el crecimiento de la demanda y el uso de los clientes.</span><span class="sxs-lookup"><span data-stu-id="a1600-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="a1600-129">Además, el nuevo centro de datos GEOS ofrece una residencia de datos geográfica para los principales datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="a1600-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="a1600-130">Para obtener más información, vea [mover datos principales a New Microsoft 365 Datacenter GEOS](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="a1600-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="a1600-131">Implementación de Microsoft 365 multigeográfico</span><span class="sxs-lookup"><span data-stu-id="a1600-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="a1600-132">Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="a1600-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="a1600-133">Para obtener más información, vea [Microsoft 365 multi-geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="a1600-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenant"></a><span data-ttu-id="a1600-134">Administrar varios inquilinos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1600-134">Manage multiple Microsoft 365 tenant</span></span> 

<span data-ttu-id="a1600-135">Aunque tener un único inquilino para su oganization es ideal, puede ser una de las muchas organizaciones que tienen varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="a1600-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenant.</span></span> <span data-ttu-id="a1600-136">Los motivos pueden incluir fusiones y adquisiciones, desear el aislamiento administrativo o tener una descentralizada.</span><span class="sxs-lookup"><span data-stu-id="a1600-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="a1600-137">Si tiene varios inquilinos de Microsoft 365, consulte estos artículos para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="a1600-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="a1600-138">Colaboración entre inquilinos</span><span class="sxs-lookup"><span data-stu-id="a1600-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="a1600-139">Migración de buzones de inquilinos cruzados</span><span class="sxs-lookup"><span data-stu-id="a1600-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="a1600-140">Migraciones de espacio empresarial a espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="a1600-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="a1600-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a1600-141">Next step</span></span>

<span data-ttu-id="a1600-142">Inicie la planeación del espacio empresarial con [suscripciones, licencias, cuentas e inquilinos](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="a1600-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
