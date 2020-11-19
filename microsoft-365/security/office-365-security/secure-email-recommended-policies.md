---
title: Directivas recomendadas para el correo electrónico seguro-Microsoft 365 para Enterprise | Microsoft docs
description: Describe las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de correo electrónico.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: f2d3b9180ad5ab58e92812ed7b2d4f7ba07e2971
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357114"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendaciones de directivas para proteger el correo electrónico

En este artículo se describe cómo implementar las directivas recomendadas de identidad y acceso a dispositivos para proteger el correo electrónico de la organización y los clientes de correo electrónico que admiten la autenticación moderna y el acceso condicional. Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md) , y también incluye algunas recomendaciones adicionales.

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades: **línea de base**, **confidencial** y **muy regulada**. Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).

Estas recomendaciones requieren que los usuarios usen clientes de correo electrónico modernos, incluidos Outlook para iOS y Android, en dispositivos móviles. Outlook para iOS y Android proporcionan compatibilidad con las mejores características de Office 365. Estas aplicaciones móviles de Outlook también tienen capacidades de seguridad que admiten el uso móvil y trabajan conjuntamente con otras funciones de seguridad en la nube de Microsoft. Para obtener más información, consulte [preguntas más frecuentes sobre Outlook para iOS y Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Actualizar directivas comunes para incluir correo electrónico

Para proteger el correo electrónico, en el siguiente diagrama se ilustran las directivas que se deben actualizar desde las directivas comunes de identidad y acceso a dispositivos.

[![Resumen de las actualizaciones de directivas para proteger el acceso a los equipos y sus servicios dependientes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Tenga en cuenta la adición de una nueva Directiva de Exchange Online para bloquear clientes de ActiveSync. Esto fuerza el uso de Outlook Mobile.

Si incluyó Exchange Online y Outlook en el ámbito de las directivas al configurarlas, solo tiene que crear la nueva Directiva para bloquear a los clientes de ActiveSync. Revise las directivas enumeradas en la tabla siguiente y haga las adiciones recomendadas, o bien confirme que ya se han incluido. Cada Directiva se vincula a las instrucciones de configuración asociadas en [las directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md).

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange online en la asignación de aplicaciones en la nube|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir Exchange online en la asignación de aplicaciones en la nube|
||[Aplicar directivas de protección de datos de aplicaciones](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrese de que Outlook está incluido en la lista de aplicaciones. Asegúrese de actualizar la Directiva para cada plataforma (iOS, Android, Windows)|
||[Requerir aplicaciones aprobadas y protección de aplicaciones](identity-access-policies.md#require-approved-apps-and-app-protection)|Incluir Exchange online en la lista de aplicaciones en la nube|
||[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir Exchange online en la lista de aplicaciones en la nube|
||[Bloquear clientes de ActiveSync](#block-activesync-clients)|Agregar esta nueva Directiva|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange online en la asignación de aplicaciones en la nube|
||[Requerir equipos *y* dispositivos móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir Exchange online en la lista de aplicaciones en la nube|
|**Extremadamente regulado**|[Requerir *siempre* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange online en la asignación de aplicaciones en la nube|
|

## <a name="block-activesync-clients"></a>Bloquear clientes de ActiveSync

Esta directiva impide a los clientes de ActiveSync omitir otras directivas de acceso condicional. La configuración de directiva solo se aplica a los clientes de ActiveSync. Al seleccionar **[requerir Directiva de protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, esta directiva bloquea a los clientes de ActiveSync. Puede encontrar más información sobre la creación de esta directiva en [requerir Directiva de protección de aplicaciones para Cloud Access Access con acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

- Siga "paso 2: configurar una directiva de acceso condicional de Azure AD para Exchange Online con ActiveSync (EAS)" en el [escenario 1: las aplicaciones de Office 365 requieren aplicaciones aprobadas con directivas de protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), lo que impide que los clientes de Exchange ActiveSync que aprovechan la autenticación básica se conecten a Exchange Online.

También puede usar directivas de autenticación para [deshabilitar la autenticación básica](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), que obliga a todas las solicitudes de acceso de cliente a usar la autenticación moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitar el acceso a Exchange online desde Outlook en la web

Puede restringir la capacidad de los usuarios para descargar datos adjuntos de Outlook en la web en dispositivos umnanaged. Los usuarios de estos dispositivos pueden ver y editar estos archivos con Office online sin perder ni almacenar los archivos en el dispositivo. También puede impedir que los usuarios vean datos adjuntos en un dispositivo no administrado.

Para ello, siga estos pasos:

1. [Conéctese a una sesión de PowerShell remoto de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Si aún no tiene una directiva de buzón de OWA, cree una con el cmdlet [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) .
3. Si desea permitir la visualización de datos adjuntos pero no descargarlos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Si desea bloquear los datos adjuntos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. En Azure portal, cree una nueva Directiva de acceso condicional con estos valores:

   **Asignaciones** \> **Usuarios y grupos**: seleccione los usuarios y grupos correspondientes que desea incluir y excluir.

   **Asignaciones** \> **Aplicaciones o acciones** \> en la nube Aplicaciones en la **nube** \> **Incluir** \> **Seleccione aplicaciones**: seleccionar **Office 365 Exchange Online**

   **Controles** \> de acceso **Sesión**: seleccione **usar restricciones de aplicación forzada**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Requerir que los dispositivos iOS y Android deban usar Outlook

Para garantizar que los usuarios de dispositivos iOS y Android solo puedan acceder al contenido de trabajo o escuela con Outlook para iOS y Android, necesitará una directiva de acceso condicional que se destina a los usuarios potenciales.

Vea los pasos para configurar esta directiva en [Manage Messaging Collaboration Access by Using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).

## <a name="set-up-message-encryption"></a>Configurar el cifrado de mensajes

Con las nuevas capacidades de cifrado de mensajes de Office 365 (OME), que aprovechan las características de protección de Azure Information Protection, su organización puede compartir fácilmente el correo electrónico protegido con cualquier persona en cualquier dispositivo. Los usuarios pueden enviar y recibir mensajes protegidos con otras organizaciones de Microsoft 365, así como no clientes que usen Outlook.com, gmail y otros servicios de correo electrónico.

Para obtener más información, vea [set up New Office 365 Message Encryption Capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Siguientes pasos

![Paso 4: directivas para las aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure las directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
