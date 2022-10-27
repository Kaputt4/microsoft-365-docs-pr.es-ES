---
title: Tiempo de espera de sesión inactiva para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- Adm_TOC
description: Establezca cuánto tiempo durará la sesión del usuario en Microsoft 365 antes de que se agote el tiempo de espera.
ms.openlocfilehash: 5a3307cd1c0d2b84b560359678bd2a22c199c33a
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68733029"
---
# <a name="idle-session-timeout-for-microsoft-365"></a>Tiempo de espera de sesión inactiva para Microsoft 365

<!-- Add metadata: localization, AdminSurgePortfolio, admindeeplinkMAC. remove robots nofollow -->

> [!IMPORTANT]
> El tiempo de espera de la sesión inactiva no está disponible para Microsoft 365 operado por 21Vianet o Microsoft 365 Alemania.

Use el tiempo de espera de la sesión inactiva para configurar una directiva sobre cuánto tiempo los usuarios están inactivos en su organización antes de que se agote la sesión de las aplicaciones web de Microsoft 365. Esto ayuda a proteger los datos confidenciales de la empresa y agrega otro nivel de seguridad para los usuarios finales que trabajan en dispositivos no corporativos o compartidos.

Cuando un usuario alcanza la sesión de tiempo de espera de inactividad que ha establecido, recibirá una notificación de que está a punto de iniciar sesión. Tienen que seleccionar mantener la sesión iniciada o cerrar sesión automáticamente de todas las aplicaciones web de Microsoft 365.

> [!IMPORTANT]
> El tiempo de espera de la sesión inactiva no afecta a las aplicaciones móviles y de escritorio de Microsoft 365.

## <a name="turn-on-idle-session-timeout"></a>Activar el tiempo de espera de la sesión inactiva

Debe ser miembro de los roles administrador global, administrador de seguridad, administrador de aplicaciones o administrador de aplicaciones en la nube para ver la configuración de tiempo de espera de sesión inactiva.

1. En el Centro de administración de Microsoft 365, seleccione **Seguridad de la configuración** **->** de la organización [& pestaña Privacidad](https://go.microsoft.com/fwlink/p/?linkid=2072756) y seleccione **Tiempo de espera de sesión inactivo**.  

2. En **Tiempo de espera de sesión inactiva** , seleccione el botón de alternancia para activarlo. Puede elegir una configuración predeterminada o elegir su propia hora personalizada. La sesión inactiva tardará unos minutos en activarse en la organización.

> [!NOTE]
> Si ha configurado directivas de tiempo de espera de sesión inactiva para [la aplicación web de Outlook](https://support.microsoft.com/topic/description-of-the-activity-based-authentication-timeout-for-owa-in-office-365-0c101e1b-020e-69c1-a0b0-26532d60c0a4) y [SharePoint Online](/sharepoint/sign-out-inactive-users), al activar el tiempo de espera de sesión inactiva en el Centro de administración de Microsoft 365 invalidará la configuración de La aplicación web de Outlook y SharePoint.

El tiempo de espera de la sesión inactiva es una de las muchas medidas de seguridad de Microsoft 365. Para obtener información sobre otras tareas de seguridad en Microsoft 365, consulte [Tareas de seguridad principales en Microsoft 365](../../security/top-security-tasks-for-remote-work.md).  

## <a name="what-users-will-see"></a>Qué verán los usuarios

Cuando un usuario ha estado inactivo en aplicaciones web de Microsoft 365 durante el período de tiempo que eligió, verá el siguiente aviso. Tienen que seleccionar **Mantener la sesión iniciada** o se van a firmar.

:::image type="content" source="../../media/idle-session-timeout.png" alt-text="Captura de pantalla: mensaje que le informa de que la sesión está a punto de expirar. Seleccione Mantener la sesión iniciada para no salir de las aplicaciones web de Microsoft 365.":::

## <a name="details-about-idle-session-timeout"></a>Detalles sobre el tiempo de espera de la sesión inactiva

- Se admiten las siguientes aplicaciones web de Microsoft 365. Pronto se agregarán más aplicaciones web.

    - Outlook Web App

    - OneDrive para la Empresa

    - SharePoint Online (SPO)

    - Office.com y otras páginas de inicio

    - Office (Word, Excel, PowerPoint) en la web

    - Centro de administración de Microsoft 365

- La actividad hace referencia a cualquier interacción del usuario del lado cliente que se produzca en el contexto de la aplicación web. Por ejemplo, los clics del mouse y las pulsaciones de teclado.  

- El tiempo de espera de la sesión inactiva funciona según la sesión por explorador. La actividad de un usuario en Microsoft Edge se trata de forma diferente a su actividad en otros exploradores, como Google Chrome. Los usuarios se cierran sesión en todas las pestañas correspondientes a su cuenta dentro de esa sesión del explorador.

- Una vez que se activa el tiempo de espera de la sesión inactiva, se aplica a toda la organización y no se puede limitar a usuarios, unidades organizativas o grupos específicos. Use directivas de [acceso condicional de Azure AD](/azure/active-directory/conditional-access/) para distintos usuarios y grupos para acceder a SharePoint y Exchange Online.

- Los usuarios deben estar inactivos en todas las pestañas de aplicaciones web de Microsoft 365 durante la duración configurada. Si el usuario está activo en una pestaña (por ejemplo, OWA) mientras está inactivo en otra pestaña (por ejemplo, SPO), se considerará activo y no se iniciará sesión.  

- En estos casos, los usuarios no podrán iniciar sesión.
    - Si obtienen el inicio de sesión único (SSO) en la aplicación web desde la cuenta unida al dispositivo.
    - Si seleccionaron **Mantener la sesión iniciada** en el momento del inicio de sesión. Para obtener más información sobre cómo ocultar esta opción para su organización, consulte [Agregar personalización de marca a la página de inicio de sesión de su organización](/azure/active-directory/fundamentals/customize-branding).
    - Si están en un dispositivo administrado (uno que es compatible o unido a un dominio) y usa un explorador compatible como Microsoft Edge o Google Chrome (con la [extensión Cuentas de Windows](https://chrome.google.com/webstore/detail/windows-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji)).

## <a name="trigger-idle-session-timeout-only-on-unmanaged-devices"></a>Desencadenar el tiempo de espera de sesión inactiva solo en dispositivos no administrados

De forma predeterminada, la característica de tiempo de espera de sesión inactiva se desencadena en todos los tipos de dispositivo si se cumplen las otras condiciones. Para que esta característica se desencadene solo en un dispositivo no administrado, se requiere una suscripción de Azure AD Premium P1 o P2 válida. También tendrá que agregar una directiva de acceso condicional en el Centro de administración de Azure AD.

## <a name="idle-session-timeout-on-unmanaged-devices"></a>Tiempo de espera de sesión inactiva en dispositivos no administrados  

Para que el tiempo de espera de la sesión inactiva se desencadene solo en dispositivos no administrados, deberá agregar una directiva de acceso condicional en el Centro de administración de Azure AD.

1. En el **acceso condicional | Página Directivas** del Centro de administración de Azure AD, seleccione **Nueva directiva** y escriba un nombre para la directiva.

2. Seleccione **Usuarios o identidades de carga de trabajo** y, a continuación, seleccione **Todos los usuarios**.

3. Seleccione **Aplicaciones o acciones** en la nube, **Seleccione aplicaciones** y busque **Office 365**. Seleccione **Office 365** y, a continuación, **Seleccione**.  

4. Seleccione **Condiciones**, **Aplicaciones cliente**, **Configurar en Sí**, **Explorador** y, a continuación, seleccione **Listo**.

5. Seleccione **Sesión**, **Usar restricciones aplicadas** a la aplicación y, a continuación, **Seleccione**.

6. Active la directiva y seleccione **Crear**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="are-there-any-browsers-or-browser-scenarios-in-which-idle-session-timeout-feature-doesnt-work"></a>¿Hay algún explorador o escenario de explorador en el que la característica de tiempo de espera de sesión inactiva no funcione?  

No se admite el tiempo de espera de la sesión inactiva cuando las cookies de terceros están deshabilitadas en el explorador. Los usuarios no verán ninguna solicitud de cierre de sesión. Se recomienda mantener la configuración de prevención de seguimiento en [Equilibrado (predeterminado)](/microsoft-edge/web-platform/tracking-prevention) para Microsoft Edge y las cookies de terceros habilitadas en los demás exploradores. Las aplicaciones y servicios de Microsoft 365 han dejado de admitir Internet Explorer 11 desde el 17 de agosto de 2021.

### <a name="how-should-i-prepare-if-my-organization-is-already-using-existing-outlook-web-app-and-sharepoint-online-idle-timeout-policies"></a>¿Cómo debo prepararme si mi organización ya usa directivas existentes de tiempo de espera de inactividad de Outlook y SharePoint Online?  

Si ya usa las directivas de tiempo de espera de inactividad de Outlook y SharePoint Online existentes, puede activar la característica tiempo de espera de sesión inactiva. Al activar la directiva de tiempo de espera de inactividad, tiene prioridad sobre las directivas existentes de La aplicación web de Outlook y SharePoint Online. Tenemos previsto dejar de usar la aplicación web de Outlook y las directivas de SharePoint Online existentes en un futuro próximo. Para preparar mejor su organización, se recomienda activar el tiempo de espera de sesión inactiva.

### <a name="what-happens-if-i-am-inactive-on-an-included-microsoft-365-web-app-but-active-on-a-microsoft-web-app-or-saas-web-app-that-doesnt-have-idle-session-timeout-turned-on"></a>¿Qué ocurre si estoy inactivo en una aplicación web de Microsoft 365 incluida, pero activa en una aplicación web de Microsoft o una aplicación web SaaS que no tiene activado el tiempo de espera de sesión inactiva?  

Se admiten las siguientes aplicaciones web de Microsoft 365.

- Outlook Web App

- OneDrive para la Empresa

- SharePoint Online (SPO)

- Office.com y otras páginas de inicio

- Office (Word, Excel, PowerPoint) en la web

- Centro de administración de Microsoft 365

Si trabaja en otra aplicación web con la misma cuenta, la actividad de esa aplicación web no se aplicará al tiempo de espera de sesión inactiva.

### <a name="i-want-to-make-changes-to-the-idle-session-timeout-policy-or-delete-it-how-can-i-do-that"></a>Quiero realizar cambios en la directiva de tiempo de espera de sesión inactiva o eliminarla. ¿Cómo puedo hacerlo?

Actualice la directiva:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración de la organización**, vaya a la pestaña **Seguridad & Privacidad** y seleccione **Tiempo de espera de sesión inactiva**.

2. En el menú desplegable, seleccione un valor de tiempo de espera diferente y, después, **Guardar**.  

Elimine la directiva:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración de la organización**, vaya a la pestaña **Seguridad & Privacidad** y seleccione **Tiempo de espera de sesión inactiva**.

2. Desactive **Activar para establecer el período de inactividad para que los usuarios cierren sesión en las aplicaciones web de Office** y seleccione **Guardar**.
