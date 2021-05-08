---
title: Recomendaciones de Microsoft para la configuración de seguridad de EOP y Defender para Office 365
keywords: Recomendaciones de seguridad de Office 365, Marco de directivas de remitentes, Informes y conformidad de mensajes basados en dominio, Correo identificado de DomainKeys, pasos, cómo funciona, líneas base de seguridad, líneas base para EOP, líneas base para Defender para Office 365, configurar Defender para Office 365, configurar EOP, configurar Defender para Office 365, configurar EOP, configuración de seguridad
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: ¿Cuáles son los procedimientos recomendados para la configuración de seguridad de Exchange Online Protection (EOP) y Defender para Office 365? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué se debe usar si quiere ser más estricto? ¿Y qué extras obtiene si también usa Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3a4447d6eaeeb907eb750d2ad668fdbb9031c28b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274873"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configuración recomendada para EOP y Microsoft Defender para la seguridad de Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** es el núcleo de seguridad de las suscripciones de Microsoft 365 y ayuda a evitar que los correos malintencionados lleguen a las bandejas de entrada de sus empleados. Sin embargo, con ataques nuevos y más sofisticados que surgen cada día, a menudo se requieren protecciones mejoradas. **Microsoft Defender para Office 365** El plan 1 o el plan 2 contienen características adicionales que dan a los administradores más capas de seguridad, control e investigación.

Aunque habilitamos a los administradores de seguridad para personalizar su configuración de seguridad, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que recomendamos: **Standard** y **Strict**. El entorno y las necesidades de cada cliente son diferentes, pero creemos que estos niveles de filtrado ayudarán a evitar que el correo no deseado llegue a la Bandeja de entrada de los empleados en la mayoría de las situaciones.

Para aplicar automáticamente la configuración estándar o estricta a los usuarios, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

> [!NOTE]
> La regla de correo no deseado debe habilitarse en los buzones para que el filtrado funcione correctamente. Está habilitado de forma predeterminada, pero debe comprobarlo si el filtrado no parece funcionar. Para obtener más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

En este artículo se describe la configuración predeterminada y también la configuración estándar y estricta recomendada para ayudar a proteger a los usuarios.

> [!TIP]
> El módulo del Analizador de configuración recomendada (ORCA) de Protección contra amenazas avanzada de Office 365 para PowerShell puede ayudarle (administradores) a encontrar los valores actuales de esta configuración. En concreto, el cmdlet **Get-ORCAReport** genera una evaluación de la configuración contra correo no deseado, contra suplantación de identidad (phishing) y otras opciones de higiene de mensajes. Puede descargar el módulo ORCA en <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo no deseado, antimalware y anti phishing en EOP

El correo no deseado, el antimalware y la suplantación de identidad (phishing) son características de EOP que pueden configurar los administradores. Se recomiendan las siguientes configuraciones estándar o estrictas.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de directiva contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, vea [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Acción de detección de correo** no deseado <p> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de correo no deseado** de elevada confianza <p> _HighConfidenceSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de correo electrónico** de suplantación de identidad <p> _PhishSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de correo electrónico de phishing de elevada** confianza <p> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección masiva** de correo electrónico <p> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|Umbral de correo electrónico masivo <p> _BulkThreshold_|7 |6 |4 |Para obtener más información, [vea Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Período de retención en cuarentena <p> _QuarantineRetentionPeriod_|15 días|30 días|30 días||
|**Sugerencias de seguridad** <p> _InlineSafetyTipsEnabled_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|Remitentes permitidos <p> _AllowedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente permitidos <p> _AllowedSenderDomains_|Ninguno|Ninguno|Ninguno|Agregar dominios a la lista de remitentes permitidos es una idea muy mala. Los atacantes podrían enviarle un correo electrónico que, de lo contrario, se filtraría. <p> Use [](learn-about-spoof-intelligence.md) la inteligencia de suplantación de identidad  en el Centro de seguridad y cumplimiento de & en la página Configuración contra correo no deseado para revisar todos los remitentes que están suplantando direcciones de correo electrónico de remitente en los dominios de correo electrónico de su organización o suplantando direcciones de correo electrónico del remitente en dominios externos.|
|Remitentes bloqueados <p> _BlockedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente bloqueados <p> _BlockedSenderDomains_|Ninguno|Ninguno|Ninguno||
|**Habilitar las notificaciones de correo no deseado para el usuario final** <p> _EnableEndUserSpamNotifications_|Deshabilitado <p> `$false`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Enviar notificaciones de correo no deseado para el usuario final cada (días)** <p> _EndUserSpamNotificationFrequency_|3 días|3 días|3 días||
|**ZAP de correo no deseado** <p> _SpamZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|_MarkAsSpamBulkMail_|Activado|Activado|Activado|Esta configuración solo está disponible en PowerShell.|
|

Hay varias otras configuraciones de filtro de correo no deseado avanzado (ASF) en directivas contra correo no deseado que están en proceso de desuso. Se comunicará más información sobre las escalas de tiempo para la depreciación de estas características fuera de este artículo.

Se recomienda desactivar esta configuración de ASF **para** los **niveles Estándar** **y Estricto.** Para obtener más información acerca de la configuración de ASF, vea [Advanced Spam Filter (ASF) settings in Office 365](advanced-spam-filtering-asf-options.md).

<br>

****

|Nombre de la característica de seguridad|Comentario|
|---|---|
|**Vínculos de imagen a sitios remotos** (_IncreaseScoreWithImageLinks_)||
|**Dirección IP numérica en dirección URL** (_IncreaseScoreWithNumericIps_)||
|**Redirección ul a otro puerto** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Dirección URL a sitios web .biz** o .info (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensajes vacíos** (_MarkAsSpamEmptyMessages_)||
|**JavaScript o VBScript en HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Etiquetas Frame o IFrame en HTML** (_MarkAsSpamFramesInHtml_)||
|**Etiquetas de objeto en HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Insertar etiquetas en HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Etiquetas de formulario en HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Errores web en HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Aplicar lista de palabras confidenciales** (_MarkAsSpamSensitiveWordList_)||
|**Registro SPF: error duro** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtrado de id. de remitente condicional: error** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Configuración de directiva de correo no deseado saliente de EOP

Para crear y configurar directivas de correo no deseado salientes, vea [Configure outbound spam filtering in Office 365](configure-the-outbound-spam-policy.md).

Para obtener más información acerca de los límites de envío predeterminados en el servicio, vea [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Número máximo de destinatarios por usuario: límite por hora externo** <p> _RecipientLimitExternalPerHour_|0|500|400|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Número máximo de destinatarios por usuario: límite por hora interno** <p> _RecipientLimitInternalPerHour_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Número máximo de destinatarios por usuario: límite diario** <p> _RecipientLimitPerDay_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Acción cuando un usuario supera los límites** <p> _ActionWhenThresholdReached_|**Restringir al usuario el envío de correo hasta el día siguiente** <p> `BlockUserForToday`|**Restringir al usuario el envío de correo** <p> `BlockUser`|**Restringir al usuario el envío de correo** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Configuración de directiva antimalware de EOP

Para crear y configurar directivas antimalware, vea [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**¿Desea notificar a los destinatarios si sus mensajes están en cuarentena?** <p> _Action_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pone en cuarentena y solo puede publicarlo un administrador.|
|**Filtro de tipos de datos adjuntos comunes** <p> _EnableFileFilter_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`|Esta configuración pone en cuarentena los mensajes que contienen datos adjuntos ejecutables según el tipo de archivo, independientemente del contenido de los datos adjuntos.|
|**Purga automática de hora cero de malware** <p> _ZapEnabled_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Notificar a los remitentes internos** del mensaje no entregado <p> _EnableInternalSenderNotifications_|Deshabilitada <p> `$false`|Deshabilitada <p> `$false`|Deshabilitada <p> `$false`||
|**Notificar a los remitentes externos** del mensaje no entregado <p> _EnableExternalSenderNotifications_|Deshabilitada <p> `$false`|Deshabilitada <p> `$false`|Deshabilitada <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Configuración de directiva contra suplantación de identidad predeterminada de EOP

Para obtener más información acerca de esta configuración, vea [Spoof settings](set-up-anti-phishing-policies.md#spoof-settings). Para configurar estas opciones, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Habilitar la protección contra la suplantación** <p> _EnableSpoofIntelligence_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Habilitar remitente no autenticado** <p> _EnableUnauthenticatedSender_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md).|
|**Si alguien que no puede suplantación de su dominio envía correo electrónico** <p> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`|Esta configuración se aplica a los remitentes bloqueados en [la inteligencia suplantación](learn-about-spoof-intelligence.md)de identidad .|
|

## <a name="microsoft-defender-for-office-365-security"></a>Seguridad de Microsoft Defender para Office 365

Las ventajas de seguridad adicionales vienen con una suscripción de Microsoft Defender para Office 365. Para obtener las últimas noticias e información, puede ver [Novedades de Defender para Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - La directiva contra suplantación de identidad predeterminada en [](set-up-anti-phishing-policies.md#spoof-settings) Microsoft Defender para Office 365 proporciona protección contra suplantación de identidad e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras [características](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) de protección de suplantación disponibles y la configuración avanzada [no](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva contra suplantación de identidad predeterminada o cree directivas adicionales contra la suplantación de identidad.
>
> - No hay directivas de vínculos seguros predeterminadas ni directivas de datos adjuntos seguros que protejan automáticamente a todos los destinatarios de la organización. Para obtener las protecciones, debe crear al menos una directiva de vínculos seguros y una directiva de datos adjuntos seguros.
>
> - Los datos adjuntos seguros para la protección [](safe-docs.md) [de SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md) y la protección de documentos seguros no tienen dependencias en las directivas de vínculos seguros.

Si la suscripción incluye Microsoft Defender para Office 365 o si ha comprado Defender para Office 365 como complemento, establezca las siguientes configuraciones estándar o estrictas.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directiva contra suplantación de identidad en Microsoft Defender para Office 365

Los clientes de EOP obtienen la protección contra suplantación de identidad básica como se describió anteriormente, pero Microsoft Defender para Office 365 incluye más características y control para ayudar a prevenir, detectar y corregir los ataques. Para crear y configurar estas directivas, vea [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, vea Configuración de suplantación en directivas contra suplantación de identidad en [Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar estas opciones, vea [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|Usuarios protegidos: **agregar usuarios para proteger** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Desactivado <p> `$false` <p> ninguno|Activado <p> `$true` <p> \<list of users\>|Activado <p> `$true` <p> \<list of users\>|En función de la organización, se recomienda agregar usuarios (remitentes de mensajes) en roles clave. Internamente, los remitentes protegidos pueden ser su director general, director financiero y otros líderes sénior. Externamente, los remitentes protegidos podrían incluir miembros del consejo o su junta directiva.|
|Dominios protegidos: **incluir automáticamente los dominios que tengo** <p> _EnableOrganizationDomainsProtection_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|Dominios protegidos: **incluir dominios personalizados** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Desactivado <p> `$false` <p> ninguno|Activado <p> `$true` <p> \<list of domains\>|Activado <p> `$true` <p> \<list of domains\>|Dependiendo de la organización, se recomienda agregar dominios (dominios de remitente) que no posee, pero con los que interactúa con frecuencia.|
|Usuarios protegidos: **si un usuario suplantado envía** correo electrónico <p> _TargetedUserProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Poner en cuarentena el mensaje** <p> `Quarantine`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|Dominios protegidos: **si un dominio suplantado envía correo electrónico** <p> _TargetedDomainProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Poner en cuarentena el mensaje** <p> `Quarantine`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Mostrar sugerencia para usuarios suplantados** <p> _EnableSimilarUsersSafetyTips_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Mostrar sugerencia para dominios suplantados** <p> _EnableSimilarDomainsSafetyTips_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Mostrar sugerencia para caracteres inusuales** <p> _EnableUnusualCharactersSafetyTips_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Habilitar la inteligencia de buzones** <p> _EnableMailboxIntelligence_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Habilitar la protección de suplantación basada en inteligencia de buzones de correo** <p> _EnableMailboxIntelligenceProtection_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Si un usuario suplantado envía correo electrónico protegido por inteligencia de buzones** <p> _MailboxIntelligenceProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Remitentes de confianza** <p> _ExcludedSenders_|Ninguno|Ninguno|Ninguno|En función de la organización, se recomienda agregar usuarios que se marquen incorrectamente como suplantación debido a la suplantación y no a otros filtros.|
|**Dominios de confianza** <p> _ExcludedDomains_|Ninguno|Ninguno|Ninguno|En función de la organización, se recomienda agregar dominios que se marquen incorrectamente como suplantación debido a la suplantación y no a otros filtros.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación de identidad en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Tenga en cuenta que estas son las mismas opciones que están disponibles en la configuración de directiva contra correo no [deseado en EOP](#eop-anti-spam-policy-settings).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|---|---|---|---|
|**Habilitar la protección contra la suplantación** <p> _EnableSpoofIntelligence_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Habilitar remitente no autenticado** <p> _EnableUnauthenticatedSender_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md).|
|**Si alguien que no puede suplantación de su dominio envía correo electrónico** <p> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`|Esta configuración se aplica a los remitentes bloqueados en [la inteligencia suplantación](learn-about-spoof-intelligence.md)de identidad .|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración avanzada en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, vea [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar esta configuración, vea [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbrales de suplantación de identidad avanzada** <p> _PhishThresholdLevel_|**1- Estándar** <p> `1`|**2 : agresivo** <p> `2`|**3: más agresivo** <p> `3`||
|

### <a name="safe-links-settings"></a>Configuración de vínculos seguros

Vínculos seguros en Defender para Office 365 incluye la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos seguros activas y la configuración específica de cada directiva de vínculos seguros. Para obtener más información, vea [Vínculos seguros en Defender para Office 365](safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Configuración global de vínculos seguros

Para configurar estas opciones, vea [Configure global settings for Safe Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Usar vínculos seguros en: aplicaciones de Office 365** <p> _EnableSafeLinksForO365Clients_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Use vínculos seguros en aplicaciones compatibles de escritorio y móviles de Office 365 (iOS y Android). Para obtener más información, vea [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).|
|**No realizar un seguimiento cuando los usuarios hacen clic en Vínculos seguros** <p> _TrackClicks_|Activada <p> `$false`|Desactivada <p> `$true`|Desactivado <p> `$true`|Al desactivar esta configuración (establecer _TrackClicks_ en ) se realiza un seguimiento de los clics del usuario en aplicaciones compatibles de `$true` Office 365.|
|**No permitir que los usuarios hagan clic en vínculos seguros a la dirección URL original** <p> _AllowClickThrough_|Activado <p> `$false`|Activado <p> `$false`|Activado <p> `$false`|Al activar esta configuración (al establecer _AllowClickThrough en_ ) se evita hacer clic en la dirección URL original en las aplicaciones compatibles de `$false` Office 365.|
|

#### <a name="safe-links-policy-settings"></a>Configuración de directiva de vínculos seguros

Para configurar estas opciones, vea [Configurar directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

En PowerShell, use los [cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) y [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva de vínculos seguros predeterminada. Los valores de la columna Predeterminado son los valores predeterminados de las nuevas directivas de vínculos seguros que cree.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes** <p> _IsEnabled_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Seleccione la acción para direcciones URL desconocidas o potencialmente malintencionadas en Microsoft Teams** <p> _EnableSafeLinksForTeams_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Aplicar análisis de url en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos** <p> _ScanUrls_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje** <p> _DeliverMessageAfterScan_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización** <p> _EnableForInternalSenders_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**No realizar un seguimiento de los clics del usuario** <p> _DoNotTrackUserClicks_|Desactivado <p> `$false`|Desactivado <p> `$false`|Desactivado <p> `$false`|Desactivar esta configuración (establecer _DoNotTrackUserClicks_ en `$false` ) realiza un seguimiento de los clics de los usuarios.|
|**No permitir que los usuarios hagan clic en la dirección URL original** <p> _DoNotAllowClickThrough_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`|Al activar esta configuración (al _establecer DoNotAllowClickThrough en_ ) se evita `$true` hacer clic en la dirección URL original.|
|

### <a name="safe-attachments-settings"></a>Configuración de datos adjuntos seguros

Datos adjuntos seguros en Microsoft Defender para Office 365 incluye la configuración global que no tiene ninguna relación con las directivas de datos adjuntos seguros y la configuración específica de cada directiva de vínculos seguros. Para obtener más información, vea [Datos adjuntos seguros en Defender para Office 365](safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Configuración global de datos adjuntos seguros

Para configurar estas opciones, vea Activar datos adjuntos seguros para [SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) y Documentos seguros [en Microsoft 365 E5](safe-docs.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Activado <p> `$true`|Activado <p> `$true`||
|**Activar documentos seguros para clientes de Office** <p> _EnableSafeDocs_|Activado <p> `$true`|Activado <p> `$true`|Esta configuración solo está disponible con licencias de seguridad de Microsoft 365 E5 o Microsoft 365 E5. Para obtener más información, vea [Documentos seguros en Microsoft Defender para Office 365](safe-docs.md).|
|**Permitir que las personas haga clic en la vista protegida incluso si documentos seguros identificaron el archivo como malintencionado** <p> _AllowSafeDocsOpen_|Desactivado <p> `$false`|Desactivado <p> `$false`|Esta configuración está relacionada con Documentos seguros.|
|

#### <a name="safe-attachments-policy-settings"></a>Configuración de directiva de datos adjuntos seguros

Para configurar estas opciones, vea [Configurar directivas de datos adjuntos seguros en Defender para Office 365](set-up-safe-attachments-policies.md).

En PowerShell, use los cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) y [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva predeterminada de datos adjuntos seguros. Los valores de la columna Predeterminado son los valores predeterminados de las nuevas directivas de datos adjuntos seguros que cree.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Respuesta de malware desconocido de datos adjuntos seguros** <p> _Action_|Bloquear <p> `Block`|Bloquear <p> `Block`|Bloquear <p> `Block`||
|**Datos adjuntos de redireccionamiento al detectar:** **Habilitar redireccionamiento** <p> _Redirigir_ <p> _RedirectAddress_|Desactivado y sin dirección de correo electrónico especificada. <p> `$true` <p> ninguno|On y especifique una dirección de correo electrónico. <p> `$true` <p> una dirección de correo electrónico|On y especifique una dirección de correo electrónico. <p> `$true` <p> una dirección de correo electrónico|Redirigir mensajes a un administrador de seguridad para su revisión.|
|**Aplica la selección anterior si el examen de malware en busca de datos adjuntos tiene tiempo de espera o se produce un error.** <p> _ActionOnError_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|

## <a name="related-articles"></a>Artículos relacionados

- ¿Está buscando procedimientos recomendados para las reglas de flujo de correo **de Exchange (también conocidas como reglas de transporte)?** Consulte [Procedimientos recomendados para configurar reglas de flujo de correo en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Los administradores y los usuarios pueden enviar falsos positivos (buen correo electrónico marcado como negativo) y falsos negativos (correo electrónico no permitido) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estos vínculos para obtener información sobre cómo **configurar el** servicio [EOP](set-up-your-eop-service.md)y **configurar** Microsoft Defender para [Office 365](defender-for-office-365.md). No olvide las instrucciones útiles en "[Proteger contra amenazas en Office 365".](protect-against-threats.md)

- **Las líneas** base de seguridad para Windows se pueden encontrar aquí: ¿Dónde puedo obtener las líneas base de [seguridad?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para GPO/opciones locales y Usar líneas base de seguridad para configurar [dispositivos windows 10](/intune/protect/security-baselines) en Intune para la seguridad basada en Intune. Por último, una comparación entre las líneas base de seguridad de Microsoft Defender para Endpoint y Microsoft Intune está disponible en Compare the Microsoft Defender for Endpoint y las líneas base de seguridad [de Windows Intune.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
