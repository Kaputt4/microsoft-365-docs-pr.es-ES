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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: La autenticación multifactor (MFA) usa una contraseña, que debe ser segura, y un método de verificación adicional.
ms.openlocfilehash: e7d32776edb0f8fa6eaa4019f394870a6346e1d2
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637657"
---
# <a name="multifactor-authentication-for-microsoft-365"></a>Autenticación multifactor para Microsoft 365

Las contraseñas son el método más común para autenticar un inicio de sesión en un equipo o servicio en línea, pero también son los más vulnerables. Las personas pueden elegir contraseñas fáciles y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios.

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, debe usar la autenticación multifactor (MFA), que usa una contraseña, que debe ser segura, y un método de verificación adicional basado en:

- Algo que tiene con usted que no se duplica fácilmente, como un teléfono inteligente.
- Algo que tiene de forma única y biológica, como las huellas digitales, la cara u otro atributo biométrico.

El método de comprobación adicional no se emplea hasta después de comprobar la contraseña del usuario. Con MFA, incluso si una contraseña de usuario segura está en peligro, el atacante no tiene su teléfono inteligente ni su huella digital para completar el inicio de sesión.

## <a name="mfa-support-in-microsoft-365"></a>Compatibilidad con MFA en Microsoft 365

De forma predeterminada, Microsoft 365 y Office 365 admiten MFA para cuentas de usuario mediante:

- Mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.
- Una llamada telefónica.
- La aplicación de teléfono inteligente Microsoft Authenticator.

En ambos casos, el inicio de sesión de MFA usa el método "algo que tiene con usted que no se duplica fácilmente" para la comprobación adicional. Hay varias maneras de habilitar MFA para Microsoft 365 y Office 365:

- Con valores predeterminados de seguridad
- Con directivas de acceso condicional
- Para cada cuenta de usuario individual (no se recomienda)

Estas formas se basan en el plan de Microsoft 365.

|Plan|Recomendación|Tipo de cliente|
|---|---|---|
|Todos los planes de Microsoft 365|Use valores predeterminados de seguridad, que requieren MFA para todas las cuentas de usuario. <p> También puede configurar MFA por usuario en cuentas de usuario individuales, pero no se recomienda.|Empresa pequeña|
|Microsoft 365 Empresa Premium <p> Microsoft 365 E3 <p> licencias de Azure Active Directory (Azure AD) Premium P1|Use directivas de acceso condicional para requerir MFA para las cuentas de usuario en función de la pertenencia a grupos, las aplicaciones u otros criterios.|Pequeña empresa a empresa|
|Microsoft 365 E5 <p> licencias de Azure AD Premium P2|Use Azure AD Identity Protection para requerir MFA en función de los criterios de riesgo de inicio de sesión.|Empresa|
||||

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019. Estas suscripciones tienen activados los valores predeterminados de seguridad, que:

- Requiere que todos los usuarios usen MFA con la aplicación Microsoft Authenticator.
- Bloquea la autenticación heredada.

Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad. Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.

Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada. Puede deshabilitar los valores predeterminados de seguridad en favor de MFA con directivas de acceso condicional.

Habilite o deshabilite los valores predeterminados de seguridad en el panel **Propiedades** de Azure AD en el Azure Portal.

![Imagen de la página de propiedades del directorio.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Puede usar los valores predeterminados de seguridad con cualquier plan de Microsoft 365.

Para más información, vea esta [información general de los valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y permiten los inicios de sesión. Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:

- Si el nombre de la cuenta de usuario es miembro de un grupo de usuarios a los que se han asignado los roles de administrador de Exchange, de usuarios, de contraseñas, de seguridad, de SharePoint o global, requerir MFA antes de permitir el acceso.

Esta directiva permite requerir MFA en función de la pertenencia a grupos, en lugar de intentar configurar cuentas de usuario individuales para MFA cuando se asignan o no se asignan a estos roles de administrador.

También puede usar directivas de acceso condicional para funcionalidades más avanzadas, como requerir MFA para aplicaciones específicas o que el inicio de sesión se realice desde un dispositivo compatible, como el equipo portátil que ejecuta Windows 10.

Las directivas de acceso condicional se configuran en el panel **Seguridad** de Azure AD en el Azure Portal.

![Imagen de la opción de menú para el acceso condicional.](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Puede usar directivas de acceso condicional con:

- Microsoft 365 Empresa Premium
- Microsoft 365 E3 y E5
- licencias de Azure AD Premium P1 y Azure AD Premium P2

Para pequeñas empresas con Microsoft 365 Empresa Premium, puede usar fácilmente directivas de acceso condicional con los pasos siguientes:

1. Cree un grupo para que contenga las cuentas de usuario que requieren MFA.
2. Habilite la directiva **Requerir MFA para administradores globales** .
3. Cree una directiva de acceso condicional basada en grupos con esta configuración:
    - Asignaciones > Usuarios y grupos: el nombre del grupo del paso 1 anterior.
    - Asignaciones > aplicaciones o acciones en la nube: todas las aplicaciones en la nube.
    - Controles de acceso > Conceder > Conceder acceso > Requerir autenticación multifactor.
4. Habilite la directiva.
5. Agregue una cuenta de usuario al grupo creado en el paso 1 anterior y pruebe.
6. Para requerir MFA para cuentas de usuario adicionales, agréguelas al grupo creado en el paso 1.

Esta directiva de acceso condicional le permite implementar el requisito de MFA para los usuarios a su propio ritmo.

Las empresas deben usar [directivas de acceso condicional común](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las siguientes directivas:

- [Requerir MFA para los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Bloquear la autenticación heredada](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Para más información, vea esta [información general sobre el acceso condicional](/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Con Azure AD Identity Protection, puede crear una directiva de acceso condicional adicional para [requerir MFA cuando el riesgo de inicio de sesión es medio o alto](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).

Puede usar Azure AD Identity Protection y directivas de acceso condicional basadas en riesgos con:

- Microsoft 365 E5
- licencias de Azure AD Premium P2

Para más información, vea esta [información general sobre la protección de identidad de Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>MFA heredado por usuario (no recomendado)

Debe usar valores predeterminados de seguridad o directivas de acceso condicional para requerir MFA para los inicios de sesión de la cuenta de usuario. Sin embargo, si no se puede usar cualquiera de ellas, Microsoft recomienda encarecidamente MFA para las cuentas de usuario que tienen roles de administrador, especialmente el rol de administrador global, para cualquier suscripción de tamaño.

Puede habilitar MFA para cuentas de usuario individuales en el panel <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos**</a> de la Centro de administración de Microsoft 365.

![Imagen de la opción Multi Factor Authentication en la página Usuarios activos.](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Después de habilitarse, la próxima vez que el usuario inicie sesión, se le pedirá que se registre en MFA y que elija y pruebe el método de comprobación adicional.

### <a name="using-these-methods-together"></a>Usar estos métodos conjuntamente

Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad, las directivas de acceso condicional y la configuración de cuenta por usuario.

|*Elemento*|Habilitado|Deshabilitado|Método de autenticación secundario|
|---|---|---|---|
|**Valores predeterminados de seguridad**|No se pueden usar directivas de acceso condicional|Se pueden usar directivas de acceso condicional|Aplicación Microsoft Authenticator|
|**Directivas de acceso condicional**|Si hay alguno habilitado, no puede habilitar los valores predeterminados de seguridad.|Si se deshabilitan todos, puede habilitar los valores predeterminados de seguridad|Especificado por el usuario durante el registro de MFA|
|**MFA heredado por usuario (no recomendado)**|Invalida los valores predeterminados de seguridad y las directivas de acceso condicional que requieren MFA en cada inicio de sesión|Invalidado por valores predeterminados de seguridad y directivas de acceso condicional|Especificado por el usuario durante el registro de MFA|
||||

Si se habilitan los valores predeterminados de seguridad, se pedirá a todos los nuevos usuarios el registro de MFA y el uso de la aplicación Microsoft Authenticator en su siguiente inicio de sesión.

## <a name="ways-to-manage-mfa-settings"></a>Formas de administrar la configuración de MFA

Hay dos maneras de administrar la configuración de MFA.

En el Azure Portal, puede:

- Habilitación y deshabilitación de valores predeterminados de seguridad
- Configuración de directivas de acceso condicional

En el Centro de administración de Microsoft 365, puede configurar las <a href="https://go.microsoft.com/fwlink/p/?linkid=2169174" target="_blank">opciones de MFA</a> por usuario y servicio.

## <a name="next-steps"></a>Siguientes pasos

[Configuración de MFA para Microsoft 365](set-up-multi-factor-authentication.md)

## <a name="related-content"></a>Contenido relacionado

[Active la autenticación multifactor](set-up-multi-factor-authentication.md) (vídeo)\
[Active la autenticación multifactor para su teléfono (Vídeo)](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)