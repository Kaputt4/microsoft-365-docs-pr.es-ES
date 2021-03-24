---
title: Autenticación multifactor para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre la autenticación multifactor en Microsoft 365.
ms.openlocfilehash: 080251efa7d7d3bda6ad89e95960e43dd38d076d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050671"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Autenticación multifactor para Microsoft 365

Las contraseñas son el método más común para autenticar un inicio de sesión en un equipo o servicio en línea, pero también son las más vulnerables. Los usuarios pueden elegir contraseñas fáciles y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios.

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, debe usar la autenticación multifactor (MFA), que usa una contraseña, que debe ser segura, y un método de comprobación adicional basado en:

- Algo que tiene con usted que no se duplica fácilmente, como un teléfono inteligente.
- Algo que tiene de forma única y biológica, como sus huellas digitales, rostro u otro atributo biométrico.

El método de comprobación adicional no se emplea hasta después de comprobar la contraseña del usuario. Con MFA, incluso si se pone en peligro una contraseña de usuario segura, el atacante no tiene el teléfono inteligente ni la huella digital para completar el inicio de sesión.

## <a name="mfa-support-in-microsoft-365"></a>Compatibilidad con MFA en Microsoft 365

De forma predeterminada, Microsoft 365 y Office 365 admiten MFA para cuentas de usuario que usan:

- Un mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.
- Una llamada telefónica.
- La aplicación de teléfono inteligente Microsoft Authenticator.

En ambos casos, el inicio de sesión de MFA usa el método "algo que tienes contigo que no se duplica fácilmente" para la comprobación adicional. Existen varias formas de habilitar MFA para Microsoft 365 y Office 365:

- Con valores predeterminados de seguridad
- Con directivas de acceso condicional
- Para cada cuenta de usuario individual (no recomendada)

Estas formas se basan en el plan de Microsoft 365.

|Plan|Recomendación|Tipo de cliente|
|---|---|---|
|Todos los planes de Microsoft 365|Use valores predeterminados de seguridad, que requieren MFA para todas las cuentas de usuario. <p> También puede configurar MFA por usuario en cuentas de usuario individuales, pero esto no se recomienda.|Empresa pequeña|
|Microsoft 365 Empresa Premium <p> Microsoft 365 E3 <p> Licencias de Azure Active Directory (Azure AD) Premium P1|Use directivas de acceso condicional para requerir MFA para cuentas de usuario basadas en la pertenencia a grupos, aplicaciones u otros criterios.|Pequeña empresa a empresa|
|Microsoft 365 E5 <p> Licencias de Azure AD Premium P2|Use Azure AD Identity Protection para requerir MFA en función de los criterios de riesgo de inicio de sesión.|Empresas|
||||

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019. Estas suscripciones tienen activados los valores predeterminados de seguridad, que:

- Requiere que todos los usuarios usen MFA con la aplicación Microsoft Authenticator.
- Bloquea la autenticación heredada.

Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad. Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.

Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada. Puede deshabilitar los valores predeterminados de seguridad a favor de MFA con directivas de acceso condicional.

Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel **Propiedades** de Azure AD en Azure Portal.

![Imagen de la página Propiedades del directorio.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Puede usar valores predeterminados de seguridad con cualquier plan de Microsoft 365.

Para más información, vea esta [información general de los valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y permiten los inicios de sesión. Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:

- Si el nombre de la cuenta de usuario es miembro de un grupo de usuarios a los que se han asignado los roles de administrador de Exchange, de usuarios, de contraseñas, de seguridad, de SharePoint o global, requerir MFA antes de permitir el acceso.

Esta directiva le permite exigir MFA en función de la pertenencia a grupos, en lugar de intentar configurar cuentas de usuario individuales para MFA cuando se asignan o se quitan estos roles de administrador.

También puedes usar directivas de acceso condicional para funcionalidades más avanzadas, como requerir MFA para aplicaciones específicas o que el inicio de sesión se realiza desde un dispositivo compatible, como el portátil que ejecuta Windows 10.

Las directivas de acceso condicional se configuran **desde** el panel Seguridad de Azure AD en Azure Portal.

![Imagen de la opción de menú para acceso condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Puede usar directivas de acceso condicional con:

- Microsoft 365 Empresa Premium
- Microsoft 365 E3 y E5
- Licencias de Azure AD Premium P1 y Azure AD Premium P2

Para las pequeñas empresas con Microsoft 365 Empresa Premium, puede usar fácilmente directivas de acceso condicional con los siguientes pasos:

1. Cree un grupo para contener las cuentas de usuario que requieren MFA.
2. Habilite la **directiva Requerir MFA para administradores** globales.
3. Cree una directiva de acceso condicional basada en grupos con esta configuración:
    - Asignaciones > usuarios y grupos: el nombre del grupo del paso 1 anterior.
    - Asignaciones > o acciones en la nube: todas las aplicaciones en la nube.
    - Controles de > conceder > conceder acceso > Requerir autenticación multifactor.
4. Habilite la directiva.
5. Agregue una cuenta de usuario al grupo creado en el paso 1 anterior y pruebe.
6. Para requerir MFA para cuentas de usuario adicionales, agrégrelas al grupo creado en el paso 1.

Esta directiva de acceso condicional le permite implantar el requisito de MFA a los usuarios a su propio ritmo.

Las empresas deben usar [directivas comunes de acceso condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las siguientes directivas:

- [Requerir MFA para los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Bloquear la autenticación heredada](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Para más información, vea esta [información general sobre el acceso condicional](/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Con Azure AD Identity Protection, puede crear una directiva de acceso condicional adicional para requerir MFA cuando el riesgo de inicio de sesión [es medio o alto.](../../security/defender-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)

Puede usar Azure AD Identity Protection y directivas de acceso condicional basadas en riesgos con:

- Microsoft 365 E5
- Licencias de Azure AD Premium P2

Para más información, vea esta [información general sobre la protección de identidad de Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>MFA heredada por usuario (no recomendada)

Debe usar los valores predeterminados de seguridad o las directivas de acceso condicional para requerir MFA para los inicios de sesión de la cuenta de usuario. Sin embargo, si cualquiera de estos no se puede usar, Microsoft recomienda encarecidamente MFA para cuentas de usuario que tienen roles de administrador, especialmente el rol de administrador global, para cualquier suscripción de tamaño.

Puede habilitar MFA para cuentas de usuario individuales desde el **panel usuario** activo del Centro de administración de Microsoft 365.

![Imagen de la opción de autenticación multifactor en la página Usuarios activos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Después de habilitarse, la próxima vez que el usuario inicia sesión, se le pedirá que se registre en MFA y que elija y pruebe el método de comprobación adicional.

### <a name="using-these-methods-together"></a>Usar estos métodos conjuntamente

Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad, las directivas de acceso condicional y la configuración de cuenta por usuario.

||Habilitado|Deshabilitado|Método de autenticación secundario|
|---|---|---|---|
|**Valores predeterminados de seguridad**|No se pueden usar directivas de acceso condicional|Se pueden usar directivas de acceso condicional|Aplicación Microsoft Authenticator|
|**Directivas de acceso condicional**|Si hay alguno habilitado, no puede habilitar los valores predeterminados de seguridad|Si se deshabilitan todos, puede habilitar los valores predeterminados de seguridad|Especificado por el usuario durante el registro de MFA|
|**MFA heredada por usuario (no recomendada)**|Invalida los valores predeterminados de seguridad y las directivas de acceso condicional que requieren MFA en cada inicio de sesión|Invalidadas por valores predeterminados de seguridad y directivas de acceso condicional|Especificado por el usuario durante el registro de MFA|
||||

Si los valores predeterminados de seguridad están habilitados, se pedirá a todos los usuarios nuevos el registro de MFA y el uso de la aplicación Microsoft Authenticator en su siguiente inicio de sesión.

## <a name="ways-to-manage-mfa-settings"></a>Formas de administrar la configuración de MFA

Hay dos formas de administrar la configuración de MFA.

En Azure Portal, puede:

- Habilitar y deshabilitar valores predeterminados de seguridad
- Configurar directivas de acceso condicional

En el Centro de administración de Microsoft 365, puede configurar las opciones de MFA por usuario y servicio.

## <a name="your-next-step"></a>El siguiente paso

[Configurar MFA para Microsoft 365](set-up-multi-factor-authentication.md)

## <a name="related-topics"></a>Temas relacionados

[Vídeo: Activar la autenticación multifactor](../../business-video/turn-on-mfa.md)

[Vídeo: Activar la autenticación multifactor para su teléfono](../../business-video/set-up-mfa.md)