---
title: Guía básica de inquilinos para Microsoft 365
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
description: Guía básica para configurar los inquilinos de Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909459"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="3c37e-103">Guía básica de inquilinos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c37e-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="3c37e-104">El inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización.</span><span class="sxs-lookup"><span data-stu-id="3c37e-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="3c37e-105">Normalmente, este inquilino está asociado a uno o varios de los nombres de dominio DNS públicos y actúa como un contenedor central y aislado para distintas suscripciones y las licencias que se asignan a cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="3c37e-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="3c37e-106">Para obtener más información, vea [Suscripciones, licencias, cuentas](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e inquilinos para las ofertas en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c37e-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="3c37e-107">Al crear un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="3c37e-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="3c37e-108">También puede tener un inquilino con varias ubicaciones geográficas y mover el espacio empresarial de una ubicación a otra.</span><span class="sxs-lookup"><span data-stu-id="3c37e-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="3c37e-109">Para preparar el espacio empresarial para usuarios, grupos, licencias y aplicaciones en la nube, es fundamental planear y ejecutar cuidadosamente la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="3c37e-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="3c37e-110">Configurar el espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c37e-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="3c37e-111">Después de asegurarse de que las redes están optimizadas para el acceso a Microsoft 365 para los trabajadores locales y remotos, las siguientes grandes tareas están planeando y configurando el inquilino de Microsoft 365 para nombres de dominio DNS, servicios comunes y para esa infraestructura de identidad que admite el inicio de sesión seguro del usuario.</span><span class="sxs-lookup"><span data-stu-id="3c37e-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="3c37e-112">Plan</span><span class="sxs-lookup"><span data-stu-id="3c37e-112">Plan</span></span>

<span data-ttu-id="3c37e-113">Para planear la implementación del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="3c37e-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="3c37e-114">Comprender suscripciones, licencias y inquilinos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3c37e-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="3c37e-115">Comprender cómo usar certificados SSL de terceros</span><span class="sxs-lookup"><span data-stu-id="3c37e-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="3c37e-116">Comprender las formas en que un inquilino de Microsoft 365 está integrado con los servicios de Azure AD</span><span class="sxs-lookup"><span data-stu-id="3c37e-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="3c37e-117">Planear la compatibilidad con aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="3c37e-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="3c37e-118">Determinar cómo usar la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="3c37e-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="3c37e-119">Planeación de actualizaciones de Office 2007 y Office 2010</span><span class="sxs-lookup"><span data-stu-id="3c37e-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="3c37e-120">Comprender el aislamiento de inquilino</span><span class="sxs-lookup"><span data-stu-id="3c37e-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="3c37e-121">Implementar</span><span class="sxs-lookup"><span data-stu-id="3c37e-121">Deploy</span></span>

<span data-ttu-id="3c37e-122">Para implementar el espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="3c37e-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="3c37e-123">Agregue los [dominios DNS](../admin/setup/add-domain.md) de la organización.</span><span class="sxs-lookup"><span data-stu-id="3c37e-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="3c37e-124">Use las guías de instalación en el Centro de administración de [Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="3c37e-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="3c37e-125">Cree su infraestructura [de identidad y](identity-roadmap-microsoft-365.md) proteja los [inicios de sesión de usuario.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="3c37e-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="3c37e-126">Mover las ubicaciones geográficas de un inquilino</span><span class="sxs-lookup"><span data-stu-id="3c37e-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="3c37e-127">Microsoft sigue abierto nuevas ubicaciones geográficas de centros de datos (geos) para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c37e-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="3c37e-128">Estas nuevas geos del centro de datos agregan capacidad y recursos informáticos para admitir la demanda del cliente y el crecimiento del uso.</span><span class="sxs-lookup"><span data-stu-id="3c37e-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="3c37e-129">Además, las nuevas geos del centro de datos ofrecen residencia de datos en geo para los datos principales del cliente.</span><span class="sxs-lookup"><span data-stu-id="3c37e-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="3c37e-130">Para obtener más información, vea [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="3c37e-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="3c37e-131">Implementar Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="3c37e-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="3c37e-132">Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="3c37e-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="3c37e-133">Para más información, vea [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="3c37e-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="3c37e-134">Administrar varios inquilinos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c37e-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="3c37e-135">Aunque tener un único inquilino para su oganización es ideal, puede ser una de muchas organizaciones que tienen varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3c37e-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="3c37e-136">Las razones pueden incluir fusiones y adquisiciones, desea aislamiento administrativo o tiene una TI descentralizada.</span><span class="sxs-lookup"><span data-stu-id="3c37e-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="3c37e-137">Si tiene varios inquilinos de Microsoft 365, vea estos artículos para obtener más información sobre:</span><span class="sxs-lookup"><span data-stu-id="3c37e-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="3c37e-138">Colaboración entre inquilinos</span><span class="sxs-lookup"><span data-stu-id="3c37e-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="3c37e-139">Migración de buzones de inquilinos cruzados</span><span class="sxs-lookup"><span data-stu-id="3c37e-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="3c37e-140">Migraciones de espacio empresarial a espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="3c37e-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="3c37e-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="3c37e-141">Next step</span></span>

<span data-ttu-id="3c37e-142">Inicie la planeación del espacio empresarial [con suscripciones, licencias, cuentas e inquilinos.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="3c37e-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>