---
title: 'Directivas de correo electrónico seguras recomendadas: Microsoft 365 para empresas | Microsoft Docs'
description: Describe las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de correo electrónico.
ms.author: dansimp
author: dansimp
manager: Laurawi
ms.service: microsoft-365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- m365-security
- remotework
- m365solution-identitydevice
- m365solution-scenario
- zerotrust-solution
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 0fae866f48e1b6de58e65c6970c788c98c21dc58
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68068949"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendaciones de directivas para proteger el correo electrónico

En este artículo se describe cómo implementar las directivas de acceso a dispositivos e identidades de Confianza cero recomendadas para proteger los clientes de correo electrónico y correo electrónico de la organización que admiten la autenticación moderna y el acceso condicional. Esta guía se basa en las [directivas de acceso a dispositivos e identidades comunes](identity-access-policies.md) y también incluye algunas recomendaciones adicionales.

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades: **punto de partida**, **empresa** y **seguridad especializada**. Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).

Estas recomendaciones requieren que los usuarios usen clientes de correo electrónico modernos, como Outlook para iOS y Android en dispositivos móviles. Outlook para iOS y Android proporcionan compatibilidad con las mejores características de Office 365. Estas aplicaciones móviles de Outlook también están diseñadas con funcionalidades de seguridad que admiten el uso móvil y funcionan junto con otras funcionalidades de seguridad en la nube de Microsoft. Para obtener más información, vea [Preguntas más frecuentes sobre Outlook para iOS y Android](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Actualización de directivas comunes para incluir correo electrónico

Para proteger el correo electrónico, en el diagrama siguiente se muestran las directivas que se van a actualizar a partir de las directivas comunes de acceso a dispositivos e identidades.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png" alt-text="Resumen de las actualizaciones de directivas para proteger el acceso a Microsoft Exchange" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png":::

Tenga en cuenta la adición de una nueva directiva para Exchange Online bloquear clientes de ActiveSync. Esto fuerza el uso de Outlook mobile.

Si incluyó Exchange Online y Outlook en el ámbito de las directivas al configurarlas, solo tendrá que crear la nueva directiva para bloquear los clientes de ActiveSync. Revise las directivas enumeradas en la tabla siguiente y realice las adiciones recomendadas o confirme que ya están incluidas. Cada directiva se vincula a las instrucciones de configuración asociadas en [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md).

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Punto de inicio**|[Requerir MFA cuando el riesgo de inicio de sesión es *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
||[Aplicación de directivas de protección de datos de APLICACIONES](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrese de que Outlook está incluido en la lista de aplicaciones. Asegúrese de actualizar la directiva para cada plataforma (iOS, Android, Windows)|
||[Requerir aplicaciones aprobadas y protección de aplicaciones](identity-access-policies.md#require-approved-apps-and-app-protection)|Incluir Exchange Online en la lista de aplicaciones en la nube|
||[Bloquear clientes de ActiveSync](#block-activesync-clients)|Agregar esta nueva directiva|
|**Empresarial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
||[Requerir equipos *compatibles y* dispositivos móviles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir Exchange Online en la lista de aplicaciones en la nube|
|**Seguridad especializada**|[*Siempre* se requiere MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange Online en la asignación de aplicaciones en la nube|

## <a name="block-activesync-clients"></a>Bloquear clientes de ActiveSync

Exchange ActiveSync se pueden usar para sincronizar datos de mensajería y calendario en dispositivos móviles y de escritorio.

En el caso de los dispositivos móviles, los clientes de Exchange ActiveSync compatibles con la autenticación moderna que no admiten directivas de protección de aplicaciones Intune (o clientes admitidos que no están definidos en la directiva de protección de aplicaciones) y Exchange ActiveSync clientes que usan la autenticación básica se bloquean en función de la directiva de acceso condicional creada en [ Requerir aplicaciones aprobadas y protección de aplicaciones](identity-access-policies.md#require-approved-apps-and-app-protection).

Para bloquear Exchange ActiveSync mediante la autenticación básica en otros dispositivos, siga los pasos descritos en [Bloquear Exchange ActiveSync en todos los dispositivos](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#block-exchange-activesync-on-all-devices), lo que impide que Exchange ActiveSync clientes que usan la autenticación básica en dispositivos no móviles se conecten a Exchange Online.

También puede usar directivas de autenticación para [deshabilitar la autenticación básica](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), lo que obliga a todas las solicitudes de acceso de cliente a usar la autenticación moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitar el acceso a Exchange Online desde Outlook en la Web

Puede restringir la capacidad de los usuarios para descargar datos adjuntos de Outlook en la Web en dispositivos no administrados. Los usuarios de estos dispositivos pueden ver y editar estos archivos mediante Office Online sin perder ni almacenar los archivos en el dispositivo. También puede impedir que los usuarios vean datos adjuntos en un dispositivo no administrado.

Estos son los pasos:

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Si aún no tiene una directiva de buzón de OWA, cree una con el cmdlet [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) .
3. Si desea permitir la visualización de datos adjuntos pero sin descarga, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Si desea bloquear los datos adjuntos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. En el Azure Portal, cree una nueva directiva de acceso condicional con esta configuración:

   **Asignaciones** \> **Usuarios y grupos**: seleccione los usuarios y grupos adecuados para incluir y excluir.

   **Asignaciones** \> **Aplicaciones o acciones** \> en la nube **Aplicaciones en la nube** \> **Incluír** \> **Seleccionar aplicaciones**: seleccione **Office 365 Exchange Online**

   \> **Controles de acceso** **Sesión**: seleccione **Usar restricciones aplicadas por la aplicación**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Requerir que los dispositivos iOS y Android usen Outlook

Para asegurarse de que los usuarios de dispositivos iOS y Android solo puedan acceder a contenido profesional o educativo mediante Outlook para iOS y Android, necesita una directiva de acceso condicional destinada a esos usuarios potenciales.

Consulte los pasos para configurar esta directiva en [Administración del acceso a la colaboración de mensajería mediante Outlook para iOS y Android](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).

## <a name="set-up-message-encryption"></a>Configuración del cifrado de mensajes

Con Cifrado de mensajes de Microsoft Purview, que aprovecha las características de protección de Azure Information Protection, su organización puede compartir fácilmente el correo electrónico protegido con cualquier usuario de cualquier dispositivo. Los usuarios pueden enviar y recibir mensajes protegidos con otras organizaciones de Microsoft 365, así como con clientes que no usen Outlook.com, Gmail y otros servicios de correo electrónico.

Para obtener más información, vea [Configurar nuevas funcionalidades de cifrado de mensajes Office 365](../../compliance/set-up-new-message-encryption-capabilities.md).

## <a name="next-steps"></a>Pasos siguientes

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Directivas para aplicaciones en la nube de Microsoft 365" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
