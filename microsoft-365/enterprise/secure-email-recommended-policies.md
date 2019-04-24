---
title: Directivas recomendadas para proteger el correo electrónico - Microsoft 365 Enterprise | Microsoft Docs
description: Describe las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de correo electrónico.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 78defc7ad5da788ae49195f6c0027f3639d50f3e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291125"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendaciones de directivas para proteger el correo electrónico
En este artículo se describe cómo implementar las directivas recomendadas de identidad y acceso a dispositivos para proteger el correo electrónico de la organización y los clientes de correo electrónico que admiten la autenticación moderna y el acceso condicional. Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md) , y también incluye algunas recomendaciones adicionales.


Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades: **línea de base**, **confidencial**y **muy regulada**. Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).

Estas recomendaciones requieren que los usuarios usen clientes de correo electrónico modernos, incluidos Outlook para iOS y Android, en dispositivos móviles. Outlook para iOS y Android proporcionan compatibilidad con las mejores características de Office 365. Estas aplicaciones móviles de Outlook también tienen capacidades de seguridad que admiten el uso móvil y trabajan conjuntamente con otras funciones de seguridad en la nube de Microsoft. Para obtener más información, consulte [preguntas más frecuentes sobre Outlook para iOS y Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Actualización de directivas comunes para incluir correo electrónico
En el siguiente diagrama se ilustran las directivas comunes de identidad y acceso a dispositivos, y se indica qué directivas deben actualizarse para proteger el correo electrónico. Tenga en cuenta la adición de una nueva regla para que Exchange Online bloquee los clientes de ActiveSync. Esto fuerza el uso de Outlook Mobile.

![Resumen de las actualizaciones de directivas para proteger el correo electrónico](../images/identity-access-ruleset-mail.png)

Si incluyó Exchange Online y Outlook en el ámbito de las directivas al configurarlas, solo tiene que crear la nueva Directiva para bloquear a los clientes de ActiveSync. Revise las directivas enumeradas en la tabla siguiente y haga las adiciones recomendadas, o bien confirme que ya se han incluido. Cada regla tiene vínculos a las instrucciones de configuración asociadas en el artículo [Common Identity and Device Access Policies](identity-access-policies.md) . 

|Nivel de protección|Directivas|Más información|
|:---------------|:-------|:----------------|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange online en la asignación de aplicaciones en la nube|
|        |[Bloquear clientes que no admitan la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir Exchange online en la asignación de aplicaciones en la nube|
|        |[Definir directivas de protección de aplicaciones](identity-access-policies.md#high-risk-users-must-change-password)|Asegúrese de que Outlook está incluido en la lista de aplicaciones. Asegúrese de actualizar la Directiva para cada plataforma (iOS, Android, Windows)|
|        |[Requerir aplicaciones aprobadas](identity-access-policies.md#require-approved-apps)|Incluir Exchange online en la lista de aplicaciones en la nube|
|        |[Requerir equipos compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir Exchange online en la lista de aplicaciones en la nube|
|        |[Bloquear clientes de ActiveSync](#block-activesync-clients)|Agregar esta nueva Directiva| 
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Incluir Exchange online en la asignación de aplicaciones en la nube|
|         |[Requerir equipos *y* dispositivos móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir Exchange online en la lista de aplicaciones en la nube|
|**Extremadamente regulado**|[Requerir *siempre* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange online en la asignación de aplicaciones en la nube|

## <a name="block-activesync-clients"></a>Bloquear clientes de ActiveSync
Esta directiva impide que los clientes de ActiveSync omitan otras reglas de acceso condicional. La configuración de la regla solo se aplica a los clientes de ActiveSync. Al seleccionar **requerir aplicación cliente aprobada**, esta directiva bloquea a los clientes de ActiveSync. Para configurar esta directiva:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Una vez que haya iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**y seleccione **Office 365 Exchange Online**. Elija **seleccionar** y **listo**.

8. Elija **condiciones**y, a continuación, elija **aplicaciones cliente**.

9. Para **configurar**, seleccione **sí**. Compruebe solo lo siguiente: **aplicaciones móviles y clientes de escritorio** y **clientes de Exchange ActiveSync**. Elija **Listo**.

10. Pulse **Conceder** en la sección **Controles de acceso**.

11. Elija **conceder acceso**y seleccione **requerir aplicación cliente aprobada**.  Para varios controles, seleccione **requerir los controles seleccionados**y, a continuación, elija **seleccionar**. 

12. Seleccione **Crear**.

## <a name="setup-office-365-message-encryption"></a>Configurar el cifrado de mensajes de Office 365
Con las nuevas capacidades de cifrado de mensajes de Office 365 (OME), que aprovechan las características de protección de Azure Information Protection, su organización puede compartir fácilmente el correo electrónico protegido con cualquier persona en cualquier dispositivo. Los usuarios pueden enviar y recibir mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son de Office 365 con Outlook.com, gmail y otros servicios de correo electrónico.

Para obtener más información, vea [set up New Office 365 Message Encryption Capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e). 



## <a name="next-steps"></a>Pasos siguientes

[Más información sobre las recomendaciones de directiva para la protección de sitios y archivos de SharePoint](sharepoint-file-access-policies.md)
