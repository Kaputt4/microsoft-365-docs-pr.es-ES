---
title: Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- scotvorg
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: En este artículo se explica cómo quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange.
ms.openlocfilehash: aaf54a9999c43488745aa4c4ceb3fa54d72ab4fb
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195619"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Si ha habilitado la autenticación moderna híbrida (HMA) solo para encontrar que no es adecuada para el entorno actual, puede deshabilitar HMA. En este artículo se explica cómo hacerlo.

## <a name="who-is-this-article-for"></a>¿Para quién es este artículo?

Si ha habilitado la autenticación moderna en Skype Empresarial en línea o local, o Exchange Online o local y ha detectado que necesita deshabilitar HMA, estos pasos son para usted.

> [!IMPORTANT]
> Consulte el artículo "[topologías de Skype Empresarial compatibles con la autenticación moderna](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)" si está en Skype Empresarial en línea o local, tiene una HMA de topología mixta y debe examinar las topologías admitidas antes de empezar.

## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Cómo deshabilitar la autenticación moderna híbrida (Exchange)

1. **Exchange local**: [abra el Shell de administración de Exchange](/powershell/exchange/open-the-exchange-management-shell) y ejecute los siguientes comandos:

   ```powershell
   Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
   Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
   ```

2. **Exchange Online**: [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Ejecute el siguiente comando para deshabilitar la autenticación moderna:

   ```powershell
   Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
   ```

## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Cómo deshabilitar la autenticación moderna híbrida (Skype Empresarial)

1. **Skype Empresarial local**: ejecute los siguientes comandos en Skype Empresarial Shell de administración:

   ```powershell
   Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
   ```

2. **Skype Empresarial En línea**: [conéctese a Skype Empresarial PowerShell en línea](manage-skype-for-business-online-with-microsoft-365-powershell.md). Ejecute el siguiente comando para deshabilitar la autenticación moderna:

   ```powershell
   Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
   ```

[Vuelva a vincular a la introducción a la autenticación moderna](hybrid-modern-auth-overview.md).
