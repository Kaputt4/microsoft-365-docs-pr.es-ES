---
title: Establecer el requisito de contraseña segura para los usuarios
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
description: Obtenga información sobre cómo establecer requisitos de contraseña segura para los usuarios con Windows PowerShell.
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646624"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="076be-103">Establecer el requisito de contraseña segura para los usuarios</span><span class="sxs-lookup"><span data-stu-id="076be-103">Set strong password requirement for users</span></span>

<span data-ttu-id="076be-104">En este artículo se explica cómo desactivar los requisitos de contraseña segura para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="076be-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="076be-105">Los requisitos de contraseña segura están activados de forma predeterminada en la organización de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="076be-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="076be-106">Es posible que su organización tenga requisitos para deshabilitar las contraseñas seguras.</span><span class="sxs-lookup"><span data-stu-id="076be-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="076be-107">Siga los pasos siguientes para desactivar los requisitos de contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="076be-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="076be-108">Debe completar estos pasos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="076be-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="076be-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="076be-109">Before you begin</span></span>

<span data-ttu-id="076be-110">Este artículo está destinado a los usuarios que administran la Directiva de contraseñas para una empresa, un centro educativo o una ONG.</span><span class="sxs-lookup"><span data-stu-id="076be-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="076be-111">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="076be-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="076be-112">¿Qué es una cuenta de administrador?</span><span class="sxs-lookup"><span data-stu-id="076be-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="076be-113">Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="076be-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="076be-114">También debe conectarse a Microsoft 365 con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="076be-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="076be-115">Establecer contraseñas seguras</span><span class="sxs-lookup"><span data-stu-id="076be-115">Set strong passwords</span></span>

1. <span data-ttu-id="076be-116">[Conéctese a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="076be-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="076be-117">Con PowerShell, puede desactivar los requisitos de contraseñas seguras para todos los usuarios con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="076be-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="076be-118">El userPrincipalName debe estar en el formato de inicio de sesión de estilo Internet, donde el nombre de usuario está seguido del signo de arroba (@) y de un nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="076be-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="076be-119">Por ejemplo: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="076be-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="076be-120">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="076be-120">Related content</span></span>

[<span data-ttu-id="076be-121">Cómo conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="076be-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="076be-122">Más información acerca de los comandos de PowerShell MsolUser</span><span class="sxs-lookup"><span data-stu-id="076be-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="076be-123">Más información sobre la Directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="076be-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)