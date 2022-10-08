---
title: Redirigir cuentas de Microsoft Defender para punto de conexión a Microsoft 365 Defender
description: Cómo redirigir cuentas y sesiones desde Defender para punto de conexión a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Introducción a Microsoft 365 Defender, redirección de Security Center
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.openlocfilehash: 3f7d7bab51a8dfb29b25701ccc87e49b437529ab
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072621"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Redirigir cuentas de Microsoft Defender para punto de conexión a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender
- Defender para punto de conexión

En consonancia con el enfoque entre dominios de Microsoft para la protección contra amenazas con SIEM y la detección y respuesta extendidas (XDR), hemos cambiado el nombre de Microsoft Defender Advanced Threat Protection como Microsoft Defender para punto de conexión y lo hemos unificado en un único portal integrado: Microsoft 365 Defender.

En esta guía se explica cómo enrutar las cuentas a Microsoft 365 Defender habilitando el redireccionamiento automático desde el portal de Microsoft Defender para punto de conexión anterior (securitycenter.windows.com o securitycenter.microsoft.com) a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender </a>.

> [!NOTE]
> Microsoft Defender para punto de conexión en Microsoft 365 Defender admite [la concesión de acceso a proveedores de servicios de seguridad administrados (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de la misma manera que se [concede acceso en el Centro de seguridad de Microsoft Defender](./mssp-access.md).

## <a name="what-to-expect"></a>Qué esperar

Una vez habilitada la redirección automática, las cuentas que acceden al portal de Microsoft Defender para punto de conexión anterior en securitycenter.windows.com o securitycenter.microsoft.com, se enrutarán automáticamente a Microsoft 365 Defender portal en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><security.microsoft.com></a>.

Obtenga más información sobre lo que ha cambiado: [Microsoft Defender para punto de conexión en Microsoft 365 Defender](microsoft-365-security-center-mde.md).

Esto incluye el redireccionamiento para el acceso directo al portal anterior a través del explorador, incluidos los vínculos que apuntan al anterior securitycenter.windows.com portal, como vínculos en notificaciones por correo electrónico y vínculos devueltos por llamadas API SIEM.  

 Actualmente, los vínculos externos de las notificaciones de correo electrónico o las API SIEM contienen vínculos a ambos portales. Una vez habilitado el redireccionamiento, ambos vínculos apuntarán a Microsoft 365 Defender hasta que finalmente se quite el vínculo anterior. Le recomendamos que adopte el nuevo vínculo que apunta a Microsoft 365 Defender.

Consulte la tabla siguiente para obtener más información sobre los vínculos y el enrutamiento.
## <a name="siem-api-routing"></a>Enrutamiento de API siem

| Propiedad | Destino cuando el redireccionamiento es OFF | Destino cuando el redireccionamiento es ON |
|---------|---------|---------|
| LinkToWDATP | Página Alerta en securitycenter.windows.com | Página Alerta en security.microsoft.com |
| IncidentLinkToWDATP | Página Incidente en securitycenter.windows.com | Página Incidente en security.microsoft.com |
| LinkToMTP | Página Alerta en security.microsoft.com | Página Alerta en security.microsoft.com |
| IncidentLinkToMTP | Página Incidente en security.microsoft.com | Página Incidente en security.microsoft.com |

## <a name="email-alert-notifications"></a>Email notificaciones de alertas

| Propiedad | Destino cuando el redireccionamiento es OFF** | Destino cuando el redireccionamiento es ON |
|---------|---------|---------|
| Página alerta | Página Alerta en securitycenter.windows.com | Página Alerta en security.microsoft.com |
| Página Incidente |Página Incidente en securitycenter.windows.com | Página Incidente en security.microsoft.com |
| Página Alerta en Defender for Cloud Portal | Página Alerta en security.microsoft.com | Página Alerta en security.microsoft.com |
| Página Incidente en El portal de Defender for Cloud | Página Incidente en security.microsoft.com | Página Incidente en security.microsoft.com |

## <a name="when-does-this-take-effect"></a>¿Cuándo surte efecto?

Una vez habilitada, esta actualización podría surtir efecto casi inmediatamente en algunas cuentas. Pero el redireccionamiento puede tardar más tiempo en propagarse a todas las cuentas de la organización. Las cuentas de las sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán a Microsoft 365 Defender después de finalizar la sesión actual y volver a iniciar sesión.  

### <a name="set-up-portal-redirection"></a>Configuración del redireccionamiento del portal

Para iniciar el enrutamiento de cuentas a Microsoft 365 Defender:

1. Asegúrese de que es un administrador global o tiene permisos de administrador de seguridad en Azure Active Directory.

2. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>.

3. Vaya al **redireccionamiento del Portal** **general** > **de puntos** >  de conexión de **configuración** >  o [haga clic aquí](https://security.microsoft.com/preferences2/portal_redirection).  

4. Cambie el valor de Redirección automática a **Activado**.

5. Haga clic en **Habilitar** para aplicar el redireccionamiento automático a Microsoft 365 Defender.

>[!IMPORTANT]
>La habilitación de esta configuración no finalizará las sesiones de usuario activas. Las cuentas que están en una sesión activa mientras se aplica esta configuración solo se dirigirán a Microsoft 365 Defender después de finalizar la sesión actual e iniciar sesión de nuevo.

>[!NOTE]
>Debe ser administrador global o tener permisos de administrador de seguridad en Azure Active Directory para habilitar o deshabilitar esta configuración.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?

Si algo no funciona para ti o si hay algo que no puedas completar a través de Microsoft 365 Defender, queremos oírlo. Si ha encontrado algún problema con el redireccionamiento, le recomendamos que nos lo informe mediante el formulario Enviar comentarios.

Para volver al portal de Microsoft Defender para punto de conexión anterior:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> como administrador global o con una cuenta y con permisos de administrador de seguridad en Azure Active Directory.

2. Vaya al **redireccionamiento del Portal** **general** > **de puntos** >  de conexión de **configuración** >  o [abra la página aquí](https://security.microsoft.com/preferences2/portal_redirection).  

3. Cambie la configuración de redireccionamiento automático a **Desactivado**.

4. Haga clic en **Deshabilitar** & compartir comentarios cuando se le solicite.

Esta configuración se puede habilitar de nuevo en cualquier momento. 

Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverá a tener acceso al portal anterior, securitycenter.windows.com o securitycenter.microsoft.com. 

## <a name="related-information"></a>Información relacionada
- [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografía de XDR frente a SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portales de seguridad y centros de administración de Microsoft](portals.md)
