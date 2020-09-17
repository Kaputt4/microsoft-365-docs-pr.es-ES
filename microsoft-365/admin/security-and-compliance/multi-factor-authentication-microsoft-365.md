---
title: Autenticación multifactor para Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información acerca de la autenticación multifactor en Microsoft 365.
ms.openlocfilehash: bca84e949e696b483b567bf5f72233840023abca
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948717"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Autenticación multifactor para Microsoft 365

Las contraseñas son el método más común para autenticar un inicio de sesión en un equipo o servicio en línea, pero también son los más vulnerables. Los usuarios pueden elegir contraseñas sencillas y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios.

Para proporcionar un nivel de seguridad adicional para los inicios de sesión, debe usar la autenticación multifactor (MFA), que usa una contraseña, que debe ser segura, y un método de verificación adicional basado en:

- Algo que tiene con usted que no se duplica fácilmente, como un smartphone.
- Algo que tiene de forma única y biológica, como sus huellas dactilares, rostro u otro atributo de biométrica.

El método de verificación adicional no se emplea hasta que se haya comprobado la contraseña del usuario. Con MFA, incluso si una contraseña de usuario segura se ve comprometida, el atacante no tiene el teléfono inteligente ni la huella digital para completar el inicio de sesión.

## <a name="mfa-support-in-microsoft-365"></a>Compatibilidad con MFA en Microsoft 365
De forma predeterminada, tanto Microsoft 365 como Office 365 admiten MFA para las cuentas de usuario mediante:

- Mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.
- Una llamada de teléfono.
- La aplicación Microsoft Authenticator Smart Phone.

En ambos casos, el inicio de sesión de MFA usa el método "algo que tiene con usted que no se duplica fácilmente" para la comprobación adicional.
Hay varias formas en las que puede habilitar MFA para Microsoft 365 y Office 365:

- Con los valores predeterminados de seguridad
- Con directivas de acceso condicional
- Para cada cuenta de usuario individual (no recomendado)

Estas formas se basan en el plan 365 de Microsoft.
    
|Plan  |Recomendación  | Tipo de cliente |
|---------|---------|----------|
| Todos los planes de 365 de Microsoft | Use los valores predeterminados de seguridad, que requieren MFA para todas las cuentas de usuario. <br> También puede requerir MFA en cada cuenta de usuario, pero no se recomienda. | Empresa pequeña |
| Microsoft 365 Empresa Premium <br><br> Microsoft 365 E3 <br><br> Licencias de Azure Active Directory (Azure AD) Premium P1 | Use las directivas de acceso condicional para requerir MFA para las cuentas de usuario en función de la pertenencia a grupos, las aplicaciones y otros criterios. | Pequeña empresa a empresarial |
| Microsoft 365 E5 <br><br> Licencias de Azure AD Premium P2 | Use Azure AD Identity Protection para requerir MFA en función de los criterios de inicio de sesión en el riesgo. |  Enterprise |
||||

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019. Estas suscripciones tienen valores predeterminados de seguridad activados, lo que:

- Requiere que todos los usuarios usen MFA con la aplicación Microsoft Authenticator.
- Bloquea la autenticación heredada.

Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad. Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.

Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada. Puede deshabilitar los valores predeterminados de seguridad en favor de MFA con directivas de acceso condicional.

Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel **propiedades** de Azure ad en Azure portal.

![Imagen de la página de propiedades del directorio.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Puede usar los valores predeterminados de seguridad con cualquier plan de 365 de Microsoft.

Para más información, vea esta [información general de los valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). 

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y permiten los inicios de sesión. Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:

- Si el nombre de la cuenta de usuario es miembro de un grupo de usuarios a los que se han asignado los roles de administrador de Exchange, de usuarios, de contraseñas, de seguridad, de SharePoint o global, requerir MFA antes de permitir el acceso.

Esta directiva le permite exigir MFA en función de la pertenencia a grupos, en lugar de intentar configurar cuentas de usuario individuales para MFA cuando se asignan o se quitan estos roles de administrador.

También puede usar directivas de acceso condicional para capacidades más avanzadas, como requerir MFA para aplicaciones específicas o que el inicio de sesión se realice desde un dispositivo compatible, como el portátil que ejecuta Windows 10.

Las directivas de acceso condicional se configuran desde el panel **seguridad** de Azure ad en Azure portal.

![Picure de la opción de menú para el acceso condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Puede usar directivas de acceso condicional con:

- Microsoft 365 Empresa Premium
- Microsoft 365 E3 y E5
- Licencias de Azure AD Premium P1 y Azure AD Premium P2 

Para las pequeñas empresas con Microsoft 365 empresa Premium, puede usar fácilmente las directivas de acceso condicional con los pasos siguientes:

1. Cree un grupo que contenga las cuentas de usuario que requieren MFA.
2. Habilite la directiva **solicitar MFA para administradores globales** .
3. Cree una directiva de acceso condicional basada en grupos con estos valores:
    - Asignaciones > Users and Groups: el nombre del grupo del paso 1 anterior.
    - Tareas > aplicaciones o acciones en la nube: todas las aplicaciones en la nube.
    - Los controles de acceso > conceder > conceder acceso > requieren la autenticación multifactor.
4. Habilite la Directiva.
5. Agregue una cuenta de usuario al grupo creado en el paso 1 y pruebe.
6. Para requerir MFA para las cuentas de usuario adicionales, agréguelos al grupo creado en el paso 1.

Esta directiva de acceso condicional permite aplicar el requisito de MFA a los usuarios a su propio ritmo.

Las empresas deben usar [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las siguientes directivas:

- [Requerir MFA para los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Requerir MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Bloquear la autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Para más información, vea esta [información general sobre el acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Con Azure AD Identity Protection, puede crear una directiva de acceso condicional adicional que [requiera MFA cuando el riesgo de inicio de sesión sea medio o alto](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).

Puede usar la protección de identidad de Azure AD y las directivas de acceso condicional basadas en riesgos con:

- Microsoft 365 E5
- Licencias de Azure AD Premium P2

Para más información, vea esta [información general sobre la protección de identidad de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-person-mfa-not-recommended"></a>MFA heredado por persona (no recomendado)

Debe usar los valores predeterminados de seguridad o directivas de acceso condicional para requerir MFA para los inicios de sesión de la cuenta de usuario. Sin embargo, si no se puede usar cualquiera de estos, Microsoft recomienda MFA para las cuentas de usuario que tienen roles de administrador, especialmente el rol de administrador global, para cualquier suscripción de tamaño. 

Habilite MFA para las cuentas de usuario individuales desde el panel de **usuario activo** del centro de administración de Microsoft 365.

![Imagen de la opción de autenticación multifactor en la página usuarios activos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Una vez habilitada, la próxima vez que el usuario inicie sesión, se le pedirá que se registre para MFA y que elija y pruebe el método de comprobación adicional.

### <a name="using-these-methods-together"></a>Usar estos métodos conjuntamente

Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad, las directivas de acceso condicional y la configuración de cuenta por usuario.

|| Habilitado | Deshabilitado | Método de autenticación secundario |
|:-------|:-----|:-------|:-------|
| **Valores predeterminados de seguridad** | No se pueden usar directivas de acceso condicional |   Se pueden usar directivas de acceso condicional | Aplicación Microsoft Authenticator |
| **Directivas de acceso condicional** |Si hay alguna habilitada, no puede habilitar los valores predeterminados de seguridad | Si se deshabilitan todos, puede habilitar los valores predeterminados de seguridad | Especificado por el usuario durante el registro de MFA |
| **MFA heredado por persona (no recomendado)** | Invalida los valores predeterminados de seguridad y las directivas de acceso condicional que requieren MFA en cada inicio de sesión | Invalidados por los valores predeterminados de seguridad y directivas de acceso condicional | Especificado por el usuario durante el registro de MFA|
||||

Si se habilitan los valores predeterminados de seguridad, todos los usuarios nuevos se solicitarán para el registro de MFA y el uso de la aplicación Microsoft Authenticator en el siguiente inicio de sesión.

## <a name="ways-to-manage-mfa-settings"></a>Formas de administrar la configuración de MFA

Hay dos formas de administrar la configuración de MFA.

En Azure portal, puede:

- Habilitar y deshabilitar los valores predeterminados de seguridad
- Configurar directivas de acceso condicional

En el centro de administración de Microsoft 365, puede configurar las opciones de configuración de MFA por usuario y servicio.

## <a name="your-next-step"></a>El siguiente paso

[Configurar MFA para Microsoft 365](set-up-multi-factor-authentication.md)
