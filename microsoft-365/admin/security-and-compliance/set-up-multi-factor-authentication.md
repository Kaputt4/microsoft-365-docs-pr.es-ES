---
title: Configuración de autenticación multifactor para usuarios
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
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
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Obtenga información sobre cómo configurar la autenticación multifactor para su organización.
monikerRange: o365-worldwide
ms.openlocfilehash: 2b4ac2b5950d2641254742e03f054f3e4c886833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399127"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor
  
En función de sus conocimientos de [multi-factor Authentication (MFA) y su compatibilidad en Microsoft 365](multi-factor-authentication-microsoft-365.md), es el momento de configurarlo y distribuirlo en su organización.

Antes de comenzar, determine si estas condiciones especiales se aplican a usted y realice las acciones adecuadas:

- Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Si tiene servicios de directorio de terceros con los servicios de Federación de Active Directory (AD FS), configure el servidor de Azure MFA. Para obtener más información [, vea escenarios avanzados con la autenticación multifactor de Azure y soluciones de VPN de otros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) fabricantes.

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Paso 1: decidir el método de exigir a los usuarios que usen la MFA

Hay tres formas de requerir que los usuarios usen MFA para iniciar sesión. Consulte [compatibilidad con MFA en Microsoft 365](multi-factor-authentication-microsoft-365.md) para obtener información detallada.

- Valores predeterminados de seguridad (recomendado para pequeñas empresas)

  Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la MFA, los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.
  
  Todas las nuevas suscripciones de Microsoft 365 tendrán habilitada la seguridad predeterminada. Esto significa que todos los usuarios tendrán que configurar MFA e instalar la aplicación Microsoft Authenticator en su dispositivo móvil.

  Todos los usuarios deben usar la aplicación Microsoft Authenticator como método de comprobación adicional y la autenticación heredada está bloqueada. 

- Directivas de acceso condicional (recomendado para empresas)

  Los usuarios eligen el método de verificación adicional durante el registro de MFA.

- Cuenta por usuario (no recomendado)

  Los usuarios eligen el método de verificación adicional durante el registro de MFA.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Paso 2. Probar la MFA en los usuarios piloto

Si usa directivas de acceso condicional o MFA por usuario (no recomendado), seleccione usuarios piloto de la empresa u organización para probar el registro de MFA y los inicios de sesión. Por ejemplo:

- Para las directivas de acceso condicional, cree un grupo de usuarios piloto y una directiva que requiera MFA para los miembros del grupo y para todas las aplicaciones. A continuación, agregue las cuentas del usuario piloto al grupo.

- Para la MFA por usuario, habilite MFA para las cuentas de usuario de los usuarios piloto una vez.

Trabaje con los usuarios de la prueba piloto para resolver las preguntas y los problemas que se deben cumplir para preparar una implementación fluida en su organización.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Paso 3. Informar a su organización de que se va a provenir MFA

Use notificaciones de correo electrónico, pósters de vestíbulos, reuniones de equipo o entrenamiento formal para asegurarse de que sus empleados entienden:

- Por qué se necesita MFA para iniciar sesión
- [Cómo registrar el método de verificación adicional](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [Cómo iniciar sesión después del registro](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [Cómo cambiar el método de verificación adicional](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [Cómo tratar con situaciones como un nuevo teléfono inteligente](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

Y, lo que es más importante, asegúrese de que sus empleados entienden ***Cuándo se va a imponer el requisito de MFA*** para que no les sorprende.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Paso 4. Implementar el requisito de MFA en la organización o los usuarios

Basándose en el método de requisito de MFA elegido, implemente la autenticación MFA a los empleados más allá de los evaluadores piloto.

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel de **propiedades** de Azure Active Directory (Azure ad) en Azure portal.

1.  Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.
2.  Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
4.  Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.

Si ha estado usando [directivas de acceso condicional de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), le mostramos cómo pasar a usar los valores predeterminados de seguridad.

1.  Vaya a la [Página acceso condicional-directivas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Elija cada directiva de línea base que esté **activada** y establezca la **Directiva de habilitación** en **desactivada**.
2.  Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
5.  Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Crear, configurar y habilitar las directivas adecuadas que incluyen el grupo de usuarios que requieren MFA para iniciar sesión.

### <a name="per-user-mfa-not-recommended"></a>MFA por usuario (no recomendado)

Habilitar cuentas de usuario para MFA correspondiente a su implementación.

### <a name="supporting-your-employees"></a>Dar soporte a sus empleados

Como los empleados se registran y comienzan a iniciar sesión con MFA, asegúrese de que los especialistas de ti, el Departamento de ti o el Departamento de soporte puedan responder a preguntas y solucionar problemas rápidamente.

Consulte este artículo para obtener [información acerca de la solución de problemas de inicios de sesión de MFA](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2). 


