---
title: Redirigir cuentas de Microsoft Defender para Office 365 al nuevo centro Microsoft 365 seguridad
description: Cómo redirigir desde defender para Office 365 al centro Microsoft 365 seguridad.
keywords: Microsoft 365 de seguridad, Introducción al centro de seguridad de Microsoft 365, redirección del centro de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2a4b122b3ef3a1ddaf61d8f9373bec3e721db177
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651385"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Redirigir cuentas de Microsoft Defender para Office 365 al centro Microsoft 365 seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender
- Defender para Office 365

En este artículo se explica cómo enrutar cuentas al centro de seguridad de Microsoft 365 habilitando la redirección automática desde el antiguo Centro de seguridad y cumplimiento de Microsoft (protection.office.com o securitycenter.microsoft.com), al centro de seguridad de Microsoft 365 (security.microsoft.com).

## <a name="what-to-expect"></a>Qué esperar
Una vez habilitada y activa la redirección automática, los usuarios que tengan acceso a las funciones relacionadas con la seguridad en Office 365 Seguridad y cumplimiento (protection.office.com), se enruta automáticamente al centro de seguridad de Microsoft 365 ( https://security.microsoft.com) .  

Obtenga más información sobre lo que ha cambiado: [Microsoft Defender para Office 365 en el centro Microsoft 365 seguridad](microsoft-365-security-center-mdo.md).

Con el redireccionamiento automático activado, los usuarios se enrutarán Microsoft 365 centro de seguridad cuando usen funciones de seguridad en el Centro de seguridad y cumplimiento Office 365 seguridad.

Estas incluyen funcionalidades en la sección Administración de amenazas y en el panel e informes de administración de amenazas. Los elementos del Office 365 seguridad y cumplimiento que no están relacionados con la seguridad no se redirigen al centro de seguridad Microsoft 365 seguridad.

Los elementos relacionados con el cumplimiento se pueden encontrar en el centro de cumplimiento Microsoft 365 y los elementos relacionados con el flujo de correo se pueden encontrar en el centro de administración Exchange correo.

El resto de funcionalidades, ya sean relacionadas con el cumplimiento o las funcionalidades que sirven a ambos, no se ven afectadas por el redireccionamiento. Office 365 alertas de seguridad aparecen en el centro de seguridad de Microsoft 365 y en el centro de seguridad y cumplimiento de Office 365, sin redirección.  

### <a name="set-up-portal-redirection"></a>Configurar la redirección del portal
Para iniciar el enrutamiento de cuentas al centro Microsoft 365 seguridad en security.microsoft.com:

1. Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory.
2. [Inicie sesión](https://security.microsoft.com/) en el centro Microsoft 365 seguridad.
3. Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**  
4. Alterna la configuración de redirección automática a **On**.
5. Haga **clic en** Habilitar para aplicar la redirección automática al portal Microsoft 365 centro de seguridad.

> [!NOTE]
> Una vez habilitada la redirección, las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?
Si algo no funciona para usted o si hay algo que no puede completar a través del portal del centro de seguridad de Microsoft 365, queremos saber cómo hacerlo con la opción de comentarios del portal. Si ha encontrado algún problema con el redireccionamiento, háganoslo saber.

Para volver al portal anterior:

1. [Inicie sesión](https://security.microsoft.com/) en el centro Microsoft 365 seguridad como administrador global o use y cuenta con permisos de administrador de seguridad en Azure Active Directory.

2. Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**   

3. Alterna la opción Redirección automática a **Desactivado**.

4. Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.

Esta configuración se puede habilitar de nuevo en cualquier momento.

Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al antiguo portal: securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Información relacionada
- [Vista general del Centro de seguridad de Microsoft 365](overview-security-center.md)
- [Microsoft Defender para endpoint en el centro Microsoft 365 seguridad](microsoft-365-security-center-mde.md)
- [Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR frente a la infografía siem](https://afrait.com/blog/xdr-versus-siem/) 
- [El nuevo defensor](https://afrait.com/blog/the-new-defender/) 
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portales de seguridad de Microsoft y centros de administración](portals.md)
