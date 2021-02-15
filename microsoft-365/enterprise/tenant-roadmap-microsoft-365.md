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
description: Guía básica para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948402"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="9052a-103">Guía básica de inquilinos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9052a-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="9052a-104">Su inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización.</span><span class="sxs-lookup"><span data-stu-id="9052a-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="9052a-105">Normalmente, este inquilino está asociado a uno o varios de los nombres de dominio DNS públicos y actúa como un contenedor central y aislado para distintas suscripciones y las licencias que se asignan a cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="9052a-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="9052a-106">Para obtener más información, vea [Suscripciones, licencias, cuentas](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e inquilinos para las ofertas de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9052a-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="9052a-107">Al crear un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="9052a-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="9052a-108">También puede tener un inquilino con varias ubicaciones geográficas y mover el inquilino de una ubicación a otra.</span><span class="sxs-lookup"><span data-stu-id="9052a-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="9052a-109">Para preparar el espacio empresarial para usuarios, grupos, licencias y aplicaciones en la nube, es fundamental planear y ejecutar cuidadosamente la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="9052a-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="9052a-110">Configurar el inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9052a-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="9052a-111">Después de asegurarse de que las redes están optimizadas para el acceso a Microsoft 365 para los trabajadores locales y remotos, las siguientes grandes tareas están planeando y configurando su inquilino de Microsoft 365 para nombres de dominio DNS, servicios comunes y para esa infraestructura de identidad que admite el inicio de sesión seguro de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9052a-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="9052a-112">Plan</span><span class="sxs-lookup"><span data-stu-id="9052a-112">Plan</span></span>

<span data-ttu-id="9052a-113">Para planear la implementación del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="9052a-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="9052a-114">Comprender las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9052a-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="9052a-115">Comprender cómo usar certificados SSL de terceros</span><span class="sxs-lookup"><span data-stu-id="9052a-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="9052a-116">Comprender las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD</span><span class="sxs-lookup"><span data-stu-id="9052a-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="9052a-117">Planeación de la compatibilidad con aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="9052a-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="9052a-118">Determinar cómo usar la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="9052a-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="9052a-119">Planear las actualizaciones de Office 2007 y Office 2010</span><span class="sxs-lookup"><span data-stu-id="9052a-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="9052a-120">Comprender el aislamiento de inquilinos</span><span class="sxs-lookup"><span data-stu-id="9052a-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="9052a-121">Implementar</span><span class="sxs-lookup"><span data-stu-id="9052a-121">Deploy</span></span>

<span data-ttu-id="9052a-122">Para implementar el espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="9052a-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="9052a-123">Agregue los [dominios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) de su organización.</span><span class="sxs-lookup"><span data-stu-id="9052a-123">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="9052a-124">Use las [guías de configuración en el Centro de administración de Microsoft 365.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="9052a-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="9052a-125">Cree su infraestructura [de identidades](identity-roadmap-microsoft-365.md) y [proteja los inicios de sesión de usuario.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="9052a-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="9052a-126">Mover las ubicaciones geográficas de un inquilino</span><span class="sxs-lookup"><span data-stu-id="9052a-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="9052a-127">Microsoft continúa abierto nuevas ubicaciones geográficas de centros de datos (geos) para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9052a-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="9052a-128">Estas nuevas ubicaciones geográficas de centro de datos agregan capacidad y recursos de cálculo para admitir la demanda del cliente y el crecimiento del uso.</span><span class="sxs-lookup"><span data-stu-id="9052a-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="9052a-129">Además, las nuevas ubicaciones geográficas del centro de datos ofrecen residencia de datos en la ubicación geográfica para los datos principales de los clientes.</span><span class="sxs-lookup"><span data-stu-id="9052a-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="9052a-130">Para obtener más información, vea Mover los datos principales a las nuevas ubicaciones geográficas del centro de datos [de Microsoft 365.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="9052a-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="9052a-131">Implementar Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="9052a-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="9052a-132">Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="9052a-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="9052a-133">Para más información, vea [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="9052a-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="9052a-134">Administrar varios inquilinos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9052a-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="9052a-135">Aunque es ideal tener un único inquilino para la organización, puede ser una de las muchas organizaciones que tienen varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="9052a-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="9052a-136">Los motivos pueden incluir fusiones y adquisiciones, quieres aislamiento administrativo o tienes una TI descentralizada.</span><span class="sxs-lookup"><span data-stu-id="9052a-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="9052a-137">Si tiene varios inquilinos de Microsoft 365, vea estos artículos para obtener más información sobre:</span><span class="sxs-lookup"><span data-stu-id="9052a-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="9052a-138">Colaboración entre inquilinos</span><span class="sxs-lookup"><span data-stu-id="9052a-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="9052a-139">Migración de buzones de inquilinos cruzados</span><span class="sxs-lookup"><span data-stu-id="9052a-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="9052a-140">Migraciones de espacio empresarial a espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="9052a-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="9052a-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="9052a-141">Next step</span></span>

<span data-ttu-id="9052a-142">Inicie la planeación del espacio empresarial [con suscripciones, licencias, cuentas e inquilinos.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="9052a-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
