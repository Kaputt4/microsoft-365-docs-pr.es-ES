---
title: Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: En este artículo se explica cómo quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927293"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Si ha habilitado la autenticación moderna híbrida (HMA) solo para encontrar que no es adecuado para el entorno actual, puede deshabilitar HMA. En este artículo se explica cómo.
  
## <a name="who-is-this-article-for"></a>Quién Cuál es este artículo?

Si ha habilitado la autenticación moderna en Skype Empresarial Online o local, y/o Exchange Online o local y ha encontrado que necesita deshabilitar HMA, estos pasos son para usted.

> [!IMPORTANT]
> Consulte el artículo '[Skype Empresarial topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' si está en Skype Empresarial Online o local, tiene una HMA de topología mixta y necesita ver las topologías admitidas antes de comenzar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Cómo deshabilitar la autenticación moderna híbrida (Exchange)

1. **Exchange local:** abra el Shell de administración Exchange y ejecute los siguientes comandos: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online:** Conectar [a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) con PowerShell remoto. Ejecute el siguiente comando para convertir la marca  *OAuth2ClientProfileEnabled*  en "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Cómo deshabilitar la autenticación moderna híbrida (Skype Empresarial)

1. **Skype Empresarial local:** ejecute los siguientes comandos en Skype Empresarial Shell de administración:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype Empresarial Online:** [Conectar a Skype Empresarial Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con PowerShell remoto. Ejecute el siguiente comando para deshabilitar la autenticación moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Vuelva a vincular a la información general sobre autenticación moderna](hybrid-modern-auth-overview.md) . 
