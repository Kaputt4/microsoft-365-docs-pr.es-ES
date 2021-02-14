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
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547101"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Si ha habilitado la autenticación moderna híbrida (HM) solo para encontrar que no es adecuado para su entorno actual, puede deshabilitar HM. En este artículo se explica cómo hacerlo.
  
## <a name="who-is-this-article-for"></a>¿Para quién es este artículo?

Si ha habilitado la autenticación moderna en Skype Empresarial Online o local, y/o Exchange Online o local y ha encontrado que necesita deshabilitar HM, estos pasos son para usted.

> [!IMPORTANT]
> Consulte el artículo "Topologías de[Skype](https://technet.microsoft.com/library/mt803262.aspx)Empresarial compatibles con la autenticación moderna" si está en Skype Empresarial Online o local, tiene una HM de topología mixta y necesita ver las topologías compatibles antes de empezar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Cómo deshabilitar la autenticación moderna híbrida (Exchange)

1. **Exchange local:** abra el Shell de administración de Exchange y ejecute los siguientes comandos: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online:** [conéctese a Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) con PowerShell remoto. Ejecute el siguiente comando para convertir la marca  *OAuth2ClientProfileEnabled*  en "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Cómo deshabilitar la autenticación moderna híbrida (Skype Empresarial)

1. **Skype Empresarial local:** ejecute los siguientes comandos en el Shell de administración de Skype Empresarial:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype Empresarial Online:** [conéctese a Skype Empresarial Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con PowerShell remoto. Ejecute el siguiente comando para deshabilitar la autenticación moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Vuelva a vincular a la introducción a la autenticación moderna.](hybrid-modern-auth-overview.md) 
  

