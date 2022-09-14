---
title: Tiempos de espera de sesión para Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
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
description: Obtenga información sobre cómo se usan los tiempos de espera de sesión para equilibrar la seguridad y la facilidad de acceso en las aplicaciones cliente de Microsoft 365.
ms.openlocfilehash: 910c0eaed754c7d41329741ecb24f15b9ac7364c
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67669087"
---
# <a name="session-timeouts-for-microsoft-365"></a>Tiempos de espera de sesión para Microsoft 365

La duración de la sesión es una parte importante de la autenticación para Microsoft 365 y es un componente importante para equilibrar la seguridad y el número de veces que se solicitan sus credenciales a los usuarios.

## <a name="session-times-for-microsoft-365-services"></a>Tiempos de sesión de los servicios de Microsoft 365

Cuando los usuarios se autentican en cualquiera de las aplicaciones web o aplicaciones móviles de Microsoft 365, se establece una sesión. Durante la sesión, los usuarios no tendrán que volver a autenticarse. Las sesiones pueden expirar cuando los usuarios están inactivos, cuando cierran el explorador o la pestaña, o cuando su token de autenticación expira por otros motivos, como cuando se ha restablecido su contraseña. Los servicios de Microsoft 365 tienen tiempos de espera de sesión diferentes que se corresponden con el uso típico de cada servicio.

En la tabla siguiente se enumeran las duraciones de sesión de los servicios de Microsoft 365:

| Servicio de Microsoft 365 | Tiempo de espera de sesión |
|:-----|:-----|
|Centro de administración de Microsoft 365  <br/> |Se le pide que proporcione credenciales para el centro de administración cada 8 horas.  <br/> |
|SharePoint Online  <br/> |5 días de inactividad, siempre y cuando los usuarios **elijan Mantener la sesión iniciada**. Si el usuario vuelve a acceder a SharePoint Online después de que hayan transcurrido 24 o más horas desde el inicio de sesión anterior, el valor de tiempo de espera se restablece a 5 días.  <br/> |
|Outlook Web App  <br/> |6 horas.  <br/> Puede cambiar este valor mediante el parámetro  _ActivityBasedAuthenticationTimeoutInterval_ del cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) .  <br/> |
|Azure Active Directory  <br/> (Lo usan las aplicaciones de Office y Microsoft 365 en clientes Windows con la autenticación moderna habilitada)  <br/> | La autenticación moderna usa tokens de acceso y tokens de actualización para conceder acceso de usuario a los recursos de Microsoft 365 mediante Azure Active Directory. Un token de acceso es un token web JSON proporcionado después de una autenticación correcta y es válido durante 1 hora. También se proporciona un token de actualización con una duración más larga. Cuando expiran los tokens de acceso, los clientes de Office usan un token de actualización válido para obtener un nuevo token de acceso. Este intercambio se realiza correctamente si la autenticación inicial del usuario sigue siendo válida.  <br/>  Los tokens de actualización son válidos durante 90 días y, con el uso continuo, pueden ser válidos hasta que se revocan.  <br/>  Los tokens de actualización pueden invalidarse mediante varios eventos, como:  <br/>  La contraseña del usuario ha cambiado desde que se emitió el token de actualización.  <br/>  Un administrador puede aplicar directivas de acceso condicional que restrinjan el acceso al recurso al que el usuario está intentando acceder.  <br/> |
|Aplicaciones móviles de SharePoint y OneDrive para Android, iOS y Windows 10  <br/> |La duración predeterminada del token de acceso es de 1 hora. El tiempo máximo de inactividad predeterminado del token de actualización es de 90 días.  <br/> [Más información sobre los tokens y cómo configurar la duración de los tokens](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Para revocar el token de actualización, puede restablecer la contraseña de Microsoft 365 del usuario.  <br/> |
|Yammer con Microsoft 365 Sign-In  <br/> |Duración del explorador. Si los usuarios cierran el explorador y acceden a Yammer en un nuevo explorador, Yammer los volverá a autenticar con Microsoft 365. Si los usuarios usan exploradores de terceros que almacenan en caché las cookies, es posible que no necesiten volver a autenticarse cuando vuelvan a abrir el explorador.  <br/> > [!NOTE]> Esto solo es válido para las redes que usan Microsoft 365 Sign-In para Yammer.           |