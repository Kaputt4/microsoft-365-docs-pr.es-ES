---
title: Desactivar los requisitos de contraseña seguros para los usuarios
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Si es un administrador que administra la directiva de contraseñas para una empresa, una escuela o una organización sin ánimo de lucro, puede establecer requisitos de contraseña seguros mediante Azure AD PowerShell.
ms.openlocfilehash: 72f7e5dd36cf011592daf4bac2e57c438106319a
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441688"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Desactivar los requisitos de contraseña seguros para los usuarios

En este artículo se explica cómo desactivar los requisitos de contraseña seguros para los usuarios. Los requisitos de contraseña seguros están activados de forma predeterminada en la organización de Microsoft 365 para empresas. Es posible que la organización tenga requisitos para deshabilitar contraseñas seguras. Siga los pasos siguientes para desactivar los requisitos de contraseña seguros. Debe completar estos pasos mediante PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está destinado a personas que administran la directiva de contraseñas para empresas, escuelas o organizaciones sin ánimo de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](../admin-overview/admin-center-overview.md#overview-of-the-microsoft-365-admin-center) Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para realizar estos pasos.

También debe conectarse a Microsoft 365 con PowerShell.

## <a name="set-strong-passwords"></a>Establecimiento de contraseñas seguras

1. [Conéctese a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Con PowerShell, puede desactivar los requisitos de contraseña seguros para todos los usuarios con el siguiente comando:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn **OFF** strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName debe tener el formato de inicio de sesión de estilo Internet, donde el nombre de usuario va seguido del signo de inicio de sesión (@) y un nombre de dominio. Por ejemplo: user@contoso.com.

## <a name="related-content"></a>Contenido relacionado

[Conexión a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Más información sobre los comandos MsolUser de PowerShell](/powershell/azure/active-directory/install-adv2)

[Más información sobre la directiva de contraseñas](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
