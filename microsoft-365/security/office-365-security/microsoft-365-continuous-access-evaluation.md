---
title: 'Evaluación de acceso continua para Microsoft 365: Microsoft 365 para empresas'
description: Describe cómo la evaluación de acceso condicional para Microsoft 365 y Azure AD termina proactivamente las sesiones de usuario activas y aplica los cambios en la directiva de inquilino casi en tiempo real.
ms.author: dansimp
author: dansimp
manager: dansimp
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: e265fd09fa7442b24868ad7f001701ef567e32bd
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681576"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>Evaluación de acceso continua para Microsoft 365

Los servicios en la nube modernos que usan OAuth 2.0 para la autenticación tradicionalmente dependen de la expiración del token de acceso para revocar el acceso de una cuenta de usuario. En la práctica, esto significa incluso si un administrador revoca el acceso de una cuenta de usuario, el usuario seguirá teniendo acceso hasta que expire el token de acceso, que para Microsoft 365 de forma predeterminada, solía estar hasta una hora después de que se produjese el evento de revocación inicial.

La evaluación de acceso condicional para Microsoft 365 y Azure Active Directory (Azure AD) termina proactivamente las sesiones de usuario activas y aplica los cambios de directiva de inquilino en tiempo casi real en lugar de depender de la expiración del token de acceso. Azure AD notifica a los servicios de Microsoft 365 habilitados para evaluación de acceso continuo (como SharePoint, Teams y Exchange) cuando la cuenta de usuario o el espacio empresarial han cambiado de una manera que requiere la reevaluación del estado de autenticación de la cuenta de usuario.

Cuando un cliente habilitado para evaluación de acceso continuo como Outlook intenta obtener acceso a Exchange con un token de acceso existente, el servicio rechaza el token, lo que solicita una nueva autenticación Azure AD acceso. El resultado es la aplicación casi en tiempo real de los cambios de la cuenta de usuario y la directiva.

Estas son algunas ventajas adicionales:

- Para un insider malintencionado que copia y exporta un token de acceso válido fuera de la organización, la evaluación continua de acceso impide el uso de este token a través de una directiva de ubicación de direcciones IP Azure AD de direcciones IP. Con la evaluación continua del acceso, Azure AD sincroniza las directivas a los servicios Microsoft 365 compatibles, de modo que cuando un token de acceso intenta obtener acceso al servicio desde fuera del intervalo de direcciones IP de la directiva, el servicio rechaza el token.

- La evaluación continua del acceso mejora la resistencia al requerir menos actualizaciones de tokens. Dado que los servicios de soporte técnico reciben notificaciones proactivas sobre cómo requerir la reauthentication, Azure AD emitir tokens de larga duración, por ejemplo, más de una hora. Con tokens de larga duración, los clientes no tienen que solicitar una actualización de tokens de Azure AD tan a menudo, por lo que la experiencia del usuario es más resistente.

Estos son algunos ejemplos de situaciones en las que la evaluación continua del acceso mejora la seguridad del control de acceso de usuario:

- La contraseña de una cuenta de usuario se ha visto comprometida, por lo que un administrador invalida todas las sesiones existentes y restablece su contraseña desde el Centro de administración de Microsoft 365. En tiempo casi real, todas las sesiones de usuario existentes con Microsoft 365 servicios se invalidan.

- Un usuario que trabaja en un documento en Word lleva su tableta a una cafetería pública que no está en un intervalo de direcciones IP definido por el administrador y aprobado. En la cafetería, el acceso del usuario al documento se bloquea inmediatamente.

Por Microsoft 365, la evaluación continua de acceso es compatible actualmente con:

- Exchange, SharePoint y Teams servicios.
- Outlook, Teams, Office y OneDrive en un explorador web y para los clientes win32, iOS, Android y Mac.

Microsoft está trabajando en servicios Microsoft 365 y clientes adicionales para admitir la evaluación continua del acceso.

La evaluación continua de acceso se incluirá en todas las versiones de Office 365 y Microsoft 365. La configuración de directivas de acceso condicional requiere Azure AD Premium P1, que se incluye en todas Microsoft 365 versiones.

> [!NOTE]
> Vea [este artículo para](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) obtener información sobre las limitaciones de la evaluación continua del acceso.

## <a name="scenarios-supported-by-microsoft-365"></a>Escenarios admitidos por Microsoft 365

La evaluación continua de acceso admite dos tipos de eventos:

- Los eventos críticos son aquellos en los que un usuario debe perder acceso.
- La evaluación de directivas de acceso condicional se produce cuando un usuario debe perder el acceso a un recurso en función de una directiva definida por el administrador.

Entre los eventos críticos se incluyen:

- La cuenta de usuario está deshabilitada
- Se cambia la contraseña
- Las sesiones de usuario se revocan
- La autenticación multifactor está habilitada para el usuario
- El riesgo de cuenta aumentó en función de la evaluación del acceso desde [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection)

La evaluación de directivas de acceso condicional se produce cuando la cuenta de usuario ya no se conecta desde una red de confianza.

Los siguientes servicios Microsoft 365 actualmente admiten la evaluación continua de acceso escuchando eventos de Azure AD.

|Tipo de aplicación|Exchange|SharePoint|Teams|
|---|---|---|---|
|**Eventos críticos:**||||
|Revocación de usuarios|Compatible|Compatible|Compatible|
|Riesgo de usuario|Compatible|No se admite|No se admite|
|**Evaluación de directivas de acceso condicional:**||||
|Directiva de ubicación de direcciones IP|Compatible|Compatible\*|Compatible|

\*SharePoint Office de explorador web admite la aplicación instantánea de directivas IP habilitando el modo estricto. Sin el modo estricto, la duración del token de acceso es de una hora.

Para obtener más información acerca de cómo configurar una directiva de acceso condicional, vea [este artículo](/azure/active-directory/conditional-access/overview).

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Microsoft 365 clientes que admiten la evaluación continua de acceso

Los clientes habilitados para evaluación de acceso continuo para Microsoft 365 admiten un desafío de notificación, que es un redireccionamiento de una sesión de usuario a Azure AD para la reauthentication, cuando un token de usuario almacenado en caché es rechazado por un servicio de Microsoft 365 de evaluación de acceso continuo.

Los siguientes clientes admiten la evaluación continua de acceso en web, Win32, iOS, Android y Mac:

- Outlook
- Teams
- Oficina\*
- SharePoint
- OneDrive

\*El desafío de notificación no se admite Office para web.

Para los clientes que no admiten la evaluación continua del acceso, la duración del token de acceso Microsoft 365 permanece como una hora de forma predeterminada.

## <a name="see-also"></a>Consulte también

- [Evaluación continua del acceso](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [Documentación de acceso condicional](/azure/active-directory/conditional-access/overview)
- [Azure AD de protección de identidades](/azure/active-directory/identity-protection/overview-identity-protection)
