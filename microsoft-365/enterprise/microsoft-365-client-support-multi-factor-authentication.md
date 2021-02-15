---
title: 'Compatibilidad con aplicaciones cliente de Microsoft 365: autenticación multifactor'
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
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097485"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Compatibilidad con aplicaciones cliente de Microsoft 365: autenticación multifactor

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, los clientes pueden configurarse para usar la autenticación multifactor (MFA), que usa una contraseña de usuario y un método de comprobación de usuario adicional basado en:

- Algo en su posesión que no se duplica fácilmente, como un smartphone.
- Algo que el usuario tiene de forma única y exclusiva, como sus huellas digitales, cara u otro atributo biométrico

Obtenga más información sobre [la autenticación multifactor.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>Clientes compatibles & plataformas

Las últimas versiones de los siguientes clientes y plataformas admiten la autenticación multifactor. Para obtener más información acerca de la compatibilidad con plataformas en Microsoft 365, consulte Requisitos del sistema [para Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicaciones modernas| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador de Azure Active Directory | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Acceso | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Administrador de Azure | N/D | N/D | N/D | N/D | N/D |
| Portal de empresa | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Cortana | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Delve | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Microsoft Edge | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Excel | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Administrador de Exchange Online | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Formularios | N/D | N/D | N/D | N/D | N/D |
| Office 365 Admin | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |  |
| Kaizala | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Office mobile | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Portal de Office | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| OneDrive | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| OneNote | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Outlook | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Planner | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Power Apps | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Power Automate | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| PowerPoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Skype Empresarial | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) |
| Administrador de Skype Empresarial | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| SharePoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Administrador de SharePoint Online | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Notas rápidas | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Stream | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Teams | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) |
| Tareas pendientes | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Visio | N/D | ![Compatible.](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Whiteboard | Planeado | ![Compatible.](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Word | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Análisis del lugar de trabajo | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)