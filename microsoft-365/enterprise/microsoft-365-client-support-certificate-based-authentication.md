---
title: 'Compatibilidad con aplicaciones cliente de Microsoft 365: autenticación basada en certificados'
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
description: En este artículo, encontrará detalles sobre la compatibilidad de la aplicación cliente de Microsoft 365 para la autenticación basada en certificados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097263"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Compatibilidad con aplicaciones cliente de Microsoft 365: autenticación basada en certificados

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La autenticación moderna es un término genérico para una combinación de métodos de autenticación y autorización. Entre ellos se incluyen:

- **Métodos de autenticación:** autenticación multifactor; Autenticación basada en certificados de cliente.
- **Métodos de** autorización: implementación de Microsoft de Open Authorization (OAuth).

La autenticación moderna se habilita mediante el uso de una biblioteca de autenticación, como la Biblioteca de autenticación de Active Directory (ADAL) o la Biblioteca de autenticación de Microsoft (MSAL). La autenticación moderna es lo que los clientes usan para autenticar y autorizar el acceso a los recursos de Microsoft 365. La autenticación moderna aprovecha OAuth y proporciona un mecanismo seguro para que los clientes accedan a los servicios de Microsoft 365, sin necesidad de tener acceso a las credenciales de usuario. Al iniciar sesión, el usuario se autentica directamente con Azure Active Directory y recibe un par de tokens de acceso y actualización a cambio. El token de acceso concede al cliente acceso a los recursos adecuados en el inquilino de Microsoft 365. Un token de actualización se usa para obtener un nuevo par de tokens de acceso o actualización cuando expira el token de acceso actual.

La autenticación moderna admite diferentes mecanismos de autenticación, como la autenticación basada en certificados. Los clientes de dispositivos Windows, Android o iOS pueden usar la autenticación basada en certificados (CBA) para autenticarse en Azure Active Directory mediante un certificado de cliente en el dispositivo. En lugar de un nombre de usuario y contraseña típicos, el certificado se usa para obtener un par de tokens de acceso y actualización de Azure Active Directory.

Obtenga más información sobre [la autenticación basada en certificados.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Clientes compatibles & plataformas

Las últimas versiones de los siguientes clientes y plataformas admiten la autenticación basada en certificados al iniciar sesión en cuentas de Azure Active Directory dentro del cliente (por ejemplo, al agregar una cuenta a la aplicación). Para obtener más información acerca de la compatibilidad con plataformas en Microsoft 365, consulte Requisitos del sistema [para Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicaciones modernas| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador de Azure Active Directory | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Acceso | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Administrador de Azure | N/D | N/D | N/D | N/D | N/D |
| Portal de empresa | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Cortana | Planeado | Planeado | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Delve | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Edge<sup>1</sup> | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Excel | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Administrador de Exchange Online | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Formularios | N/D | N/D | N/D | N/D | N/D |
| Office 365 Admin | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |  |
| Kaizala | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Office mobile | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Portal de Office | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| OneDrive | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Planeado | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
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
| Administrador de SharePoint Online | Planeado | Planeado | N/D | N/D | N/D |
| Notas rápidas | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Stream | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Teams | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | Planeado |
| Tareas pendientes | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Visio | N/D | ![Compatible.](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Whiteboard | Planeado | Planeado | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Word | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Análisis del lugar de trabajo | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Planeado | N/D | Planeado |

>[!NOTE]
><sup>1</sup> Edge para iOS y Android admite la autenticación basada en certificados durante los flujos de adición de cuentas. Edge para iOS y Android no admite la autenticación basada en certificados al realizar la autenticación en sitios web, que normalmente son sitios de intranet. <br><br>  En este escenario, un usuario navega a un sitio web (normalmente en la intranet) donde el sitio web requiere que el usuario se autentique a través de un certificado. Esto no implica la autenticación moderna en absoluto y no aprovecha una biblioteca de autenticación de Microsoft. Esto se debe a una limitación con iOS: iOS impide que las aplicaciones de terceros accedan a la cadena de claves del sistema donde se almacenan los certificados (solo las aplicaciones de Apple y el controlador [de vista web safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) pueden acceder a la cadena de claves del sistema). <br><br> Como Edge se basa en el marco [WebKit](https://developer.apple.com/documentation/webkit) para representar sitios web, Edge no puede acceder a la cadena de claves del sistema y presentar al usuario una opción de certificado. Esto, desafortunadamente, es por diseño debido a la arquitectura de Apple.

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

