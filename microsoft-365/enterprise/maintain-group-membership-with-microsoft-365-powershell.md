---
title: Mantener la pertenencia a grupos de seguridad con PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Obtenga información sobre cómo usar PowerShell para mantener la pertenencia a Microsoft 365 grupos.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909579"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="1e3e1-103">Mantener la pertenencia a grupos de seguridad con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e3e1-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="1e3e1-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1e3e1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1e3e1-105">Puede usar PowerShell para Microsoft 365 como alternativa al Centro de administración de Microsoft 365 para mantener la pertenencia a grupos de seguridad en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="1e3e1-106">[Obtenga información sobre cómo mantener la Microsoft 365 grupo con](../admin/create-groups/add-or-remove-members-from-groups.md) el Centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="1e3e1-107">Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="1e3e1-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1e3e1-108">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="1e3e1-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="1e3e1-109">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1e3e1-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="1e3e1-110">Agregar o quitar cuentas de usuario como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="1e3e1-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="1e3e1-111">Para agregar una cuenta de usuario por su **UPN,** rellene la cuenta de usuario Nombre principal de usuario (UPN) (ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo de seguridad, quitando los caracteres "<" y ">" y ejecute estos comandos en la ventana de PowerShell o en el entorno de script integrado (ISE) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-112">**Para** agregar una cuenta de usuario por su nombre para mostrar, rellene el nombre para mostrar de la cuenta de usuario (por ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-113">Para quitar una cuenta de usuario por su **UPN,** rellene la cuenta de usuario UPN (por ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-114">**Para** quitar una cuenta de usuario por su nombre para mostrar, rellene el nombre para mostrar de la cuenta de usuario (por ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="1e3e1-115">Agregar o quitar grupos como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="1e3e1-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="1e3e1-116">Los grupos de seguridad pueden contener otros grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="1e3e1-117">Microsoft 365 grupos, sin embargo, no pueden.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="1e3e1-118">Esta sección contiene comandos de PowerShell para agregar o quitar grupos solo para un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="1e3e1-119">**Para** agregar un grupo por su nombre para mostrar, rellene el nombre para mostrar del grupo que va a agregar y el nombre para mostrar del grupo que contendrá el grupo de miembros y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-120">**To remove a group by its display name**, fill in the display name of the group you're going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1e3e1-121">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e3e1-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1e3e1-122">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e3e1-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="1e3e1-123">Agregar o quitar cuentas de usuario como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="1e3e1-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="1e3e1-124">Para agregar una cuenta de usuario por su **UPN,** rellene la cuenta de usuario Nombre principal de usuario (UPN) (por ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo, quitando los caracteres "<" y ">" y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-125">**Para** agregar una cuenta de usuario por su nombre para mostrar, rellene el nombre para mostrar de la cuenta de usuario (por ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-126">Para quitar una cuenta de usuario por su **UPN,** rellene la cuenta de usuario UPN (por ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1e3e1-127">**Para** quitar una cuenta de usuario por su nombre para mostrar, rellene el nombre para mostrar de la cuenta de usuario (por ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="1e3e1-128">Agregar o quitar grupos como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="1e3e1-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="1e3e1-129">Los grupos de seguridad pueden contener otros grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="1e3e1-130">Microsoft 365 grupos, sin embargo, no pueden.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="1e3e1-131">Esta sección contiene comandos de PowerShell para agregar o quitar grupos solo para un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="1e3e1-132">**Para** agregar un grupo por su nombre para mostrar, rellene el nombre para mostrar del grupo que va a agregar y el nombre para mostrar del grupo que contendrá el grupo de miembros y ejecute estos comandos en la ventana de PowerShell o el ISE de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="1e3e1-133">**To remove a group by its display name**, fill in the display name of the group you're going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="1e3e1-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e3e1-134">See also</span></span>

[<span data-ttu-id="1e3e1-135">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e3e1-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1e3e1-136">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e3e1-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1e3e1-137">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e3e1-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)