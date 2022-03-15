---
title: Tiempo de espera de la sesión inactiva Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Adm_TOC
description: Establece cuánto tiempo durará la sesión del usuario en Microsoft 365 antes de que se les desalome el tiempo de espera.
ms.openlocfilehash: 215b900315b2d98b01a8cf87b14a6fa65289e121
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504898"
---
# <a name="idle-session-timeout-for-microsoft-365-public-preview"></a>Tiempo de espera de la sesión inactiva Microsoft 365 (versión preliminar pública)

<!-- Add metadata: localization, AdminSurgePortfolio, admindeeplinkMAC. remove robots nofollow -->

Use el tiempo de espera de la sesión inactiva para configurar una directiva sobre cuánto tiempo los usuarios están inactivos en la organización antes de que se haya iniciado sesión Microsoft 365 aplicaciones web. Esto ayuda a proteger los datos confidenciales de la empresa y agrega otra capa de seguridad para los usuarios finales que trabajan en dispositivos compartidos o no de la empresa.

Cuando un usuario llegue a la sesión de tiempo de espera de inactividad que haya establecido, se le mostrará una notificación de que está a punto de salir. Tienen que seleccionar para que no se inicie sesión o que se desescriba automáticamente de todas las Microsoft 365 web.

> [!IMPORTANT]
> El tiempo de espera de la sesión inactiva no afecta Microsoft 365 aplicaciones de escritorio y móviles.

## <a name="turn-on-idle-session-timeout"></a>Activar tiempo de espera de la sesión inactiva

Si no eres un administrador Microsoft 365 o Office 365 global, no verás la pestaña Seguridad **& privacidad**.

1. En la Centro de administración de Microsoft 365, seleccione **Org Configuración** **->**[Security & privacy](https://go.microsoft.com/fwlink/p/?linkid=2072756) tab y seleccione **Idle session timeout**.  

2. En tiempo **de espera de la sesión inactiva** , seleccione la alternancia para activarla. Puede elegir una configuración predeterminada o elegir su propia hora personalizada. Llevará unos minutos antes de que se activa la sesión inactiva en la organización.

> [!NOTE]
> Si has configurado directivas de tiempo de espera de sesión inactiva para Outlook [web app](https://support.microsoft.com/topic/description-of-the-activity-based-authentication-timeout-for-owa-in-office-365-0c101e1b-020e-69c1-a0b0-26532d60c0a4) y [SharePoint Online](/sharepoint/sign-out-inactive-users), activar el tiempo de espera de la sesión inactiva en el Centro de administración de Microsoft 365 invalidará la configuración de Outlook web app y SharePoint.

El tiempo de espera de la sesión inactiva es una de las muchas medidas de seguridad de Microsoft 365. Para obtener información sobre otras tareas de seguridad en Microsoft 365, vea [Top security tasks in Microsoft 365](../../security/top-security-tasks-for-remote-work.md).  

## <a name="what-users-will-see"></a>Qué verán los usuarios

Cuando un usuario haya estado inactivo en Microsoft 365 web durante el período de tiempo que haya elegido, verá el siguiente mensaje. Tienen que seleccionar **Permanecer iniciado sesión** o se va a haber iniciado sesión.

:::image type="content" source="../../media/idle-session-timeout.png" alt-text="Screenshot: Prompt letting you know that your session is about to expire. Selecciona Permanecer iniciado sesión para que no salgas de la sesión de Microsoft 365 web":::

## <a name="details-about-idle-session-timeout"></a>Detalles sobre el tiempo de espera de la sesión inactiva

- Se admiten las Microsoft 365 web siguientes. Pronto se agregarán más aplicaciones web.

    - Outlook Web App

    - OneDrive para la Empresa

    - SharePoint Online (SPO)

    - Office.com y otras páginas de inicio

    - Office (Word, Excel, PowerPoint) en la web

    - Centro de administración de Microsoft 365

- La actividad hace referencia a cualquier interacción del usuario del lado cliente que se está produciendo en el contexto de la aplicación web. Por ejemplo, los clics del mouse y las pulsaciones del teclado.  

- El tiempo de espera de la sesión inactiva funciona por sesión de explorador. La actividad de un usuario en Microsoft Edge se trata de forma diferente que su actividad en otros exploradores como Google Chrome. Los usuarios se cierran sesión en todas las pestañas correspondientes a su cuenta dentro de esa sesión del explorador.

- Una vez que se activa el tiempo de espera de la sesión inactiva, se aplica a toda la organización y no se puede establecer en el ámbito de usuarios, unidades organizativas o grupos específicos. Use [Azure AD acceso condicional para](/azure/active-directory/conditional-access/) directivas para diferentes usuarios y grupos.

- Los usuarios deben estar inactivos en todas Microsoft 365 pestañas de la aplicación web durante la duración configurada. Si el usuario está activo en una pestaña (por ejemplo, OWA) mientras está inactivo en otra pestaña (por ejemplo, SPO), se considerará activo y no se firmará.  

- Los usuarios no se firman en estos casos.
    - Si obtienen el inicio de sesión único (SSO) en la aplicación web desde la cuenta unida al  dispositivo o seleccionan Permanecer conectado en el momento de iniciar sesión. Para obtener más información sobre cómo ocultar esta opción para la organización, consulta [Agregar personalidad de marca a la página de inicio de sesión de la organización](/azure/active-directory/fundamentals/customize-branding).
    - Si están en un dispositivo administrado (compatible o unido a un dominio) y usando un explorador compatible como Microsoft Edge o Google Chrome (con la extensión [cuentas de Windows](https://chrome.google.com/webstore/detail/windows-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji)). Para que esta característica no se desencadene en un dispositivo administrado, se requiere una suscripción Azure AD Premium P1 o P2 elegible, y una directiva de acceso condicional específica. Vea a continuación para obtener más información.

> [!IMPORTANT]
> El tiempo de espera de la sesión inactiva no está disponible para Microsoft 365 operado por 21Vianet o Microsoft 365 Alemania.

## <a name="idle-session-timeout-on-unmanaged-devices"></a>Tiempo de espera de la sesión inactiva en dispositivos no administrados  

Para que el tiempo de espera de la sesión inactiva se desencadene en dispositivos no administrados, deberá agregar una directiva de acceso condicional en el centro Azure AD administración.

1. En el **acceso condicional | Página Directivas** del Centro Azure AD administración, **seleccione Nueva directiva** y escriba un nombre para la directiva.

2. Seleccione **Usuarios o identidades de carga de** trabajo y, a continuación, **seleccione Todos los usuarios**.

3. Selecciona **Aplicaciones o acciones en la nube**, **Seleccionar aplicaciones** y buscar **Office 365**. Seleccione **Office 365** y, a continuación **, Seleccione**.  

4. Selecciona **Condiciones**, **Aplicaciones cliente**, **Configurar en Sí**, **Explorador** y, a continuación, selecciona **Listo**.

5. Selecciona **Sesión**, **Usar restricciones aplicadas por la aplicación** y, a continuación, **Seleccionar**.

6. Active la directiva y seleccione **Crear**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="are-there-any-browsers-or-browser-scenarios-in-which-idle-session-timeout-feature-doesnt-work"></a>¿Hay algún explorador o escenario de explorador en el que la característica de tiempo de espera de sesión inactiva no funciona?  

El tiempo de espera de la sesión inactiva no se admite cuando las cookies de terceros están deshabilitadas en el explorador. Los usuarios no verán ningún mensaje de salida. Se recomienda mantener la configuración de prevención de seguimiento en [Balanced (Valor predeterminado)](/microsoft-edge/web-platform/tracking-prevention) para Microsoft Edge y las cookies de terceros habilitadas en los otros exploradores. Microsoft 365 aplicaciones y servicios han dejado de admitir Internet Explorer 11 desde el 17 de agosto de 2021.

### <a name="how-should-i-prepare-if-my-organization-is-already-using-existing-outlook-web-app-and-sharepoint-online-idle-timeout-policies"></a>¿Cómo debo prepararme si mi organización ya está usando Outlook aplicación web y SharePoint de tiempo de espera de inactividad en línea?  

Si ya estás usando las directivas de tiempo de espera de Outlook web y SharePoint de tiempo de espera de inactividad en línea, puedes activar la característica de tiempo de espera de la sesión inactiva. Al activar la directiva de tiempo de espera de inactividad, tiene prioridad sobre las directivas Outlook web y SharePoint online. Estamos planeando desuso de las Outlook web existentes y SharePoint en línea en un futuro próximo. Para preparar mejor la organización, se recomienda activar el tiempo de espera de la sesión inactiva.

### <a name="what-happens-if-i-am-inactive-on-an-included-microsoft-365-web-app-but-active-on-a-microsoft-web-app-or-saas-web-app-that-doesnt-have-idle-session-timeout-turned-on"></a>¿Qué sucede si estoy inactivo en una aplicación web Microsoft 365 incluida, pero activa en una aplicación web de Microsoft o una aplicación web SaaS que no tenga activado el tiempo de espera de sesión inactivo?  

Se admiten las Microsoft 365 web siguientes.

- Outlook Web App

- OneDrive para la Empresa

- SharePoint Online (SPO)

- Office.com y otras páginas de inicio

- Office (Word, Excel, PowerPoint) en la web

- Centro de administración de Microsoft 365

Si estás trabajando en una aplicación web diferente con la misma cuenta, la actividad de esa aplicación web no se aplicará al tiempo de espera de la sesión inactiva.

### <a name="i-want-to-make-changes-to-the-idle-session-timeout-policy-or-delete-it-how-can-i-do-that"></a>Quiero realizar cambios en la directiva de tiempo de espera de la sesión inactiva o eliminarla. ¿Cómo puedo hacerlo?

Actualice la directiva:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración de** la organización, vaya a la pestaña Seguridad **& Privacidad** y seleccione **Tiempo de espera de la sesión inactiva**.

2. En el menú desplegable, seleccione un valor de tiempo de espera diferente y, a continuación **, Guarde**.  

Elimine la directiva:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración de** la organización, vaya a la pestaña Seguridad **& Privacidad** y seleccione **Tiempo de espera de la sesión inactiva**.

2. **Desmarque Activar para establecer el período de inactividad** para que los usuarios puedan haber iniciado sesión en Office web y seleccione **Guardar**.
