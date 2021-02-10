---
title: Implementar un sitio de grupo de SharePoint Online aislado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Use esta guía de implementación paso a paso para crear y configurar un sitio de grupo aislado de SharePoint Online en Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165504"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="4ca63-103">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="4ca63-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4ca63-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="4ca63-104">**Applies to**</span></span>
- [<span data-ttu-id="4ca63-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4ca63-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4ca63-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ca63-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="4ca63-107">**Resumen:** Implemente un nuevo sitio de grupo aislado de SharePoint Online con estas instrucciones paso a paso.</span><span class="sxs-lookup"><span data-stu-id="4ca63-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="4ca63-108">Este artículo es una guía de implementación paso a paso para crear y configurar un sitio de grupo de SharePoint Online aislado en Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ca63-108">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="4ca63-109">Estos pasos suponen el uso de los tres grupos de SharePoint predeterminados y los niveles de permisos correspondientes, con un único grupo de acceso basado en Azure Active Directory (AD) para cada nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="4ca63-109">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="4ca63-110">Fase 1: Crear y rellenar los grupos de acceso al sitio de grupo</span><span class="sxs-lookup"><span data-stu-id="4ca63-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="4ca63-111">En esta fase, creará los tres grupos de acceso basados en Azure AD para los tres grupos de SharePoint predeterminados y los rellenará con las cuentas de usuario adecuadas.</span><span class="sxs-lookup"><span data-stu-id="4ca63-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="4ca63-112">En los pasos siguientes se supone que ya existen todas las cuentas de usuario necesarias y que se les asignan las licencias correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4ca63-112">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="4ca63-113">Si no es así, agrédalos y asigne licencias antes de continuar con el paso 1.</span><span class="sxs-lookup"><span data-stu-id="4ca63-113">If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="4ca63-114">Paso 1: Enumerar los administradores de SharePoint Online para el sitio</span><span class="sxs-lookup"><span data-stu-id="4ca63-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="4ca63-115">Determine el conjunto de cuentas de usuario correspondiente a los administradores de SharePoint Online para el sitio de grupo aislado.</span><span class="sxs-lookup"><span data-stu-id="4ca63-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="4ca63-116">Si administra cuentas de usuario y grupos a través de Microsoft 365 y desea usar Windows PowerShell, haga una lista de sus nombres principales de usuario (UPN) (por ejemplo, UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4ca63-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="4ca63-117">Paso 2: Enumerar los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="4ca63-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="4ca63-118">Determine el conjunto de cuentas de usuario correspondiente a los miembros del sitio de grupo aislado, aquellos que colaborarán en los recursos almacenados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="4ca63-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="4ca63-119">Si está administrando cuentas de usuario y grupos a través de Microsoft 365 y desea usar PowerShell, haga una lista de sus UPN.</span><span class="sxs-lookup"><span data-stu-id="4ca63-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="4ca63-120">Si hay una gran cantidad de miembros del sitio, puede almacenar la lista de UPN en un archivo de texto y agregarlos todos con un solo comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ca63-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="4ca63-121">Paso 3: Enumerar los visores del sitio</span><span class="sxs-lookup"><span data-stu-id="4ca63-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="4ca63-122">Determine el conjunto de cuentas de usuario correspondiente a los visores del sitio de grupo aislado, aquellos que pueden ver los recursos almacenados en el sitio pero no modificarlos o colaborar directamente en su contenido.</span><span class="sxs-lookup"><span data-stu-id="4ca63-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="4ca63-123">Si está administrando cuentas de usuario y grupos a través de Microsoft 365 y desea usar PowerShell, haga una lista de sus UPN.</span><span class="sxs-lookup"><span data-stu-id="4ca63-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="4ca63-124">Si hay una gran cantidad de miembros del sitio, puede almacenar la lista de UPN en un archivo de texto y agregarlos todos con un solo comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ca63-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="4ca63-125">Los visores del sitio pueden incluir la administración ejecutiva, los asesores legales o las partes interesadas entre departamentos.</span><span class="sxs-lookup"><span data-stu-id="4ca63-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="4ca63-126">Paso 4: Crear los tres grupos de acceso para el sitio en Azure AD</span><span class="sxs-lookup"><span data-stu-id="4ca63-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="4ca63-127">Debe crear los siguientes grupos de acceso en Azure AD:</span><span class="sxs-lookup"><span data-stu-id="4ca63-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="4ca63-128">Administradores del sitio (que contendrán la lista del paso 1)</span><span class="sxs-lookup"><span data-stu-id="4ca63-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="4ca63-129">Miembros del sitio (que contendrán la lista del paso 2)</span><span class="sxs-lookup"><span data-stu-id="4ca63-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="4ca63-130">Visores de sitios (que contendrán la lista del paso 3)</span><span class="sxs-lookup"><span data-stu-id="4ca63-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="4ca63-131">En el explorador, vaya a Azure Portal e inicie sesión con las credenciales de una cuenta asignada con el rol administrador de administración de usuarios o <https://portal.azure.com> administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="4ca63-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="4ca63-132">En Azure Portal, haga clic en **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="4ca63-133">En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="4ca63-134">En la **hoja Nuevo** grupo:</span><span class="sxs-lookup"><span data-stu-id="4ca63-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="4ca63-135">Seleccione **Seguridad** en **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="4ca63-136">Escriba el nombre del grupo en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="4ca63-137">Escriba una descripción del grupo en la **descripción del grupo.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="4ca63-138">Seleccione **Asignada** en **Tipo de pertenencia**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="4ca63-139">Haga clic en **Crear** y, después, cierre la hoja **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="4ca63-140">Repita los pasos del 3 al 5 para los grupos adicionales.</span><span class="sxs-lookup"><span data-stu-id="4ca63-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="4ca63-141">Debe usar Azure Portal para crear los grupos de modo que tengan habilitadas las características de Office.</span><span class="sxs-lookup"><span data-stu-id="4ca63-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="4ca63-142">Si un sitio aislado de SharePoint Online se configura más adelante como un sitio extremadamente confidencial con una etiqueta de Azure Information Protection para cifrar archivos y asignar permisos a grupos específicos, los grupos permitidos deben haber sido creados con las características de Office habilitadas.</span><span class="sxs-lookup"><span data-stu-id="4ca63-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="4ca63-143">No puede cambiar la configuración de características de Office de un grupo de Azure AD después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="4ca63-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="4ca63-144">Esta es la configuración resultante con los tres grupos de acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="4ca63-144">Here is your resulting configuration with the three site access groups.</span></span>

![Los tres grupos de acceso para la implementación de un sitio aislado de SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="4ca63-146">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="4ca63-146">Step 5.</span></span> <span data-ttu-id="4ca63-147">Agregar las cuentas de usuario a los grupos de acceso</span><span class="sxs-lookup"><span data-stu-id="4ca63-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="4ca63-148">En este paso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ca63-148">In this step, do the following:</span></span>

1. <span data-ttu-id="4ca63-149">Agregue la lista de usuarios del paso 1 al grupo de acceso de administradores del sitio.</span><span class="sxs-lookup"><span data-stu-id="4ca63-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="4ca63-150">Agregue la lista de usuarios del paso 2 al grupo de acceso de miembros del sitio.</span><span class="sxs-lookup"><span data-stu-id="4ca63-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="4ca63-151">Agregue la lista de usuarios del paso 3 al grupo de acceso de visores del sitio.</span><span class="sxs-lookup"><span data-stu-id="4ca63-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="4ca63-152">Si administra cuentas de usuario y grupos a través de servicios de dominio de Active Directory (AD DS), agregue usuarios a los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a que se la sincronización con su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ca63-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="4ca63-153">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ca63-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="4ca63-154">Si tiene nombres de grupo duplicados para cualquiera de los grupos de acceso, debe usar el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ca63-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="4ca63-155">Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para agregar las cuentas de usuario y los grupos adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="4ca63-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="4ca63-156">Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="4ca63-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="4ca63-157">A continuación, use el siguiente bloque de comandos para agregar una cuenta de usuario individual a un grupo de acceso:</span><span class="sxs-lookup"><span data-stu-id="4ca63-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="4ca63-158">Si almacenaste los UPN de las cuentas de usuario para cualquiera de los grupos de acceso en un archivo de texto, puedes usar el siguiente bloque de comandos de PowerShell para agregarlos todos a la vez:</span><span class="sxs-lookup"><span data-stu-id="4ca63-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="4ca63-159">Para PowerShell, use el siguiente bloque de comandos para agregar un grupo individual a un grupo de acceso:</span><span class="sxs-lookup"><span data-stu-id="4ca63-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="4ca63-160">Los resultados deben ser los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ca63-160">The results should be the following:</span></span>

- <span data-ttu-id="4ca63-161">El grupo de administradores del sitio de Azure AD contiene los grupos o cuentas de usuario de administrador del sitio</span><span class="sxs-lookup"><span data-stu-id="4ca63-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="4ca63-162">El grupo de Azure AD de los miembros del sitio contiene las cuentas de usuario o grupos de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="4ca63-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="4ca63-163">El grupo de visores de sitios de Azure AD contiene las cuentas de usuario o grupos que solo pueden ver el contenido del sitio</span><span class="sxs-lookup"><span data-stu-id="4ca63-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="4ca63-164">Valide la lista de miembros del grupo para cada grupo de acceso con el Centro de administración de Microsoft 365 o con el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4ca63-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="4ca63-165">Esta es la configuración resultante con los tres grupos de acceso al sitio rellenados con cuentas de usuario o grupos.</span><span class="sxs-lookup"><span data-stu-id="4ca63-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![Los tres grupos de acceso se rellenan con cuentas de usuario.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="4ca63-167">Fase 2: Crear y configurar el sitio de grupo aislado</span><span class="sxs-lookup"><span data-stu-id="4ca63-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="4ca63-168">En esta fase, creará el sitio aislado de SharePoint Online y configurará los permisos para los niveles de permisos predeterminados de SharePoint Online para usar los nuevos grupos de acceso basados en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4ca63-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="4ca63-169">De forma predeterminada, los nuevos sitios de grupo incluyen un grupo de Microsoft 365 y otros recursos relacionados, pero en este caso, crearemos un sitio de grupo sin un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ca63-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="4ca63-170">Esto permite mantener los permisos completamente a través de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ca63-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="4ca63-171">En primer lugar, cree el sitio de grupo de SharePoint Online con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4ca63-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="4ca63-172">Inicie sesión en el Centro de administración de Microsoft 365 con una cuenta que también se usará para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="4ca63-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="4ca63-173">Para obtener ayuda, vea [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="4ca63-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4ca63-174">En el Centro de administración de Microsoft 365, en **Centros de administración,** haga clic **en SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="4ca63-175">En el Centro de administración de SharePoint, expanda **Sitios** y haga clic **en Sitios activos.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="4ca63-176">Haga **clic en** Crear y, a continuación, elija **Otras opciones.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="4ca63-177">En la **lista Elegir una plantilla,** elija **Sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="4ca63-178">En **Nombre del sitio,** escriba un nombre para el sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="4ca63-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="4ca63-179">En **administrador principal,** escriba la cuenta con la que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="4ca63-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="4ca63-180">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-180">Click **Finish**.</span></span>

<span data-ttu-id="4ca63-181">A continuación, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos.</span><span class="sxs-lookup"><span data-stu-id="4ca63-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="4ca63-182">En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="4ca63-183">En **Uso compartido de sitios,** haga clic en Cambiar cómo pueden compartir los **miembros.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="4ca63-184">Elija el **único sitio que los propietarios pueden compartir archivos, carpetas y el sitio.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="4ca63-185">Establezca **Permitir solicitudes de acceso** en **Desactivado.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="4ca63-186">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-186">Click **Save**.</span></span>

6. <span data-ttu-id="4ca63-187">En el **panel Permisos,** haga clic **en Configuración avanzada de permisos.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="4ca63-188">En la **pestaña Permisos** del explorador, haga clic **\<site name> en Miembros** de la lista.</span><span class="sxs-lookup"><span data-stu-id="4ca63-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="4ca63-189">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="4ca63-190">En el **cuadro de** diálogo Compartir, escriba el nombre del grupo de acceso de miembros del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="4ca63-191">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="4ca63-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="4ca63-192">Haga **\<site name> clic en Propietarios** en la lista.</span><span class="sxs-lookup"><span data-stu-id="4ca63-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="4ca63-193">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="4ca63-194">En el **cuadro de** diálogo Compartir, escriba el nombre del grupo de acceso de administradores del sitio, selecciónelo y, a continuación, haga clic en **Compartir.**</span><span class="sxs-lookup"><span data-stu-id="4ca63-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="4ca63-195">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="4ca63-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="4ca63-196">Haga **\<site name> clic en** Visitantes de la lista.</span><span class="sxs-lookup"><span data-stu-id="4ca63-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="4ca63-197">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="4ca63-198">En el **cuadro de** diálogo Compartir, escriba el nombre del grupo de acceso de visores del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="4ca63-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="4ca63-199">Cierre la pestaña **Permisos** del explorador.</span><span class="sxs-lookup"><span data-stu-id="4ca63-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="4ca63-200">Los resultados de esta configuración de permisos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ca63-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="4ca63-201">El **\<site name> grupo propietarios** de SharePoint contiene el grupo de acceso de administradores del sitio, en el que todos los miembros tienen el **nivel de permisos control** total.</span><span class="sxs-lookup"><span data-stu-id="4ca63-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="4ca63-202">El **\<site name> grupo de** Miembros de SharePoint contiene el grupo de acceso de miembros del sitio, en el que todos los miembros tienen el **nivel de** permisos Editar.</span><span class="sxs-lookup"><span data-stu-id="4ca63-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="4ca63-203">El **\<site name> grupo visitantes** de SharePoint contiene el grupo de acceso de visores del sitio, en el que todos los miembros tienen el nivel **de** permisos de lectura.</span><span class="sxs-lookup"><span data-stu-id="4ca63-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="4ca63-204">La posibilidad de que los miembros inviten a otros miembros o que no miembros soliciten acceso está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4ca63-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="4ca63-205">Esta es la configuración resultante con los tres grupos de SharePoint para el sitio configurados para usar los tres grupos de acceso, que se rellenan con cuentas de usuario o grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4ca63-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![La configuración final del sitio aislado de SharePoint Online con grupos de acceso y cuentas de usuario.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="4ca63-207">Usted y los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar con los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="4ca63-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="4ca63-208">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="4ca63-208">Next step</span></span>

<span data-ttu-id="4ca63-209">Cuando necesite cambiar la pertenencia al grupo de acceso al sitio o crear una carpeta de documentos con permisos personalizados, vea Administrar un sitio de grupo de [SharePoint Online aislado.](manage-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="4ca63-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ca63-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ca63-210">See Also</span></span>

[<span data-ttu-id="4ca63-211">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="4ca63-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="4ca63-212">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="4ca63-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="4ca63-213">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="4ca63-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
