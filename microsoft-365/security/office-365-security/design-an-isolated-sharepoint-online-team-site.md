---
title: Diseñar un sitio de grupo de SharePoint Online aislado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Diseñe sitios de grupo aislados de SharePoint Online, incluidos los niveles de permisos, asigne permisos a usuarios con grupos de acceso y grupos anidados de Azure AD.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288340"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="d4a04-103">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="d4a04-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d4a04-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="d4a04-104">**Applies to**</span></span>
- [<span data-ttu-id="d4a04-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d4a04-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d4a04-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4a04-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="d4a04-107">**Resumen:** Paso a paso por el proceso de diseño para sitios de grupo aislados de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d4a04-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="d4a04-108">Este artículo le lleva a través de las decisiones de diseño clave que debe tomar antes de crear un sitio de grupo de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="d4a04-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="d4a04-109">Fase 1: Determinar los grupos y niveles de permisos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4a04-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="d4a04-110">Todos los sitios de grupo de SharePoint Online se crean de forma predeterminada con los siguientes grupos de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="d4a04-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="d4a04-111">\<site name> Miembros</span><span class="sxs-lookup"><span data-stu-id="d4a04-111">\<site name> Members</span></span>

- <span data-ttu-id="d4a04-112">\<site name> Visitantes</span><span class="sxs-lookup"><span data-stu-id="d4a04-112">\<site name> Visitors</span></span>

- <span data-ttu-id="d4a04-113">\<site name> Propietarios</span><span class="sxs-lookup"><span data-stu-id="d4a04-113">\<site name> Owners</span></span>

<span data-ttu-id="d4a04-114">Estos grupos son independientes de los grupos de Microsoft 365 y Azure Active Directory (AD) y son la base para asignar permisos para los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="d4a04-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="d4a04-115">El conjunto de permisos específicos que determina lo que un miembro de un grupo de SharePoint puede hacer en un sitio es un nivel de permisos.</span><span class="sxs-lookup"><span data-stu-id="d4a04-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="d4a04-116">Hay tres niveles de permisos de forma predeterminada para un sitio de grupo de SharePoint Online: Edición, Lectura y Control total.</span><span class="sxs-lookup"><span data-stu-id="d4a04-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="d4a04-117">En la tabla siguiente se muestra la correlación predeterminada de los grupos de SharePoint y los niveles de permisos asignados:</span><span class="sxs-lookup"><span data-stu-id="d4a04-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="d4a04-118">Grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4a04-118">SharePoint group</span></span>|<span data-ttu-id="d4a04-119">Nivel de permisos</span><span class="sxs-lookup"><span data-stu-id="d4a04-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="d4a04-120">\<site name> Miembros</span><span class="sxs-lookup"><span data-stu-id="d4a04-120">\<site name> Members</span></span>|<span data-ttu-id="d4a04-121">Editar</span><span class="sxs-lookup"><span data-stu-id="d4a04-121">Edit</span></span>|
|<span data-ttu-id="d4a04-122">\<site name> Visitantes</span><span class="sxs-lookup"><span data-stu-id="d4a04-122">\<site name> Visitors</span></span>|<span data-ttu-id="d4a04-123">Lectura</span><span class="sxs-lookup"><span data-stu-id="d4a04-123">Read</span></span>|
|<span data-ttu-id="d4a04-124">\<site name> Propietarios</span><span class="sxs-lookup"><span data-stu-id="d4a04-124">\<site name> Owners</span></span>|<span data-ttu-id="d4a04-125">Control total</span><span class="sxs-lookup"><span data-stu-id="d4a04-125">Full control</span></span>|
|

 <span data-ttu-id="d4a04-126">**Procedimiento recomendado:** Puede crear grupos y niveles de permisos adicionales de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a04-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="d4a04-127">Sin embargo, se recomienda usar los grupos y niveles de permisos predeterminados de SharePoint para el sitio aislado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d4a04-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="d4a04-128">Estos son los grupos y niveles de permisos predeterminados de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a04-128">Here are the default SharePoint groups and permission levels.</span></span>

![Los grupos y niveles de permisos predeterminados de SharePoint para un sitio de SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="d4a04-130">Fase 2: Asignar permisos a usuarios con grupos de acceso</span><span class="sxs-lookup"><span data-stu-id="d4a04-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="d4a04-131">Puede asignar permisos a los usuarios agregando su cuenta de usuario, o un grupo de Microsoft 365 o Azure AD del que la cuenta de usuario es miembro, a los grupos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a04-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="d4a04-132">Una vez agregadas, a las cuentas de usuario, ya sea directa o indirectamente a través de la pertenencia a un grupo de Microsoft 365 o Azure AD, se les asigna el nivel de permisos asociado con el grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a04-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="d4a04-133">Usar los grupos de SharePoint predeterminados como ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d4a04-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="d4a04-134">A los miembros del **\<site name> grupo de** SharePoint Miembros, que pueden incluir cuentas de usuario y grupos, se les asigna el **nivel de** permiso Editar</span><span class="sxs-lookup"><span data-stu-id="d4a04-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="d4a04-135">A los miembros del **\<site name> grupo de** Visitantes de SharePoint, que pueden incluir cuentas de usuario y grupos, se les asigna el nivel **de** permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d4a04-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="d4a04-136">A los miembros del **\<site name> grupo propietarios** de SharePoint, que pueden incluir tanto cuentas de usuario como grupos, se les asigna el nivel de **permiso Control** total</span><span class="sxs-lookup"><span data-stu-id="d4a04-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="d4a04-137">**Procedimiento recomendado:** Aunque puede administrar permisos a través de cuentas de usuario individuales, se recomienda usar un único grupo de Azure AD, conocido como grupo de acceso, en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d4a04-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="d4a04-138">Esto simplifica la administración de permisos mediante la pertenencia al grupo de acceso, en lugar de administrar la lista de cuentas de usuario para cada grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a04-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="d4a04-139">Los grupos de Azure AD para Microsoft 365 son diferentes, por ejemplo, grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4a04-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="d4a04-140">Los grupos de Azure AD aparecen en el  Centro  de administración de Microsoft 365 con su tipo establecido en Seguridad y no tienen una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d4a04-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="d4a04-141">Los grupos de Azure AD se pueden administrar en:</span><span class="sxs-lookup"><span data-stu-id="d4a04-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="d4a04-142">Servicios de dominio de Active Directory (AD DS)</span><span class="sxs-lookup"><span data-stu-id="d4a04-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="d4a04-143">Se trata de grupos que se han creado en la infraestructura local de AD DS y se han sincronizado con su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4a04-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="d4a04-144">En el Centro de administración de Microsoft 365, estos grupos tienen un estado **de** sincronización con **Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="d4a04-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="d4a04-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="d4a04-145">Office 365</span></span>

    <span data-ttu-id="d4a04-146">Se trata de grupos creados con el Centro de administración de Microsoft 365, Azure Portal o PowerShell de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4a04-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="d4a04-147">En el Centro de administración de Microsoft 365, estos grupos tienen un **estado** de **nube.**</span><span class="sxs-lookup"><span data-stu-id="d4a04-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="d4a04-148">**Procedimiento recomendado:** Si usa AD DS local y se sincroniza con su suscripción de Microsoft 365, realice la administración de usuarios y grupos con AD DS.</span><span class="sxs-lookup"><span data-stu-id="d4a04-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="d4a04-149">Para los sitios de grupo de SharePoint Online aislados, la estructura de grupo recomendada tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d4a04-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="d4a04-150">Grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4a04-150">SharePoint group</span></span>|<span data-ttu-id="d4a04-151">Grupo de acceso basado en Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4a04-151">Azure AD-based access group</span></span>|<span data-ttu-id="d4a04-152">Nivel de permisos</span><span class="sxs-lookup"><span data-stu-id="d4a04-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="d4a04-153">\<site name> Miembros</span><span class="sxs-lookup"><span data-stu-id="d4a04-153">\<site name> Members</span></span>|<span data-ttu-id="d4a04-154">\<site name> Miembros</span><span class="sxs-lookup"><span data-stu-id="d4a04-154">\<site name> Members</span></span>|<span data-ttu-id="d4a04-155">Editar</span><span class="sxs-lookup"><span data-stu-id="d4a04-155">Edit</span></span>|
|<span data-ttu-id="d4a04-156">\<site name> Visitantes</span><span class="sxs-lookup"><span data-stu-id="d4a04-156">\<site name> Visitors</span></span>|<span data-ttu-id="d4a04-157">\<site name> Visores</span><span class="sxs-lookup"><span data-stu-id="d4a04-157">\<site name> Viewers</span></span>|<span data-ttu-id="d4a04-158">Lectura</span><span class="sxs-lookup"><span data-stu-id="d4a04-158">Read</span></span>|
|<span data-ttu-id="d4a04-159">\<site name> Propietarios</span><span class="sxs-lookup"><span data-stu-id="d4a04-159">\<site name> Owners</span></span>|<span data-ttu-id="d4a04-160">\<site name> Administradores</span><span class="sxs-lookup"><span data-stu-id="d4a04-160">\<site name> Admins</span></span>|<span data-ttu-id="d4a04-161">Control total</span><span class="sxs-lookup"><span data-stu-id="d4a04-161">Full control</span></span>|
|

 <span data-ttu-id="d4a04-162">**Procedimiento recomendado:** Aunque puede usar grupos de Microsoft 365 o Azure AD como miembros de grupos de SharePoint, se recomienda usar grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d4a04-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="d4a04-163">Los grupos de Azure AD, administrados a través de AD DS o Microsoft 365, ofrecen más flexibilidad para usar grupos anidados para asignar permisos.</span><span class="sxs-lookup"><span data-stu-id="d4a04-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="d4a04-164">Estos son los grupos de SharePoint predeterminados configurados para usar grupos de acceso basados en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d4a04-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Usar grupos de acceso como miembros de grupos de sitios predeterminados de SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="d4a04-166">Al diseñar los tres grupos de acceso, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4a04-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="d4a04-167">Solo debe haber unos pocos **\<site name>** miembros en el grupo de acceso Administradores, correspondiente a un pequeño número de administradores de SharePoint Online que administran el sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="d4a04-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="d4a04-168">La mayoría de los miembros del sitio están en los grupos **\<site name> de** acceso Miembros o Visores. **\<site name>**</span><span class="sxs-lookup"><span data-stu-id="d4a04-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="d4a04-169">Dado que los miembros del **sitio \<site name>** del grupo de acceso Miembros tienen la capacidad de eliminar o modificar recursos del sitio, considere detenidamente su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="d4a04-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="d4a04-170">Cuando haya dudas, agregue el miembro del sitio al grupo **\<site name> de acceso** Visores.</span><span class="sxs-lookup"><span data-stu-id="d4a04-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="d4a04-171">Este es un ejemplo de los grupos de SharePoint y grupos de acceso para un sitio aislado denominado ProjectX.</span><span class="sxs-lookup"><span data-stu-id="d4a04-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Ejemplo de uso de grupos de acceso para un sitio de SharePoint Online denominado ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="d4a04-173">Fase 3: Usar grupos anidados de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4a04-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="d4a04-174">Para un proyecto limitado a un número reducido de personas, la mayoría de los escenarios se ajustarán a la mayoría de los escenarios con un solo nivel de grupos de acceso basados en Azure AD agregados a los grupos de SharePoint del sitio.</span><span class="sxs-lookup"><span data-stu-id="d4a04-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="d4a04-175">Sin embargo, si tiene un gran número de personas y esas personas ya son miembros de grupos de Azure AD establecidos, puede asignar más fácilmente permisos de SharePoint mediante grupos anidados o grupos que contienen otros grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="d4a04-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="d4a04-176">Por ejemplo, desea crear un sitio de grupo aislado de SharePoint Online para la colaboración entre los ejecutivos de los departamentos de ventas, marketing, ingeniería, legal y soporte técnico, y esos departamentos ya son sus propios grupos con la pertenencia a cuentas de usuario ejecutivo.</span><span class="sxs-lookup"><span data-stu-id="d4a04-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="d4a04-177">En lugar de crear un nuevo grupo para los nuevos miembros del sitio y colocar todas las cuentas de usuario ejecutivo individuales en él, coloque los grupos ejecutivos existentes para cada departamento en el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="d4a04-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="d4a04-178">Si comparte una suscripción de Microsoft 365 entre varias organizaciones, es posible que sea difícil administrar un solo nivel de pertenencia a grupos para un sitio aislado de una organización debido al gran número de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="d4a04-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="d4a04-179">En este caso, puede usar grupos anidados de Azure AD para cada organización que contenga los grupos dentro de sus organizaciones para administrar los permisos.</span><span class="sxs-lookup"><span data-stu-id="d4a04-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="d4a04-180">Para usar grupos anidados de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="d4a04-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="d4a04-181">Identifique o cree los grupos de Azure AD que contendrán cuentas de usuario y agregue las cuentas de usuario apropiadas como miembros.</span><span class="sxs-lookup"><span data-stu-id="d4a04-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="d4a04-182">Cree el grupo de acceso basado en Azure AD contenedor que contendrá los demás grupos de Azure AD y agregue esos grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="d4a04-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="d4a04-183">Para el nivel de acceso adecuado para el grupo de acceso de contenedor, identifique el grupo de SharePoint y el nivel de permisos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d4a04-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="d4a04-184">No puede usar grupos anidados de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4a04-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="d4a04-185">Este es un ejemplo de grupos anidados de Azure AD para el grupo de acceso de miembros de ProjectX.</span><span class="sxs-lookup"><span data-stu-id="d4a04-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Ejemplo de uso de grupos de acceso anidados para el grupo de acceso de miembros para el sitio ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="d4a04-187">Dado que todas las cuentas de usuario de los equipos de investigación, ingeniería y proyectos principales están pensadas para ser miembros del sitio, es más fácil agregar sus grupos de Azure AD al grupo de acceso de miembros de ProjectX.</span><span class="sxs-lookup"><span data-stu-id="d4a04-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4a04-188">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d4a04-188">Next step</span></span>

<span data-ttu-id="d4a04-189">Cuando esté listo para crear y configurar un sitio aislado en producción, vea Implementar un sitio de grupo de [SharePoint Online aislado.](deploy-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="d4a04-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a04-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4a04-190">See Also</span></span>

[<span data-ttu-id="d4a04-191">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="d4a04-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="d4a04-192">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="d4a04-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="d4a04-193">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="d4a04-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
