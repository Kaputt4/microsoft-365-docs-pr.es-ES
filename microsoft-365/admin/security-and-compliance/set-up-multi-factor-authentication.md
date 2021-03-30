---
title: Configuración de autenticación multifactor para usuarios
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.openlocfilehash: de5f8ffbc5c26015f6ff0eb2863b622273f96ca1
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408518"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor

Basándose en su conocimiento de la [autenticación multifactor (MFA) y su compatibilidad con Microsoft 365](multi-factor-authentication-microsoft-365.md), es hora de configurarla e implementarla en la organización.

> [!IMPORTANT]
> Si ha comprado la suscripción o la versión de evaluación después del 21 de octubre de 2019, y se le solicita la MFA al iniciar sesión, los [valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para la suscripción.

## <a name="before-you-begin"></a>Antes de empezar

- Para poder gestionar la MFA, debe ser administrador global. Para obtener más información, vea [Sobre los roles de administrador](../add-users/about-admin-roles.md).
- Si tiene activada la MFA heredada por usuario, [Desactive la MFA heredada por usuario](#turn-off-legacy-per-user-mfa).
- Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna para clientes de Office 2013](./enable-modern-authentication.md).
- Configuración avanzada: si tiene servicios de directorio de terceros con Servicios de federación de Active Directory (AD FS), configure el Servidor Azure MFA. Para más información, consulte [Escenarios avanzados con la autenticación multifactor de Microsoft Azure AD y soluciones VPN de terceros](/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

## <a name="turn-security-defaults-on-or-off"></a>Activar o desactivar las opciones predeterminadas de seguridad

En la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad adicional de inicio de sesión. Para obtener más información, vea [¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Si la suscripción es nueva, es posible que los valores predeterminados de seguridad ya estén activados automáticamente.

Puede habilitar o deshabilitar los valores predeterminados de seguridad en el panel **Propiedades** de Azure Active Directory (Azure AD) en Azure Portal.

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.
2. En el panel de navegación izquierdo, elija **Mostrar todo** y, en **Centros de administración**, elija **Azure Active Directory**.
3. En el **Centro de administración de Azure Active Directory** elija **Azure Active Directory** \> **Propiedades**.
4. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
5. Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad; a continuación, elija **Guardar**.

Si ha estado usando [directivas de acceso condicional de línea base](/azure/active-directory/conditional-access/concept-baseline-protection), se le pedirá que las desactive antes de pasar a usar los valores predeterminados de seguridad.

1. Vaya a la página [Directivas: Acceso condicional](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Elija cada directiva de línea base que esté **Activada** y establezca **Activar directiva** en **Desactivado**.
3. Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
5. Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad, después, elija **Guardar**.

## <a name="use-conditional-access-policies"></a>Usar directivas de acceso condicional

Si su organización tiene necesidades de seguridad de inicio de sesión más pormenorizadas, las directivas de acceso condicional le ofrecen más control. El acceso condicional le permite crear y definir directivas que reaccionan a eventos de inicio de sesión y solicitan acciones adicionales antes de otorgar acceso a un usuario a una aplicación o a un servicio.

> [!IMPORTANT]
> Desactive la MFA por usuario y los valores predeterminados de seguridad antes de habilitar las directivas de acceso condicional.

El acceso condicional está disponible para los clientes que han adquirido Azure AD Premium P1 o licencias que lo incluyen, como Microsoft 365 Empresa Premium y Microsoft 365 E3. Para obtener más información, vea [creación de una directiva de acceso condicional](/azure/active-directory/authentication/tutorial-enable-azure-mfa).

El acceso condicional basado en el riesgo está disponible con la licencia de Azure AD Premium P2 o las licencias que lo incluyen, como Microsoft 365 E5. Para más información, vea [Acceso condicional basado en el riesgo](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).

Para obtener más información sobre Azure AD P1 y P2, vea [Precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Activar la autenticación moderna para su organización

Para la mayoría de las suscripciones, la autenticación moderna se activa automáticamente, pero si compró la suscripción antes de agosto de 2017, es probable que deba activar la autenticación moderna para que características como la autenticación multifactor funcionen en clientes de Windows como Outlook.


1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, elija **Configuración** \> **Configuración de la organización**.
2. En la pestaña **Servicios**, elija **Autenticación moderna** y, en el panel **Autenticación moderna**, asegúrese de que **Habilitar autenticación moderna** esté seleccionado. Elija **Guardar cambios**.

### <a name="turn-off-legacy-per-user-mfa"></a>Desactivar la MFA heredada por usuario

Si ha activado previamente la MFA por usuario, debe desactivarla antes de habilitar los valores predeterminados de seguridad.

1. En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, elija **Usuarios** \> **Usuarios activos**.
1. En la página **Usuarios activos**, elija **Autenticación multifactor**.
1. En la página de autenticación multifactor, seleccione cada usuario y establezca el estado de la autenticación multifactor en **Deshabilitado**.

## <a name="next-steps"></a>Pasos siguientes

- [Cómo registrarse para el método de verificación adicional](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Qué es: la autenticación multifactor](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [Cómo iniciar sesión después del registro](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Cómo cambiar el método de verificación adicional](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a>Contenido relacionado

[Activar la autenticación multifactor (vídeo)](../../business-video/turn-on-mfa.md)

[Activar la autenticación multifactor para su teléfono (Vídeo)](../../business-video/set-up-mfa.md)