---
title: 'Microsoft 365 Compatibilidad con aplicaciones cliente: autenticación basada en certificados'
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
description: En este artículo, encontrará detalles sobre la compatibilidad Microsoft 365 aplicación cliente para la autenticación basada en certificados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904998"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Compatibilidad con aplicaciones cliente: autenticación basada en certificados

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

La autenticación moderna es un término general para una combinación de métodos de autenticación y autorización. Estos métodos son:

- **Métodos de autenticación**: Autenticación multifactor; Autenticación basada en certificados de cliente.
- **Métodos de** autorización: la implementación de Microsoft de Open Authorization (OAuth).

La autenticación moderna se habilita mediante una biblioteca de autenticación, como biblioteca de autenticación de Active Directory (ADAL) o biblioteca de autenticación de Microsoft (MSAL). La autenticación moderna es lo que usan los clientes para autenticar y autorizar el acceso a Microsoft 365 recursos. La autenticación moderna usa OAuth y proporciona un mecanismo seguro para que los clientes accedan a Microsoft 365 servicios, sin necesidad de tener acceso a las credenciales de usuario. Al iniciar sesión, el usuario se autentica directamente con Azure Active Directory y recibe un par de tokens de acceso y actualización a cambio. El token de acceso concede al cliente acceso a los recursos adecuados en el Microsoft 365 inquilino. Un token de actualización se usa para obtener un nuevo par de tokens de acceso o actualización cuando expira el token de acceso actual.

La autenticación moderna admite diferentes mecanismos de autenticación, como la autenticación basada en certificados. Los clientes Windows, Android o dispositivos iOS pueden usar la autenticación basada en certificados (CBA) para autenticarse en Azure Active Directory mediante un certificado de cliente en el dispositivo. En lugar de un nombre de usuario/contraseña típico, el certificado se usa para obtener un par de tokens de acceso y actualización de Azure Active Directory.

Obtenga más información sobre [la autenticación basada en certificados](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Clientes compatibles & plataformas

Las versiones más recientes de los siguientes clientes y plataformas admiten la autenticación basada en certificados al iniciar sesión en cuentas de Azure Active Directory dentro del cliente (por ejemplo, al agregar una cuenta a la aplicación). Para obtener más información acerca de la compatibilidad de plataforma Microsoft 365, vea [Requisitos del](/microsoft-365/microsoft-365-and-office-resources)sistema para Microsoft 365 .
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
>Edge para iOS y Android admite la autenticación basada en certificados durante los flujos de adición de cuentas. Edge para iOS y Android no admite la autenticación basada en certificados al realizar la autenticación en sitios web, que suelen ser sitios de intranet. <br><br>  En este escenario, un usuario navega a un sitio web (normalmente en la intranet) donde el sitio web requiere que el usuario se autentique a través de un certificado. Esto no implica autenticación moderna en absoluto y no aprovecha una biblioteca de autenticación de Microsoft. Esto se debe a una limitación con iOS: iOS impide que las aplicaciones de terceros accedan al llavero del sistema donde se almacenan los certificados (solo las aplicaciones de Apple y el controlador de vista [web safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) pueden acceder al llavero del sistema). <br><br> Como Edge se basa en el marco [webKit](https://developer.apple.com/documentation/webkit) para representar sitios web, Edge no puede tener acceso a la cadena de claves del sistema y presentar al usuario una opción de certificado. Esto, desafortunadamente, es por diseño debido a la arquitectura de Apple.

## <a name="supported-powershell-modules"></a>Módulos de PowerShell compatibles

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

