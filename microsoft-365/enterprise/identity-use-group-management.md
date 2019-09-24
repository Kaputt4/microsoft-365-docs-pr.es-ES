---
title: 'Paso 5: Usar grupos para administración'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Se pueden usar grupos para automatizar la administración de algunas tareas administrativas.
ms.openlocfilehash: 01bbce00457362ed0eb089e126f0d17f31237eb4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37093009"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="4efdb-103">Paso 5: Usar grupos para administración</span><span class="sxs-lookup"><span data-stu-id="4efdb-103">Step 6: Use groups for easier management</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="4efdb-104">Permitir a los usuarios crear y administrar sus propios grupos</span><span class="sxs-lookup"><span data-stu-id="4efdb-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="4efdb-105">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4efdb-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4efdb-106">En esta sección, podrá identificar grupos de Azure Active Directory (Azure AD) que pueden ser administrados por los propietarios del grupo en lugar de los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="4efdb-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="4efdb-107">Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4efdb-107">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="4efdb-p102">Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="4efdb-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="4efdb-110">La administración de grupos de autoservicio está disponible solo para grupos de seguridad de Azure AD y Office 365.</span><span class="sxs-lookup"><span data-stu-id="4efdb-110">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="4efdb-111">No está disponible para grupos habilitados por correo electrónico listas de distribución o grupos sincronizados desde su Active Directory Domain Services (AD DS) local.</span><span class="sxs-lookup"><span data-stu-id="4efdb-111">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="4efdb-112">Para obtener más información, consulte las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="4efdb-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="4efdb-113">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-self-service-groups) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="4efdb-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="4efdb-114">Configurar la pertenencia a grupo dinámico</span><span class="sxs-lookup"><span data-stu-id="4efdb-114">Set up dynamic group membership</span></span>

<span data-ttu-id="4efdb-115">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4efdb-115">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4efdb-116">En esta sección, creará una serie de reglas para añadir o eliminar automáticamente cuentas de usuario como miembros de un grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4efdb-116">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="4efdb-117">Esto se conoce como *pertenencia a grupo dinámico*.</span><span class="sxs-lookup"><span data-stu-id="4efdb-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="4efdb-118">Las reglas se basan en atributos de cuenta de usuario, como el país o el departamento.</span><span class="sxs-lookup"><span data-stu-id="4efdb-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="4efdb-119">Las reglas se aplican de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4efdb-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="4efdb-120">Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.</span><span class="sxs-lookup"><span data-stu-id="4efdb-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="4efdb-121">Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="4efdb-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="4efdb-122">Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.</span><span class="sxs-lookup"><span data-stu-id="4efdb-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="4efdb-123">Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="4efdb-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="4efdb-p105">Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="4efdb-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="4efdb-126">Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4efdb-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="4efdb-127">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="4efdb-127">The results of this section are:</span></span>

- <span data-ttu-id="4efdb-128">Un conjunto de grupos de Azure AD que se puede configurar para la pertenencia dinámica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="4efdb-129">Un conjunto de reglas para cada grupo dinámico.</span><span class="sxs-lookup"><span data-stu-id="4efdb-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4efdb-131">Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="4efdb-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4efdb-132">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-dyn-groups) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="4efdb-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="4efdb-133">Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="4efdb-133">Set up automatic licensing</span></span>

<span data-ttu-id="4efdb-134">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4efdb-134">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4efdb-135">En esta sección, deberá configurar los grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones para todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="4efdb-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="4efdb-136">Esto se conoce como *licencias basadas en grupos*.</span><span class="sxs-lookup"><span data-stu-id="4efdb-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="4efdb-137">Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="4efdb-137">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="4efdb-138">Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar la licencia apropiada de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4efdb-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="4efdb-139">Asegúrese de que tiene suficientes licencias para todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="4efdb-139">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="4efdb-140">Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="4efdb-140">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="4efdb-141">No configure las *licencias basadas en grupos* para los grupos que contengan cuentas entre empresas (B2B) de Azure.</span><span class="sxs-lookup"><span data-stu-id="4efdb-141">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="4efdb-142">Para obtener más información, vea [Conceptos básicos de las licencias basadas en grupos de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4efdb-142">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="4efdb-143">Vea los [pasos para configurar las licencias basadas en grupos para un grupo de seguridad de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4efdb-143">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="4efdb-144">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="4efdb-144">The results of this section are:</span></span>

- <span data-ttu-id="4efdb-145">Identificó los grupos de seguridad adecuados para las licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="4efdb-145">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="4efdb-146">Configuró estos grupos para las licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="4efdb-146">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4efdb-148">Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="4efdb-148">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4efdb-149">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-group-license) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="4efdb-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="4efdb-150">Configurar Identity Governance</span><span class="sxs-lookup"><span data-stu-id="4efdb-150">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
