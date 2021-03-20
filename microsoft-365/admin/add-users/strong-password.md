---
title: Desactivar los requisitos de contraseña segura para los usuarios
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo establecer requisitos de contraseña segura para los usuarios mediante Windows PowerShell.
ms.openlocfilehash: e2300e3c94de53cd04d0c1726538fdb8a86a1ccf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903541"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="df082-103">Desactivar los requisitos de contraseña segura para los usuarios</span><span class="sxs-lookup"><span data-stu-id="df082-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="df082-104">En este artículo se explica cómo desactivar los requisitos de contraseña segura para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="df082-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="df082-105">Los requisitos de contraseña segura están activados de forma predeterminada en la organización de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="df082-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="df082-106">Es posible que su organización tenga requisitos para deshabilitar contraseñas seguras.</span><span class="sxs-lookup"><span data-stu-id="df082-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="df082-107">Siga los pasos siguientes para desactivar los requisitos de contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="df082-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="df082-108">Debe completar estos pasos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df082-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="df082-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="df082-109">Before you begin</span></span>

<span data-ttu-id="df082-110">Este artículo está para personas que administran la directiva de contraseñas para una empresa, escuela o organización sin ánimo de lucro.</span><span class="sxs-lookup"><span data-stu-id="df082-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="df082-111">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df082-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="df082-112">¿Qué es una cuenta de administrador?</span><span class="sxs-lookup"><span data-stu-id="df082-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="df082-113">Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="df082-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="df082-114">También debe conectarse a Microsoft 365 con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df082-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="df082-115">Establecer contraseñas seguras</span><span class="sxs-lookup"><span data-stu-id="df082-115">Set strong passwords</span></span>

1. <span data-ttu-id="df082-116">[Conéctese a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="df082-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="df082-117">Con PowerShell, puede desactivar los requisitos de contraseña segura para todos los usuarios con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="df082-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="df082-118">El userPrincipalName debe estar en el formato de inicio de sesión de estilo de Internet donde el nombre de usuario va seguido del signo al (@) y un nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="df082-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="df082-119">Por ejemplo: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="df082-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="df082-120">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="df082-120">Related content</span></span>

[<span data-ttu-id="df082-121">Cómo conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="df082-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="df082-122">Más información sobre los comandos MsolUser de PowerShell</span><span class="sxs-lookup"><span data-stu-id="df082-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="df082-123">Más información sobre la directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="df082-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)