---
title: 'Paso 6: Uso de grupos para facilitar la administración'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la administración de grupos de autoservicio de Azure AD.
ms.openlocfilehash: 97077f5e047f55ea6bf6e532d25d25f4682ff179
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981781"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="3d181-103">Paso 6: Uso de grupos para facilitar la administración</span><span class="sxs-lookup"><span data-stu-id="3d181-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="3d181-104">Permitir a los usuarios crear y administrar sus propios grupos</span><span class="sxs-lookup"><span data-stu-id="3d181-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="3d181-105">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3d181-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3d181-106">En esta sección, podrá identificar grupos de Azure Active Directory (Azure AD) que pueden ser administrados por los propietarios del grupo en lugar de los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="3d181-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="3d181-107">Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d181-107">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="3d181-p102">Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="3d181-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="3d181-110">La administración de grupos de autoservicio está disponible solo para grupos de seguridad de Azure AD y Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d181-110">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="3d181-111">No está disponible para grupos habilitados por correo electrónico listas de distribución o grupos sincronizados desde su Active Directory Domain Services (AD DS) local.</span><span class="sxs-lookup"><span data-stu-id="3d181-111">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="3d181-112">Para obtener más información, consulte las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="3d181-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="3d181-113">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-self-service-groups) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="3d181-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="3d181-114">Configurar la pertenencia a grupo dinámico</span><span class="sxs-lookup"><span data-stu-id="3d181-114">Set up dynamic group membership</span></span>

<span data-ttu-id="3d181-115">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3d181-115">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3d181-116">En esta sección, creará una serie de reglas para añadir o eliminar automáticamente cuentas de usuario como miembros de un grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d181-116">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="3d181-117">Esto se conoce como *pertenencia a grupo dinámico*.</span><span class="sxs-lookup"><span data-stu-id="3d181-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="3d181-118">Las reglas se basan en atributos de cuenta de usuario, como el país o el departamento.</span><span class="sxs-lookup"><span data-stu-id="3d181-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="3d181-119">Las reglas se aplican de esta forma:</span><span class="sxs-lookup"><span data-stu-id="3d181-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="3d181-120">Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.</span><span class="sxs-lookup"><span data-stu-id="3d181-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="3d181-121">Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="3d181-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="3d181-122">Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.</span><span class="sxs-lookup"><span data-stu-id="3d181-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="3d181-123">Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="3d181-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="3d181-p105">Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="3d181-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="3d181-126">Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3d181-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="3d181-127">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="3d181-127">The results of this section are:</span></span>

- <span data-ttu-id="3d181-128">Un conjunto de grupos de Azure AD que se puede configurar para la pertenencia dinámica.</span><span class="sxs-lookup"><span data-stu-id="3d181-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="3d181-129">Un conjunto de reglas para cada grupo dinámico.</span><span class="sxs-lookup"><span data-stu-id="3d181-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3d181-131">Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="3d181-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="3d181-132">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-dyn-groups) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="3d181-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="3d181-133">Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="3d181-133">Set up automatic licensing</span></span>

<span data-ttu-id="3d181-134">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3d181-134">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3d181-135">En esta sección, deberá configurar los grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones para todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="3d181-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="3d181-136">Esto se conoce como *licencias basadas en grupos*.</span><span class="sxs-lookup"><span data-stu-id="3d181-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="3d181-137">Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="3d181-137">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="3d181-138">Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar la licencia apropiada de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3d181-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="3d181-139">Asegúrese de que tiene suficientes licencias para todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="3d181-139">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="3d181-140">Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="3d181-140">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="3d181-141">No configure las *licencias basadas en grupos* para los grupos que contengan cuentas entre empresas (B2B) de Azure.</span><span class="sxs-lookup"><span data-stu-id="3d181-141">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="3d181-142">Para obtener más información, vea [Conceptos básicos de las licencias basadas en grupos de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3d181-142">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="3d181-143">Vea los [pasos para configurar las licencias basadas en grupos para un grupo de seguridad de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3d181-143">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="3d181-144">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="3d181-144">The results of this section are:</span></span>

- <span data-ttu-id="3d181-145">Identificó los grupos de seguridad adecuados para las licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="3d181-145">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="3d181-146">Configuró estos grupos para las licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="3d181-146">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3d181-148">Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="3d181-148">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="3d181-149">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-group-license) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="3d181-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="3d181-150">Configurar Identity Governance</span><span class="sxs-lookup"><span data-stu-id="3d181-150">Configure identity governance</span></span>](identity-governance.md) |
