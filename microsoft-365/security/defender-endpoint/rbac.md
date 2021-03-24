---
title: Usar el control de acceso basado en roles para conceder acceso preciso al Centro de seguridad de Microsoft Defender
description: Cree roles y grupos dentro de las operaciones de seguridad para conceder acceso al portal.
keywords: rbac, role, based, access, control, groups, control, tier, aad
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071880"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="54d85-104">Administrar el acceso al portal mediante el control de acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="54d85-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54d85-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="54d85-105">**Applies to:**</span></span>
- <span data-ttu-id="54d85-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="54d85-106">Azure Active Directory</span></span>
- <span data-ttu-id="54d85-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="54d85-107">Office 365</span></span>

> <span data-ttu-id="54d85-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="54d85-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54d85-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="54d85-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="54d85-110">Con el control de acceso basado en roles (RBAC), puede crear roles y grupos dentro del equipo de operaciones de seguridad para conceder el acceso adecuado al portal.</span><span class="sxs-lookup"><span data-stu-id="54d85-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="54d85-111">En función de los roles y grupos que cree, tiene un control preciso sobre lo que los usuarios con acceso al portal pueden ver y hacer.</span><span class="sxs-lookup"><span data-stu-id="54d85-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="54d85-112">Los grandes equipos de operaciones de seguridad distribuidas geográficamente suelen adoptar un modelo basado en niveles para asignar y autorizar el acceso a portales de seguridad.</span><span class="sxs-lookup"><span data-stu-id="54d85-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="54d85-113">Los niveles típicos incluyen los tres niveles siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d85-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="54d85-114">Nivel</span><span class="sxs-lookup"><span data-stu-id="54d85-114">Tier</span></span> | <span data-ttu-id="54d85-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="54d85-115">Description</span></span>
:---|:---
<span data-ttu-id="54d85-116">Nivel 1</span><span class="sxs-lookup"><span data-stu-id="54d85-116">Tier 1</span></span> | <span data-ttu-id="54d85-117">**Equipo de operaciones de seguridad local / equipo de TI**</span><span class="sxs-lookup"><span data-stu-id="54d85-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="54d85-118">Este equipo normalmente realiza una triage e investiga las alertas contenidas en su geolocalización y escala al nivel 2 en los casos en los que se requiere una corrección activa.</span><span class="sxs-lookup"><span data-stu-id="54d85-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="54d85-119">Nivel 2</span><span class="sxs-lookup"><span data-stu-id="54d85-119">Tier 2</span></span> | <span data-ttu-id="54d85-120">**Equipo de operaciones de seguridad regional**</span><span class="sxs-lookup"><span data-stu-id="54d85-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="54d85-121">Este equipo puede ver todos los dispositivos de su región y realizar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="54d85-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="54d85-122">Nivel 3</span><span class="sxs-lookup"><span data-stu-id="54d85-122">Tier 3</span></span> | <span data-ttu-id="54d85-123">**Equipo de operaciones de seguridad global**</span><span class="sxs-lookup"><span data-stu-id="54d85-123">**Global security operations team**</span></span> <br> <span data-ttu-id="54d85-124">Este equipo está formado por expertos en seguridad y están autorizados a ver y realizar todas las acciones desde el portal.</span><span class="sxs-lookup"><span data-stu-id="54d85-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="54d85-125">Defender for Endpoint RBAC está diseñado para admitir el modelo de opciones basado en roles o niveles y le proporciona un control detallado sobre qué roles pueden ver, los dispositivos a los que pueden acceder y las acciones que pueden realizar.</span><span class="sxs-lookup"><span data-stu-id="54d85-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="54d85-126">El marco RBAC se centra en los siguientes controles:</span><span class="sxs-lookup"><span data-stu-id="54d85-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="54d85-127">**Controlar quién puede realizar una acción específica**</span><span class="sxs-lookup"><span data-stu-id="54d85-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="54d85-128">Crea roles personalizados y controla a qué capacidades de Defender for Endpoint pueden acceder con granularidad.</span><span class="sxs-lookup"><span data-stu-id="54d85-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="54d85-129">**Controlar quién puede ver información sobre grupos o grupos de dispositivos específicos**</span><span class="sxs-lookup"><span data-stu-id="54d85-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="54d85-130">[Cree grupos de](machine-groups.md) dispositivos por criterios específicos, como nombres, etiquetas, dominios y otros, y, a continuación, conceda acceso a los roles mediante un grupo de usuarios específico de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="54d85-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="54d85-131">Para implementar el acceso basado en roles, deberá definir roles de administrador, asignar los permisos correspondientes y asignar grupos de usuarios de Azure AD asignados a los roles.</span><span class="sxs-lookup"><span data-stu-id="54d85-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="54d85-132">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="54d85-132">Before you begin</span></span>
<span data-ttu-id="54d85-133">Antes de usar RBAC, es importante que comprenda los roles que pueden conceder permisos y las consecuencias de activar RBAC.</span><span class="sxs-lookup"><span data-stu-id="54d85-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="54d85-134">Antes de habilitar la característica, es importante que tenga un rol de administrador global o de administrador de seguridad en Azure AD y que tenga los grupos de Azure AD listos para reducir el riesgo de que se bloquee el portal.</span><span class="sxs-lookup"><span data-stu-id="54d85-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="54d85-135">Al iniciar sesión por primera vez en el Centro de seguridad de Microsoft Defender, se le concede acceso completo o acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="54d85-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="54d85-136">Los derechos de acceso completo se conceden a los usuarios con roles de administrador de seguridad o administrador global en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="54d85-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="54d85-137">El acceso de solo lectura se concede a los usuarios con un rol lector de seguridad en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="54d85-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="54d85-138">Alguien con un rol de administrador global de Defender for Endpoint tiene acceso sin restricciones a todos los dispositivos, independientemente de su asociación de grupo de dispositivos y las asignaciones de grupos de usuarios de Azure AD</span><span class="sxs-lookup"><span data-stu-id="54d85-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="54d85-139">Inicialmente, solo aquellos con derechos de administrador global de Azure AD o administrador de seguridad podrán crear y asignar roles en el Centro de seguridad de Microsoft Defender, por lo que es importante tener los grupos adecuados listos en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="54d85-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="54d85-140">**Al activar el control de acceso basado en roles, los usuarios con permisos de solo lectura (por ejemplo, los usuarios asignados al rol de lector de seguridad de Azure AD) perderán el acceso hasta que se les asigne un rol.**</span><span class="sxs-lookup"><span data-stu-id="54d85-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="54d85-141">A los usuarios con permisos de administrador se les asigna automáticamente el rol de administrador global de Defender for Endpoint integrado predeterminado con permisos completos.</span><span class="sxs-lookup"><span data-stu-id="54d85-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="54d85-142">Después de participar en el uso de RBAC, puede asignar usuarios adicionales que no sean administradores globales o de seguridad de Azure AD al rol de administrador global de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="54d85-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="54d85-143">Después de participar en el uso de RBAC, no puede volver a los roles iniciales como cuando inició sesión por primera vez en el portal.</span><span class="sxs-lookup"><span data-stu-id="54d85-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="54d85-144">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="54d85-144">Related topic</span></span>
- [<span data-ttu-id="54d85-145">Crear y administrar grupos de dispositivos en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="54d85-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
