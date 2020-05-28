---
title: Configurar directivas de acceso condicional para campañas de 365 de Microsoft
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo configurar directivas de acceso condicional para las campañas de Microsoft 365 para agregar una seguridad adicional importante.
ms.openlocfilehash: d7c9cfee2ef00e4ebe231a28ccca185c10f53c6b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403026"
---
# <a name="set-up-conditional-access-policies"></a>Configurar directivas de acceso condicional

Las directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) agregan una seguridad adicional importante. Microsoft proporciona un conjunto de directivas de acceso condicional de línea base que se recomiendan para todos los clientes. Las directivas de línea base son un conjunto de directivas predefinidas que ayudan a proteger a las organizaciones frente a muchos ataques comunes. Estos ataques comunes pueden incluir aerosol, reproducción y suplantación de identidad.

Estas directivas requieren que los administradores y los usuarios escriban una segunda forma de autenticación (denominada autenticación multifactor o MFA) cuando se cumplan ciertas condiciones. Por ejemplo, si un usuario inicia sesión desde un país diferente, el inicio de sesión puede considerarse arriesgado y el usuario debe proporcionar una forma de autenticación adicional. 

Actualmente, las directivas de línea base son las siguientes:
- **Requerir MFA para los administradores** &ndash; Requiere multi-factor Authentication para los roles de administrador con mayor privilegios, incluido el administrador global.
- Protección del usuario **final** &ndash; Requiere la autenticación multifactor para los usuarios solo cuando un inicio de sesión es arriesgado. 
- **Bloquear la autenticación** &ndash; heredada Las aplicaciones cliente más antiguas y algunas aplicaciones nuevas no usan protocolos de autenticación más recientes, más seguros. Estas aplicaciones antiguas pueden omitir las directivas de acceso condicional y obtener acceso no autorizado a su entorno. Esta directiva bloquea el acceso de los clientes que no admiten el acceso condicional. 
- **Requerir MFA para la administración** &ndash; de servicios Requiere multi-factor Authentication para el acceso a las herramientas de administración, incluido Azure portal (donde se configuran las directivas de línea base). 

Microsoft recomienda habilitar todas estas directivas de línea base. Una vez habilitadas estas directivas, se pedirá a los administradores y a los usuarios que se registren para la autenticación de varios factores de Azure.

Para obtener más información acerca de estas directivas, vea [¿Qué son las directivas de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Configurar directivas de línea base

1. Vaya a [Azure portal](https://portal.azure.com)y navegue a **Azure Active Directory** \> **Conditional Access**.
    
    Las directivas de línea base se enumeran en la página. <br/> <br/>
    ![Página donde se enumeran las directivas de línea base para el acceso condicional.](../media/baslinepolicies.png)
1. Consulte las siguientes instrucciones específicas para cada directiva:

  - [Requerir MFA para los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Requerir MFA para los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Bloquear la autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Requerir MFA para la administración de servicios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Puede configurar muchas directivas adicionales, como requerir aplicaciones cliente aprobadas. Para obtener más información, consulte la [documentación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/).
