---
title: Recomendaciones de Microsoft para EOP y Office 365 la configuración de seguridad de ATP, recomendaciones, marco de directivas de remitente, informes de mensajes basados en dominio y conformidad, correo identificado por DomainKeys, pasos, cómo funciona, etc.
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: ¿Cuáles son los procedimientos recomendados para la configuración de seguridad de Exchange Online Protection (EOP) y la protección contra amenazas avanzada (ATP)? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué debe usar si desea ser más estricto? ¿Y qué extras obtiene si también usa la protección contra amenazas avanzada (ATP)?
ms.openlocfilehash: 9ef3344bd6497495d3d2279f570a8090d4fa4573
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677543"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Configuración recomendada para EOP y la seguridad de ATP de Office 365

**Exchange Online Protection (EOP)** es el núcleo de la seguridad de las suscripciones de Office 365 y ayuda a que los mensajes malintencionados lleguen a las bandejas de entrada de sus empleados. Pero con los nuevos y sofisticados ataques emergentes cada día, las protecciones mejoradas suelen ser necesarias. **Office 365 Advanced Threat Protection (ATP)** El plan 1 de ATP o el plan ATP 2 contienen características adicionales que ofrecen más niveles de seguridad, control e investigación a los administradores. 

Aunque se permite a los administradores de seguridad personalizar la configuración de seguridad, hay dos niveles de seguridad en EOP y en ATP de Office 365 que le recomendamos: **estándar** y **estricto**. El entorno y las necesidades de cada cliente son diferentes, pero creemos que estos niveles de configuraciones de filtrado de correo ayudarán a evitar que el correo no deseado llegue a la bandeja de entrada de sus empleados en la mayoría de las situaciones. 

En este tema se describe esta configuración recomendada por Microsoft para ayudar a proteger a los usuarios de Office 365.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo electrónico no deseado, anti-malware y antiphishing en EOP
Anti-spam, anti-malware y anti-phishing son características de EOP que los administradores pueden configurar. Se recomiendan las siguientes configuraciones.

### <a name="anti-spam-policy"></a>Directiva contra correo no deseado

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Acción de detección de correo no deseado|Mover mensaje a la carpeta Correo no deseado|Colocar el mensaje en cuarentena||
|Acción de detección de correo no deseado de confianza alta|Colocar el mensaje en cuarentena|Colocar el mensaje en cuarentena||
|Acción de detección de correo phishing|Colocar el mensaje en cuarentena|Colocar el mensaje en cuarentena||
|Acción de detección de correo electrónico de phish de confianza alta|Colocar el mensaje en cuarentena|Colocar el mensaje en cuarentena||
|Acción de detección de correo electrónico en masa|Mover mensaje a la carpeta Correo no deseado|Colocar el mensaje en cuarentena||
|Establecer el umbral de correo electrónico masivo en|6,5|4||
|Período de retención de cuarentena|30 días|30 días||
|Sugerencias de seguridad|Activado|Activado||
|Remitentes permitidos|Ninguno|Ninguno||
|Dominios de remitentes permitidos|Ninguno|Ninguno|No es necesario agregar dominios de su propiedad (también conocidos como _dominios aceptados_) a la lista de remitentes permitidos. De hecho, se considera un riesgo alto, ya que crea oportunidades para que los actores incorrectos le envíen correo que, de lo contrario, se filtraría. Use [inteligencia de identidad](learn-about-spoof-intelligence.md) en el centro de seguridad & cumplimiento de la página **configuración contra correo no deseado** para revisar todos los remitentes que suplantan dominios que forman parte de la organización o suplantación de dominios externos.|
|Remitentes bloqueados|Ninguno|Ninguno||
|Dominios de remitentes bloqueados|Ninguno|Ninguno||
|Frecuencia de notificación de correo no deseado del usuario final|Habilitado|Habilitado|3 días|
|Purga automática de cero horas|Activado|Activado|Para ZAP de correo no deseado y phish|
|MarkAsSpamBulkMail|Activado|Activado|Esta opción solo está disponible en PowerShell|

Hay varios otros parámetros en la Directiva contra correo no deseado denominados filtro de correo no deseado avanzado que se han dejado de estar en desuso en el momento de escribir este tema. Nuestra configuración recomendada para estos **son desactivar los** niveles estándar y estrictos:

|Nombre de la característica de seguridad|
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
|MarkAsSpamSpfRecordHardFail|

#### <a name="outbound-spam-filter-policy"></a>Directiva de filtro de correo no deseado saliente

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Límites de destinatarios de la Directiva de correo no deseado saliente-límite externo por hora|400|500||
|Límites de destinatarios de la Directiva de correo no deseado saliente: límite interno por hora|800|1000||
|Límites de destinatarios de la Directiva de correo no deseado saliente: límite diario|800|1000||
|Acción cuando un usuario supera los límites|Restringir al usuario el envío de correo|Restringir al usuario el envío de correo||

### <a name="anti-malware-policy"></a>Directiva antimalware

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Respuesta de detección de malware|No|No|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pondrá en cuarentena y solo un administrador podrá publicarlo.|
|"Filtro de tipo de datos adjuntos comunes" para bloquear tipos de archivos sospechosos|Activado|Activado||
|Purga automática de cero horas de malware|Activado|Activado||
|Notificar a los remitentes internos del mensaje no entregado|Deshabilitado|Deshabilitado||
|Notificar a remitentes externos del mensaje no entregado|Deshabilitado|Deshabilitado||

### <a name="anti-phishing-policy"></a>Directiva contra la suplantación de identidad

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Habilitar la protección contra la suplantación de identidad|Activado|Activado||
|Habilitar remitente sin autenticar (etiquetado)|Activado|Activado||
|Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio|Mover mensaje a las carpetas de correo no deseado de los destinatarios|Poner en cuarentena el mensaje||

## <a name="office-365-advanced-threat-protection-atp-security"></a>Seguridad de la protección contra amenazas avanzada (ATP) de Office 365
Los beneficios de seguridad adicionales incluyen una suscripción a la protección contra amenazas avanzada de Office 365. Para obtener las últimas noticias e información, puede ver las novedades [de Office 365 ATP](whats-new-in-office-365-atp.md). 

Office 365 ATP incluye directivas de datos adjuntos seguros y vínculos seguros para evitar que se entregue el correo electrónico con datos adjuntos potencialmente malintencionados y evitar que los usuarios haga clic en direcciones URL potencialmente no seguras.

> [!IMPORTANT]
> Anti-phishing avanzado es una de las ventajas de una suscripción de ATP de Office 365. Habilitado de forma predeterminada, la protección contra suplantación de identidad (phishing) ***debe*** configurarse mediante directivas antes de empezar a filtrar correo. Olvidarse de configurar las directivas antiphishing podría exponer a los usuarios a mensajes de correo electrónico arriesgados. Asegúrese de configurar las directivas contra suplantación de identidad (phishing) después de agregar una suscripción a Office 365 ATP.

Si ha agregado una suscripción de ATP de Office 365 a su EOP, establezca las siguientes configuraciones.

### <a name="office-atp-anti-phishing-policy"></a>Directiva contra la suplantación de identidad ATP de Office
Los clientes de EOP establecen una directiva básica antiphishing, pero con Office 365 ATP, los administradores obtienen más características y control para ayudar a prevenir, detectar y remidiate contra ataques.

|Nombre de la característica de seguridad de suplantación|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|(Editar Directiva de suplantación) Agregar usuarios para protegerlos|Activado|Activado|Depende de su organización, pero le recomendamos que agregue usuarios en los roles clave. Internamente, pueden ser su CEO, director financiero y otros líderes senior. Externamente, pueden incluir miembros del Consejo o su Consejo de administración.|
|(Editar Directiva de suplantación) Incluir automáticamente los dominios de su propiedad|Activado|Activado||
|(Editar Directiva de suplantación) Incluir dominios personalizados|Activado|Activado|Depende de su organización, pero se recomienda agregar los dominios con los que interactúa con la mayoría de los que no son de su propiedad.|
|Si un usuario suplantado ha enviado el correo electrónico que ha especificado|Poner en cuarentena el mensaje|Poner en cuarentena el mensaje||
|Si se envía un correo electrónico por un dominio suplantado especificado|Poner en cuarentena el mensaje|Poner en cuarentena el mensaje||
|Mostrar sugerencia para usuarios suplantados|Activado|Activado||
|Mostrar sugerencia para dominios suplantados|Activado|Activado||
|Mostrar sugerencia para caracteres inusuales|Activado|Activado||
|Habilitar la inteligencia de buzones|Activado|Activado||
|Habilitar la protección de suplantación basada en la inteligencia de buzones|Activado|Activado||
|Si un usuario suplantado envía un correo electrónico protegido por la inteligencia de buzones|Mover mensaje a las carpetas de correo no deseado de los destinatarios|Poner en cuarentena el mensaje||
|(Editar Directiva de suplantación) Agregar dominios y remitentes de confianza|Ninguno|Ninguno|Depende de su organización, pero se recomienda agregar usuarios o dominios que se marquen incorrectamente como phish debido solo a la suplantación y no a otros filtros.|

|Nombre de la característica de seguridad de falsificación|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Habilitar la protección contra la suplantación de identidad|Activado|Activado||
|Habilitar remitente sin autenticar (etiquetado)|Activado|Activado||
|Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio|Mover mensaje a las carpetas de correo no deseado de los destinatarios|Poner en cuarentena el mensaje||
|EnableAuthenticationSafetyTip|True|True|Esta opción solo está disponible en PowerShell|
|EnableAuthenticationSoftPassSafetyTip|False|True|Esta opción solo está disponible en PowerShell|
|EnableSuspiciousSafetyTip|False|True|Esta opción solo está disponible en PowerShell|
|TreatSoftPassAsAuthenticated|True|False|Esta opción solo está disponible en PowerShell|

|Nombre de la característica de seguridad de configuración avanzada|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Umbrales de suplantación de identidad avanzada|2-agresivo|3-más agresivo||

### <a name="safe-links-settings"></a>Configuración de vínculos seguros

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Usar vínculos seguros de ATP en aplicaciones de Office 365, Office para iOS y Android|Habilitado|Habilitado|Esto está dentro de las directivas de vínculos a prueba de ATP que se aplican a toda la organización|
No realizar seguimiento cuando los usuarios hagan clic en vínculos seguros|Deshabilitado|Deshabilitado|Esto está dentro de las directivas de vínculos a prueba de ATP que se aplican a toda la organización|
|No permitir que los usuarios hagan clic en los vínculos seguros a la dirección URL original|Habilitado|Habilitado|Esto está dentro de las directivas de vínculos a prueba de ATP que se aplican a toda la organización|
|Acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Activado|Activado||
|Aplicar un análisis de URL en tiempo real de vínculos y vínculos sospechosos que señalan a archivos|Habilitado|Habilitado||
|Esperar a que se complete el análisis de URL antes de entregar el mensaje|Habilitado|Habilitado||
|Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización|Habilitado|Habilitado||

### <a name="safe-attachments"></a>Datos adjuntos seguros

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Activar ATP para SharePoint, OneDrive y Microsoft Teams.|Habilitado|Habilitado||
|Datos adjuntos seguros de ATP respuesta de malware desconocida|Desbloquear|Desbloquear||
|Redirigir datos adjuntos en detección|Habilitado|Habilitado|Redirigir a la dirección de correo electrónico de un administrador de seguridad que sabe cómo determinar si los datos adjuntos son malware o no.|
|Respuesta de datos adjuntos seguros de ATP si se produce un análisis de malware para archivos adjuntos de tiempo de espera o error|Habilitado|Habilitado||

## <a name="miscellaneous-settings-for-eop-or-office-365-atp"></a>Configuración variada para EOP u Office 365 ATP

Esta configuración cubre una serie de características que no se ajustan necesariamente a categorías específicas más arriba. Algunas de las opciones son externas al centro de seguridad & cumplimiento.

Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|[Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sí|Sí||
|[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)|Sí|Sí||
|[Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)|Sí|Sí|Use Action = Quarantine para Standard y Action = Reject para STRICT.|
|Implementar el complemento de mensajes de informe para mejorar los informes de usuarios finales de correos sospechosos|Sí|Sí||
|Programar informes de malware y correo no deseado|Sí|Sí||
|No se debe permitir ni supervisar el reenvío automático a dominios externos|Sí|Sí||
|La auditoría unificada debe estar habilitada|Sí|Sí||
|Conectividad IMAP a buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad POP al buzón de correo|Deshabilitado|Deshabilitado||
|Envío autenticado mediante SMTP al buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad de EWS al buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad de PowerShell|Deshabilitado|Deshabilitado||
|Usar inteligencia simulada para los remitentes de listas blancas siempre que sea posible|Sí|Sí||
|Bloqueo perimetral basado en directorios (DBEB)|Habilitado|Habilitado|Tipo de dominio = autoritario|
|[Configurar la autenticación multifactor para todas las cuentas de administrador](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||
