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
ms.openlocfilehash: 1230ff4b4235ac5acbc28aa823506dfa5af26c2d
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48581029"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="ce310-103">Establecer el requisito de contraseña segura para los usuarios</span><span class="sxs-lookup"><span data-stu-id="ce310-103">Set strong password requirement for users</span></span>

<span data-ttu-id="ce310-104">En este artículo se explica cómo establecer los requisitos de contraseña segura para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ce310-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="ce310-105">Debe completar estos pasos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce310-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce310-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ce310-106">Before you begin</span></span>

<span data-ttu-id="ce310-107">Este artículo está destinado a los usuarios que administran la Directiva de contraseñas para una empresa, un centro educativo o una ONG.</span><span class="sxs-lookup"><span data-stu-id="ce310-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="ce310-108">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce310-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="ce310-109">[¿Qué es una cuenta de administrador?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ce310-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="ce310-110">Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ce310-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="ce310-111">También debe conectarse a Microsoft 365 con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce310-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="ce310-112">Establecer contraseñas seguras</span><span class="sxs-lookup"><span data-stu-id="ce310-112">Set strong passwords</span></span>

1. <span data-ttu-id="ce310-113">[Conéctese a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ce310-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="ce310-114">Con PowerShell, puede deshabilitar las contraseñas seguras para determinados usuarios con este comando:</span><span class="sxs-lookup"><span data-stu-id="ce310-114">Using PowerShell, you can disable strong passwords for specific users with this command:</span></span>

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="ce310-115">El userPrincipalName debe estar en el formato de inicio de sesión de estilo Internet, donde el nombre de usuario está seguido del signo de arroba (@) y de un nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="ce310-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="ce310-116">Por ejemplo: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ce310-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="ce310-117">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="ce310-117">Related content</span></span>

[<span data-ttu-id="ce310-118">Cómo conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce310-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="ce310-119">Más información acerca de los comandos de PowerShell MsolUser</span><span class="sxs-lookup"><span data-stu-id="ce310-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="ce310-120">Más información sobre la Directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="ce310-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)