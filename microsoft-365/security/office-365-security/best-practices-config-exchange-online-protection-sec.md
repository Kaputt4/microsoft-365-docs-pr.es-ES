---
title: Procedimientos recomendados de configuración para EOP y Office 365 la seguridad de ATP, los procedimientos recomendados, la configuración, las recomendaciones, el marco de directivas de remitente, la creación de informes de mensajes basados en dominio y la conformidad, el correo identificado por DomainKeys, los pasos, cómo funciona,
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: ¿Cuáles son los procedimientos recomendados para la configuración de seguridad de Exchange Online Protection (EOP) y la protección contra amenazas avanzada (ATP)? ¿Qué se recomienda? ¿Qué se debe usar de forma agresiva? ¿Y qué extras obtiene si también usa la protección contra amenazas avanzada (ATP)?
ms.openlocfilehash: fb6a39756c54e46f5ac8208c9c92af30bc144a57
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "37387162"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>Procedimientos recomendados para configurar EOP y la seguridad de ATP de Office 365

Exchange Online Protection (EOP) es la base de seguridad de las suscripciones E3 de Office 365. Es opcional e incluso se recomienda que los clientes de E3 compren una suscripción a Office 365 Advanced Threat Protection (ATP), por ejemplo: Plan ATP 1 o ATP 2, a fin de aprovechar la seguridad agregada disponible en las suscripciones de Office 365 E5.

Analizaremos dos niveles de seguridad, denominados recomendadas y agresivos en EOP, en los que se describen los comentarios sobre cómo usar las características en ambos niveles de seguridad. Las secciones comienzan con la validación de correo electrónico y la autenticación, que implica algunos Tinkering fuera de Office 365, en DNS y protege el correo saliente, lo que hace que los inquilinos sean buenos para los recursos que se envíen. Esta configuración protege mejor su suscripción.


## <a name="email-authentication"></a>Autenticación de correo electrónico

SPF, DKIM y DMARC son acrónimos para el marco de directivas de remitente, correo identificado por DomainKeys y autenticación de mensajes basada en dominio, informes y cumplimiento (bastante mouthful), y son la base de la autenticación y validación de correo electrónico.

Estos métodos administran el correo electrónico saliente desde Office 365 y ayudan a los sistemas de destino a confiar en que el correo electrónico de su dominio es válido. Son los únicos procedimientos recomendados que conllevan la configuración que se va a realizar *fuera* de Office 365, en su DNS. Para conocer los pasos de configuración específicos, consulte la sección de [validación y autenticación de correo electrónico](https://docs.microsoft.com/en-us/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing) en la tabla de contenido seguridad y cumplimiento.


|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|[Crear registros de SPF](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | v        |    v     |   -      |
|[Configurar la firma DKIM para los dominios](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  v       |    v     |  -       |
|[Implementar DMARC con la acción de rechazar o poner en cuarentena](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dmarc-to-validate-email)     |   v      |     v    |   Use Action = None para la opción recomendada y Action = Reject para agresivo.     |

> [!IMPORTANT]
> Para trabajar con roles de seguridad y permisos, asegúrese de que tiene el rol o los roles correctos en Office 365 o en el centro de seguridad y cumplimiento. Si es un *Administrador de seguridad* de Azure Active Directory, un *Administrador Global* de Office 365 o un administrador de la *organización de Exchange Online* en Exchange Online y Exchange Online PowerShell, ya está listo para continuar.

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>Protección contra correo electrónico no deseado, antimalware y contra la suplantación de identidad

Tanto los contra correo electrónico no deseado como los antimalware son características de EOP. El filtrado de correo no deseado, activado de forma predeterminada en Office 365, analiza todo el correo y asigna un valor de número de confianza contra correo no deseado (SCL) a cada correo. Para aclararlo, su objetivo es enumerar el grado de confianza del filtro de que el correo es (o no) correo no deseado. Los valores bajos, como-1, no son correo no deseado de los remitentes seguros y se encuentran en la bandeja de entrada de un usuario. Las puntuaciones altas, como 7, 8 o 9, son muy sospechosas, o responsables y responsables de correo no deseado conocidos para el correo no deseado de un usuario o la cuarentena de acceso del administrador.

El filtrado de malware también está activado de forma predeterminada en Office 365. Como el filtrado contra correo no deseado, los filtros antimalware funcionan tanto en el correo entrante como en el saliente. En ambos casos, esta protección se puede configurar para que los administradores la ajusten mejor.

De forma predeterminada, los filtros de phising están en Office 365, pero deben configurarse para que se ajuste mejor. Esto es lo que recomendamos para la protección contra el phishing en EOP.

### <a name="anti-spam"></a>Contra correo electrónico no deseado

|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|Período de retención de cuarentena    |   v      |     v    |   30 días   |
|Frecuencia de notificación de correo no deseado del usuario final   |   v      |     v    |   3 días   |
|Se debe habilitar la depuración de cero por horas   |   v      |     v    |   True  |
|La acción de detección de correo no deseado debería enviarse a | JMF | Cuarentena | - |
|La acción de detección de correo no deseado de confianza alta debería enviarse a | Cuarentena | Cuarentena| - |
|La acción de detección en masa debe establecerse en | JMF | Cuarentena | - |
|Establecer el umbral de correo electrónico masivo en | 6  | 4  | - |
|Las sugerencias de seguridad deben estar habilitadas| True | True | - |
|Habilitar notificación de correo no deseado para el usuario final| True | False | - |
|Remitentes permitidos | Ninguno | Ninguno | - |
|Dominios de remitentes permitidos | Ninguno | Ninguno | - |
|Remitentes bloqueados | Ninguno | Ninguno | - |
|Dominios de remitentes bloqueados | Ninguno | Ninguno | - |
|RRL Directiva de correo no deseado saliente | 500 | 500 | - |

Recomendado para **desactivarse** en niveles agresivos y recomendados:

|Nombre de la característica de seguridad  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

Recomendado para **en** los niveles recomendado y agresivo:

|Nombre de la característica de seguridad  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>Anti-malware

|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|Configuración de notificaciones de malware para orígenes internos |Sí |Sí |- |
|Deshabilitar la notificación a los remitentes externos de detección de malware |Sí |Sí |- |
|Usar el filtro de tipo "datos adjuntos comunes" para bloquear los tipos de archivo sospechosos | Sí |Sí |- |
|ZAP de malware |True |True |- |
|Acción de malware |Desbloquear |Desbloquear |- |

### <a name="anti-phishing"></a>Contra la suplantación de identidad

|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|Se debe habilitar la depuración de cero por horas-phish| True | True | - | 
|La acción de detección de phish debe establecerse en | Quarantine-request | Quarantine-admin | - |
|La acción de detección de phish de confianza alta debe establecerse en | Quarantine-admin | Quarantine-admin | - |
|EnableMailboxIntelligence | True | True | - |
|EnableSimilarUsersSafetyTips | True | True | - |
|EnableSimilarDomainsSafetyTips | True | True | - |
|EnableUnusualCharactersSafetyTips | True | True | - |
|TargetedUserProtectionAction |Noacción |Desbloquear | - |
|MailboxIntelligenceProtectionAction |Noacción |Desbloquear | - |
|TargetedDomainProtectionAction |Noacción |Desbloquear | - |
|AuthenticationFailAction |MoveToJmf |Cuarentena | - |
|AntiSpoofEnforcementType |Alto |Alto | - |
|EnableAuthenticationSafetyTip |False |True | - |
|EnableAntiSpoofEnforcement |True |True | - |
|EnableUnauthenticatedSender |True |True | - |
|EnableAuthenticationSoftPassSafetyTip |False |True | - |
|TreatSoftPassAsAuthenticated |True |False | - |
|EnableSuspiciousSafetyTip |True |True | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Seguridad de la protección contra amenazas avanzada (ATP) de Office 365

Anteriormente, dije que se animaron a las suscripciones E3 agregar un plan 1 de ATP de Office 365 o el plan 2 más completo. La protección avanzada contra suplantación de identidad es una de las razones. Habilitado de forma predeterminada, la protección contra el phishing ***debe*** configurarse con directivas para operar. Olvidarse de configurar las directivas antiphishing expone a los usuarios a los riesgos, asegúrese de que se trata del paso 2 después de agregar una suscripción a ATP.

> [!IMPORTANT]
>  Si tiene una suscripción a E5, actualmente tiene el [plan 2 de ATP](https://products.office.com/en-us/exchange/advance-threat-protection). Active este vínculo cuando quiera obtener información sobre las novedades [de ATP](https://review.docs.microsoft.com/en-us/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff).

### <a name="advanced-anti-phishing"></a>Protección contra suplantación de identidad avanzada

La suplantación de identidad (phishing) intenta hacerse pasar por una empresa o persona acreditada con el fin de robar información personal, como los números de tarjeta de crédito o los pin o las contraseñas del equipo o del dispositivo. La suplantación de identidad puede implicar:

- **Suplantación de identidad**, en la que los suplantadores intentan enviar correo en nombre de un destino específico de un dominio (por ejemplo, Ellar@2020contoso.com intentando enviar correo para Ellar@2020litware.com (un escenario los métodos de autenticación de correo electrónico pueden ayudar a frustrar). 

- **Suplantación**, donde se recibe el correo cuyo remitente es visualmente similar (o de aspecto similar) a un dominio o nombre de usuario de destino. El actor malo, imita a un nombre de usuario específico o finge enviar correo desde un dominio de destino. Este es un dominio de pretipos: la misma @ 2020 | itware. com y este es un usuario de un día de ampliación, ellαr @ 2020litware. com (Mire atentamente los nombres de dominio y de usuario en estos ejemplos para detectar la suplantación de dominio y de usuario).

Si ha agregado una suscripción de ATP de Office 365 a su EOP, asegúrese de establecer las siguientes configuraciones.

|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|Establecer el umbral de suplantación de identidad avanzado en | 2  | 4  | - |
|Habilitar la protección contra la suplantación | Sí | Sí | - |
|Habilitar la inteligencia de buzones en las directivas de anti-suplantación | Sí | Sí | - |
|Habilitar la protección de suplantación basada en la inteligencia de buzones | Sí | Sí | - |
|La acción de suplantación de dominio debe ser | JMF | Cuarentena | - |
|La acción de suplantación del usuario debe ser | JMF | Qurantine | - |
|La acción de protección de suplantación basada en buzones de correo debe ser |Sugerencia  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>Vínculos seguros y datos adjuntos seguros

 ATP incluye directivas de datos adjuntos seguros y vínculos seguros para evitar que se entregue el correo electrónico con datos adjuntos potencialmente malintencionados y evitar que los usuarios haga clic y se desplazan a direcciones URL potencialmente no seguras.

#### <a name="safe-links"></a>Vínculos seguros

|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|Los vínculos seguros de ATP deben realizar un seguimiento de los clics del usuario con fines de respuesta |Sí |Sí |- |
|Los vínculos seguros ATP deben estar habilitados para las aplicaciones de Office |Sí |Sí |- |
|Los vínculos seguros ATP deben estar habilitados para el dominio interno |Sí |Sí |- |
|Los vínculos seguros ATP deben aplicar el análisis de URL en tiempo real para vínculos sospechosos y vínculos que apunten a archivos. |Sí |Sí |- |
|Los vínculos seguros ATP deben esperar a que se complete el análisis de URL antes de entregar el mensaje. |Sí |Sí |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>Datos adjuntos seguros

|Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|La acción de directiva de datos adjuntos seguros ATP debería ser |Cuarentena |Cuarentena |- |
|La protección ATP debe estar habilitada para OneDrive, SharePoint y Teams |Sí |Sí |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>Configuraciones varias

Esta configuración cubre una serie de características que no se ajustan necesariamente a categorías específicas más arriba. También puede encontrar una configuración de 1-desactivado.

Nombre de la característica de seguridad  |Recomendado |Agresiva  |Comment  |
|---------|---------|---------|---------|
|Crear registros de SPF |Sí |Sí |- |
|Configurar la firma DKIM para los dominios |Sí |Sí |- |
|Implementación de la elaboración de informes y la conformidad de mensajes basada en dominios (DMARC) con la acción de rechazar o poner en cuarentena |Action = None |acción = rechazar | |
|Implementar el complemento de mensajes de informe para mejorar los informes de usuarios finales de correos sospechosos |Sí |Sí |- |
|Programar informes de malware y correo no deseado |Sí |Sí |- |
|La fowarding? a de los dominios externos no debe ser permitida o supervisada |- |Sí |- |
|La auditoría unificada debe estar habilitada |Sí |Sí |- |
|IMAP debe estar deshabilitado cuando no es necesario |- |capacidad |- |
|El POP debe estar deshabilitado cuando no es necesario |- |capacidad |- |
|El envío autenticado SMTP debe estar desactivado cuando las aplicaciones no lo requieran |- |capacidad |- |
|EWS debe estar deshabilitado |- |capacidad |- |
|PowerShell |- |capacidad |- |
|Configurar el marco de directivas de remitente a un error difícil |-all |-all |- |
|Usar inteligencia simulada para los remitentes de listas blancas siempre que sea posible |Sí |Sí |- |
|Bloqueo perimetral basado en directorios (DBEB) |Habilitado |Habilitado |Tipo de dominio = autoritario |
