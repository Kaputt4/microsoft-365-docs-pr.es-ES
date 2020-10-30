---
title: 'Soporte técnico de la aplicación cliente de Microsoft 365: acceso condicional'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: En este artículo, obtenga información acerca de las plataformas, los clientes y los módulos de PowerShell que admiten el acceso condicional para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806687"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Soporte técnico de la aplicación cliente de Microsoft 365: acceso condicional

En el lugar de trabajo moderno, los usuarios pueden tener acceso a los recursos de la organización usando varios dispositivos y aplicaciones desde cualquier lugar. Como resultado, simplemente centrarse en quién puede tener acceso a un recurso ya no es suficiente. La organización también debe admitir cómo y dónde se obtiene acceso a un recurso en su infraestructura de control de acceso.

Con el acceso condicional de dispositivo, ubicación y autenticación multifactor de Azure Active Directory, puede cumplir con este nuevo requisito. El acceso condicional es una capacidad de Azure Active Directory que permite aplicar controles en el acceso a las aplicaciones de su entorno, todo ello en función de condiciones específicas y administradas desde una ubicación central.

Obtenga más información sobre el [acceso condicional de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-clients--platforms"></a>Plataformas & clientes compatibles

Las versiones más recientes de los siguientes clientes y plataformas admiten el acceso condicional. Para obtener más información acerca de la compatibilidad de plataformas de Microsoft 365, vea [requisitos del sistema para microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicaciones modernas| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador de Azure Active Directory | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Azure admin | N/D | N/D | N/D | N/D | N/D |
| Portal de empresa | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Cortana | Plane | Plane | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
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
| PowerApps | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | Plane | N/D |
| Power Automate | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| PowerPoint | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Skype Empresarial | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D ||
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
