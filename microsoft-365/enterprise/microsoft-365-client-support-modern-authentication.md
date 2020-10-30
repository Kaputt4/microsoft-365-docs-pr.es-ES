---
title: 'Soporte técnico de la aplicación cliente de Microsoft 365: autenticación moderna'
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
description: En este artículo, obtenga información sobre las plataformas, los clientes y los módulos de PowerShell compatibles con la autenticación moderna para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 290a151e127b05e984b9d262c3b429b561201545
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806674"
---
# <a name="microsoft-365-client-app-support-modern-authentication"></a>Soporte técnico de la aplicación cliente de Microsoft 365: autenticación moderna

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La autenticación moderna habilita el inicio de sesión basado en la biblioteca de autenticación de Active Directory (ADAL) para aplicaciones cliente de Office en distintas plataformas. Esto habilita las características de inicio de sesión, como la autenticación multifactor (MFA), la tarjeta inteligente y la autenticación basada en certificados.

Obtenga más información sobre [la autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) y [la autenticación basada en certificados](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Plataformas & clientes compatibles

Las versiones más recientes de los siguientes clientes y plataformas admiten la autenticación moderna. Para obtener más información acerca de la compatibilidad de plataformas de Microsoft 365, vea [requisitos del sistema para microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicaciones modernas| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador de Azure Active Directory | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Azure admin | N/D | N/D | N/D | N/D | N/D |
| Portal de empresa | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Cortana | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Delve | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Microsoft Edge | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Excel | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Administración de Exchange Online | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Formularios | N/D | N/D | N/D | N/D | N/D |
| Office 365 Admin | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |  |
| Kaizala | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Office Mobile | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Portal de Office | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| OneDrive | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| OneNote | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Outlook | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Planner | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| PowerApps | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Power Automate | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| PowerPoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Skype Empresarial | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) |
| Administrador de Skype empresarial | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| SharePoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Administrador de SharePoint Online | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Notas rápidas | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Stream | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Teams | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) |
| Acciones que realizar | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Visio | N/D | ![Compatible.](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Whiteboard | Plane | ![Compatible.](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Word | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Análisis de trabajo | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)