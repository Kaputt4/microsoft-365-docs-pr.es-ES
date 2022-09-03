---
title: 'Evaluación de acceso continuo para Microsoft 365: Microsoft 365 para empresas'
description: Describe cómo la evaluación del acceso condicional para Microsoft 365 y Azure AD finaliza proactivamente las sesiones de usuario activas y aplica los cambios de directiva de inquilino casi en tiempo real.
ms.author: dansimp
author: dansimp
manager: dansimp
ms.service: microsoft-365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
- highpri
ms.subservice: mdo
ms.openlocfilehash: a6c6816148820cb40287449fcea94cc4d2b6c633
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597335"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>Evaluación de acceso continuo para Microsoft 365

Los servicios en la nube modernos que usan OAuth 2.0 para la autenticación se basan tradicionalmente en la expiración del token de acceso para revocar el acceso de una cuenta de usuario. En la práctica, esto significa incluso si un administrador revoca el acceso de una cuenta de usuario, el usuario seguirá teniendo acceso hasta que expire el token de acceso, que para Microsoft 365 de forma predeterminada, solía ser hasta una hora después de que se produjera el evento de revocación inicial.

La evaluación de acceso condicional para Microsoft 365 y Azure Active Directory (Azure AD) finaliza proactivamente las sesiones de usuario activas y aplica los cambios de directiva de inquilino casi en tiempo real en lugar de depender de la expiración del token de acceso. Azure AD notifica a los servicios de Microsoft 365 habilitados para la evaluación de acceso continuo (como SharePoint, Teams y Exchange) cuando la cuenta de usuario o el inquilino han cambiado de una manera que requiere la reevaluación del estado de autenticación de la cuenta de usuario.

Cuando un cliente habilitado para la evaluación de acceso continuo, como Outlook, intenta acceder a Exchange con un token de acceso existente, el servicio rechaza el token, lo que solicita una nueva autenticación de Azure AD. El resultado es la aplicación casi en tiempo real de los cambios de directiva y cuenta de usuario.

Estas son algunas ventajas adicionales:

- En el caso de un usuario interno malintencionado que copia y exporta un token de acceso válido fuera de su organización, la evaluación continua del acceso impide el uso de este token a través de la directiva de ubicación de direcciones IP de Azure AD. Con la evaluación continua del acceso, Azure AD sincroniza las directivas con los servicios de Microsoft 365 compatibles, por lo que cuando un token de acceso intenta acceder al servicio desde fuera del intervalo de direcciones IP de la directiva, el servicio rechaza el token.

- La evaluación continua del acceso mejora la resistencia al requerir menos actualizaciones de tokens. Dado que los servicios auxiliares reciben notificaciones proactivas sobre la necesidad de volver a autenticarse, Azure AD puede emitir tokens de larga duración, por ejemplo, más allá de una hora. Con tokens de larga duración, los clientes no tienen que solicitar una actualización de tokens de Azure AD con tanta frecuencia, por lo que la experiencia del usuario es más resistente.

Estos son algunos ejemplos de situaciones en las que la evaluación continua del acceso mejora la seguridad del control de acceso de los usuarios:

- La contraseña de una cuenta de usuario se ha puesto en peligro para que un administrador invalide todas las sesiones existentes y restablezca su contraseña del Centro de administración de Microsoft 365. Casi en tiempo real, se invalidan todas las sesiones de usuario existentes con servicios de Microsoft 365.

- Un usuario que trabaja en un documento en Word lleva su tableta a una cafetería pública que no se encuentra en un intervalo de direcciones IP definidas y aprobadas por el administrador. En la cafetería, el acceso del usuario al documento se bloquea inmediatamente.

Para Microsoft 365, la evaluación de acceso continua es compatible actualmente con:

- Servicios de Exchange, SharePoint y Teams.
- Outlook, Teams, Office y OneDrive en un explorador web y para los clientes Win32, iOS, Android y Mac.

Microsoft está trabajando en servicios y clientes adicionales de Microsoft 365 para admitir la evaluación continua del acceso.

La evaluación continua del acceso se incluirá en todas las versiones de Office 365 y Microsoft 365. La configuración de directivas de acceso condicional requiere Azure AD Premium P1, que se incluye en todas las versiones de Microsoft 365.

> [!NOTE]
> Consulte [este artículo](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) para conocer las limitaciones de la evaluación continua del acceso.

## <a name="scenarios-supported-by-microsoft-365"></a>Escenarios admitidos por Microsoft 365

La evaluación de acceso continuo admite dos tipos de eventos:

- Los eventos críticos son aquellos en los que un usuario debe perder el acceso.
- La evaluación de directivas de acceso condicional se produce cuando un usuario debe perder el acceso a un recurso en función de una directiva definida por el administrador.

Entre los eventos críticos se incluyen:

- La cuenta de usuario está deshabilitada
- Se cambia la contraseña
- Se revocan las sesiones de usuario
- La autenticación multifactor está habilitada para el usuario
- El riesgo de la cuenta aumentó en función de la evaluación del acceso desde [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection)

La evaluación de directivas de acceso condicional se produce cuando la cuenta de usuario ya no se conecta desde una red de confianza.

Los siguientes servicios de Microsoft 365 admiten actualmente la evaluación continua de acceso mediante la escucha de eventos de Azure AD.

|Tipo de aplicación|Exchange|SharePoint|Teams|
|---|---|---|---|
|**Eventos críticos:**||||
|Revocación de usuarios|Compatible|Compatible|Compatible|
|Riesgo de usuario|Compatible|No se admite|No compatible|
|**Evaluación de directivas de acceso condicional:**||||
|Directiva de ubicación de direcciones IP|Compatible|Compatible\*|Compatible|

\* El acceso al explorador web de Office de SharePoint admite la aplicación instantánea de directivas IP al habilitar el modo estricto. Sin el modo estricto, la duración del token de acceso es de una hora.

Para obtener más información sobre cómo configurar una directiva de acceso condicional, consulte [este artículo](/azure/active-directory/conditional-access/overview).

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Clientes de Microsoft 365 que admiten la evaluación continua del acceso

Los clientes habilitados para la evaluación de acceso continuo para Microsoft 365 admiten un desafío de notificación, que es una redirección de una sesión de usuario a Azure AD para la reautorización, cuando un servicio de Microsoft 365 habilitado para la evaluación de acceso continuo rechaza un token de usuario almacenado en caché.

Los siguientes clientes admiten la evaluación de acceso continuo en web, Win32, iOS, Android y Mac:

- Outlook
- Teams
- Office\*
- SharePoint
- OneDrive

\* El desafío de notificación no se admite en Office para web.

Para los clientes que no admiten la evaluación continua de acceso, la duración del token de acceso a Microsoft 365 permanece como una hora de forma predeterminada.

## <a name="see-also"></a>Vea también

- [Evaluación continua del acceso](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [Documentación de acceso condicional](/azure/active-directory/conditional-access/overview)
- [Documentación de Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection)
