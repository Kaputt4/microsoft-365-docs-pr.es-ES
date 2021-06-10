---
title: Tiempos de espera de sesión para Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Obtén información sobre cómo se usan los tiempos de espera de sesión para equilibrar la seguridad y la facilidad de acceso en Microsoft 365 cliente.
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924921"
---
# <a name="session-timeouts-for-microsoft-365"></a>Tiempos de espera de sesión para Microsoft 365

Las duraciones de sesión son una parte importante de la autenticación para Microsoft 365 y son un componente importante para equilibrar la seguridad y el número de veces que se solicita a los usuarios sus credenciales.

## <a name="session-times-for-microsoft-365-services"></a>Horas de sesión para Microsoft 365 servicios

Cuando los usuarios se autentican en cualquiera de las Microsoft 365 web o aplicaciones móviles, se establece una sesión. Durante la sesión, los usuarios no necesitarán volver a autenticarse. Las sesiones pueden expirar cuando los usuarios están inactivos, cuando cierran el explorador o la pestaña, o cuando su token de autenticación expira por otros motivos, como cuando se ha restablecido su contraseña. Los Microsoft 365 tienen tiempos de espera de sesión diferentes para que se correspondan con el uso típico de cada servicio.

En la tabla siguiente se enumeran las duraciones de la sesión Microsoft 365 servicios:

| Servicio de Microsoft 365 | Tiempo de espera de sesión |
|:-----|:-----|
|Centro de administración de Microsoft 365  <br/> |Se le pedirá que proporcione credenciales para el centro de administración cada 8 horas.  <br/> |
|SharePoint Online  <br/> |5 días de inactividad siempre que los usuarios elijan **Mantenerme iniciado sesión.** Si el usuario vuelve a SharePoint Online después de pasar 24 o más horas desde el inicio de sesión anterior, el valor de tiempo de espera se restablece a 5 días.  <br/> |
|Outlook Web App  <br/> |6 horas.  <br/> Puede cambiar este valor mediante el parámetro _ActivityBasedAuthenticationTimeoutInterval_ en el cmdlet [Set-OrganizationConfig.](/powershell/module/exchange/set-organizationconfig)  <br/> |
|Azure Active Directory  <br/> (Usado por Office y Microsoft 365 aplicaciones en Windows clientes con autenticación moderna habilitada)  <br/> | La autenticación moderna usa tokens de acceso y tokens de actualización para conceder acceso de usuario a Microsoft 365 recursos mediante Azure Active Directory. Un token de acceso es un token web JSON proporcionado después de una autenticación correcta y es válido durante 1 hora. También se proporciona un token de actualización con una duración más larga. Cuando expiran los tokens de acceso, Office los clientes usan un token de actualización válido para obtener un nuevo token de acceso. Este intercambio se realiza correctamente si la autenticación inicial del usuario sigue siendo válida.  <br/>  Los tokens de actualización son válidos durante 90 días y, con uso continuo, pueden ser válidos hasta que se revocan.  <br/>  Los tokens de actualización se pueden invalidar mediante varios eventos, como:  <br/>  La contraseña del usuario ha cambiado desde que se emitió el token de actualización.  <br/>  Un administrador puede aplicar directivas de acceso condicional que restringen el acceso al recurso al que el usuario está intentando acceder.  <br/> |
|SharePoint y OneDrive aplicaciones móviles para Android, iOS y Windows 10  <br/> |La duración predeterminada del token de acceso es de 1 hora. El tiempo máximo inactivo predeterminado del token de actualización es de 90 días.  <br/> [Obtenga más información sobre tokens y cómo configurar duraciones de tokens](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Para revocar el token de actualización, puedes restablecer la contraseña de Microsoft 365 usuario  <br/> |
|Yammer con Microsoft 365 Sign-In  <br/> |Duración del explorador. Si los usuarios cierran el explorador y acceden a Yammer en un nuevo explorador, Yammer los volverá a autenticar con Microsoft 365. Si los usuarios usan exploradores de terceros que almacenan en caché cookies, es posible que no necesiten volver a autenticarse cuando vuelvan a abrir el explorador.  <br/> > [!NOTE]> Esto solo es válido para redes que usan Microsoft 365 Sign-In para Yammer.           |