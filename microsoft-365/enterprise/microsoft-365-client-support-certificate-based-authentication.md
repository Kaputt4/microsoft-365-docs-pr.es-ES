---
title: 'Soporte técnico de Microsoft 365 Client App: autenticación basada en certificados'
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
ms.openlocfilehash: fde124fcefdf3b949ec35a3b2ed99b15ee36f85e
ms.sourcegitcommit: 2beefb695cead03cc21d6066f589572d3ae029aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349685"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Soporte técnico de Microsoft 365 Client App: autenticación basada en certificados

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La autenticación moderna es un término genérico para una combinación de métodos de autenticación y autorización. Entre ellas se incluyen:

- **Métodos de autenticación**: multi-factor Authentication; Autenticación basada en certificados de cliente.
- **Métodos de autorización**: implementación de Microsoft de Open Authorization (OAuth).

La autenticación moderna se habilita mediante el uso de una biblioteca de autenticación, como la biblioteca de autenticación de Active Directory (ADAL) o la biblioteca de autenticación de Microsoft (MSAL). La autenticación moderna es lo que los clientes usan para autenticar y autorizar el acceso a los recursos 365 de Microsoft. La autenticación moderna aprovecha OAuth y proporciona un mecanismo seguro para que los clientes tengan acceso a los servicios de 365 de Microsoft, sin necesidad de tener acceso a las credenciales del usuario. Al iniciar sesión, el usuario se autentica directamente con Azure Active Directory y recibe un par de tokens de acceso y actualización en devolución. El token de acceso concede al cliente acceso a los recursos adecuados en el inquilino de Microsoft 365. Un token de actualización se usa para obtener un nuevo par de tokens de acceso o actualización cuando expira el token de acceso actual.

La autenticación moderna admite diferentes mecanismos de autenticación, como la autenticación basada en certificados. Los clientes de dispositivos Windows, Android o iOS pueden usar la autenticación basada en certificados (CBA) para autenticarse en Azure Active Directory con un certificado de cliente en el dispositivo. En lugar de un nombre de usuario y contraseña típicos, el certificado se usa para obtener un par de tokens de acceso y actualización desde Azure Active Directory.

Obtenga más información acerca de [la autenticación basada en certificados](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Plataformas & clientes compatibles

Las versiones más recientes de los siguientes clientes y plataformas admiten la autenticación basada en certificados al iniciar sesión en cuentas de Azure Active Directory dentro del cliente (por ejemplo, al agregar una cuenta a la aplicación). Para obtener más información acerca de la compatibilidad de plataformas de Microsoft 365, vea [requisitos del sistema para microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicaciones modernas| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador de Azure Active Directory | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Azure admin | N/D | N/D | N/D | N/D | N/D |
| Portal de empresa | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Cortana | Plane | Plane | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Delve | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Edge<sup>1</sup> | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Excel | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Administración de Exchange Online | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Formularios | N/D | N/D | N/D | N/D | N/D |
| Office 365 Admin | N/D | N/D | N/D | N/D | ![Compatible](../media/check-mark.png) |  |
| Kaizala | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | ![Compatible.](../media/check-mark.png) | No aplicable |
| Office Mobile | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Portal de Office | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| OneDrive | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Plane | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
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
| Administrador de SharePoint Online | Plane | Plane | N/D | N/D | N/D |
| Notas rápidas | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Stream | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Teams | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable | Plane |
| To Do | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | No aplicable |
| Visio | N/D | ![Compatible.](../media/check-mark.png) | N/D | N/D | ![Compatible](../media/check-mark.png) |
| Whiteboard | Plane | Plane | N/D | ![Compatible.](../media/check-mark.png) | No aplicable |
| Word | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) |
| Análisis de trabajo | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Compatible](../media/check-mark.png) | ![Compatible](../media/check-mark.png) | Plane | N/D | Plane |

>[!NOTE]
><sup>1</sup> perimetral para iOS y Android admite la autenticación basada en certificados durante la adición de la cuenta de flujos. El servidor perimetral para iOS y Android no admite la autenticación basada en certificados al realizar la autenticación en sitios web, que normalmente son sitios de intranet. <br><br>  En este escenario, un usuario navega a un sitio web (normalmente en la intranet) en el que el sitio web requiere que el usuario se autentique a través de un certificado. Esto no implica ninguna autenticación moderna y no aprovecha una biblioteca de autenticación de Microsoft. Esto se debe a una limitación de iOS: iOS impide que las aplicaciones de terceros accedan a la cadena de claves del sistema en la que se almacenan los certificados (solo las aplicaciones de Apple y el [controlador WebView de Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) pueden tener acceso a la cadena de claves del sistema). <br><br> Como Edge se basa en el marco [WebKit](https://developer.apple.com/documentation/webkit) para la representación de sitios web, Edge no puede tener acceso a las llaves del sistema y presenta al usuario una elección de certificado. Por desgracia, es por diseño debido a la arquitectura de Apple.

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

