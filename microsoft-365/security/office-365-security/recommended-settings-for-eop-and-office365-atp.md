---
title: Recomendaciones de Microsoft para EOP y Office 365 la configuración de seguridad de ATP, las recomendaciones, el marco de directivas de remitente, la creación de informes de mensajes basados en dominios y su conformidad, el correo identificado por DomainKeys, los pasos, cómo funciona, las líneas de base de seguridad, las líneas de base para EOP, líneas de base para ATP, configurar ATP, configurar EOP, configurar ATP, configurar EOP, configuración de seguridad
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
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
ms.openlocfilehash: b7c98fe4b362a5be72be9e103a2602cd4954e028
ms.sourcegitcommit: 3b6e226d07b5227054d5c8d1a012694caf88f50a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587290"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Configuración recomendada para EOP y la seguridad de ATP de Office 365

**Exchange Online Protection (EOP)** es el núcleo de la seguridad de las suscripciones de Office 365 y ayuda a que los mensajes malintencionados lleguen a las bandejas de entrada de sus empleados. Pero con los nuevos y sofisticados ataques emergentes cada día, las protecciones mejoradas suelen ser necesarias. **Office 365 Advanced Threat Protection (ATP)** El plan 1 de ATP o el plan ATP 2 contienen características adicionales que ofrecen más niveles de seguridad, control e investigación a los administradores.

Aunque se permite a los administradores de seguridad personalizar la configuración de seguridad, hay dos niveles de seguridad en EOP y en ATP de Office 365 que le recomendamos: **estándar** y **estricto**. El entorno y las necesidades de cada cliente son diferentes, pero creemos que estos niveles de configuraciones de filtrado de correo ayudarán a evitar que el correo no deseado llegue a la bandeja de entrada de sus empleados en la mayoría de las situaciones.

> [!IMPORTANT]
> La configuración del correo electrónico no deseado tiene que estar habilitada en el buzón para que el filtrado funcione correctamente. Esta opción está habilitada de forma predeterminada, pero debe comprobarse si el filtrado parece no funcionar. Lea [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) para obtener más información. 

En este tema se describe esta configuración recomendada por Microsoft para ayudar a proteger a los usuarios de Office 365.

> [!TIP]
> Hay un nuevo módulo de PowerShell que puede descargar, llamado analizador de configuración de la protección contra amenazas avanzada de Office 365 (ORCA), que ayuda a determinar algunas de estas opciones de configuración. Cuando se ejecuta como administrador en el espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes. Puede descargar este módulo en https://www.powershellgallery.com/packages/ORCA/.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo electrónico no deseado, anti-malware y antiphishing en EOP

Anti-spam, anti-malware y anti-phishing son características de EOP que los administradores pueden configurar. Se recomiendan las siguientes configuraciones.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de la Directiva contra correo no deseado de EOP

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Acción de detección de correo no deseado|Mover mensaje a la carpeta Correo no deseado|Colocar el mensaje en cuarentena||
|Acción de detección de correo no deseado de confianza alta|Colocar el mensaje en cuarentena|Colocar el mensaje en cuarentena||
|Acción de detección de correo phishing|Colocar el mensaje en cuarentena|Colocar el mensaje en cuarentena||
|Acción de detección de correo electrónico de phish de confianza alta|Colocar el mensaje en cuarentena|Colocar el mensaje en cuarentena||
|Acción de detección de correo electrónico en masa|Mover mensaje a la carpeta Correo no deseado|Colocar el mensaje en cuarentena||
|Establecer el umbral de correo electrónico masivo en|6 |4 |Actualmente, el valor predeterminado es 7, pero se recomienda cambiarlo a 6. Para obtener más información, vea [valores de nivel de queja masiva](bulk-complaint-level-values.md).|
|Período de retención de cuarentena|30 días|30 días||
|Sugerencias de seguridad|Activado|Activado||
|Remitentes permitidos|Ninguno|Ninguno||
|Dominios de remitentes permitidos|Ninguno|Ninguno|No es necesario agregar dominios de su propiedad (también conocidos como _dominios aceptados_) a la lista de remitentes permitidos. De hecho, se considera un riesgo alto, ya que crea oportunidades para que los actores incorrectos le envíen correo que, de lo contrario, se filtraría. Use [inteligencia de identidad](learn-about-spoof-intelligence.md) en el centro de seguridad & cumplimiento de la página **configuración contra correo no deseado** para revisar todos los remitentes que suplantan dominios que forman parte de la organización o suplantación de dominios externos.|
|Remitentes bloqueados|Ninguno|Ninguno||
|Dominios de remitentes bloqueados|Ninguno|Ninguno||
|Frecuencia de notificación de correo no deseado del usuario final|Habilitado|Habilitado|3 días|
|Purga automática de cero horas|Activado|Activado|Para ZAP de correo no deseado y phish|
|MarkAsSpamBulkMail|Activado|Activado|Esta opción solo está disponible en PowerShell|

Hay varios otros parámetros en la Directiva contra correo no deseado denominado filtro de correo no deseado avanzado (ASF) que están en desuso. Se comunicará más información sobre las escalas de tiempo de la depreciación de estas características fuera de este tema.

Le recomendamos que **desactive estos valores para** los niveles estándar y estricto:

|Nombre de la característica de seguridad|Comentarios|
|---------|---------|
|IncreaseScoreWithImageLinks||
|IncreaseScoreWithNumericIps||
|IncreaseScoreWithRedirectToOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamEmptyMessages||
|MarkAsSpamJavaScriptInHtml||
|MarkAsSpamFramesInHtml||
|MarkAsSpamObjectTagsInHtml||
|MarkAsSpamEmbedTagsInHtml||
|MarkAsSpamFormTagsInHtml||
|MarkAsSpamWebBugsInHtml||
|MarkAsSpamSensitiveWordList||
|MarkAsSpamFromAddressAuthFail||
|MarkAsSpamNdrBackscatter||
|MarkAsSpamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>Configuración de directiva de filtro de correo no deseado de EOP

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Límites de destinatarios de la Directiva de correo no deseado saliente-límite externo por hora|500|400||
|Límites de destinatarios de la Directiva de correo no deseado saliente: límite interno por hora|1000|800||
|Límites de destinatarios de la Directiva de correo no deseado saliente: límite diario|1000|800||
|Acción cuando un usuario supera los límites|Restringir al usuario el envío de correo|Restringir al usuario el envío de correo||

### <a name="eop-anti-malware-policy-settings"></a>Configuración de la Directiva de EOP contra malware

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Respuesta de detección de malware|No|No|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pondrá en cuarentena y solo un administrador podrá publicarlo.|
|"Filtro de tipos de datos adjuntos comunes" para bloquear tipos de archivos sospechosos|Activado|Activado||
|Purga automática de cero horas de malware|Activado|Activado||
|Notificar a los remitentes internos del mensaje no entregado|Deshabilitado|Deshabilitado||
|Notificar a remitentes externos del mensaje no entregado|Deshabilitado|Deshabilitado||

### <a name="eop-anti-phishing-policy-settings"></a>Configuración de la Directiva de protección contra suplantación de EOP

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Habilitación de la protección contra la suplantación de identidad|Activado|Activado||
|Habilitar remitente sin autenticar (etiquetado)|Activado|Activado||
|Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio|Mover mensaje a las carpetas de correo no deseado de los destinatarios|Poner en cuarentena el mensaje||

## <a name="office-365-advanced-threat-protection-security"></a>Seguridad de la protección contra amenazas avanzada de Office 365

Los beneficios de seguridad adicionales incluyen una suscripción a la protección contra amenazas avanzada (ATP) de Office 365. Para obtener las últimas noticias e información, puede ver las novedades [de Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP incluye directivas de datos adjuntos seguros y vínculos seguros para evitar que se entregue el correo electrónico con datos adjuntos potencialmente malintencionados y evitar que los usuarios haga clic en direcciones URL potencialmente no seguras.

> [!IMPORTANT]
> Anti-phishing avanzado es una de las ventajas de una suscripción de ATP de Office 365. Aunque está habilitado de forma predeterminada, ***debe*** configurar al menos una directiva antiphishing antes de que pueda empezar a filtrar correo. Olvidarse de configurar las directivas antiphishing podría exponer a los usuarios a mensajes de correo electrónico arriesgados. Asegúrese de configurar las directivas contra suplantación de identidad (phishing) después de agregar una suscripción a Office 365 ATP.

Si ha agregado una suscripción de ATP de Office 365 a su EOP, establezca las siguientes configuraciones.

### <a name="office-atp-anti-phishing-policy-settings"></a>Configuración de la Directiva contra phishing de ATP de Office

Los clientes de EOP obtienen contra la suplantación de identidad (phishing) básica como se describió anteriormente, pero Office 365 ATP incluye más características y control para ayudar a prevenir, detectar y corregir los ataques.

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
|Habilitación de la protección contra la suplantación de identidad|Activado|Activado||
|Habilitar remitente sin autenticar (etiquetado)|Activado|Activado||
|Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio|Mover mensaje a las carpetas de correo no deseado de los destinatarios|Poner en cuarentena el mensaje||
|EnableSuspiciousSafetyTip|False|True|Esta opción solo está disponible en PowerShell|
|TreatSoftPassAsAuthenticated|True|False|Esta opción solo está disponible en PowerShell|


|Nombre de la característica de seguridad de configuración avanzada|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Umbrales de suplantación de identidad avanzada|2-agresivo|3-más agresivo||

### <a name="safe-links-settings"></a>Configuración de vínculos seguros

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Usar vínculos seguros de ATP en aplicaciones de Office 365, Office para iOS y Android|Habilitado|Habilitado|Esto está dentro de las directivas de vínculos a prueba de ATP que se aplican a toda la organización|
No realizar seguimiento cuando los usuarios hagan clic en vínculos seguros|Deshabilitado|Deshabilitado|Esto es para ambas directivas que se aplican a toda la organización y a todas las directivas que se aplican a destinatarios específicos.|
|No permitir que los usuarios hagan clic en los vínculos seguros a la dirección URL original|Habilitado|Habilitado|Esto es tanto para las directivas que se aplican a toda la organización como para todas las directivas que se aplican a destinatarios específicos.|
|Acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Activado|Activado||
|Aplicar un análisis de URL en tiempo real de vínculos y vínculos sospechosos que señalan a archivos|Habilitado|Habilitado||
|Esperar a que se complete el análisis de URL antes de entregar el mensaje|Habilitado|Habilitado||
|Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización|Habilitado|Habilitado||

### <a name="safe-attachments"></a>Datos adjuntos seguros

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|Activar ATP para SharePoint, OneDrive y Microsoft Teams|Habilitado|Habilitado||
|Datos adjuntos seguros de ATP respuesta de malware desconocida|Desbloquear|Desbloquear||
|Redirigir datos adjuntos en detección|Habilitado|Habilitado|Redirigir a la dirección de correo electrónico de un administrador de seguridad que sabe cómo determinar si los datos adjuntos son malware o no.|
|Respuesta de datos adjuntos seguros de ATP si se produce un análisis de malware para archivos adjuntos de tiempo de espera o error|Habilitado|Habilitado||


## <a name="related-topics"></a>Temas relacionados

- ¿Necesita procedimientos recomendados con **las reglas de transporte de Exchange/flujo de correo**de Exchange? Consulte [este artículo](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) para obtener más información.

- Enviar correos sospechosos, sospechosos de ser correo no deseado, phish o direcciones URL a Microsoft para su análisis. Use las instrucciones de los **envíos de administración** de [este artículo](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

- Use estos vínculos para obtener información sobre cómo **configurar** el [servicio de EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)y cómo **configurar** la [protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (No olvide ver las direcciones útiles en '[proteger contra amenazas en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)').

- Las **líneas de base de seguridad para Windows** se pueden encontrar [aquí](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO/local y para la seguridad basada en Intune, [aquí](https://docs.microsoft.com/intune/protect/security-baselines). Por último, puede encontrar [aquí](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)una comparación entre la protección contra amenazas avanzada (ATP) de Microsoft defender y las líneas de seguridad de Windows Intune.
