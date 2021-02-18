---
title: Administrar un sitio de grupo de SharePoint Online aislado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Administre un sitio de grupo de SharePoint Online aislado, agregue nuevos usuarios y grupos, quite usuarios y grupos y cree una subcarpeta de documentos con permisos personalizados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289526"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="bddc5-103">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="bddc5-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bddc5-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bddc5-104">**Applies to**</span></span>
- [<span data-ttu-id="bddc5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bddc5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bddc5-106">Plan 1 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bddc5-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="bddc5-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bddc5-107">SharePoint Online</span></span> 

 <span data-ttu-id="bddc5-108">**Resumen:** Administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="bddc5-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="bddc5-109">En este artículo se describen las operaciones de administración comunes para un sitio de grupo de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="bddc5-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="bddc5-110">Agregar un nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="bddc5-110">Add a new user</span></span>

<span data-ttu-id="bddc5-111">Cuando alguien nuevo se une al sitio, debe decidir su nivel de participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="bddc5-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="bddc5-112">Administración: agregar la nueva cuenta de usuario al grupo de acceso de administradores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="bddc5-113">Colaboración activa: agregar la cuenta de usuario al grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="bddc5-114">Visualización: agregar la cuenta de usuario al grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="bddc5-115">Si administra cuentas de usuario y grupos a través de servicios de dominio de Active Directory (AD DS), agregue los usuarios adecuados a los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a que se la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="bddc5-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="bddc5-116">Si administra cuentas de usuario y grupos a través de Microsoft 365, puede usar el Centro de administración de Microsoft 365 o PowerShell de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="bddc5-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="bddc5-117">Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para agregar los usuarios adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="bddc5-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="bddc5-118">Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="bddc5-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="bddc5-119">Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="bddc5-120">Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="bddc5-121">Agregar un nuevo grupo</span><span class="sxs-lookup"><span data-stu-id="bddc5-121">Add a new group</span></span>

<span data-ttu-id="bddc5-122">Para agregar acceso a un grupo completo, debe decidir el nivel de participación de todos los miembros del grupo en el sitio:</span><span class="sxs-lookup"><span data-stu-id="bddc5-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="bddc5-123">Administración: agregar el grupo al grupo de acceso de administradores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="bddc5-124">Colaboración activa: agregar el grupo al grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="bddc5-125">Visualización: agregar el grupo al grupo de acceso de visores de sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="bddc5-126">Si está administrando cuentas de usuario y grupos a través de AD DS, agregue los grupos adecuados a los grupos adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="bddc5-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="bddc5-127">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="bddc5-128">Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para agregar los grupos adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="bddc5-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="bddc5-129">Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="bddc5-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="bddc5-130">A continuación, use los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="bddc5-131">Eliminar a un usuario</span><span class="sxs-lookup"><span data-stu-id="bddc5-131">Remove a user</span></span>

<span data-ttu-id="bddc5-132">Cuando se debe quitar el acceso de alguien del sitio, se quita del grupo de acceso del que es miembro actualmente en función de su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="bddc5-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="bddc5-133">Administración: quitar la cuenta de usuario del grupo de acceso de administradores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="bddc5-134">Colaboración activa: quitar la cuenta de usuario del grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="bddc5-135">Visualización: quitar la cuenta de usuario del grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="bddc5-136">Si está administrando cuentas de usuario y grupos a través de AD DS, quite los usuarios adecuados de los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="bddc5-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="bddc5-137">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="bddc5-138">Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para quitar los usuarios adecuados de los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="bddc5-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="bddc5-139">Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="bddc5-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="bddc5-140">Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="bddc5-141">Para quitar una cuenta de usuario de un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="bddc5-142">Quitar un grupo</span><span class="sxs-lookup"><span data-stu-id="bddc5-142">Remove a group</span></span>

<span data-ttu-id="bddc5-143">Para quitar el acceso de un grupo completo, debe quitar el grupo del grupo de acceso del que es miembro actualmente en función de su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="bddc5-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="bddc5-144">Administración: quitar el grupo del grupo de acceso de administradores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="bddc5-145">Colaboración activa: quitar el grupo del grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="bddc5-146">Visualización: quitar el grupo del grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="bddc5-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="bddc5-147">Si está administrando cuentas de usuario y grupos a través de Windows Server Active Directory, quite los grupos adecuados de los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="bddc5-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="bddc5-148">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="bddc5-149">Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario a la que se haya asignado el rol administrador de cuentas de usuario o administrador de la compañía y use Grupos para quitar los grupos adecuados de los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="bddc5-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="bddc5-150">Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="bddc5-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="bddc5-151">Para quitar un grupo de un grupo de acceso con sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bddc5-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="bddc5-152">Crear una subcarpeta de documentos con permisos personalizados</span><span class="sxs-lookup"><span data-stu-id="bddc5-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="bddc5-153">En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesitan un lugar más privado para colaborar.</span><span class="sxs-lookup"><span data-stu-id="bddc5-153">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="bddc5-154">Para los sitios de SharePoint Online, puede crear una subcarpeta en la carpeta Documentos del sitio y asignar permisos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bddc5-154">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="bddc5-155">Aquellos que no tienen permisos no verán la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="bddc5-155">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="bddc5-156">Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bddc5-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="bddc5-157">Inicie sesión en una cuenta que sea miembro del grupo de acceso de administradores del sitio.</span><span class="sxs-lookup"><span data-stu-id="bddc5-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="bddc5-158">Para obtener ayuda, vea [Dónde iniciar sesión en Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="bddc5-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="bddc5-159">Vaya al sitio de grupo aislado y haga clic en **Documentos.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="bddc5-160">Vaya a la carpeta de la carpeta de documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábrala.</span><span class="sxs-lookup"><span data-stu-id="bddc5-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="bddc5-161">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="bddc5-161">Click **Share**.</span></span>

5. <span data-ttu-id="bddc5-162">Haga **clic en Compartido > opciones avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="bddc5-163">Haga **clic en Detener la herencia de permisos** y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="bddc5-164">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="bddc5-164">Click **Share**.</span></span>

8. <span data-ttu-id="bddc5-165">Haga **clic en Compartido > opciones avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="bddc5-166">Haga **clic en Conceder permisos > compartido con > avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="bddc5-167">En la página de permisos, haga clic **\<site name> en Miembros de la lista.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="bddc5-168">En la **\<site name> página Miembros,** seleccione la marca de verificación junto al grupo de acceso de miembros del sitio, haga clic en Acciones **,** haga clic en Quitar usuarios del grupo y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="bddc5-169">Para agregar miembros específicos a esta subcarpeta, haga clic en **> Agregar usuarios.**</span><span class="sxs-lookup"><span data-stu-id="bddc5-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="bddc5-170">En el **cuadro de** diálogo Compartir, escriba los nombres de las cuentas de usuario que pueden colaborar en archivos de la subcarpeta y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="bddc5-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="bddc5-171">Actualice la página web para ver los nuevos resultados.</span><span class="sxs-lookup"><span data-stu-id="bddc5-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="bddc5-172">En **Grupos** del panel de **\<site name>** navegación izquierdo, haga clic en el grupo Visitantes y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que pueden ver los archivos en la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="bddc5-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="bddc5-173">En **Grupos** del panel de **\<site name>** navegación izquierdo, haga clic en el grupo Propietarios y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que pueden administrar los permisos en la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="bddc5-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="bddc5-174">Cierre la **pestaña Personas y grupos** en el explorador.</span><span class="sxs-lookup"><span data-stu-id="bddc5-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="bddc5-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bddc5-175">See Also</span></span>

[<span data-ttu-id="bddc5-176">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="bddc5-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="bddc5-177">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="bddc5-177">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="bddc5-178">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="bddc5-178">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
