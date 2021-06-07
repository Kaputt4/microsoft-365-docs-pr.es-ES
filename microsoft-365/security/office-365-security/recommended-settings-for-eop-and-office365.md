---
title: Recomendaciones de Microsoft para EOP y Defender para la configuración Office 365 seguridad
keywords: Office 365 recomendaciones de seguridad, Marco de directivas de remitente, Informes y conformidad de mensajes basados en dominio, DomainKeys Identified Mail, pasos, cómo funciona, líneas base de seguridad, líneas base para EOP, líneas base para Defender para Office 365, configurar Defender para Office 365, configurar EOP, configurar Defender para Office 365, configurar EOP, configuración de seguridad
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
description: ¿Cuáles son los procedimientos recomendados para Exchange Online Protection (EOP) y Defender para Office 365 de seguridad? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué se debe usar si quiere ser más estricto? ¿Y qué extras obtiene si también usa Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f00e1e2356839e70acafb0f98a5424a1311082e7
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793225"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** es el núcleo de seguridad de las suscripciones de Microsoft 365 y ayuda a evitar que los correos electrónicos malintencionados lleguen a las bandejas de entrada de los empleados. Sin embargo, con ataques nuevos y más sofisticados que surgen cada día, a menudo se requieren protecciones mejoradas. **Microsoft Defender para Office 365** El plan 1 o el plan 2 contienen características adicionales que dan a los administradores más capas de seguridad, control e investigación.

Aunque habilitamos a los administradores de seguridad para personalizar su configuración de seguridad, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que recomendamos: **Standard** y **Strict**. El entorno y las necesidades de cada cliente son diferentes, pero creemos que estos niveles de filtrado ayudarán a evitar que el correo no deseado llegue a la Bandeja de entrada de los empleados en la mayoría de las situaciones.

Para aplicar automáticamente la configuración Estándar o Estricta a los usuarios, consulte [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

> [!NOTE]
> La regla de correo no deseado debe habilitarse en los buzones para que el filtrado funcione correctamente. Está habilitado de forma predeterminada, pero debe comprobarlo si el filtrado no parece funcionar. Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

En este artículo se describe la configuración predeterminada y también la configuración estándar y estricta recomendada para ayudar a proteger a los usuarios. Las tablas contienen la configuración del centro de seguridad de Microsoft 365 y PowerShell (Exchange Online PowerShell o powershell independiente Exchange Online Protection powershell para organizaciones sin Exchange Online buzones de correo).

> [!TIP]
> El Office 365 advanced threat protection recommended configuration analyzer (ORCA) para PowerShell puede ayudarle (administradores) a encontrar los valores actuales de esta configuración. En concreto, el cmdlet **Get-ORCAReport** genera una evaluación de la configuración contra correo no deseado, contra suplantación de identidad (phishing) y otras opciones de higiene de mensajes. Puede descargar el módulo ORCA en <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo no deseado, antimalware y anti phishing en EOP

El correo no deseado, el antimalware y la suplantación de identidad (phishing) son características de EOP que pueden configurar los administradores. Se recomiendan las siguientes configuraciones estándar o estrictas.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de directiva contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Acción de detección de correo** no deseado <p> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de correo no deseado** de elevada confianza <p> _HighConfidenceSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección** de phishing <p> _PhishSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de phishing de elevada** confianza <p> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de** detección masiva <p> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Umbral de correo electrónico masivo** <p> _BulkThreshold_|7 |6 |4 |Para obtener más información, [vea Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).|
|_MarkAsSpamBulkMail_|Activado|Activado|Activado|Esta configuración solo está disponible en PowerShell.|
|**Conservar el correo no deseado en cuarentena durante estos días** <p> _QuarantineRetentionPeriod_|15 días|30 días|30 días||
|**Habilitar sugerencias de seguridad contra correo no deseado** <p> _InlineSafetyTipsEnabled_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|Remitentes permitidos <p> _AllowedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente permitidos <p> _AllowedSenderDomains_|Ninguno|Ninguno|Ninguno|Agregar dominios a la lista de remitentes permitidos es una idea muy mala. Los atacantes podrían enviarle un correo electrónico que, de lo contrario, se filtraría. <p> Use [](learn-about-spoof-intelligence.md) la información de inteligencia de suplantación de identidad y la lista de permitidos [o](tenant-allow-block-list.md) bloqueados de inquilinos para revisar todos los remitentes que suplanten direcciones de correo electrónico de remitente en los dominios de correo electrónico de su organización o suplanten direcciones de correo electrónico de remitente en dominios externos.|
|Remitentes bloqueados <p> _BlockedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente bloqueados <p> _BlockedSenderDomains_|Ninguno|Ninguno|Ninguno||
|**Habilitar las notificaciones de correo no deseado para el usuario final** <p> _EnableEndUserSpamNotifications_|Deshabilitado <p> `$false`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Enviar notificaciones de correo no deseado para el usuario final cada (días)** <p> _EndUserSpamNotificationFrequency_|3 días|3 días|3 días||
|Habilitar la purga automática de hora cero (ZAP) para mensajes de suplantación de identidad <p> _PhishZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|Habilitar ZAP para mensajes de correo no deseado <p> _SpamZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|

Hay muchas configuraciones de filtro de correo no deseado avanzado (ASF) en directivas contra correo no deseado que están en proceso de desuso. Se comunicará más información sobre las escalas de tiempo para la depreciación de estas características fuera de este artículo.

Se recomienda dejar desactivada la siguiente configuración de ASF **para** los **niveles Estándar** **y** Estricto. Para obtener más información acerca de la configuración de ASF, vea [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).

<br>

****

|Nombre de la característica de seguridad|Comentario|
|---|---|
|**Vínculos de imagen a sitios remotos** (_IncreaseScoreWithImageLinks_)||
|**Dirección IP numérica en dirección URL** (_IncreaseScoreWithNumericIps_)||
|**Redirección de dirección URL a otro puerto** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Vínculos a sitios web .biz** o .info (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensajes vacíos** (_MarkAsSpamEmptyMessages_)||
|**Insertar etiquetas en HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**JavaScript o VBScript en HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Etiquetas de formulario en HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Etiquetas frame o iframe en HTML** (_MarkAsSpamFramesInHtml_)||
|**Errores web en HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Etiquetas de objeto en HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Palabras confidenciales** (_MarkAsSpamSensitiveWordList_)||
|**Registro SPF: error duro** (_MarkAsSpamSpfRecordHardFail_)||
|**Error de filtrado de id. de remitente** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Configuración de directiva de correo no deseado saliente de EOP

Para crear y configurar directivas de correo no deseado saliente, vea [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).

Para obtener más información acerca de los límites de envío predeterminados en el servicio, vea [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Establecer un límite de mensajes externos** <p> _RecipientLimitExternalPerHour_|0|500|400|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Establecer un límite de mensajes interno** <p> _RecipientLimitInternalPerHour_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Establecer un límite de mensajes diario** <p> _RecipientLimitPerDay_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Restricción impuesta a los usuarios que alcanzan el límite de mensajes** <p> _ActionWhenThresholdReached_|**Restringir al usuario el envío de correo hasta el día siguiente** <p> `BlockUserForToday`|**Restringir al usuario el envío de correo** <p> `BlockUser`|**Restringir al usuario el envío de correo** <p> `BlockUser`||
|**Reglas de reenvío automático** <p> _AutoForwardingMode_|**Automático: controlado por el sistema** <p> `Automatic`|**Automático: controlado por el sistema** <p> `Automatic`|**Automático: controlado por el sistema** <p> `Automatic`|
|

### <a name="eop-anti-malware-policy-settings"></a>Configuración de directiva antimalware de EOP

Para crear y configurar directivas antimalware, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Notificar a los destinatarios cuando los mensajes se ponen en cuarentena como malware** <p> _Action_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pone en cuarentena y solo puede publicarlo un administrador.|
|**Habilitar el filtro de datos adjuntos común** <p> _EnableFileFilter_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`|Esta configuración pone en cuarentena los mensajes que contienen datos adjuntos ejecutables según el tipo de archivo, independientemente del contenido de los datos adjuntos.|
|**Habilitar la purga automática de hora cero para malware** <p> _ZapEnabled_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Notificar a los remitentes internos cuando los mensajes se ponen en cuarentena como malware** <p> _EnableInternalSenderNotifications_|Deshabilitado <p> `$false`|Deshabilitado <p> `$false`|Deshabilitado <p> `$false`||
|**Notificar a remitentes externos cuando los mensajes se ponen en cuarentena como malware** <p> _EnableExternalSenderNotifications_|Deshabilitado <p> `$false`|Deshabilitado <p> `$false`|Deshabilitado <p> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>Configuración de directiva contra suplantación de identidad de EOP

Para obtener más información acerca de esta configuración, vea [Spoof settings](set-up-anti-phishing-policies.md#spoof-settings). Para configurar estas opciones, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Habilitar la inteligencia de suplantación** <p> _EnableSpoofIntelligence_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Si el correo electrónico se detecta como suplantación** <p> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`|Esta configuración se aplica a remitentes suplantados que se [](learn-about-spoof-intelligence.md) bloquearon automáticamente, como se muestra en la información de inteligencia de suplantación de identidad o bloqueados manualmente en la lista de inquilinos permitidos [o bloqueados.](tenant-allow-block-list.md)|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <p> _EnableUnauthenticatedSender_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md).|
|**Mostrar etiqueta "via"** <p> _EnableViaTag_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la **dirección MAIL FROM.** <p> Si esta configuración no está disponible para  usted, el signo de interrogación y la etiqueta via se controlan mediante la opción **Mostrar (?)** para remitentes no autenticados para la configuración de suplantación de identidad en su organización.|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender para la Office 365 seguridad

Las ventajas de seguridad adicionales vienen con una suscripción de Microsoft Defender para Office 365 suscripción. Para obtener las últimas noticias e información, puede ver [Novedades de Defender para Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - La directiva contra suplantación de identidad predeterminada [](set-up-anti-phishing-policies.md#spoof-settings) en Microsoft Defender para Office 365 proporciona protección contra suplantación de identidad e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras [características](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) de protección de suplantación disponibles y la configuración avanzada [no](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva contra suplantación de identidad predeterminada o cree directivas adicionales contra la suplantación de identidad.
>
> - No hay directivas de vínculos Caja fuerte predeterminadas ni directivas Caja fuerte datos adjuntos que protejan automáticamente a todos los destinatarios de la organización. Para obtener las protecciones, debe crear al menos una directiva Caja fuerte vínculos y una directiva Caja fuerte datos adjuntos.
>
> - [Caja fuerte datos adjuntos para SharePoint, OneDrive y](mdo-for-spo-odb-and-teams.md) Microsoft Teams protección y protección Caja fuerte [Documentos](safe-docs.md) no tienen dependencias en las directivas Caja fuerte vínculos.

Si la suscripción incluye Microsoft Defender para Office 365 o si has comprado Defender para Office 365 como complemento, establece las siguientes configuraciones estándar o estrictas.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directiva contra suplantación de identidad en Microsoft Defender para Office 365

Los clientes de EOP obtienen el anti phishing básico como se describió anteriormente, pero Microsoft Defender para Office 365 incluye más características y control para ayudar a prevenir, detectar y corregir los ataques. Para crear y configurar estas directivas, vea [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, vea Configuración de suplantación en directivas contra suplantación en [Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar estas opciones, vea [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|Usuarios protegidos (remitentes): **permitir a los usuarios proteger** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Desactivado <p> `$false` <p> ninguno|Activado <p> `$true` <p> \<list of users\>|Activado <p> `$true` <p> \<list of users\>|En función de la organización, se recomienda agregar usuarios (remitentes de mensajes) en roles clave. Internamente, los remitentes protegidos pueden ser su director general, director financiero y otros líderes sénior. Externamente, los remitentes protegidos podrían incluir miembros del consejo o su junta directiva.|
|Usuarios protegidos: **si el mensaje se detecta como un usuario suplantado** <p> _TargetedUserProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Poner en cuarentena el mensaje** <p> `Quarantine`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|Dominios protegidos: **incluir dominios de mi propiedad** <p> _EnableOrganizationDomainsProtection_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|Dominios protegidos: **incluir dominios personalizados** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Desactivado <p> `$false` <p> ninguno|Activado <p> `$true` <p> \<list of domains\>|Activado <p> `$true` <p> \<list of domains\>|Dependiendo de la organización, se recomienda agregar dominios (dominios de remitente) que no posee, pero con los que interactúa con frecuencia.|
|Dominios protegidos: **si el mensaje se detecta como un dominio suplantado** <p> _TargetedDomainProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Poner en cuarentena el mensaje** <p> `Quarantine`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Agregar dominios y remitentes de confianza** <p> _ExcludedSenders_ <p> _ExcludedDomains_|Ninguno|Ninguno|Ninguno|Según la organización, se recomienda agregar remitentes o dominios que se identifiquen incorrectamente como intentos de suplantación.|
|**Habilitar la inteligencia de buzones** <p> _EnableMailboxIntelligence_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Habilitar la inteligencia para la protección de suplantación** <p> _EnableMailboxIntelligenceProtection_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`|Esta configuración permite la acción especificada para las detecciones de suplantación por inteligencia de buzones.|
|**Si la inteligencia de buzones detecta y suplanta al usuario** <p> _MailboxIntelligenceProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Mostrar la suplantación de usuario consejo de seguridad** <p> _EnableSimilarUsersSafetyTips_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Mostrar la suplantación de dominio consejo de seguridad** <p> _EnableSimilarDomainsSafetyTips_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** <p> _EnableUnusualCharactersSafetyTips_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación de identidad en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Tenga en cuenta que estas son las mismas opciones que están disponibles en la configuración de directiva contra correo no [deseado en EOP](#eop-anti-spam-policy-settings).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Habilitar la inteligencia de suplantación** <p> _EnableSpoofIntelligence_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|**Si el correo electrónico se detecta como suplantación** <p> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`|Esta configuración se aplica a remitentes suplantados que se [](learn-about-spoof-intelligence.md) bloquearon automáticamente, como se muestra en la información de inteligencia de suplantación de identidad o bloqueados manualmente en la lista de inquilinos permitidos [o bloqueados.](tenant-allow-block-list.md)|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <p> _EnableUnauthenticatedSender_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md).|
|**Mostrar etiqueta "via"** <p> _EnableViaTag_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la **dirección MAIL FROM.** <p> Si esta configuración no está disponible para  usted, el signo de interrogación y la etiqueta via se controlan mediante la opción **Mostrar (?)** para remitentes no autenticados para la configuración de suplantación de identidad en su organización.|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración avanzada en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, consulte [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar esta configuración, vea [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico de suplantación de identidad** <p> _PhishThresholdLevel_|**1- Estándar** <p> `1`|**2 : agresivo** <p> `2`|**3: más agresivo** <p> `3`||
|

### <a name="safe-links-settings"></a>Caja fuerte Configuración de vínculos

Caja fuerte Los vínculos de Defender para Office 365 incluyen la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos de Caja fuerte activas y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, [vea Caja fuerte Links in Defender for Office 365](safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Configuración global de Caja fuerte vínculos

Para configurar estas opciones, vea [Configure global settings for Caja fuerte Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Usar Caja fuerte vínculos en: Office 365 aplicaciones** <p> _EnableSafeLinksForO365Clients_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`|Usa Caja fuerte links en aplicaciones Office 365 de escritorio y móviles (iOS y Android). Para obtener más información, [consulta Caja fuerte configuración de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).|
|**No realizar un seguimiento cuando los usuarios hacen clic en vínculos protegidos en Office 365 aplicaciones** <p> _TrackClicks_|Activada <p> `$false`|Desactivada <p> `$true`|Desactivado <p> `$true`|Desactivar esta configuración (establecer _TrackClicks_ en ) realiza un seguimiento de los clics del usuario `$true` en las aplicaciones Office 365 compatibles.|
|**No permitir que los usuarios hagan clic en la dirección URL original en Office 365 aplicaciones** <p> _AllowClickThrough_|Activado <p> `$false`|Activado <p> `$false`|Activado <p> `$false`|Al activar esta configuración (establecer _AllowClickThrough en_ ) se evita hacer clic en la dirección URL original en las `$false` aplicaciones Office 365 compatibles.|
|

#### <a name="safe-links-policy-settings"></a>Caja fuerte Configuración de directiva de vínculos

Para configurar estas opciones, consulte [Configurar Caja fuerte de vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

En PowerShell, use los [cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) y [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva Caja fuerte links predeterminada. Los valores de la columna Predeterminado son los valores predeterminados de las nuevas directivas Caja fuerte vínculos que cree.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes** <p> _IsEnabled_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Seleccione la acción para direcciones URL desconocidas o potencialmente malintencionadas en Microsoft Teams** <p> _EnableSafeLinksForTeams_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Aplicar análisis de url en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos** <p> _ScanUrls_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje** <p> _DeliverMessageAfterScan_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**Aplicar Caja fuerte a los mensajes de correo electrónico enviados dentro de la organización** <p> _EnableForInternalSenders_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`||
|**No realizar un seguimiento de los clics del usuario** <p> _DoNotTrackUserClicks_|Desactivado <p> `$false`|Desactivado <p> `$false`|Desactivado <p> `$false`|Desactivar esta configuración (establecer _DoNotTrackUserClicks_ en `$false` ) realiza un seguimiento de los clics de los usuarios.|
|**No permitir que los usuarios hagan clic en la dirección URL original** <p> _DoNotAllowClickThrough_|Desactivada <p> `$false`|Activada <p> `$true`|Activado <p> `$true`|Al activar esta configuración (al _establecer DoNotAllowClickThrough en_ ) se evita `$true` hacer clic en la dirección URL original.|
|

### <a name="safe-attachments-settings"></a>Caja fuerte Configuración de datos adjuntos

Caja fuerte Los datos adjuntos de Microsoft Defender para Office 365 incluyen la configuración global que no tiene ninguna relación con las directivas de datos adjuntos de Caja fuerte y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, [vea Caja fuerte Attachments in Defender para Office 365](safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Configuración global de datos Caja fuerte datos adjuntos

Para configurar estas opciones, vea Activar Caja fuerte datos adjuntos para [SharePoint, OneDrive y](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams y [Caja fuerte documentos en Microsoft 365 E5](safe-docs.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Activado <p> `$true`|Activado <p> `$true`||
|**Activar documentos Caja fuerte para Office clientes** <p> _EnableSafeDocs_|Activado <p> `$true`|Activado <p> `$true`|Esta configuración solo está disponible con Microsoft 365 E5 o Seguridad de Microsoft 365 E5 licencias. Para obtener más información, [vea Caja fuerte Documents in Microsoft Defender for Office 365](safe-docs.md).|
|**Permitir que las personas haga clic en la vista protegida incluso si Caja fuerte documentos identifican el archivo como malintencionado** <p> _AllowSafeDocsOpen_|Desactivado <p> `$false`|Desactivado <p> `$false`|Esta configuración está relacionada con Caja fuerte documentos.|
|

#### <a name="safe-attachments-policy-settings"></a>Caja fuerte Configuración de directiva de datos adjuntos

Para configurar estas opciones, consulte [Configurar Caja fuerte de datos adjuntos en Defender para Office 365](set-up-safe-attachments-policies.md).

En PowerShell, use los cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) y [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva Caja fuerte de datos adjuntos predeterminada. Los valores de la columna Predeterminado son los valores predeterminados en las nuevas directivas Caja fuerte datos adjuntos que cree.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Caja fuerte Respuesta de malware desconocido de datos adjuntos** <p> _Action_|Bloquear <p> `Block`|Bloquear <p> `Block`|Bloquear <p> `Block`||
|**Datos adjuntos de redireccionamiento al detectar:** **Habilitar redireccionamiento** <p> _Redirigir_ <p> _RedirectAddress_|Desactivado y sin dirección de correo electrónico especificada. <p> `$true` <p> ninguno|On y especifique una dirección de correo electrónico. <p> `$true` <p> una dirección de correo electrónico|On y especifique una dirección de correo electrónico. <p> `$true` <p> una dirección de correo electrónico|Redirigir mensajes a un administrador de seguridad para su revisión.|
|**Aplica la selección anterior si el examen de malware en busca de datos adjuntos tiene tiempo de espera o se produce un error.** <p> _ActionOnError_|Activado <p> `$true`|Activado <p> `$true`|Activado <p> `$true`||
|

## <a name="related-articles"></a>Artículos relacionados

- ¿Está buscando procedimientos recomendados para Exchange de flujo de **correo (también conocidas como reglas de transporte)?** Consulte [Procedimientos recomendados para configurar reglas de flujo](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)de correo en Exchange Online .

- Los administradores y los usuarios pueden enviar falsos positivos (buen correo electrónico marcado como negativo) y falsos negativos (correo electrónico no permitido) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estos vínculos para obtener información sobre cómo **configurar el** servicio [EOP](/exchange/standalone-eop/set-up-your-eop-service)y **configurar** Microsoft Defender [para Office 365](defender-for-office-365.md). No olvide las instrucciones útiles en['Proteger contra amenazas en Office 365'.](protect-against-threats.md)

- Las líneas base de seguridad para **Windows** se pueden encontrar aquí: ¿Dónde puedo obtener las líneas base de [seguridad?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO/local y Usar líneas base de seguridad para configurar [dispositivos Windows 10](/intune/protect/security-baselines) en Intune para la seguridad basada en Intune. Por último, una comparación entre Las líneas base de seguridad de Microsoft Defender para endpoint y Microsoft Intune está disponible en Comparar las líneas base de seguridad de Microsoft Defender para Endpoint y Windows [de seguridad de Intune.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
