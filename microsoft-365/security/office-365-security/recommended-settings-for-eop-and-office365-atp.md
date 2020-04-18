---
title: Recomendaciones de Microsoft para EOP y Office 365 la configuración de seguridad de ATP, las recomendaciones, el marco de directivas de remitente, la creación de informes de mensajes basados en dominios y su conformidad, el correo identificado por DomainKeys, los pasos, cómo funciona, las líneas de base de seguridad, las líneas de base para EOP, las líneas de base para ATP, la configuración de EOP, configurar EOP
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
ms.openlocfilehash: 0d5d626da8f8bdcdc234f578145db0dfde2c06a5
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547613"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Configuración recomendada para EOP y la seguridad de ATP de Office 365

**Exchange Online Protection (EOP)** es el núcleo de la seguridad de las suscripciones de Office 365 y ayuda a que los mensajes malintencionados lleguen a las bandejas de entrada de sus empleados. Pero con los nuevos y sofisticados ataques emergentes cada día, las protecciones mejoradas suelen ser necesarias. **Office 365 Advanced Threat Protection (ATP)** El plan 1 de ATP o el plan ATP 2 contienen características adicionales que ofrecen más niveles de seguridad, control e investigación a los administradores.

Aunque se permite a los administradores de seguridad personalizar la configuración de seguridad, hay dos niveles de seguridad en EOP y en ATP de Office 365 que le recomendamos: **estándar** y **estricto**. El entorno y las necesidades de cada cliente son diferentes, pero creemos que estos niveles de configuraciones de filtrado de correo ayudarán a evitar que el correo no deseado llegue a la bandeja de entrada de sus empleados en la mayoría de las situaciones.

> [!IMPORTANT]
> La regla de correo no deseado debe estar habilitada en un buzón para que el filtrado funcione correctamente. Está habilitado de forma predeterminada, pero debe comprobarlo si el filtrado no parece funcionar. Para obtener más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

En este tema se describe esta configuración recomendada por Microsoft para ayudar a proteger a los usuarios de Office 365.

> [!TIP]
> Hay un nuevo módulo de PowerShell que puede descargar, llamado analizador de configuración de la protección contra amenazas avanzada de Office 365 (ORCA), que ayuda a determinar algunas de estas opciones de configuración. Cuando se ejecuta como administrador en el espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes. Puede descargar este módulo en https://www.powershellgallery.com/packages/ORCA/.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo electrónico no deseado, anti-malware y antiphishing en EOP

Anti-spam, anti-malware y anti-phishing son características de EOP que los administradores pueden configurar. Se recomiendan las siguientes configuraciones.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de la Directiva contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|Acción de detección de **correo no deseado** <br/><br/> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo no deseado de confianza alta** <br/><br/> _HighConfidenceSpamAction_|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo phishing** <br/><br/> _PhishSpamAction_|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo de phishing de alta confianza** <br/><br/> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo electrónico en masa** <br/><br/> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Umbral de correo electrónico masivo <br/><br/> _BulkThreshold_|6 |4 |Actualmente, el valor predeterminado es 7, pero se recomienda cambiarlo a 6. Para obtener más información, consulte [nivel de queja masiva (BCL) en Office 365](bulk-complaint-level-values.md).|
|Período de retención de cuarentena <br/><br/> _QuarantineRetentionPeriod_|30 días|30 días||
|**Sugerencias de seguridad** <br/><br/> _InlineSafetyTipsEnabled_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|Remitentes permitidos <br/><br/> _AllowedSenders_|Ninguno|Ninguno||
|Dominios de remitentes permitidos <br/><br/> _AllowedSenderDomains_|Ninguno|Ninguno|No es necesario agregar dominios de su propiedad (también conocidos como _dominios aceptados_) a la lista de remitentes permitidos. De hecho, se considera un riesgo alto, ya que crea oportunidades para que los actores incorrectos le envíen correo que, de lo contrario, se filtraría. Use [inteligencia de identidad](learn-about-spoof-intelligence.md) en el centro de seguridad & cumplimiento de la página **configuración contra correo no deseado** para revisar todos los remitentes que imitan direcciones de correo electrónico de remitentes en los dominios de correo electrónico de su organización o direcciones de correo electrónico de remitentes suplantados en dominios externos.|
|Remitentes bloqueados <br/><br/> _BlockedSenders_|Ninguno|Ninguno||
|Dominios de remitentes bloqueados <br/><br/> _BlockedSenderDomains_|Ninguno|Ninguno||
|**Habilitar las notificaciones de correo no deseado para el usuario final** <br/><br/> _EnableEndUserSpamNotifications_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Enviar notificaciones de correo no deseado para el usuario final cada (días)** <br/><br/> _EndUserSpamNotificationFrequency_|3 días|3 días||
|**ZAP de correo no deseado** <br/><br/> _SpamZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**ZAP de phish** <br/><br/> _PhishZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Activado|Activado|Esta opción solo está disponible en PowerShell.|

Hay otras configuraciones avanzadas de filtro de correo no deseado (ASF) en las directivas contra correo no deseado que están en desuso. Se comunicará más información sobre las escalas de tiempo de la depreciación de estas características fuera de este tema.

Le recomendamos que **desactive esta configuración ASF** para niveles **estándar** y **estrictos** . Para obtener más información acerca de la configuración de ASF, consulte [Configuración avanzada de filtro de correo no deseado (ASF) en Office 365](advanced-spam-filtering-asf-options.md).

| Nombre de la característica de seguridad | Comentarios |
|----|---|
|**Vínculos de imagen a sitios remotos** (_IncreaseScoreWithImageLinks_)||
|**Dirección IP numérica en la dirección URL** (_IncreaseScoreWithNumericIps_)||
|**Redireccionamiento UL a otro puerto** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Dirección URL de los sitios Web. BIZ o. info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensajes vacíos** (_MarkAsSpamEmptyMessages_)||
|**JavaScript o VBScript en HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Etiquetas frame o iframe en HTML** (_MarkAsSpamFramesInHtml_)||
|**Etiquetas de objeto en HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Etiquetas embed en HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Etiquetas de formulario en HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Web bugs en HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Aplicar lista de palabras confidenciales** (_MarkAsSpamSensitiveWordList_)||
|**Registro de SPF: error grave** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtrado de identificador de remitente condicional: error grave** (_MarkAsSpamFromAddressAuthFail_)||
|**Retrodispersión de NDR** (_MarkAsSpamNdrBackscatter_)||

#### <a name="eop-outbound-spam-policy-settings"></a>Configuración de la Directiva de correo no deseado de EOP

Para crear y configurar directivas de correo no deseado saliente, consulte [configurar el filtrado de correo no deseado saliente en Office 365](configure-the-outbound-spam-policy.md).

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|**Número máximo de destinatarios por usuario: límite horario externo** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**Número máximo de destinatarios por usuario: límite interno por hora** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Número máximo de destinatarios por usuario: límite diario** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Acción cuando un usuario supera los límites** <br/><br/> _ActionWhenThresholdReached_|**Restringir al usuario el envío de correo** <br/><br/> `BlockUser`|**Restringir al usuario el envío de correo** <br/><br/> `BlockUser`||

### <a name="eop-anti-malware-policy-settings"></a>Configuración de la Directiva de EOP contra malware

Para crear y configurar directivas antimalware, vea [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|**¿Desea notificar a los destinatarios si sus mensajes están en cuarentena?** <br/><br/> _Acción_|No <br/><br/> _DeleteMessage_|No <br/><br/> _DeleteMessage_|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pone en cuarentena y solo puede ser lanzado por un administrador.|
|**Filtro de tipos de datos adjuntos comunes** <br/><br/> _EnableFileFilter_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Esta opción pone en cuarentena los mensajes que contienen datos adjuntos ejecutables basados en el tipo de archivo, independientemente del contenido de datos adjuntos.|
|**Purga automática de cero horas de malware** <br/><br/> _ZapEnabled_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Notificar a los remitentes internos** del mensaje no entregado <br/><br/> _EnableInternalSenderNotifications_|Deshabilitado <br/><br/> `$false`|Deshabilitado <br/><br/> `$false`||
|**Notificar a remitentes externos** del mensaje no entregado <br/><br/> _EnableExternalSenderNotifications_|Deshabilitado <br/><br/> `$false`|Deshabilitado <br/><br/> `$false`||

### <a name="eop-default-anti-phishing-policy-settings"></a>Configuración de directiva antiphishing predeterminada de EOP

Solo puede configurar estas opciones en las organizaciones de Office 365 con buzones de Exchange Online. Para configurar estas opciones, vea [Configure the default anti-phishing Policy in EOP](configure-anti-phishing-policies-eop.md).

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|**Habilitación de la protección contra la suplantación de identidad** <br/><br/> _EnableAntispoofEnforcement_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Habilitar remitente sin autenticar** <br/><br/> _EnableUnauthenticatedSender_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para los remitentes suplantados no identificados. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).|
|**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio** <br/><br/> _AuthenticationFailAction_|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esto se aplica a los remitentes bloqueados en [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).|

## <a name="office-365-advanced-threat-protection-security"></a>Seguridad de la protección contra amenazas avanzada de Office 365

Los beneficios de seguridad adicionales incluyen una suscripción a la protección contra amenazas avanzada (ATP) de Office 365. Para obtener las últimas noticias e información, puede ver las novedades [de Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP incluye directivas de datos adjuntos seguros y vínculos seguros para evitar que se entregue el correo electrónico con datos adjuntos potencialmente malintencionados y evitar que los usuarios haga clic en direcciones URL potencialmente no seguras.

> [!IMPORTANT]
> Anti-phishing avanzado es una de las ventajas de una suscripción de ATP de Office 365. Aunque está habilitado de forma predeterminada, ***debe*** configurar al menos una directiva antiphishing antes de que pueda empezar a filtrar correo. Olvidarse de configurar las directivas antiphishing podría exponer a los usuarios a mensajes de correo electrónico arriesgados. Asegúrese de configurar las directivas contra suplantación de identidad (phishing) después de agregar una suscripción a Office 365 ATP.

Si ha agregado una suscripción de ATP de Office 365 a su EOP, establezca las siguientes configuraciones.

### <a name="office-atp-anti-phishing-policy-settings"></a>Configuración de la Directiva contra phishing de ATP de Office

Los clientes de EOP obtienen contra la suplantación de identidad (phishing) básica como se describió anteriormente, pero Office 365 ATP incluye más características y control para ayudar a prevenir, detectar y corregir los ataques. Para crear y configurar estas directivas, consulte [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).

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

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Configuración de suplantación en las directivas antiphishing de ATP

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|Usuarios protegidos: **Agregar usuarios para protegerlos** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|Activado <br/><br/> `$true` <br/><br/> \<lista de usuarios\>|Activado <br/><br/> `$true` <br/><br/> \<lista de usuarios\>|Depende de su organización, pero le recomendamos que agregue usuarios en los roles clave. Internamente, pueden ser su CEO, director financiero y otros líderes senior. Externamente, pueden incluir miembros del Consejo o su Consejo de administración.|
|Dominios protegidos: **incluir automáticamente los dominios de su propiedad** <br/><br/> _EnableOrganizationDomainsProtection_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|Dominios protegidos: **incluir dominios personalizados** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Activado <br/><br/> `$true` <br/><br/> \<lista de dominios\>|Activado <br/><br/> `$true` <br/><br/> \<lista de dominios\>|Depende de su organización, pero se recomienda agregar los dominios con los que interactúa con frecuencia y que no son de su propiedad.|
|Usuarios protegidos: **si un usuario suplantado envía un correo electrónico** <br/><br/> _TargetedUserProtectionAction_|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|Dominios protegidos: **si un dominio suplantado envía un correo electrónico** <br/><br/> _TargetedUserProtectionAction_|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|**Mostrar sugerencia para usuarios suplantados** <br/><br/> _EnableSimilarUsersSafetyTips_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Mostrar sugerencia para dominios suplantados** <br/><br/> _EnableSimilarDomainsSafetyTips_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Mostrar sugerencia para caracteres inusuales** <br/><br/> _EnableUnusualCharactersSafetyTips_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**¿Habilitar la inteligencia de buzones?** <br/><br/> _EnableMailboxIntelligence_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**¿Habilitar la protección de suplantación basada en buzones de correo?** <br/><br/> _EnableMailboxIntelligenceProtection_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Si un usuario suplantado envía un correo electrónico protegido por la inteligencia de buzones** <br/><br/> _MailboxIntelligenceProtectionAction_|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|**Remitentes de confianza** <br/><br/> _ExcludedSenders_|Ninguno|Ninguno|Depende de su organización, pero se recomienda agregar usuarios que se marquen correctamente como phish debido a la suplantación y no a otros filtros.|
|**Dominios de confianza** <br/><br/> _ExcludedDomains_|Ninguno|Ninguno|Depende de su organización, pero se recomienda agregar dominios que se marquen incorrectamente como phish debido a la suplantación y no a otros filtros.|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Configuración de suplantación en las directivas antiphishing de ATP

Tenga en cuenta que estos son los mismos valores de configuración que están disponibles en la [configuración de la Directiva contra correo no deseado en EOP](#eop-anti-spam-policy-settings).

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|**Habilitación de la protección contra la suplantación de identidad** <br/><br/> _EnableAntispoofEnforcement_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Habilitar remitente sin autenticar** <br/><br/> _EnableUnauthenticatedSender_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para los remitentes suplantados no identificados. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).|
|**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio** <br/><br/> _AuthenticationFailAction_|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esto se aplica a los remitentes bloqueados en [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Configuración avanzada en las directivas antiphishing de ATP

| Nombre de la característica de seguridad | Estándar | Estricta | Comentario |
|---|---|---|---|
|**Umbrales de suplantación de identidad avanzada** <br/><br/> _PhishThresholdLevel_|**2-agresivo** <br/><br/> `2`|**3-más agresivo** <br/><br/> `3`||

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

- Los administradores y los usuarios pueden enviar falsos positivos (correo electrónico bueno marcado como no válido) y falsos negativos (se permite correo electrónico incorrecto) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estos vínculos para obtener información sobre cómo **configurar** el [servicio de EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)y cómo **configurar** la [protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (No olvide ver las direcciones útiles en '[proteger contra amenazas en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)').

- Las **líneas de base de seguridad para Windows** se pueden encontrar [aquí](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO/local y para la seguridad basada en Intune, [aquí](https://docs.microsoft.com/intune/protect/security-baselines). Por último, puede encontrar [aquí](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)una comparación entre la protección contra amenazas avanzada (ATP) de Microsoft defender y las líneas de seguridad de Windows Intune.
