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
localization_priority: Priority
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
description: Obtenga información acerca de cómo configurar la autenticación multifactor para su organización.
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083543"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor
  
Basándose en su conocimiento de la [autenticación multifactor (MFA) y su compatibilidad con Microsoft 365](multi-factor-authentication-microsoft-365.md), es hora de configurarla e implementarla en la organización.

Antes de empezar, determine si estas condiciones especiales se aplican a usted y realice una de las acciones adecuadas:

- Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Si tiene servicios de directorio de terceros con Servicios de federación de Active Directory (ADFS), configure el servidor de MFA de Azure. Para más información, consulte [escenarios avanzados con la autenticación multifactor de Azure y soluciones VPN de terceros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario. Para más información, visite [Método y configuración de la verificación de dos factores](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Paso 1: Decidir el método para requerir que los usuarios usen MFA

> [!NOTE]
> Debe ser un administrador global para configurar o modificar la MFA. Hay tres formas de requerir que los usuarios usen MFA para iniciar sesión. Para más información, consulte [Compatibilidad con MFA en Microsoft 365](multi-factor-authentication-microsoft-365.md).

- Opciones predeterminadas de seguridad (recomendado para pequeñas empresas)

  Si ha comprado la suscripción o la versión de evaluación después del 21 de octubre de 2019, y se le ha solicitado de forma inesperada la MFA, los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para la suscripción.
  
  Todas las nuevas suscripciones de Microsoft 365 tendrán activados automáticamente los valores predeterminados de seguridad. Esto significa que todos los usuarios tendrán que configurar la MFA e instalar la aplicación Microsoft Authenticator en su dispositivo móvil.

  Todos los usuarios deben usar la aplicación Microsoft Authenticator como su método de verificación adicional y se bloquea la autenticación heredada. 

- Directivas de acceso condicional (recomendado para empresas)

  Los usuarios pueden seleccionar el método de comprobación adicional durante el registro de MFA.

- Cuenta por usuario (no recomendado)

  Los usuarios pueden seleccionar el método de comprobación adicional durante el registro de MFA.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Paso 2. Probar MFA en los usuarios piloto

Si usa directivas de acceso condicional o MFA por usuario (no recomendado), seleccione los usuarios piloto de su empresa u organización para probar el registro y los inicios de sesión de MFA. Por ejemplo:

- Para las directivas de acceso condicional, cree un grupo de usuarios piloto y una directiva que requiera MFA para los miembros del grupo y para todas las aplicaciones. Después, agregue las cuentas de los usuarios de la prueba piloto al grupo.

- En el caso de MFA por usuario, habilite MFA para las cuentas de usuario de los usuarios de la prueba piloto una a una.

Trabaje con los usuarios de la prueba piloto para responder a las preguntas y problemas a tener en cuenta para prepararse para la implementación.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Paso 3. Informar a su organización de que se va a cambiar a MFA

Use notificaciones de correo electrónico, pósteres en el vestíbulo, reuniones de equipo o entrenamiento formal para asegurarse de que sus empleados entienden:

- Por qué se requiere MFA para iniciar sesión
- [Cómo registrarse para el método de verificación adicional](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Cómo iniciar sesión después del registro](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Cómo cambiar el método de verificación adicional](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Cómo lidiar con situaciones como un nuevo smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

Y lo que es más importante, asegúrese de que los empleados entienden ***cuándo se va a imponer el requisito de MFA*** para que no se sorprendan.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Paso 4. Implementar el requisito de MFA en la organización o los usuarios

Basándose en el método de requisito de MFA elegido, distribuya la autenticación de MFA para los empleados más allá de los usuarios piloto.

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Puede habilitar o deshabilitar los valores predeterminados de seguridad en el panel **Propiedades** de Azure Active Directory (Azure AD) en Azure Portal.

1.  Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.
2.  Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
4.  Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad, después, elija **Guardar**.

Si ha estado usando [directivas de acceso condicional de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), aquí se muestra cómo pasar a usar los valores predeterminados de seguridad.

1.  Vaya a la página [Directivas: Acceso condicional](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Elija cada directiva de línea base que esté **Activada** y establezca **Activar directiva** en **Desactivado**.
2.  Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
5.  Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad, después, elija **Guardar**.

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Cree, configure y habilite las directivas adecuadas que incluyan el grupo de usuarios que necesiten MFA para iniciar sesión.

### <a name="per-user-mfa-not-recommended"></a>MFA por usuario (no recomendado)

Habilite las cuentas de usuario para el MFA en base al lanzamiento.

### <a name="supporting-your-employees"></a>Soporte para los empleados

Cuando los empleados se registren y empiecen a iniciar sesión con MFA, asegúrese de que los especialistas de TI, el departamento de TI o el departamento de soporte puedan responder a las preguntas y solucionar los problemas rápidamente.

Consulte este artículo para obtener [información acerca de cómo solucionar los problemas de inicio de sesión de MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


