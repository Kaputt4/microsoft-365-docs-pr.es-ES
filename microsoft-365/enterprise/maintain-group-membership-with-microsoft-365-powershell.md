---
title: Mantener la pertenencia a grupos de Microsoft 365 con PowerShell
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
description: Obtenga información sobre cómo usar PowerShell para mantener la pertenencia a grupos de Microsoft 365.
ms.openlocfilehash: 7763f4275ff31f3dc26aa7fecba93e545f7c7644
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580979"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="6ffa7-103">Mantener la pertenencia a grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ffa7-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="6ffa7-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6ffa7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6ffa7-105">Puede usar PowerShell para Microsoft 365 como una alternativa al centro de administración de Microsoft 365 para mantener la pertenencia a grupos en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="6ffa7-106">[Obtenga información acerca de cómo mantener la pertenencia al grupo de microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="6ffa7-107">Para obtener una lista de recursos adicionales, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="6ffa7-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6ffa7-108">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="6ffa7-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="6ffa7-109">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6ffa7-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="6ffa7-110">Agregar o quitar cuentas de usuario como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="6ffa7-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="6ffa7-111">**Para agregar una cuenta de usuario por su UPN**, rellene el nombre principal de usuario (UPN) de la cuenta de usuario (ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo, quitando los caracteres "<" y ">", y ejecute estos comandos en la ventana de PowerShell o en el entorno de scripting integrado (ISE) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-112">**Para agregar una cuenta de usuario por su nombre para mostrar**, rellene el nombre para mostrar de la cuenta de usuario (ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-113">**Para quitar una cuenta de usuario por su UPN**, rellene el UPN de la cuenta de usuario (ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-114">**Para quitar una cuenta de usuario por su nombre para mostrar**, rellene el nombre para mostrar de la cuenta de usuario (ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="6ffa7-115">Agregar o quitar grupos como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="6ffa7-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="6ffa7-116">Los grupos de seguridad pueden contener otros grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="6ffa7-117">No obstante, los grupos de Microsoft 365 no pueden.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="6ffa7-118">Esta sección contiene comandos de PowerShell para agregar o quitar grupos solo para un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="6ffa7-119">**Para agregar un grupo por su nombre para mostrar**, rellene el nombre para mostrar del grupo que va a agregar y el nombre para mostrar del grupo que contendrá el grupo de miembros y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-120">**Para quitar un grupo por su nombre para mostrar**, rellene el nombre para mostrar del grupo que va a quitar y el nombre para mostrar del grupo que contendrá el grupo de miembros y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6ffa7-121">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ffa7-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6ffa7-122">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6ffa7-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="6ffa7-123">Agregar o quitar cuentas de usuario como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="6ffa7-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="6ffa7-124">**Para agregar una cuenta de usuario por su UPN**, rellene el nombre principal de usuario (UPN) de la cuenta de usuario (ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo, quitando los caracteres "<" y ">" y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-125">**Para agregar una cuenta de usuario por su nombre para mostrar**, rellene el nombre para mostrar de la cuenta de usuario (ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-126">**Para quitar una cuenta de usuario por su UPN**, rellene el UPN de la cuenta de usuario (ejemplo: belindan@contoso.com) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6ffa7-127">**Para quitar una cuenta de usuario por su nombre para mostrar**, rellene el nombre para mostrar de la cuenta de usuario (ejemplo: Belinda Newman) y el nombre para mostrar del grupo y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="6ffa7-128">Agregar o quitar grupos como miembros de un grupo</span><span class="sxs-lookup"><span data-stu-id="6ffa7-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="6ffa7-129">Los grupos de seguridad pueden contener otros grupos como miembros.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="6ffa7-130">No obstante, los grupos de Microsoft 365 no pueden.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="6ffa7-131">Esta sección contiene comandos de PowerShell para agregar o quitar grupos solo para un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="6ffa7-132">**Para agregar un grupo por su nombre para mostrar**, rellene el nombre para mostrar del grupo que va a agregar y el nombre para mostrar del grupo que contendrá el grupo de miembros y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="6ffa7-133">**Para quitar un grupo por su nombre para mostrar**, rellene el nombre para mostrar del grupo que va a quitar y el nombre para mostrar del grupo que contendrá el grupo de miembros y ejecute estos comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ffa7-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="6ffa7-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ffa7-134">See also</span></span>

[<span data-ttu-id="6ffa7-135">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ffa7-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6ffa7-136">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ffa7-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6ffa7-137">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ffa7-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

