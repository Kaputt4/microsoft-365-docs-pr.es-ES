---
title: Administrar grupos de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar grupos de Microsoft 365.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328553"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="5ca91-103">Administrar grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ca91-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="5ca91-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5ca91-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5ca91-105">Puede administrar grupos de Microsoft 365 de varias maneras diferentes, según su configuración.</span><span class="sxs-lookup"><span data-stu-id="5ca91-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="5ca91-106">Puede administrar cuentas de usuario en el Centro de administración de [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/add-users/)PowerShell, en Servicios de dominio de Active Directory (AD DS) o en el Centro de administración de [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="5ca91-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="5ca91-107">Planear dónde y cómo administrará los grupos</span><span class="sxs-lookup"><span data-stu-id="5ca91-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="5ca91-108">El lugar y la forma en que puede administrar las cuentas de usuario depende del modelo de identidad que desee usar para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ca91-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="5ca91-109">Los dos modelos generales son híbridos y solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="5ca91-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="5ca91-110">Solo de nube</span><span class="sxs-lookup"><span data-stu-id="5ca91-110">Cloud-only</span></span>

<span data-ttu-id="5ca91-111">Puede crear y administrar grupos con:</span><span class="sxs-lookup"><span data-stu-id="5ca91-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="5ca91-112">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ca91-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="5ca91-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ca91-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="5ca91-114">Centro de administración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5ca91-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="5ca91-115">Híbrido</span><span class="sxs-lookup"><span data-stu-id="5ca91-115">Hybrid</span></span>

<span data-ttu-id="5ca91-116">Los grupos de AD DS se sincronizan con Microsoft 365 desde AD DS, por lo que debe usar las herramientas locales de AD DS para administrar estos grupos.</span><span class="sxs-lookup"><span data-stu-id="5ca91-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="5ca91-117">También puedes crear y administrar grupos de Azure AD independientes de los grupos de AD DS, pero que pueden contener usuarios y grupos de AD DS.</span><span class="sxs-lookup"><span data-stu-id="5ca91-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="5ca91-118">En este caso, puede usar:</span><span class="sxs-lookup"><span data-stu-id="5ca91-118">In this case, you can use:</span></span>

- [<span data-ttu-id="5ca91-119">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ca91-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="5ca91-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ca91-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="5ca91-121">Centro de administración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5ca91-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="5ca91-122">Permitir a los usuarios crear y administrar sus propios grupos</span><span class="sxs-lookup"><span data-stu-id="5ca91-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="5ca91-123">Azure AD permite grupos que pueden administrar los propietarios de grupos en lugar de los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="5ca91-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="5ca91-124">Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5ca91-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="5ca91-p105">Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="5ca91-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="5ca91-127">La administración de grupos de autoservicio está disponible solo para grupos de seguridad de Azure AD y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ca91-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="5ca91-128">No está disponible para grupos habilitados para correo, listas de distribución ni para ningún grupo que se haya sincronizado desde AD DS.</span><span class="sxs-lookup"><span data-stu-id="5ca91-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="5ca91-129">Para obtener más información, consulte las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="5ca91-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="5ca91-130">Configurar la pertenencia a grupo dinámico</span><span class="sxs-lookup"><span data-stu-id="5ca91-130">Set up dynamic group membership</span></span>

<span data-ttu-id="5ca91-131">Azure AD admite la configuración de una serie de reglas que agregan o quitan automáticamente cuentas de usuario como miembros de un grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ca91-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="5ca91-132">Esto se conoce como *pertenencia a grupo dinámico*.</span><span class="sxs-lookup"><span data-stu-id="5ca91-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="5ca91-133">Las reglas se basan en atributos de cuenta de usuario, como el país o el departamento.</span><span class="sxs-lookup"><span data-stu-id="5ca91-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="5ca91-134">Las reglas se aplican de esta forma:</span><span class="sxs-lookup"><span data-stu-id="5ca91-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="5ca91-135">Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.</span><span class="sxs-lookup"><span data-stu-id="5ca91-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="5ca91-136">Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="5ca91-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="5ca91-137">Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.</span><span class="sxs-lookup"><span data-stu-id="5ca91-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="5ca91-138">Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="5ca91-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="5ca91-p108">Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="5ca91-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="5ca91-141">Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5ca91-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="5ca91-142">Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="5ca91-142">Set up automatic licensing</span></span>

<span data-ttu-id="5ca91-143">Puedes configurar grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="5ca91-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="5ca91-144">Esto se conoce como *licencias basadas en grupos*.</span><span class="sxs-lookup"><span data-stu-id="5ca91-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="5ca91-145">Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5ca91-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="5ca91-146">Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar la licencia apropiada de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5ca91-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="5ca91-147">Asegúrese de que tiene suficientes licencias para todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="5ca91-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="5ca91-148">Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="5ca91-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="5ca91-149">No configure las licencias basadas en grupos para los grupos que contengan cuentas entre empresas (B2B) de Azure.</span><span class="sxs-lookup"><span data-stu-id="5ca91-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="5ca91-150">Para obtener más información, consulte Conceptos básicos [de licencias basadas en grupos en Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="5ca91-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="5ca91-151">Vea las [instrucciones para configurar licencias basadas en grupos para un grupo de seguridad de Azure.](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="5ca91-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
