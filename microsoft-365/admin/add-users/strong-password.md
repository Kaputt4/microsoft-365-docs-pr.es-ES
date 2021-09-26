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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo establecer requisitos de contraseñas seguras para los usuarios mediante Windows PowerShell.
ms.openlocfilehash: e9bf4fc81cf788ab51ef174d73a7c6086ebb9d46
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59773420"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Desactivar los requisitos de contraseña segura para los usuarios

En este artículo se explica cómo desactivar los requisitos de contraseña segura para los usuarios. Los requisitos de contraseña segura están activados de forma predeterminada en Microsoft 365 para la organización empresarial. Es posible que su organización tenga requisitos para deshabilitar contraseñas seguras. Siga los pasos siguientes para desactivar los requisitos de contraseña segura. Debe completar estos pasos con PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está para personas que administran la directiva de contraseñas para una empresa, escuela o organización sin ánimo de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](/microsoft-365/business-video/admin-center-overview) Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.

También debe conectarse a Microsoft 365 con PowerShell.

## <a name="set-strong-passwords"></a>Establecer contraseñas seguras

1. [Conectar para Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Con PowerShell, puede desactivar los requisitos de contraseña segura para todos los usuarios con el siguiente comando:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn **OFF** strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> El userPrincipalName debe estar en el formato de inicio de sesión de estilo de Internet donde el nombre de usuario va seguido del signo al (@) y un nombre de dominio. Por ejemplo: user@contoso.com.

## <a name="related-content"></a>Contenido relacionado

[Cómo conectarse a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Más información sobre los comandos MsolUser de PowerShell](/powershell/azure/active-directory/install-adv2)

[Más información sobre la directiva de contraseñas](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
