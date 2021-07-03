---
title: 'Microsoft 365 Compatibilidad con aplicaciones cliente: autenticación multifactor'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: En este artículo, obtenga información sobre qué plataformas, clientes y módulos de PowerShell admiten la autenticación multifactor para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286458"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 Compatibilidad con aplicaciones cliente: autenticación multifactor

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, los clientes pueden configurarse para usar la autenticación multifactor (MFA), que usa una contraseña de usuario y otro método de verificación de usuario basado en:

- Algo en su poder que no se duplica fácilmente, como un teléfono inteligente.
- Algo que el usuario tiene de forma única y biológica, como sus huellas digitales, rostro u otro atributo biométrico

Obtenga más información [sobre la autenticación multifactor](/azure/active-directory/authentication/multi-factor-authentication).

## <a name="supported-clients--platforms"></a>Clientes compatibles & plataformas

Las últimas versiones de los siguientes clientes y plataformas admiten la autenticación multifactor. Para obtener más información acerca de la compatibilidad de plataforma Microsoft 365, vea [Requisitos del](/microsoft-365/microsoft-365-and-office-resources)sistema para Microsoft 365 .
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
