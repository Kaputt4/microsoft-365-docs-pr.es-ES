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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Administrar un sitio de grupo de SharePoint Online aislado, agregar nuevos usuarios y grupos, quitar usuarios y grupos y crear una subcarpeta de documentos con permisos personalizados.
ms.openlocfilehash: d66f9a349bd5834d07fbc13146127bde522923e4
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308272"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="a6492-103">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="a6492-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="a6492-104">**Resumen:** Administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="a6492-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="a6492-105">En este artículo se describen las operaciones de administración comunes para un sitio de grupo de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="a6492-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="a6492-106">Agregar un nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="a6492-106">Add a new user</span></span>

<span data-ttu-id="a6492-107">Cuando alguien nuevo se une al sitio, debe decidir su nivel de participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="a6492-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="a6492-108">Administración: agregar la nueva cuenta de usuario al grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="a6492-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="a6492-109">Colaboración activa: agregar la cuenta de usuario al grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="a6492-110">Ver: agregar la cuenta de usuario al grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="a6492-111">Si administra cuentas de usuario y grupos a través de los servicios de dominio de Active Directory (AD DS), agregue los usuarios adecuados a los grupos de acceso adecuados mediante los procedimientos de administración de grupos y usuarios normales de AD DS y espere la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a6492-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="a6492-112">Si administra cuentas de usuario y grupos a través de Microsoft 365, puede usar el centro de administración de Microsoft 365 o PowerShell de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="a6492-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="a6492-113">En el centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar los usuarios adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="a6492-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="a6492-114">Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a6492-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="a6492-115">Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="a6492-116">Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="a6492-117">Agregar un nuevo grupo</span><span class="sxs-lookup"><span data-stu-id="a6492-117">Add a new group</span></span>

<span data-ttu-id="a6492-118">Para agregar acceso a todo un grupo, debe decidir el nivel de participación de todos los miembros del grupo en el sitio:</span><span class="sxs-lookup"><span data-stu-id="a6492-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="a6492-119">Administración: agregar el grupo al grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="a6492-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="a6492-120">Colaboración activa: agregar el grupo al grupo de acceso de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="a6492-121">Ver: agregar el grupo al grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="a6492-122">Si administra cuentas de usuario y grupos a través de AD DS, agregue los grupos adecuados a los grupos adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a6492-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="a6492-123">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="a6492-124">En el centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar los grupos adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="a6492-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="a6492-125">Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a6492-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="a6492-126">A continuación, use los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="a6492-127">Eliminar a un usuario</span><span class="sxs-lookup"><span data-stu-id="a6492-127">Remove a user</span></span>

<span data-ttu-id="a6492-128">Cuando es necesario quitar el acceso de un usuario del sitio, se quitan del grupo de acceso para el que actualmente son miembros según su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="a6492-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="a6492-129">Administración: quitar la cuenta de usuario del grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="a6492-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="a6492-130">Colaboración activa: quitar la cuenta de usuario del grupo de acceso de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="a6492-131">Ver: quitar la cuenta de usuario del grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="a6492-132">Si administra cuentas de usuario y grupos a través de AD DS, quite los usuarios correspondientes de los grupos de acceso adecuados mediante los procedimientos normales de administración de grupos y usuarios de AD DS y espere la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a6492-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="a6492-133">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="a6492-134">En el centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para quitar los usuarios correspondientes de los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="a6492-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="a6492-135">Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a6492-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="a6492-136">Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="a6492-137">Para quitar una cuenta de usuario de un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="a6492-138">Quitar un grupo</span><span class="sxs-lookup"><span data-stu-id="a6492-138">Remove a group</span></span>

<span data-ttu-id="a6492-139">Para quitar el acceso de un grupo completo, se quita el grupo del grupo de acceso para el que se integra en ese momento en función de su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="a6492-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="a6492-140">Administración: quitar el grupo del grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="a6492-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="a6492-141">Colaboración activa: quitar el grupo del grupo de acceso de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="a6492-142">Ver: quitar el grupo del grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="a6492-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="a6492-143">Si administra cuentas de usuario y grupos a través de Windows Server Active Directory, quite los grupos adecuados de los grupos de acceso adecuados mediante los procedimientos normales de administración de grupos y usuarios de AD DS y espere la sincronización con la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a6492-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="a6492-144">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="a6492-145">En el centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para quitar los grupos adecuados de los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="a6492-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="a6492-146">Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a6492-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="a6492-147">Para quitar un grupo de un grupo de acceso mediante sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6492-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="a6492-148">Crear una subcarpeta de documentos con permisos personalizados</span><span class="sxs-lookup"><span data-stu-id="a6492-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="a6492-149">En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesita un lugar más privado para colaborar.</span><span class="sxs-lookup"><span data-stu-id="a6492-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="a6492-150">Para los sitios de SharePoint Online, puede crear una subcarpeta en la carpeta documentos del sitio y asignar permisos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a6492-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="a6492-151">Los usuarios sin permisos no verán la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="a6492-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="a6492-152">Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6492-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="a6492-153">Inicie sesión en una cuenta que sea miembro del grupo de acceso administradores del sitio.</span><span class="sxs-lookup"><span data-stu-id="a6492-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="a6492-154">Para obtener ayuda, vea [Dónde iniciar sesión en Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="a6492-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a6492-155">Vaya al sitio de grupo aislado y haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="a6492-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="a6492-156">Vaya a la carpeta de la carpeta documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábrala.</span><span class="sxs-lookup"><span data-stu-id="a6492-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="a6492-157">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="a6492-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="a6492-158">Haga clic en **compartido con > avanzada**.</span><span class="sxs-lookup"><span data-stu-id="a6492-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="a6492-159">Haga clic en **dejar de heredar permisos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6492-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="a6492-160">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="a6492-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="a6492-161">Haga clic en **compartido con > avanzada**.</span><span class="sxs-lookup"><span data-stu-id="a6492-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="a6492-162">Haga clic en **conceder permisos > compartidos con > avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="a6492-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="a6492-163">En la página permisos, haga clic en \*\* \<site name> miembros en la lista\*\*.</span><span class="sxs-lookup"><span data-stu-id="a6492-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="a6492-164">En la página \*\* \<site name> miembros\*\* , seleccione la marca de verificación junto al grupo acceso de miembros del sitio, haga clic en **acciones**, haga clic en **quitar usuarios del grupo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6492-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="a6492-165">Para agregar miembros específicos a esta subcarpeta, haga clic en **nuevo > agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="a6492-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="a6492-166">En el cuadro de diálogo **compartir** , escriba los nombres de las cuentas de usuario que pueden colaborar en los archivos de la subcarpeta y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="a6492-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="a6492-167">Actualice la página web para ver los nuevos resultados.</span><span class="sxs-lookup"><span data-stu-id="a6492-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="a6492-168">En **grupos** en el panel de navegación izquierdo, haga clic en el grupo \*\* \<site name> visitantes\*\* y use los pasos 11-14 para especificar el conjunto de cuentas de usuario que pueden ver los archivos de la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="a6492-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="a6492-169">En **grupos** en el panel de navegación izquierdo, haga clic en el grupo \*\* \<site name> propietarios\*\* y use los pasos 11-14 para especificar el conjunto de cuentas de usuario que pueden administrar los permisos de la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="a6492-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="a6492-170">Cierre la pestaña **personas y grupos** del explorador.</span><span class="sxs-lookup"><span data-stu-id="a6492-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6492-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6492-171">See Also</span></span>

[<span data-ttu-id="a6492-172">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="a6492-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="a6492-173">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="a6492-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="a6492-174">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="a6492-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



