---
title: Redirigir cuentas de Microsoft Defender para endpoint al Centro de seguridad de Microsoft 365
description: Cómo redirigir cuentas y sesiones desde Defender for Endpoint al Centro de seguridad de Microsoft 365.
keywords: Centro de seguridad de Microsoft 365, Introducción al centro de seguridad de Microsoft 365, redirección del centro de seguridad
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 626bc9950512438bfa43e6500adf72940ddcbfec
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727570"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Redirigir cuentas de Microsoft Defender para endpoint al Centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**
- Microsoft 365 Defender
- Defender para punto de conexión

En línea con el enfoque entre dominios de Microsoft para la protección contra amenazas con SIEM y la detección y respuesta extendidas (XDR), hemos cambiado el nombre de Protección contra amenazas avanzada de Microsoft Defender como Microsoft Defender para endpoint y lo hemos unificado en un único portal integrado: el Centro de seguridad de Microsoft 365.

En esta guía se explica cómo enrutar cuentas al centro de seguridad de Microsoft 365 habilitando la redirección automática desde el antiguo portal de Microsoft Defender para endpoints (securitycenter.windows.com o securitycenter.microsoft.com), al portal del centro de seguridad de Microsoft 365 (security.microsoft.com).

> [!NOTE]
> Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365 admite la concesión de acceso a proveedores de servicios de seguridad administrados [(MSSP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) del mismo modo que se concede acceso en el Centro de seguridad de [Microsoft Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)

## <a name="what-to-expect"></a>Qué esperar
Una vez habilitada la redirección automática, las cuentas que tengan acceso al antiguo portal de Microsoft Defender para endpoints en securitycenter.windows.com o securitycenter.microsoft.com, se enruta automáticamente al portal del centro de seguridad de Microsoft 365 en security.microsoft.com.
 
Obtenga más información sobre los cambios: Microsoft Defender para endpoint en el Centro de [seguridad de Microsoft 365.](microsoft-365-security-center-mde.md)

Esto incluye el redireccionamiento para el acceso directo al antiguo portal a través del explorador, incluidos los vínculos que apuntan hacia el antiguo portal de securitycenter.windows.com, como vínculos en notificaciones de correo electrónico y vínculos devueltos por llamadas api siem.  

 Actualmente, los vínculos externos de las notificaciones de correo electrónico o las API SIEM contienen vínculos a ambos portales. Una vez habilitado el redireccionamiento, ambos vínculos apuntarán al centro de seguridad de Microsoft 365 hasta que el vínculo antiguo se quite finalmente. Le recomendamos que adopte el nuevo vínculo que apunta al centro de seguridad de Microsoft 365.

Consulte la tabla siguiente para obtener más información sobre los vínculos y el enrutamiento.
## <a name="siem-api-routing"></a>Enrutamiento de API siem

|**Propiedad**  |**Destino cuando el redireccionamiento está DESACTIVADO**  |**Destino cuando el redireccionamiento está ON** | 
|---------|---------|---------|
| LinkToWDATP | Página de alerta en securitycenter.windows.com | Página de alerta en security.microsoft.com  |
| IncidentLinkToWDATP | Página de incidentes en securitycenter.windows.com  | Página de incidentes en security.microsoft.com  |
| LinkToMTP | Página de alerta en security.microsoft.com | Página de alerta en security.microsoft.com  |
| IncidentLinkToMTP | Página de incidentes en security.microsoft.com  | Página de incidentes en security.microsoft.com  

## <a name="email-alert-notifications"></a>Notificaciones de alertas de correo electrónico

|**Propiedad**  |**Destino cuando el redireccionamiento está DESACTIVADO**  |**Destino cuando el redireccionamiento está ON** |
|---------|---------|---------|
| Página alerta  | Página de alerta en securitycenter.windows.com  | Página de alerta en security.microsoft.com  |
| Página Incidentes  |Página de incidentes en securitycenter.windows.com  | Página de incidentes en security.microsoft.com  
| Página de alertas en el portal del centro de seguridad | Página de alerta en security.microsoft.com | Página de alerta en security.microsoft.com | 
| Página de incidentes en el portal del centro de seguridad | Página de incidentes en security.microsoft.com  | Página de incidentes en security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>¿Cuándo tiene efecto? 
Una vez habilitada, esta actualización podría tener efecto casi inmediatamente para algunas cuentas. Pero la redirección puede tardar más tiempo en propagarse a todas las cuentas de la organización. Las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.  

### <a name="set-up-portal-redirection"></a>Configurar la redirección del portal
Para iniciar el enrutamiento de cuentas al Centro de seguridad de Microsoft 365:
1. Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory 

2. [Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365.

3. Vaya a **Configuración Redirección** del Portal general de  >    >    >  **extremos o** [haga clic aquí.](https://security.microsoft.com/preferences2/portal_redirection)  

4. Alterna la configuración de redirección automática a **On**.

5. Haga **clic en** Habilitar para aplicar el redireccionamiento automático al portal del centro de seguridad de Microsoft 365.

>[!IMPORTANT]
>Si se habilita esta configuración, no se finalizarán las sesiones de usuario activas. Las cuentas que se encuentran en una sesión activa mientras se aplica esta configuración solo se dirigirán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.

>[!NOTE]
>Debe ser un administrador global o tener permisos de administrador de seguridad en Azure Active Directory para habilitar o deshabilitar esta configuración.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?
Si algo no funciona para usted o si hay algo que no puede completar a través del portal del centro de seguridad de Microsoft 365, queremos escucharlo. Si ha encontrado algún problema con el redireccionamiento, le recomendamos que nos lo haga saber mediante el formulario Enviar comentarios.

Para volver al antiguo portal de Microsoft Defender para endpoint:

1. [Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365 como administrador global o use y tenga una cuenta con permisos de administrador de seguridad en Azure Active Directory.

2. Vaya a **Configuración**  >  **Desdireccionamiento del** Portal general de extremos  >    >   o [abra la página aquí](https://security.microsoft.com/preferences2/portal_redirection).  

3. Alterna la opción Redirección automática a **Desactivado**.

4. Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.

Esta configuración se puede habilitar de nuevo en cualquier momento. 

Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al antiguo portal: securitycenter.windows.com o securitycenter.microsoft.com. 

## <a name="related-information"></a>Información relacionada
- [Vista general del Centro de seguridad de Microsoft 365](overview-security-center.md)
- [Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mde.md)
- [Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR frente a la infografía siem](https://afrait.com/blog/xdr-versus-siem/) 
- [El nuevo defensor](https://afrait.com/blog/the-new-defender/) 
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portales de seguridad de Microsoft y centros de administración](portals.md)
