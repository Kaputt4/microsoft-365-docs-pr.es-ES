---
title: Recomendaciones de Microsoft para EOP y defender para la configuración de seguridad de Office 365, recomendaciones, marco de directivas de remitente, informes de mensajes basados en dominio y conformidad, correo identificado por DomainKeys, pasos, cómo funciona, Security Baselines, Baselines for EOP, Baselines for defender for Office 365, set up defender for Office 365, set up EOP, configure defender for Office 365, configurar EOP, configuración de seguridad
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: ¿Cuáles son los procedimientos recomendados para la configuración de seguridad de Exchange Online Protection (EOP) y defender para Office 365? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué debe usar si desea ser más estricto? ¿Y qué extras obtiene si también usa defender para Office 365?
ms.openlocfilehash: ab8640574d15cc1950ac0873ef90c4d984553510
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845653"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configuración recomendada para EOP y Microsoft defender para Office 365 Security

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** es el núcleo de la seguridad de las suscripciones de Microsoft 365 y ayuda a que los mensajes malintencionados lleguen a las bandejas de entrada de sus empleados. Pero con los nuevos y sofisticados ataques emergentes cada día, las protecciones mejoradas suelen ser necesarias. **Microsoft defender para Office 365** El plan 1 o el plan 2 contienen características adicionales que ofrecen más niveles de seguridad, control e investigación a los administradores.

Aunque se permite a los administradores de seguridad personalizar la configuración de seguridad, hay dos niveles de seguridad en EOP y en Microsoft defender para Office 365 que se recomiendan: **estándar** y **estricto**. El entorno y las necesidades de cada cliente son diferentes, pero creemos que estos niveles de filtrado ayudarán a evitar que el correo no deseado llegue a la bandeja de entrada de sus empleados en la mayoría de las situaciones.

Para aplicar automáticamente la configuración estándar o estricta a los usuarios, vea [directivas de seguridad preestablecidas en EOP y Microsoft defender para Office 365](preset-security-policies.md).

> [!NOTE]
> La regla de correo no deseado debe estar habilitada en los buzones para que el filtrado funcione correctamente. Está habilitado de forma predeterminada, pero debe comprobarlo si el filtrado no parece funcionar. Para obtener más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

En este artículo se describe la configuración predeterminada y también la configuración estándar y estricta recomendada para ayudar a proteger a los usuarios.

> [!TIP]
> El módulo analizador de configuración de la protección contra amenazas avanzada de Office 365 (ORCA) para PowerShell puede ayudarle a (administradores) a encontrar los valores actuales de esta configuración. Concretamente, el cmdlet **Get-ORCAReport** genera una evaluación de las opciones de protección contra correo electrónico no deseado, antiphishing y otras opciones de higiene de mensajes. Puede descargar el módulo ORCA que se encuentra en <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo electrónico no deseado, anti-malware y antiphishing en EOP

La protección contra correo electrónico no deseado, antimalware y antiphishing son características de EOP que los administradores pueden configurar. Se recomiendan las siguientes configuraciones estándar o estrictas.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de la Directiva contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|Acción de detección de **correo no deseado** <br/><br/> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo no deseado de confianza alta** <br/><br/> _HighConfidenceSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo phishing** <br/><br/> _PhishSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo de phishing de alta confianza** <br/><br/> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo electrónico en masa** <br/><br/> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Umbral de correo electrónico masivo <br/><br/> _BulkThreshold_|7 |6 |4 |Para obtener más información, consulte [nivel de queja masiva (BCL) en Office 365](bulk-complaint-level-values.md).|
|Período de retención de cuarentena <br/><br/> _QuarantineRetentionPeriod_|15 días|30 días|30 días||
|**Sugerencias de seguridad** <br/><br/> _InlineSafetyTipsEnabled_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|Remitentes permitidos <br/><br/> _AllowedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitentes permitidos <br/><br/> _AllowedSenderDomains_|Ninguno|Ninguno|Ninguno|No es buena idea agregar dominios a la lista de remitentes permitidos. Los atacantes podrían enviar correos electrónicos que, de lo contrario, se filtrarían. <br/><br/> Use [inteligencia de identidad](learn-about-spoof-intelligence.md) en el centro de seguridad & cumplimiento de la página **configuración contra correo no deseado** para revisar todos los remitentes que imitan direcciones de correo electrónico de remitentes en los dominios de correo electrónico de su organización o direcciones de correo electrónico de remitentes suplantados en dominios externos.|
|Remitentes bloqueados <br/><br/> _BlockedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitentes bloqueados <br/><br/> _BlockedSenderDomains_|Ninguno|Ninguno|Ninguno||
|**Habilitar las notificaciones de correo no deseado para el usuario final** <br/><br/> _EnableEndUserSpamNotifications_|Deshabilitado <br/><br/> `$false`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Enviar notificaciones de correo no deseado para el usuario final cada (días)** <br/><br/> _EndUserSpamNotificationFrequency_|3 días|3 días|3 días||
|**ZAP de correo no deseado** <br/><br/> _SpamZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**ZAP de phish** <br/><br/> _PhishZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Activado|Activado|Activado|Esta opción solo está disponible en PowerShell.|
|

Hay otras configuraciones avanzadas de filtro de correo no deseado (ASF) en las directivas contra correo no deseado que están en desuso. Se comunicará más información sobre las escalas de tiempo de la depreciación de estas características fuera de este artículo.

Le recomendamos que **desactive esta configuración ASF** para niveles **estándar** y **estrictos** . Para obtener más información acerca de la configuración de ASF, consulte [Configuración avanzada de filtro de correo no deseado (ASF) en Office 365](advanced-spam-filtering-asf-options.md).

****

|Nombre de la característica de seguridad|Comentario|
|---|---|
|**Vínculos de imagen a sitios remotos** ( _IncreaseScoreWithImageLinks_ )||
|**Dirección IP numérica en la dirección URL** ( _IncreaseScoreWithNumericIps_ )||
|**Redireccionamiento UL a otro puerto** ( _IncreaseScoreWithRedirectToOtherPort_ )||
|**Dirección URL de los sitios Web. BIZ o. info** ( _IncreaseScoreWithBizOrInfoUrls_ )||
|**Mensajes vacíos** ( _MarkAsSpamEmptyMessages_ )||
|**JavaScript o VBScript en HTML** ( _MarkAsSpamJavaScriptInHtml_ )||
|**Etiquetas frame o iframe en HTML** ( _MarkAsSpamFramesInHtml_ )||
|**Etiquetas de objeto en HTML** ( _MarkAsSpamObjectTagsInHtml_ )||
|**Etiquetas embed en HTML** ( _MarkAsSpamEmbedTagsInHtml_ )||
|**Etiquetas de formulario en HTML** ( _MarkAsSpamFormTagsInHtml_ )||
|**Web bugs en HTML** ( _MarkAsSpamWebBugsInHtml_ )||
|**Aplicar lista de palabras confidenciales** ( _MarkAsSpamSensitiveWordList_ )||
|**Registro de SPF: error grave** ( _MarkAsSpamSpfRecordHardFail_ )||
|**Filtrado de identificador de remitente condicional: error grave** ( _MarkAsSpamFromAddressAuthFail_ )||
|**Retrodispersión de NDR** ( _MarkAsSpamNdrBackscatter_ )||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Configuración de la Directiva de correo no deseado de EOP

Para crear y configurar directivas de correo no deseado saliente, consulte [configurar el filtrado de correo no deseado saliente en Office 365](configure-the-outbound-spam-policy.md).

Para obtener más información acerca de los límites de envío predeterminados en el servicio, consulte [send limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Número máximo de destinatarios por usuario: límite horario externo** <br/><br/> _RecipientLimitExternalPerHour_|comprendi|500|400|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Número máximo de destinatarios por usuario: límite interno por hora** <br/><br/> _RecipientLimitInternalPerHour_|comprendi|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Número máximo de destinatarios por usuario: límite diario** <br/><br/> _RecipientLimitPerDay_|comprendi|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Acción cuando un usuario supera los límites** <br/><br/> _ActionWhenThresholdReached_|**Restringir al usuario el envío de correo hasta el siguiente día** <br/><br/> `BlockUserForToday`|**Restringir al usuario el envío de correo** <br/><br/> `BlockUser`|**Restringir al usuario el envío de correo** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Configuración de la Directiva de EOP contra malware

Para crear y configurar directivas antimalware, vea [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**¿Desea notificar a los destinatarios si sus mensajes están en cuarentena?** <br/><br/> _Acción_|No <br/><br/> _DeleteMessage_|No <br/><br/> _DeleteMessage_|No <br/><br/> _DeleteMessage_|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pone en cuarentena y solo puede ser lanzado por un administrador.|
|**Filtro de tipos de datos adjuntos comunes** <br/><br/> _EnableFileFilter_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`|Esta opción pone en cuarentena los mensajes que contienen datos adjuntos ejecutables basados en el tipo de archivo, independientemente del contenido de datos adjuntos.|
|**Purga automática de cero horas de malware** <br/><br/> _ZapEnabled_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Notificar a los remitentes internos** del mensaje no entregado <br/><br/> _EnableInternalSenderNotifications_|Deshabilitado <br/><br/> `$false`|Deshabilitado <br/><br/> `$false`|Deshabilitado <br/><br/> `$false`||
|**Notificar a remitentes externos** del mensaje no entregado <br/><br/> _EnableExternalSenderNotifications_|Deshabilitado <br/><br/> `$false`|Deshabilitado <br/><br/> `$false`|Deshabilitado <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Configuración de directiva antiphishing predeterminada de EOP

Para obtener más información acerca de estas opciones, consulte Configuración de la [suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings). Para configurar estas opciones, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Habilitación de la protección contra la suplantación de identidad** <br/><br/> _EnableAntispoofEnforcement_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Habilitar remitente sin autenticar** <br/><br/> _EnableUnauthenticatedSender_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para los remitentes suplantados no identificados. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md).|
|**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio** <br/><br/> _AuthenticationFailAction_|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esta configuración se aplica a los remitentes bloqueados en [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Seguridad de Microsoft defender para Office 365

Los beneficios de seguridad adicionales vienen con una suscripción de Microsoft defender para Office 365. Para obtener las últimas noticias e información, puede ver las novedades [de defender para Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - La Directiva antiphishing predeterminada de Microsoft defender para Office 365 proporciona [protección falsa](set-up-anti-phishing-policies.md#spoof-settings) para todos los destinatarios. Sin embargo, la configuración de [protección de suplantación](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponible para determinados remitentes o dominios de remitentes no está configurada o habilitada en la directiva predeterminada. Para habilitar la protección de suplantación, configure la directiva predeterminada o cree directivas antiphishing adicionales en defender para Office 365.
>
> - No hay directivas de vínculos seguros predeterminadas ni directivas de datos adjuntos seguros que protejan automáticamente a todos los destinatarios de la organización. Para obtener las protecciones, debe crear al menos una directiva de vínculos seguros y una directiva de datos adjuntos seguros.
>
> - La protección [de ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) y la protección de [documentos seguros](safe-docs.md) no tienen dependencias en las directivas de vínculos a prueba de errores.

Si su suscripción incluye a Microsoft defender para Office 365 o si ha comprado defender para Office 365 como un complemento, establezca las siguientes configuraciones estándar o estrictas.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directivas antiphishing en Microsoft defender para Office 365

Los clientes de EOP obtienen contra la suplantación de identidad (phishing) básica como se describió anteriormente, pero Microsoft defender para Office 365 incluye más características y control para ayudar a prevenir, detectar y corregir los ataques. Para crear y configurar estas directivas, vea [Configure anti-phishing policies in defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas antiphishing en Microsoft defender para Office 365

Para obtener más información acerca de estas opciones, vea [configuración de suplantación en directivas antiphishing en Microsoft defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar estas opciones, vea [Configure anti-phishing policies in defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|Usuarios protegidos: **Agregar usuarios para protegerlos** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|Desactivado <br/><br/> `$false` <br/><br/> ninguno|Activado <br/><br/> `$true` <br/><br/> \<list of users\>|Activado <br/><br/> `$true` <br/><br/> \<list of users\>|Según la organización, se recomienda agregar usuarios (remitentes de mensajes) en los roles clave. Internamente, los remitentes protegidos podrían ser su CEO, CFO y otros líderes senior. Externamente, los remitentes protegidos podrían incluir miembros del Consejo o su Consejo de administración.|
|Dominios protegidos: **incluir automáticamente los dominios de su propiedad** <br/><br/> _EnableOrganizationDomainsProtection_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|Dominios protegidos: **incluir dominios personalizados** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Desactivado <br/><br/> `$false` <br/><br/> ninguno|Activado <br/><br/> `$true` <br/><br/> \<list of domains\>|Activado <br/><br/> `$true` <br/><br/> \<list of domains\>|En función de la organización, se recomienda agregar dominios (dominios de remitente) que no son de su propiedad, pero con la que interactúan con frecuencia.|
|Usuarios protegidos: **si un usuario suplantado envía un correo electrónico** <br/><br/> _TargetedUserProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|Dominios protegidos: **si un dominio suplantado envía un correo electrónico** <br/><br/> _TargetedDomainProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|**Mostrar sugerencia para usuarios suplantados** <br/><br/> _EnableSimilarUsersSafetyTips_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Mostrar sugerencia para dominios suplantados** <br/><br/> _EnableSimilarDomainsSafetyTips_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Mostrar sugerencia para caracteres inusuales** <br/><br/> _EnableUnusualCharactersSafetyTips_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**¿Habilitar la inteligencia de buzones?** <br/><br/> _EnableMailboxIntelligence_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**¿Habilitar la protección de suplantación basada en buzones de correo?** <br/><br/> _EnableMailboxIntelligenceProtection_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Si un usuario suplantado envía un correo electrónico protegido por la inteligencia de buzones** <br/><br/> _MailboxIntelligenceProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|**Remitentes de confianza** <br/><br/> _ExcludedSenders_|Ninguno|Ninguno|Ninguno|Según la organización, se recomienda agregar usuarios que se marquen correctamente como phishing debido a la suplantación y no a otros filtros.|
|**Dominios de confianza** <br/><br/> _ExcludedDomains_|Ninguno|Ninguno|Ninguno|Según la organización, se recomienda agregar dominios que se marquen incorrectamente como phishing debido a la suplantación y no a otros filtros.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación de identidad en directivas antiphishing en Microsoft defender para Office 365

Tenga en cuenta que estos son los mismos valores de configuración que están disponibles en la [configuración de la Directiva contra correo no deseado en EOP](#eop-anti-spam-policy-settings).

****

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---|---|---|---|
|**Habilitación de la protección contra la suplantación de identidad** <br/><br/> _EnableAntispoofEnforcement_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Habilitar remitente sin autenticar** <br/><br/> _EnableUnauthenticatedSender_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para los remitentes suplantados no identificados. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md).|
|**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio** <br/><br/> _AuthenticationFailAction_|**Mover mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esta configuración se aplica a los remitentes bloqueados en [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración avanzada en directivas antiphishing en Microsoft defender para Office 365

Para obtener más información acerca de esta configuración, consulte [umbrales de suplantación de identidad avanzada en directivas antiphishing en Microsoft defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar esta opción, vea [Configure anti-phishing policies in defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbrales de suplantación de identidad avanzada** <br/><br/> _PhishThresholdLevel_|**1-estándar** <br/><br/> `1`|**2-agresivo** <br/><br/> `2`|**3-más agresivo** <br/><br/> `3`||
|

### <a name="safe-links-settings"></a>Configuración de vínculos seguros

Vínculos seguros en defender para Office 365 incluye la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos seguros activos y la configuración específica de cada directiva de vínculos seguros. Para obtener más información, vea [vínculos a prueba de errores en defender para Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Configuración global para vínculos seguros

Para configurar estas opciones, vea [Configure global Settings for Safe links in defender for Office 365](configure-global-settings-for-safe-links.md).

En PowerShell, use el cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para estas opciones de configuración.

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Usar vínculos seguros en: aplicaciones de Office 365** <br/><br/> _EnableSafeLinksForO365Clients_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Use vínculos seguros en aplicaciones compatibles con Office 365 Desktop y Mobile (iOS y Android). Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**No realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** <br/><br/> _TrackClicks_|Activada <br/><br/> `$false`|Desactivada <br/><br/> `$true`|Desactivado <br/><br/> `$true`|Si se desactiva esta configuración (al establecer _TrackClicks_ en), se hace `$true` un seguimiento de los clics del usuario en las aplicaciones de Office 365 compatibles.|
|**No permitir que los usuarios hagan clic en los vínculos seguros a la dirección URL original** <br/><br/> _AllowClickThrough_|Activado <br/><br/> `$false`|Activado <br/><br/> `$false`|Activado <br/><br/> `$false`|Si se activa esta configuración (al establecer _AllowClickThrough_ en), se `$false` impide que se haga clic a través de la dirección URL original en aplicaciones de Office 365 compatibles.|
|

#### <a name="safe-links-policy-settings"></a>Configuración de directiva de vínculos seguros

Para configurar estas opciones, consulte [configurar directivas de vínculos seguros en Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).

En PowerShell, se usan los cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) y [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva predeterminada de vínculos a prueba de errores. Los valores de la columna predeterminada son los valores predeterminados de las nuevas directivas de vínculos a prueba de errores que cree.

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes** <br/><br/> _IsEnabled_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Seleccione la acción para direcciones URL potencialmente malintencionadas o desconocidas en Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Aplicar un análisis de URL en tiempo real de vínculos y vínculos sospechosos que señalan a archivos** <br/><br/> _ScanUrls_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Esperar a que se complete el análisis de URL antes de entregar el mensaje** <br/><br/> _DeliverMessageAfterScan_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización** <br/><br/> _EnableForInternalSenders_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**No hacer un seguimiento de los clics del usuario** <br/><br/> _DoNotTrackUserClicks_|Desactivado <br/><br/> `$false`|Desactivado <br/><br/> `$false`|Desactivado <br/><br/> `$false`|Si se desactiva esta configuración (al establecer _DoNotTrackUserClicks_ en), se `$false` hace un seguimiento de los usuarios.|
|**No permitir que los usuarios hagan clic a través de la dirección URL original** <br/><br/> _DoNotAllowClickThrough_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Activado <br/><br/> `$true`|Si se activa esta configuración (al establecer _DoNotAllowClickThrough_ en), se `$true` impide que se haga clic en la dirección URL original.|
|

### <a name="safe-attachments-settings"></a>Configuración de datos adjuntos seguros

Datos adjuntos seguros en Microsoft defender para Office 365 incluye configuraciones globales que no tienen relación con directivas de datos adjuntos seguros y opciones específicas de cada directiva de vínculos seguros. Para obtener más información, consulte [datos adjuntos seguros en defender para Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Configuración global de datos adjuntos seguros

Para configurar estas opciones, consulte [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) y [documentos seguros en Microsoft 365 E5](safe-docs.md).

En PowerShell, use el cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para estas opciones de configuración.

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Activar ATP para SharePoint, OneDrive y Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|**Activar documentos seguros para clientes de Office**<bt/><br/> _EnableSafeDocs_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Esta configuración solo está disponible con las licencias de seguridad de Microsoft 365 E5 o Microsoft 365 E5. Para obtener más información, vea [documentos seguros en Microsoft defender para Office 365](safe-docs.md).|
|**Permitir que los usuarios haga clic a través de la vista protegida, incluso si los documentos seguros identificaron el archivo como malintencionado**<bt/><br/> _AllowSafeDocsOpen_|Desactivado <br/><br/> `$false`|Desactivado <br/><br/> `$false`|Esta configuración está relacionada con documentos seguros.|
|

#### <a name="safe-attachments-policy-settings"></a>Configuración de la Directiva de datos adjuntos seguros

Para configurar estas opciones, consulte [configurar directivas de datos adjuntos seguros en defender para Office 365](set-up-atp-safe-attachments-policies.md).

En PowerShell, se usan los cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) y [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay una directiva de datos adjuntos seguros predeterminada. Los valores de la columna predeterminada son los valores predeterminados de las nuevas directivas de datos adjuntos seguros que cree.

****

|Nombre de la característica de seguridad|Predeterminada|Estándar|Estricta|Comentario|
|---|:---:|:---:|:---:|---|
|**Datos adjuntos seguros respuesta de malware desconocida** <br/><br/> _Acción_|Bloquear <br/><br/> `Block`|Bloquear <br/><br/> `Block`|Bloquear <br/><br/> `Block`||
|**Redirigir datos adjuntos en detección** : **Habilitar redireccionamiento** <br/><br/> _Redirigir_ <br/><br/> _RedirectAddress_|Desactivado y ninguna dirección de correo electrónico especificada. <br/><br/> `$true` <br/><br/> ninguno|En y especifica una dirección de correo electrónico. <br/><br/> `$true` <br/><br/> una dirección de correo electrónico|En y especifica una dirección de correo electrónico. <br/><br/> `$true` <br/><br/> una dirección de correo electrónico|Redirigir mensajes a un administrador de seguridad para su revisión.|
|**Aplique la selección anterior si se produce un error de análisis de malware para archivos adjuntos o errores.** <br/><br/> _ActionOnError_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`||
|

## <a name="related-articles"></a>Artículos relacionados

- ¿Necesita procedimientos recomendados para **las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte** )? Consulte los [procedimientos recomendados para configurar reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Los administradores y los usuarios pueden enviar falsos positivos (correo electrónico bueno marcado como no válido) y falsos negativos (se permite correo electrónico incorrecto) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estos vínculos para obtener información sobre cómo **configurar** el [servicio de EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)y cómo **configurar** [Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). No olvide las direcciones útiles en '[proteger contra amenazas en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.

- Las **líneas de base de seguridad para Windows** se pueden encontrar aquí: ¿ [Dónde puedo obtener las líneas de base de seguridad?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO/locales y [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/intune/protect/security-baselines) para la seguridad basada en Intune. Por último, hay disponible una comparación entre Microsoft defender for Endpoint y Microsoft Intune Security Baselines en [Compare The Microsoft defender for Endpoint and the Windows Intune Security Baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
