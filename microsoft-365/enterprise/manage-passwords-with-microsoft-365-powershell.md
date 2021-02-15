---
title: Administrar contraseñas con PowerShell
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
description: Obtenga información sobre cómo usar PowerShell para administrar contraseñas.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073217"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="2dde3-103">Administrar contraseñas con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dde3-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="2dde3-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2dde3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2dde3-105">Puede usar PowerShell para Microsoft 365 como alternativa al Centro de administración de Microsoft 365 para administrar contraseñas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2dde3-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="2dde3-106">Cuando un bloque de comandos de este artículo requiera que especifique valores de variable, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2dde3-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="2dde3-107">Copie el bloque de comandos en el Portapapeles y péguelo en el Bloc de notas o en el Entorno de scripts integrado (ISE) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dde3-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="2dde3-108">Rellene los valores de variable y quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="2dde3-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="2dde3-109">Ejecute los comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="2dde3-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2dde3-110">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="2dde3-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2dde3-111">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="2dde3-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="2dde3-112">Establecer una contraseña</span><span class="sxs-lookup"><span data-stu-id="2dde3-112">Set a password</span></span>

<span data-ttu-id="2dde3-113">Use estos comandos para especificar una contraseña para una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="2dde3-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="2dde3-114">Forzar a un usuario a cambiar su contraseña</span><span class="sxs-lookup"><span data-stu-id="2dde3-114">Force a user to change their password</span></span>

<span data-ttu-id="2dde3-115">Use estos comandos para establecer una contraseña y forzar a un usuario a cambiar su nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="2dde3-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="2dde3-116">Use estos comandos para establecer una contraseña y forzar a un usuario a cambiar su nueva contraseña la próxima vez que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2dde3-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2dde3-117">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dde3-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="2dde3-118">En primer [lugar, conéctese a su inquilino de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2dde3-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="2dde3-119">Establecer una contraseña</span><span class="sxs-lookup"><span data-stu-id="2dde3-119">Set a password</span></span>

<span data-ttu-id="2dde3-120">Use estos comandos para especificar una contraseña para una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="2dde3-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="2dde3-121">Forzar a un usuario a cambiar su contraseña</span><span class="sxs-lookup"><span data-stu-id="2dde3-121">Force a user to change their password</span></span>

<span data-ttu-id="2dde3-122">Use estos comandos para forzar a un usuario a cambiar su contraseña.</span><span class="sxs-lookup"><span data-stu-id="2dde3-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="2dde3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dde3-123">See also</span></span>

[<span data-ttu-id="2dde3-124">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dde3-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2dde3-125">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dde3-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2dde3-126">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dde3-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

