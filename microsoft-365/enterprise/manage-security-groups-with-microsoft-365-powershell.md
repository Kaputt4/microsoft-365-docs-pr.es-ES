---
title: Administrar grupos de seguridad con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Obtenga información sobre cómo usar PowerShell para administrar grupos de seguridad.
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909507"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="dd300-103">Administrar grupos de seguridad con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd300-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="dd300-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="dd300-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dd300-105">Puede usar PowerShell para Microsoft 365 como alternativa al Centro de administración de Microsoft 365 para administrar grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="dd300-106">En este artículo se describe la descripción, la creación, el cambio de configuración y la eliminación de grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="dd300-107">Cuando un bloque de comandos de este artículo requiera que especifique valores de variables, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dd300-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="dd300-108">Copie el bloque de comandos en el Portapapeles y péguelo en el Bloc de notas o en el entorno de script integrado (ISE) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd300-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="dd300-109">Rellene los valores de variable y quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="dd300-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="dd300-110">Ejecute los comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd300-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="dd300-111">Consulte [Mantener la pertenencia a grupos de seguridad](maintain-group-membership-with-microsoft-365-powershell.md) para administrar la pertenencia a grupos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd300-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="dd300-112">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="dd300-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="dd300-113">En primer [lugar, conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="dd300-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="dd300-114">Enumerar los grupos</span><span class="sxs-lookup"><span data-stu-id="dd300-114">List your groups</span></span>

<span data-ttu-id="dd300-115">Use este comando para enumerar todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="dd300-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="dd300-116">Use estos comandos para mostrar la configuración de un grupo específico por su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="dd300-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="dd300-117">Creación de un grupo nuevo</span><span class="sxs-lookup"><span data-stu-id="dd300-117">Create a new group</span></span>

<span data-ttu-id="dd300-118">Use este comando para crear un nuevo grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="dd300-119">Cambiar la configuración de un grupo</span><span class="sxs-lookup"><span data-stu-id="dd300-119">Change the settings on a group</span></span>

<span data-ttu-id="dd300-120">Muestra la configuración del grupo con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="dd300-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="dd300-121">A continuación, use [el artículo Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) para determinar cómo cambiar una configuración.</span><span class="sxs-lookup"><span data-stu-id="dd300-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="dd300-122">Quitar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="dd300-122">Remove a security group</span></span>

<span data-ttu-id="dd300-123">Use estos comandos para quitar un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="dd300-124">Administrar los propietarios de un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="dd300-124">Manage the owners of a security group</span></span>

<span data-ttu-id="dd300-125">Use estos comandos para mostrar los propietarios actuales de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="dd300-126">Use estos comandos para agregar una cuenta de usuario por su nombre principal de usuario **(UPN)** a los propietarios actuales de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="dd300-127">Use estos comandos para agregar una cuenta de usuario por su nombre **para** mostrar a los propietarios actuales de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="dd300-128">Use estos comandos para quitar una cuenta de usuario por su **UPN** a los propietarios actuales de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="dd300-129">Use estos comandos para quitar una cuenta de usuario por su nombre **para** mostrar a los propietarios actuales de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="dd300-130">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd300-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="dd300-131">En primer [lugar, conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="dd300-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="dd300-132">Enumerar los grupos</span><span class="sxs-lookup"><span data-stu-id="dd300-132">List your groups</span></span>

<span data-ttu-id="dd300-133">Use este comando para enumerar todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="dd300-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="dd300-134">Use estos comandos para mostrar la configuración de un grupo específico por su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="dd300-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="dd300-135">Creación de un grupo nuevo</span><span class="sxs-lookup"><span data-stu-id="dd300-135">Create a new group</span></span>

<span data-ttu-id="dd300-136">Use este comando para crear un nuevo grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="dd300-137">Cambiar la configuración de un grupo</span><span class="sxs-lookup"><span data-stu-id="dd300-137">Change the settings on a group</span></span>

<span data-ttu-id="dd300-138">Muestra la configuración del grupo con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="dd300-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="dd300-139">A continuación, use [el artículo Set-MsolGroup](/powershell/module/msonline/set-msolgroup) para determinar cómo cambiar una configuración.</span><span class="sxs-lookup"><span data-stu-id="dd300-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="dd300-140">Quitar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="dd300-140">Remove a security group</span></span>

<span data-ttu-id="dd300-141">Use estos comandos para quitar un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd300-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="dd300-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd300-142">See also</span></span>

[<span data-ttu-id="dd300-143">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd300-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="dd300-144">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd300-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="dd300-145">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd300-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)