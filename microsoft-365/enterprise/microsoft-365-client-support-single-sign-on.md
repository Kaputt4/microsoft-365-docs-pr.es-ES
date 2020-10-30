---
title: 'Soporte técnico de la aplicación cliente de Microsoft 365: una única Sign-On'
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
description: En este artículo, obtenga información acerca de las plataformas, los clientes y los módulos de PowerShell que admiten el inicio de sesión único para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806673"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Soporte técnico de la aplicación cliente de Microsoft 365: una única Sign-On

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El inicio de sesión único (SSO) agrega seguridad y comodidad cuando los usuarios inician sesión en aplicaciones de Azure Active Directory. Con el inicio de sesión único, los usuarios inician sesión una vez con una cuenta para tener acceso a los servicios de dominio de Active Directory (AD DS) y a los dispositivos Unidos a un dominio, software como servicio (SaaS) y aplicaciones web locales.

Obtenga más información sobre [el inicio de sesión único](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-clients--platforms"></a>Plataformas & clientes compatibles

Las versiones más recientes de los siguientes clientes y plataformas admiten el inicio de sesión único. Para obtener más información acerca de la compatibilidad de plataformas de Microsoft 365, vea [requisitos del sistema para microsoft 365](https://products.office.com/office-system-requirements).
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicaciones modernas| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Portal de empresa | N/D | ![Compatible](../media/check-mark.png) | Plane | ![Compatible.](../media/check-mark.png) | No aplicable |
| Cortana | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Delve | Plane | ![Compatible.](../media/check-mark.png) | N/D | N/D | N/D |
| Microsoft Edge | ![Compatible](../media/check-mark.png) | Plane | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Excel | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Kaizala | ![Compatible](../media/check-mark.png) | Plane | N/D | N/D | N/D |
| Office Lens| ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Office Mobile | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Portal de Office | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| OneDrive | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Plane | ![Compatible](../media/check-mark.png) | Plane |
| OneNote | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Plane |
| Outlook | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Plane | ![Compatible](../media/check-mark.png) |
| Planner | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| PowerApps | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | Plane | N/D |
| Power Automate | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) | Plane |
| PowerPoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Skype Empresarial | Plane | Plane | N/D | N/D | N/D |
| SharePoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Notas rápidas | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Stream | Plane | Plane | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Teams | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Plane | N/D | Plane |
| Acciones que realizar | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Visio | N/D | ![Compatible.](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Whiteboard | N/D | ![Compatible.](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Word | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Yammer | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | Plane |

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
