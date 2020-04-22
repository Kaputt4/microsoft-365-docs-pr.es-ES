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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Resumen: paso a paso del proceso de diseño de sitios de grupo de SharePoint Online aislados.'
ms.openlocfilehash: 5efd5fb0501d88fda37f1530ef62e4c5110e4da2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638517"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="f29b9-103">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="f29b9-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="f29b9-104">**Resumen:** Recorra el proceso de diseño de sitios de grupo de SharePoint Online aislados.</span><span class="sxs-lookup"><span data-stu-id="f29b9-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="f29b9-105">Este artículo le guiará por las decisiones de diseño clave que debe tomar antes de crear un sitio de grupo de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="f29b9-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="f29b9-106">Fase 1: determinar los grupos de SharePoint y los niveles de permisos</span><span class="sxs-lookup"><span data-stu-id="f29b9-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="f29b9-107">Todos los sitios de grupo de SharePoint Online se crean de forma predeterminada con los siguientes grupos de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="f29b9-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="f29b9-108">\<nombre del sitio> miembros</span><span class="sxs-lookup"><span data-stu-id="f29b9-108">\<site name> Members</span></span>
    
- <span data-ttu-id="f29b9-109">\<nombre del sitio> visitantes</span><span class="sxs-lookup"><span data-stu-id="f29b9-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="f29b9-110">\<nombre del sitio> propietarios</span><span class="sxs-lookup"><span data-stu-id="f29b9-110">\<site name> Owners</span></span>
    
<span data-ttu-id="f29b9-111">Estos grupos son independientes de los grupos de Microsoft 365 y Azure Active Directory (AD) y constituyen la base para asignar permisos a los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="f29b9-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="f29b9-112">El conjunto de permisos específicos que determina lo que un miembro de un grupo de SharePoint puede hacer en un sitio es un nivel de permisos.</span><span class="sxs-lookup"><span data-stu-id="f29b9-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="f29b9-113">De forma predeterminada, hay tres niveles de permisos para un sitio de grupo de SharePoint Online: editar, leer y control total.</span><span class="sxs-lookup"><span data-stu-id="f29b9-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="f29b9-114">La siguiente tabla muestra la correlación predeterminada de los grupos de SharePoint y los niveles de permisos asignados:</span><span class="sxs-lookup"><span data-stu-id="f29b9-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="f29b9-115">**Grupo de SharePoint**</span><span class="sxs-lookup"><span data-stu-id="f29b9-115">**SharePoint group**</span></span>|<span data-ttu-id="f29b9-116">**Nivel de permisos**</span><span class="sxs-lookup"><span data-stu-id="f29b9-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f29b9-117">\<nombre del sitio> miembros</span><span class="sxs-lookup"><span data-stu-id="f29b9-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="f29b9-118">Edit</span><span class="sxs-lookup"><span data-stu-id="f29b9-118">Edit</span></span>  <br/> |
|<span data-ttu-id="f29b9-119">\<nombre del sitio> visitantes</span><span class="sxs-lookup"><span data-stu-id="f29b9-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="f29b9-120">Leer</span><span class="sxs-lookup"><span data-stu-id="f29b9-120">Read</span></span>  <br/> |
|<span data-ttu-id="f29b9-121">\<nombre del sitio> propietarios</span><span class="sxs-lookup"><span data-stu-id="f29b9-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="f29b9-122">Control total</span><span class="sxs-lookup"><span data-stu-id="f29b9-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="f29b9-123">**Procedimiento recomendado:** Puede crear grupos de SharePoint y niveles de permisos adicionales.</span><span class="sxs-lookup"><span data-stu-id="f29b9-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="f29b9-124">Sin embargo, se recomienda usar los grupos de SharePoint y los niveles de permisos predeterminados para el sitio de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="f29b9-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="f29b9-125">Estos son los grupos de SharePoint y los niveles de permisos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f29b9-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![Los grupos de SharePoint y los niveles de permisos predeterminados para un sitio de SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="f29b9-127">Fase 2: asignar permisos a los usuarios con grupos de acceso</span><span class="sxs-lookup"><span data-stu-id="f29b9-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="f29b9-128">Para asignar permisos a usuarios, puede agregar su cuenta de usuario o un grupo de Microsoft 365 o de Azure AD del que la cuenta de usuario es miembro a los grupos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f29b9-128">You can assign permissions to users by adding their user account, or an Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="f29b9-129">Una vez agregadas, las cuentas de usuario, ya sea directa o indirectamente a través de la pertenencia a un grupo de Microsoft 365 o de Azure AD, se les asigna el nivel de permisos asociado con el grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f29b9-129">Once added, the user accounts, either directly or indirectly via membership in an Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="f29b9-130">Con los grupos de SharePoint predeterminados como ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f29b9-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="f29b9-131">Los miembros del grupo de \*\* \<SharePoint nombre> miembros\*\* , que pueden incluir cuentas de usuario y grupos, tienen asignado el nivel de permisos **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f29b9-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="f29b9-132">Los miembros del \*\* \<nombre del sitio>\*\* grupo de SharePoint visitantes, que puede incluir cuentas de usuario y grupos, tienen asignado el nivel de permisos de **lectura** .</span><span class="sxs-lookup"><span data-stu-id="f29b9-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="f29b9-133">Se asigna el nivel de permisos **control total** a los miembros del \*\* \<nombre de sitio>\*\* grupo de SharePoint, que puede incluir cuentas de usuario y grupos.</span><span class="sxs-lookup"><span data-stu-id="f29b9-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="f29b9-134">**Procedimiento recomendado:** Aunque puede administrar permisos mediante cuentas de usuario individuales, en su lugar se recomienda usar un único grupo de Azure AD, conocido como grupo de acceso.</span><span class="sxs-lookup"><span data-stu-id="f29b9-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="f29b9-135">Esto simplifica la administración de permisos a través de la pertenencia al grupo de acceso, en lugar de administrar la lista de cuentas de usuario para cada grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f29b9-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="f29b9-136">Los grupos de Azure AD para Microsoft 365 son distintos de los grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f29b9-136">Azure AD groups for Microsoft 365 are different than Microsoft 365 groups.</span></span> <span data-ttu-id="f29b9-137">Los grupos de Azure AD aparecen en el centro de administración de Microsoft 365 con el **tipo** establecido en **seguridad** y no tienen una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f29b9-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="f29b9-138">Los grupos de Azure AD se pueden administrar dentro de:</span><span class="sxs-lookup"><span data-stu-id="f29b9-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="f29b9-139">Servicios de dominio de Active Directory (AD DS)</span><span class="sxs-lookup"><span data-stu-id="f29b9-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="f29b9-140">Estos son grupos que se han creado en su infraestructura de AD DS local y sincronizados con su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f29b9-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="f29b9-141">En el centro de administración de Microsoft 365, estos grupos tienen un **Estado** **sincronizado con Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="f29b9-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="f29b9-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="f29b9-142">Office 365</span></span>
    
    <span data-ttu-id="f29b9-143">Se trata de grupos que se han creado con el centro de administración de Microsoft 365, el portal de Azure o PowerShell de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f29b9-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="f29b9-144">En el centro de administración de Microsoft 365, estos grupos tienen un **Estado** de **nube**.</span><span class="sxs-lookup"><span data-stu-id="f29b9-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="f29b9-145">**Procedimiento recomendado:** Si está usando AD DS local y sincronizando con la suscripción de Microsoft 365, realice la administración de usuarios y grupos con AD DS.</span><span class="sxs-lookup"><span data-stu-id="f29b9-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="f29b9-146">Para los sitios de grupo de SharePoint Online aislados, la estructura de grupo recomendada tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="f29b9-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="f29b9-147">**Grupo de SharePoint**</span><span class="sxs-lookup"><span data-stu-id="f29b9-147">**SharePoint group**</span></span>|<span data-ttu-id="f29b9-148">**Grupo de acceso basado en Azure AD**</span><span class="sxs-lookup"><span data-stu-id="f29b9-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="f29b9-149">**Nivel de permisos**</span><span class="sxs-lookup"><span data-stu-id="f29b9-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f29b9-150">\<nombre del sitio> miembros</span><span class="sxs-lookup"><span data-stu-id="f29b9-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="f29b9-151">\<nombre del sitio> miembros</span><span class="sxs-lookup"><span data-stu-id="f29b9-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="f29b9-152">Edit</span><span class="sxs-lookup"><span data-stu-id="f29b9-152">Edit</span></span>  <br/> |
|<span data-ttu-id="f29b9-153">\<nombre del sitio> visitantes</span><span class="sxs-lookup"><span data-stu-id="f29b9-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="f29b9-154">\<nombre del sitio> visores</span><span class="sxs-lookup"><span data-stu-id="f29b9-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="f29b9-155">Leer</span><span class="sxs-lookup"><span data-stu-id="f29b9-155">Read</span></span>  <br/> |
|<span data-ttu-id="f29b9-156">\<nombre del sitio> propietarios</span><span class="sxs-lookup"><span data-stu-id="f29b9-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="f29b9-157">\<nombre del sitio> administradores</span><span class="sxs-lookup"><span data-stu-id="f29b9-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="f29b9-158">Control total</span><span class="sxs-lookup"><span data-stu-id="f29b9-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="f29b9-159">**Procedimiento recomendado:** Aunque puede usar los grupos de Microsoft 365 o de Azure AD como miembros de los grupos de SharePoint, le recomendamos que use grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f29b9-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="f29b9-160">Los grupos de Azure AD, administrados mediante AD DS o Microsoft 365, proporcionan más flexibilidad para usar grupos anidados para asignar permisos.</span><span class="sxs-lookup"><span data-stu-id="f29b9-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="f29b9-161">Estos son los grupos predeterminados de SharePoint configurados para usar grupos de acceso basados en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f29b9-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Uso de grupos de acceso como miembros de grupos de sitio de SharePoint Online predeterminados.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="f29b9-163">Al diseñar los tres grupos de acceso, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f29b9-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="f29b9-164">Debe haber solo unos pocos miembros en el \*\* \<\*\* grupo de acceso de nombre de sitio> administradores, que corresponde a un número reducido de administradores de SharePoint Online que administran el sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="f29b9-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="f29b9-165">La mayoría de los miembros del sitio se encuentran en el \*\* \<nombre del sitio> miembros\*\* o \*\* \<el nombre del sitio> los visores\*\* tienen acceso a los grupos.</span><span class="sxs-lookup"><span data-stu-id="f29b9-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="f29b9-166">Como los miembros del sitio \*\* \<\*\* en el grupo de acceso de nombre> miembros tienen la capacidad de eliminar o modificar los recursos del sitio, considere atentamente su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="f29b9-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="f29b9-167">En caso de duda, agregue el miembro de sitio al grupo de acceso de \*\* \<nombres de sitio> visores\*\* .</span><span class="sxs-lookup"><span data-stu-id="f29b9-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="f29b9-168">Este es un ejemplo de los grupos de SharePoint y los grupos de acceso para un sitio aislado denominado ProyectoX.</span><span class="sxs-lookup"><span data-stu-id="f29b9-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Un ejemplo del uso de grupos de acceso para un sitio de SharePoint Online denominado ProyectoX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="f29b9-170">Fase 3: usar grupos anidados de Azure AD</span><span class="sxs-lookup"><span data-stu-id="f29b9-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="f29b9-171">Para un proyecto limitado a un número reducido de personas, un solo nivel de grupos de acceso basado en Azure AD que se agrega a los grupos de SharePoint del sitio se ajustará a la mayoría de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="f29b9-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="f29b9-172">Sin embargo, si tiene un gran número de personas y esas personas ya son miembros de grupos de Azure AD establecidos, puede asignar permisos de SharePoint más fácilmente mediante grupos anidados o grupos que contengan otros grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="f29b9-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="f29b9-173">Por ejemplo, desea crear un sitio de grupo aislado de SharePoint Online para colaborar entre los ejecutivos de los departamentos de ventas, marketing, ingeniería, legal y soporte técnico, y los departamentos que ya tienen su propio grupo con pertenencia a la cuenta de usuario Ejecutivo.</span><span class="sxs-lookup"><span data-stu-id="f29b9-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="f29b9-174">En lugar de crear un grupo nuevo para los nuevos miembros del sitio y colocar en él todas las cuentas de usuario Ejecutiva, coloque los grupos ejecutivos existentes para cada departamento en el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="f29b9-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="f29b9-175">Si está compartiendo una suscripción de Microsoft 365 entre varias organizaciones, un único nivel de pertenencia al grupo de un sitio aislado para una organización podría ser difícil de administrar debido al número total de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="f29b9-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="f29b9-176">En este caso, puede usar grupos anidados de Azure AD para cada organización que contenga los grupos dentro de sus organizaciones para administrar los permisos.</span><span class="sxs-lookup"><span data-stu-id="f29b9-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="f29b9-177">Para usar grupos anidados de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="f29b9-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="f29b9-178">Identifique o cree los grupos de Azure AD que contendrán cuentas de usuario y agregue las cuentas de usuario adecuadas como miembros.</span><span class="sxs-lookup"><span data-stu-id="f29b9-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="f29b9-179">Cree el grupo de acceso de Azure AD basado en el contenedor que contendrá los otros grupos de Azure AD y agregue esos grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="f29b9-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="f29b9-180">Para el nivel adecuado de acceso para el grupo de acceso del contenedor, identifique el grupo de SharePoint y el nivel de permisos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f29b9-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f29b9-181">No puede usar grupos anidados de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f29b9-181">You cannot use nested Microsoft 365 groups.</span></span> 
  
<span data-ttu-id="f29b9-182">Este es un ejemplo de grupos de Azure AD anidados para el grupo de acceso a los miembros del ProyectoX.</span><span class="sxs-lookup"><span data-stu-id="f29b9-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Un ejemplo del uso de grupos de acceso anidados para el grupo de acceso de los miembros del sitio del ProyectoX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="f29b9-184">Debido a que todas las cuentas de usuario de los equipos de clientes potenciales de investigación, ingeniería y proyecto tienen como objetivo ser miembros del sitio, es más fácil agregar sus grupos de Azure AD al grupo de acceso de los miembros del ProyectoX.</span><span class="sxs-lookup"><span data-stu-id="f29b9-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="f29b9-185">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f29b9-185">Next step</span></span>

<span data-ttu-id="f29b9-186">Cuando esté listo para crear y configurar un sitio aislado en producción, vea [implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="f29b9-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f29b9-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="f29b9-187">See Also</span></span>

[<span data-ttu-id="f29b9-188">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="f29b9-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="f29b9-189">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="f29b9-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="f29b9-190">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="f29b9-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



