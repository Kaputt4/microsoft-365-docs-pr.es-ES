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
# <a name="set-strong-password-requirement-for-users"></a>Establecer el requisito de contraseña segura para los usuarios

En este artículo se explica cómo establecer los requisitos de contraseña segura para los usuarios. Debe completar estos pasos con PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está destinado a los usuarios que administran la Directiva de contraseñas para una empresa, un centro educativo o una ONG. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](../admin-overview/admin-overview.md). Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para poder realizar estos pasos.

También debe conectarse a Microsoft 365 con PowerShell.

## <a name="set-strong-passwords"></a>Establecer contraseñas seguras

1. [Conéctese a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Con PowerShell, puede deshabilitar las contraseñas seguras para determinados usuarios con este comando:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> El userPrincipalName debe estar en el formato de inicio de sesión de estilo Internet, donde el nombre de usuario está seguido del signo de arroba (@) y de un nombre de dominio. Por ejemplo: user@contoso.com.

## <a name="related-content"></a>Contenido relacionado

[Cómo conectarse a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Más información acerca de los comandos de PowerShell MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Más información sobre la Directiva de contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)