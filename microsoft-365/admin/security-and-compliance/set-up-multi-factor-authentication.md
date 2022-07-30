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
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
- adminvideo
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Obtenga información acerca de cómo configurar la autenticación multifactor para su organización.
monikerRange: o365-worldwide
ms.openlocfilehash: 32e429f2d24c8754603c3ab32b060a9b7656df4e
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085517"
---
# <a name="set-up-multifactor-authentication-for-microsoft-365"></a>Configurar la autenticación multifactor para Microsoft 365

Consulte [Microsoft 365 ayuda de pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

La autenticación multifactor significa que usted y sus empleados deben proporcionar más de una manera de iniciar sesión en Microsoft 365 es una de las formas más fáciles de proteger su negocio. En función de su comprensión de [autenticación multifactor (MFA) y su compatibilidad con Microsoft 365](multi-factor-authentication-microsoft-365.md), es el momento de configurarla e implementarla en su organización. 

> [!IMPORTANT]
> Si ha comprado la suscripción o la versión de evaluación después del 21 de octubre de 2019, y se le solicita la MFA al iniciar sesión, los [valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para la suscripción.

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="watch-turn-on-multifactor-authentication"></a>Vea: Activar la autenticación multifactor

Vea este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2197909).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2MuO3?autoplay=false]

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://admin.microsoft.com/ " target="_blank">https://admin.microsoft.com</a>.
1. Seleccione **Mostrar todos** y, a continuación, elija el **Centro de administración de Azure Active Directory**.
1. Seleccione **Azure Active Directory**, **Propiedades**, **Administrar valores predeterminados de seguridad**.
1. En **Habilitar valores predeterminados de seguridad**, seleccione **Sí** y, a continuación, **Guardar**.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser administrador global para administrar MFA. Para obtener más información, consulte [Acerca de los roles de administrador](../add-users/about-admin-roles.md).
- Si tiene activada la MFA heredada por usuario, [Desactive la MFA heredada por usuario](#turn-off-legacy-per-user-mfa).
- Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna para clientes de Office 2013](./enable-modern-authentication.md).
- Configuración avanzada: si tiene servicios de directorio de terceros con Servicios de federación de Active Directory (AD FS), configure el Servidor Azure MFA. Consulte [escenarios avanzados con Azure AD Multifactor Authentication y soluciones VPN de terceros](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obtener más información.

### <a name="turn-off-legacy-per-user-mfa"></a>Desactivar la MFA heredada por usuario

Si ha activado previamente la MFA por usuario, debe desactivarla antes de habilitar los valores predeterminados de seguridad.

1. En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, elija **Usuarios** \> **Usuarios activos**.
1. En la página **Usuarios activos**, elija **Autenticación multifactor**.
1. En la página de autenticación multifactor, seleccione cada usuario y establezca el estado de la autenticación multifactor en **Deshabilitado**.

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

El acceso condicional está disponible para los clientes que hayan adquirido Azure AD Premium P1 o licencias que lo incluyan, como Microsoft 365 Empresa Premium y Microsoft 365 E3. Para obtener más información, vea [Crear una directiva de acceso condicional](/azure/active-directory/authentication/tutorial-enable-azure-mfa).

El acceso condicional basado en riesgos está disponible a través de Azure AD Premium licencia P2 o de licencias que lo incluyen, como Microsoft 365 E5. Para obtener más información, consulte [Acceso condicional basado en riesgos](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).

Para obtener más información sobre Azure AD P1 y P2, vea [Precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Activar la autenticación moderna para su organización

Para la mayoría de las suscripciones, la autenticación moderna se activa automáticamente, pero si compró la suscripción antes de agosto de 2017, es probable que deba activar la autenticación moderna para que características como la autenticación multifactor funcionen en clientes de Windows como Outlook.

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, en el panel de navegación izquierdo, elija **Configuración** \> **Configuración de la organización**.
2. En la pestaña **Servicios**, elija **Autenticación moderna** y, en el panel **Autenticación moderna**, asegúrese de que esté seleccionada la opción **Activar autenticación moderna**. Seleccione **Guardar cambios**.

## <a name="next-steps"></a>Pasos siguientes

- [Cómo registrarse para el método de verificación adicional](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Qué es: la autenticación multifactor](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [Cómo iniciar sesión después del registro](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Cómo cambiar el método de verificación adicional](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a>Contenido relacionado

[configurar la autenticación multifactor](set-up-multi-factor-authentication.md) (vídeo)\

[Activar la autenticación multifactor para su teléfono (artículo)](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

[Valores predeterminados de seguridad y autenticación multifactor](/microsoft-365/business-premium/m365bp-conditional-access) (artículo)