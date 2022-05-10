---
title: Recomendaciones de Microsoft para la configuración de seguridad de EOP y Defender para Office 365
keywords: Office 365 recomendaciones de seguridad, Marco de directivas de remitente, Informes y conformidad de mensajes basados en dominio, Correo identificado con DomainKeys, pasos, cómo funciona, líneas base de seguridad, líneas base para EOP, líneas base para Defender para Office 365, configurar Defender para Office 365, configurar EOP, configurar Defender para Office 365, configurar EOP, configuración de seguridad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: ¿Cuáles son los procedimientos recomendados para Exchange Online Protection (EOP) y Defender para Office 365 configuración de seguridad? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué se debe usar si desea ser más estricto? ¿Y qué extras obtienes si también usas Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6e2b52c9dbde60dfb554dd92c8a0cae2ba05ced
ms.sourcegitcommit: 4cd8be7c22d29100478dce225dce3bcdce52644d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "65302296"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configuración recomendada de seguridad para EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** es el núcleo de seguridad de las suscripciones Microsoft 365 y ayuda a evitar que los correos electrónicos malintencionados lleguen a las bandejas de entrada de los empleados. Pero con nuevos ataques más sofisticados que aparecen cada día, a menudo se requieren protecciones mejoradas. **Microsoft Defender para Office 365** Plan 1 o Plan 2 contienen características adicionales que proporcionan a los administradores más niveles de seguridad, control e investigación.

Aunque se permite a los administradores de seguridad personalizar su configuración de seguridad, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que se recomiendan: **Estándar** y **Estricto**. Aunque los entornos y las necesidades de los clientes son diferentes, estos niveles de filtrado ayudarán a evitar que el correo no deseado llegue a la Bandeja de entrada de los empleados en la mayoría de las situaciones.

Para aplicar automáticamente la configuración estándar o estricta a los usuarios, consulte [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

En este artículo se describen la configuración predeterminada y también la configuración estándar y estricta recomendada para ayudar a proteger a los usuarios. Las tablas contienen la configuración del portal de Microsoft 365 Defender y PowerShell (Exchange Online PowerShell o PowerShell Exchange Online Protection independiente para organizaciones sin buzones de Exchange Online).

> [!NOTE]
> El módulo Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) para PowerShell puede ayudarle (los administradores) a encontrar los valores actuales de esta configuración. En concreto, el cmdlet **Get-ORCAReport** genera una evaluación de la configuración de protección contra el correo no deseado, la suplantación de identidad (phishing) y otras configuraciones de higiene de mensajes. Puede descargar el módulo ORCA en <https://www.powershellgallery.com/packages/ORCA/>.
>
> En Microsoft 365 organizaciones, se recomienda dejar el filtro de correo no deseado en Outlook establecido en **Sin filtrado automático** para evitar conflictos innecesarios (positivos y negativos) con los veredictos de filtrado de correo no deseado de EOP. Para más información, consulte los siguientes artículos:
>
> - [Configurar las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)
> - [Acerca de la configuración del correo no deseado en Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)
> - [Cambiar el nivel de protección en el filtro correo no deseado](https://support.microsoft.com/en-us/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)
> - [Creación de listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md)
> - [Creación de listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md)

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo no deseado, antimalware y contra suplantación de identidad (phishing) en EOP

El antispam, el antimalware y la suplantación de identidad son características de EOP que pueden configurar los administradores. Se recomiendan las siguientes configuraciones Estándar o Estricta.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de directivas contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, consulte [Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico masivo & propiedades de correo no deseado**|||||
|**Umbral de correo electrónico masivo** <br/><br/> _BulkThreshold_|7 |6 |4|Para obtener más información, consulte [Nivel de quejas masivas (BCL) en EOP](bulk-complaint-level-values.md).|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|Esta configuración solo está disponible en PowerShell.|
|**Aumentar la configuración de puntuación de correo no deseado**|Desactivado|Desactivado|Desactivado|Todas estas configuraciones forman parte del filtro de correo no deseado avanzado (ASF). Para obtener más información, consulte la sección [Configuración de ASF en las directivas contra correo no deseado](#asf-settings-in-anti-spam-policies) de este artículo.|
|**Marcar como configuración de correo no deseado**|Desactivado|Desactivado|Desactivado|La mayoría de estas configuraciones forman parte de ASF. Para obtener más información, consulte la sección [Configuración de ASF en las directivas contra correo no deseado](#asf-settings-in-anti-spam-policies) de este artículo.|
|**Contiene idiomas específicos** <br/><br/> _EnableLanguageBlockList_ <br/><br/> _LanguageBlockList_|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|No tenemos ninguna recomendación específica para esta configuración. Puede bloquear mensajes en lenguajes específicos en función de sus necesidades empresariales.|
|**De estos países** <br/><br/> _EnableRegionBlockList_ <br/><br/> _RegionBlockList_|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|No tenemos ninguna recomendación específica para esta configuración. Puede bloquear mensajes de países específicos en función de sus necesidades empresariales.|
|**Modo de prueba** (_TestModeAction_)|**Ninguna**|**Ninguna**|**Ninguna**|Esta configuración forma parte de ASF. Para obtener más información, consulte la sección [Configuración de ASF en las directivas contra correo no deseado](#asf-settings-in-anti-spam-policies) de este artículo.|
|**Acciones**||||Dondequiera que seleccione **Mensaje de cuarentena**, hay disponible un cuadro **Seleccionar directiva de cuarentena** . Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. <br/><br/> Al crear una nueva directiva contra correo no deseado, un valor en blanco significa que la directiva de cuarentena predeterminada se usa para definir las capacidades históricas de los mensajes que se pusieron en cuarentena por ese veredicto determinado (AdminOnlyAccessPolicy para **suplantación de identidad de alta confianza**; DefaultFullAccessPolicy para todo lo demás). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definan funcionalidades más restrictivas o menos restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|Acción de detección de **correo no deseado** <br/><br/> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **correo no deseado de alta confianza** <br/><br/> _HighConfidenceSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|Acción de detección de **suplantación de identidad** <br/><br/> _PhishSpamAction_|**Mover el mensaje a la carpeta correo no deseado**<sup>\*</sup> <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|<sup>\*</sup> El valor predeterminado es **Mover mensaje a la carpeta Correo electrónico no deseado** en la directiva de correo no deseado predeterminada y en las nuevas directivas de correo no deseado que cree en PowerShell. El valor predeterminado es **Mensaje de cuarentena** en las nuevas directivas de antispam que se crean en el portal de Microsoft 365 Defender.|
|Acción de detección de **suplantación de identidad (phishing) de alta confianza** <br/><br/> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Acción** de detección masiva <br/><br/> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Conservar el correo no deseado en cuarentena durante estos días** <br/><br/> _QuarantineRetentionPeriod_|15 días<sup>\*</sup>|30 días|30 días|<sup>\*</sup> El valor predeterminado es 15 días en la directiva predeterminada contra correo no deseado y en las nuevas directivas contra correo no deseado que cree en PowerShell. El valor predeterminado es 30 días en las nuevas directivas contra correo no deseado que cree en el portal de Microsoft 365 Defender. <br/><br/> Este valor también afecta a los mensajes que están en cuarentena mediante directivas anti phishing. Para obtener más información, vea [Mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).|
|**Habilitar sugerencias de seguridad de correo no deseado** <br/><br/> _InlineSafetyTipsEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|Habilitación de la purga automática de cero horas (ZAP) para mensajes de suplantación de identidad <br/><br/> _PhishZapEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|Habilitación de ZAP para mensajes de correo no deseado <br/><br/> _SpamZapEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Permitir & lista de bloques**|||||
|Remitentes permitidos <br/><br/> _AllowedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente permitidos <br/><br/> _AllowedSenderDomains_|Ninguno|Ninguno|Ninguno|Agregar dominios a la lista de remitentes permitidos es una muy mala idea. Los atacantes podrían enviarle un correo electrónico que, de lo contrario, se filtraría. <br/><br/> Use la [información de inteligencia sobre suplantación](learn-about-spoof-intelligence.md) de identidad y la lista de permitidos [o bloqueados](tenant-allow-block-list.md) de inquilinos para revisar todos los remitentes que suplantan las direcciones de correo electrónico del remitente en los dominios de correo electrónico de la organización o suplantan las direcciones de correo electrónico del remitente en dominios externos.|
|Remitentes bloqueados <br/><br/> _BlockedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente bloqueados <br/><br/> _BlockedSenderDomains_|Ninguno|Ninguno|Ninguno||

#### <a name="asf-settings-in-anti-spam-policies"></a>Configuración de ASF en directivas contra correo no deseado

En la tabla de esta sección se describe la configuración del filtro de correo no deseado avanzado (ASF) que están disponibles en las directivas contra correo no deseado. Todas estas configuraciones están **desactivadas** para los niveles **Estándar** y **Estricto** . Para obtener más información sobre la configuración de ASF, consulte [Configuración avanzada de filtro de correo no deseado (ASF) en EOP](advanced-spam-filtering-asf-options.md).

|Nombre de la característica de seguridad|Comentario|
|---|---|
|**Vínculos de imagen a sitios remotos** (_IncreaseScoreWithImageLinks_)||
|**Dirección IP numérica en la dirección URL** (_IncreaseScoreWithNumericIps_)||
|**Redirección de dirección URL a otro puerto** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Vínculos a sitios web .biz o .info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensajes vacíos** (_MarkAsSpamEmptyMessages_)||
|**Insertar etiquetas en HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**JavaScript o VBScript en HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Etiquetas de formulario en HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Etiquetas frame o iframe en HTML** (_MarkAsSpamFramesInHtml_)||
|**Errores web en HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Etiquetas de objeto en HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Palabras confidenciales** (_MarkAsSpamSensitiveWordList_)||
|**Registro SPF: error duro** (_MarkAsSpamSpfRecordHardFail_)||
|**Error de filtrado de identificador de remitente** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|**Modo de prueba** (_TestModeAction_)|En el caso de las opciones de ASF que admiten **Probar** como una acción, puede configurar la acción del modo de prueba en **Ninguno**, **Agregar texto de encabezado X predeterminado** o **Enviar mensaje cco** (`None`, `AddXHeader`o `BccMessage`). Para obtener más información, vea [Habilitar, deshabilitar o probar la configuración de ASF](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings).|

#### <a name="eop-outbound-spam-policy-settings"></a>Configuración de la directiva de correo no deseado saliente de EOP

Para crear y configurar directivas de correo no deseado saliente, consulte [Configuración del filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).

Para obtener más información sobre los límites de envío predeterminados en el servicio, consulte [Límites de envío](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

> [!NOTE]
> Las directivas de correo no deseado saliente no forman parte de las directivas de seguridad preestablecidas Estándar o Estricta. Los valores **Estándar** y **Estricto** indican nuestros valores **recomendados** en la directiva de correo no deseado saliente predeterminada o en las directivas de correo no deseado de salida personalizadas que cree.

|Nombre de la característica de seguridad|Predeterminado|Recomendado<br/>Estándar|Recomendado<br/>Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Establecimiento de un límite de mensajes externos** <br/><br/> _RecipientLimitExternalPerHour_|0|500|400|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Establecimiento de un límite de mensajes interno** <br/><br/> _RecipientLimitInternalPerHour_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Establecer un límite de mensajes diario** <br/><br/> _RecipientLimitPerDay_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Restricción impuesta a los usuarios que alcanzan el límite de mensajes** <br/><br/> _ActionWhenThresholdReached_|**Restringir al usuario el envío de correo hasta el día siguiente** <br/><br/> `BlockUserForToday`|**Restricción del envío de correo por parte del usuario** <br/><br/> `BlockUser`|**Restricción del envío de correo por parte del usuario** <br/><br/> `BlockUser`||
|**Reglas de reenvío automático** <br/><br/> _AutoForwardingMode_|**Automático: controlado por el sistema** <br/><br/> `Automatic`|**Automático: controlado por el sistema** <br/><br/> `Automatic`|**Automático: controlado por el sistema** <br/><br/> `Automatic`|
|**Enviar una copia de mensajes salientes que superen estos límites a estos usuarios y grupos** <br/><br/> _BccSuspiciousOutboundMail_ <br/><br/> _BccSuspiciousOutboundAdditionalRecipients_|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Esta configuración solo funciona en la directiva de correo no deseado saliente predeterminada. No funciona en las directivas de correo no deseado saliente personalizadas que cree.|
|**Notificar a estos usuarios y grupos si un remitente está bloqueado debido al envío de correo no deseado saliente** <br/><br/> _NotifyOutboundSpam_ <br/><br/> _NotifyOutboundSpamRecipients_|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|La [directiva de alerta](../../compliance/alert-policies.md) predeterminada denominada **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in policy. **Se recomienda encarecidamente usar la directiva de alertas en lugar de esta configuración en la directiva de correo no deseado saliente para notificar a los administradores y a otros usuarios**. Para obtener instrucciones, consulte [Comprobación de la configuración de alertas para usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).|

### <a name="eop-anti-malware-policy-settings"></a>Configuración de directivas antimalware de EOP

Para crear y configurar directivas antimalware, consulte [Configurar directivas antimalware en EOP](configure-anti-malware-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Configuración de protección**|||||
|**Habilitación del filtro de datos adjuntos comunes** <br/><br/> _EnableFileFilter_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Esta configuración pone en cuarentena los mensajes que contienen datos adjuntos ejecutables en función del tipo de archivo, independientemente del contenido de los datos adjuntos.|
|**Habilitación de la purga automática de cero horas para malware** <br/><br/> _ZapEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Directiva de cuarentena**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Al crear una nueva directiva antimalware, un valor en blanco significa que la directiva de cuarentena predeterminada se usa para definir las funcionalidades históricas de los mensajes que se pusieron en cuarentena como malware (AdminOnlyAccessPolicy). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definan más funcionalidades para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Notificaciones de destinatarios**|||||
|**Notificar a los destinatarios cuando los mensajes se ponen en cuarentena como malware** <br/><br/> _Action_|No seleccionada <br/><br/> _DeleteMessage_|No seleccionada <br/><br/> _DeleteMessage_|No seleccionada <br/><br/> _DeleteMessage_|Si se detecta malware en los datos adjuntos de un correo electrónico, el mensaje se pone en cuarentena y solo lo puede liberar un administrador.|
|**Notificaciones del remitente**|||||
|**Notificar a los remitentes internos cuando los mensajes se ponen en cuarentena como malware** <br/><br/> _EnableInternalSenderNotifications_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**Notificar a remitentes externos cuando los mensajes se ponen en cuarentena como malware** <br/><br/> _EnableExternalSenderNotifications_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**Notificaciones de administrador**|||||
|**Notificar a un administrador acerca de los mensajes no entregados de remitentes internos** <br/><br/> _EnableInternalSenderAdminNotifications_ <br/><br/> _InternalSenderAdminAddress_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No tenemos ninguna recomendación específica para esta configuración.|
|**Notificar a un administrador acerca de los mensajes no entregados de remitentes externos** <br/><br/> _EnableExternalSenderAdminNotifications_ <br/><br/> _ExternalSenderAdminAddress_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No tenemos ninguna recomendación específica para esta configuración.|
|**Personalización de notificaciones**||||No tenemos recomendaciones específicas para esta configuración.|
|**Usar texto de notificación personalizado** <br/><br/> _CustomNotifications_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**Nombre De** <br/><br/> _CustomFromName_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Dirección de origen** <br/><br/> _CustomFromAddress_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Personalización de notificaciones para mensajes de remitentes internos**||||Esta configuración solo se usa si se selecciona **Notificar a los remitentes internos cuando los mensajes se ponen en cuarentena como malware** o **Notificar a un administrador acerca de los mensajes no entregados de remitentes internos** .|
|**Asunto** <br/><br/> _CustomInternalSubject_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Message** <br/><br/> _CustomInternalBody_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Personalización de notificaciones para mensajes de remitentes externos**||||Esta configuración solo se usa si se selecciona **Notificar a remitentes externos cuando los mensajes se ponen en cuarentena como malware** o **Notificar a un administrador acerca de los mensajes no entregados de remitentes externos** .|
|**Asunto** <br/><br/> _CustomExternalSubject_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Message** <br/><br/> _CustomExternalBody_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||

### <a name="eop-anti-phishing-policy-settings"></a>Configuración de la directiva contra suplantación de identidad (EOP)

Para obtener más información sobre esta configuración, consulte [Configuración de suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings). Para configurar estas opciones, consulte [Configuración de directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md).

La configuración de suplantación de identidad está relacionada entre sí, pero la opción **Mostrar primer contacto consejo de seguridad** no depende de la configuración de suplantación de identidad.

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección & umbral de suplantación de identidad**|||||
|**Habilitación de la inteligencia de suplantación de identidad** <br/><br/> _EnableSpoofIntelligence_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Acciones**|||||
|**Si el mensaje se detecta como suplantación de identidad** <br/><br/> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esta configuración se aplica a los remitentes suplantados que se bloquearon automáticamente como se muestra en la [información de inteligencia sobre suplantación de identidad](learn-about-spoof-intelligence.md) o que se bloquearon manualmente en la [lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md). <br/><br/> Si selecciona **Poner en cuarentena el mensaje**, hay disponible un cuadro **Aplicar directiva de cuarentena** para seleccionar la directiva de cuarentena que define lo que los usuarios pueden hacer en los mensajes que se ponen en cuarentena como suplantación de identidad. Al crear una nueva directiva contra suplantación de identidad (phishing), un valor en blanco significa que la directiva de cuarentena predeterminada se usa para definir las funcionalidades históricas de los mensajes que se pusieron en cuarentena como suplantación de identidad (DefaultFullAccessPolicy). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definan funcionalidades más restrictivas o menos restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Mostrar el primer consejo de seguridad de contacto** <br/><br/> _EnableFirstContactSafetyTips_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|Para obtener más información, consulte [Primer contacto consejo de seguridad](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <br/><br/> _EnableUnauthenticatedSender_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Remitente no autenticado](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostrar etiqueta "via"** <br/><br/> _EnableViaTag_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección From si es diferente del dominio de la firma DKIM o de la dirección **MAIL FROM** . <br/><br/> Para obtener más información, vea [Remitente no autenticado](set-up-anti-phishing-policies.md#unauthenticated-sender).|

## <a name="microsoft-defender-for-office-365-security"></a>seguridad de Microsoft Defender para Office 365

Las ventajas de seguridad adicionales incluyen una suscripción Microsoft Defender para Office 365. Para obtener las últimas noticias e información, puede ver [las novedades de Defender para Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - La directiva predeterminada contra suplantación de identidad (phishing) de Microsoft Defender para Office 365 proporciona [protección contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras características de [protección de suplantación](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibles y [la configuración avanzada](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) no están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva predeterminada contra suplantación de identidad (phishing) o cree directivas adicionales contra phishing.
>
> - Aunque no hay ninguna directiva de datos adjuntos de Caja fuerte predeterminada ni directiva de vínculos de Caja fuerte, la directiva de seguridad preestablecida de **protección integrada** proporciona Caja fuerte protección de datos adjuntos y Caja fuerte La protección de vínculos a todos los destinatarios (usuarios que no están definidos en directivas de datos adjuntos Caja fuerte personalizados o Caja fuerte Directivas de vínculos). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).
>
> - [Caja fuerte Los datos adjuntos para la protección de SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md) y [la protección de documentos de Caja fuerte](safe-docs.md) no tienen dependencias en las directivas de vínculos de Caja fuerte.

Si la suscripción incluye Microsoft Defender para Office 365 o si ha comprado Defender para Office 365 como complemento, establezca las siguientes configuraciones Estándar o Estricta.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365

Los clientes de EOP obtienen anti-phishing básico como se describió anteriormente, pero Defender para Office 365 incluye más características y control para ayudar a prevenir, detectar y corregir ataques. Para crear y configurar estas directivas, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración avanzada en las directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información sobre esta configuración, consulte [Umbrales avanzados de suplantación de identidad en las directivas contra suplantación de identidad en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar esta configuración, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico de suplantación de identidad** <br/><br/> _PhishThresholdLevel_|**1- Estándar** <br/><br/> `1`|**2 - Agresivo** <br/><br/> `2`|**3 - Más agresivo** <br/><br/> `3`||

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información sobre esta configuración, consulte [Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar estas opciones, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección & umbral de suplantación de identidad**|||||
|**Permitir que los usuarios protejan** (protección de usuarios suplantados) <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|No seleccionada <br/><br/> `$false` <br/><br/> ninguno|Seleccionado <br/><br/> `$true` <br/><br/> \<list of users\>|Seleccionado <br/><br/> `$true` <br/><br/> \<list of users\>|Se recomienda agregar usuarios (remitentes de mensajes) en roles clave. Internamente, los remitentes protegidos pueden ser su director general, director financiero y otros líderes sénior. Externamente, los remitentes protegidos podrían incluir miembros del consejo o su consejo de administración. <br/><br/> En las directivas de seguridad preestablecidas, no puede especificar los usuarios que se van a proteger. Debe deshabilitar las directivas de seguridad preestablecidas y usar directivas anti phishing personalizadas para agregar usuarios en roles clave como se sugiere.|
|**Habilitar dominios para proteger** (protección de dominio suplantado)|No seleccionada|Seleccionado|Seleccionado||
|**Incluir dominios de mi propiedad** <br/><br/> _EnableOrganizationDomainsProtection_|Desactivado <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Incluir dominios personalizados** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Desactivado <br/><br/> `$false` <br/><br/> ninguno|Seleccionado <br/><br/> `$true` <br/><br/> \<list of domains\>|Seleccionado <br/><br/> `$true` <br/><br/> \<list of domains\>|Se recomienda agregar dominios (dominios de remitente) que no posea, pero que interactúe con frecuencia. <br/><br/> En las directivas de seguridad preestablecidas, no puede especificar los dominios custm que se van a proteger. Debe deshabilitar las directivas de seguridad preestablecidas y usar directivas anti phishing personalizadas para agregar dominios personalizados para protegerlos según lo sugerido.|
|**Agregar dominios y remitentes de confianza** <br/><br/> _ExcludedSenders_ <br/><br/> _ExcludedDomains_|Ninguno|Ninguno|Ninguno|En función de su organización, se recomienda agregar remitentes o dominios que se identifiquen incorrectamente como intentos de suplantación.|
|**Habilitación de la inteligencia de buzones** <br/><br/> _EnableMailboxIntelligence_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Habilitación de la inteligencia para la protección contra suplantación** <br/><br/> _EnableMailboxIntelligenceProtection_|Desactivado <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Esta configuración permite la acción especificada para las detecciones de suplantación por parte de la inteligencia del buzón de correo.|
|**Acciones**||||Dondequiera que seleccione **Poner en cuarentena el mensaje**, hay disponible un cuadro **Seleccionar directiva de cuarentena** . Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. <br/><br/> Cuando se crea una nueva directiva contra phishing, un valor en blanco significa que la directiva de cuarentena predeterminada se usa para definir las funcionalidades históricas de los mensajes que ese veredicto ha puesto en cuarentena (DefaultFullAccessPolicy para todos los tipos de detección de suplantación). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definan funcionalidades menos restrictivas o más restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Si el mensaje se detecta como un usuario suplantado** <br/><br/> _TargetedUserProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Recuerde que las directivas de seguridad preestablecidas no permiten especificar los usuarios que se van a proteger, por lo que esta configuración no hace nada en las directivas de seguridad preestablecidas.|
|**Si el mensaje se detecta como un dominio suplantado** <br/><br/> _TargetedDomainProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Recuerde que las directivas de seguridad preestablecidas no permiten especificar los dominios personalizados que se van a proteger, por lo que esta configuración afecta solo a los dominios que posee, no a los dominios personalizados.|
|**Si la inteligencia del buzón detecta y suplanta al usuario** <br/><br/> _MailboxIntelligenceProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|**Mostrar consejo de seguridad de suplantación de usuario** <br/><br/> _EnableSimilarUsersSafetyTips_|Desactivado <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Mostrar consejo de seguridad de suplantación de dominio** <br/><br/> _EnableSimilarDomainsSafetyTips_|Desactivado <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** <br/><br/> _EnableUnusualCharactersSafetyTips_|Desactivado <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directivas contra phishing de EOP en Microsoft Defender para Office 365

Estas son las mismas configuraciones que están disponibles en la [configuración de directivas contra correo no deseado en EOP](#eop-anti-spam-policy-settings).

### <a name="safe-attachments-settings"></a>configuración de datos adjuntos de Caja fuerte

Caja fuerte Datos adjuntos de Microsoft Defender para Office 365 incluye la configuración global que no tiene ninguna relación con las directivas de datos adjuntos de Caja fuerte y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, consulte [datos adjuntos de Caja fuerte en Defender para Office 365](safe-attachments.md).

Aunque no hay ninguna directiva de datos adjuntos de Caja fuerte predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona Caja fuerte protección de datos adjuntos a todos los destinatarios (usuarios que no están definidos en directivas personalizadas de datos adjuntos de Caja fuerte). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

#### <a name="global-settings-for-safe-attachments"></a>Configuración global de datos adjuntos de Caja fuerte

> [!NOTE]
> La configuración global de los datos adjuntos de Caja fuerte se establece mediante la directiva de seguridad preestablecida **de protección integrada**, pero no por las directivas de seguridad preestablecidas **Estándar** o **Estricta**. En cualquier caso, los administradores pueden modificar esta configuración global de datos adjuntos de Caja fuerte en cualquier momento.
>
> La columna **Predeterminado** muestra los valores anteriores a la existencia de la directiva de seguridad preestablecida **de protección integrada** . La columna **Protección integrada** muestra los valores establecidos por la directiva de seguridad preestablecida **de protección integrada** , que también son nuestros valores recomendados.

Para configurar estas opciones, consulte [Activar datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) y [Caja fuerte Documentos en Microsoft 365 E5](safe-docs.md).

En PowerShell, se usa el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

|Nombre de la característica de seguridad|Predeterminado|Protección integrada|Comentario|
|---|:---:|:---:|---|
|**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Para evitar que los usuarios descarguen archivos malintencionados, consulte [Uso SharePoint PowerShell en línea para evitar que los usuarios descarguen archivos malintencionados](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).|
|**Activar Caja fuerte Documentos para clientes de Office** <br/><br/> _EnableSafeDocs_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Esta característica solo está disponible y es significativa con licencias que no se incluyen en Defender para Office 365 (por ejemplo, Microsoft 365 E5 o Seguridad de Microsoft 365 E5). Para obtener más información, consulte [Caja fuerte Documentos en Microsoft 365 E5](safe-docs.md).|
|**Permitir a los usuarios hacer clic en la vista protegida incluso si Caja fuerte documentos identificaron el archivo como malintencionado** <br/><br/> _AllowSafeDocsOpen_|Desactivado <br/><br/> `$false`|Desactivado <br/><br/> `$false`|Esta configuración está relacionada con Caja fuerte Documents.|

#### <a name="safe-attachments-policy-settings"></a>configuración de la directiva de datos adjuntos de Caja fuerte

Para configurar estas opciones, consulte [Configuración de directivas de datos adjuntos de Caja fuerte en Defender para Office 365](set-up-safe-attachments-policies.md).

En PowerShell, se usan los cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) y [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva de datos adjuntos de Caja fuerte predeterminada, pero la directiva [de seguridad preestablecida **de protección integrada**](preset-security-policies.md) asigna Caja fuerte protección de datos adjuntos a todos los destinatarios.
>
> La columna **Predeterminado en personalizado** hace referencia a los valores predeterminados de las nuevas directivas de datos adjuntos Caja fuerte que se crean. Las columnas restantes indican (a menos que se indique lo contrario) los valores configurados en las directivas de seguridad preestablecidas correspondientes.

|Nombre de la característica de seguridad|Valor predeterminado en personalizado|Protección integrada|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|:---:|---|
|**Caja fuerte respuesta de malware desconocida de datos adjuntos** <br/><br/> _Habilitar_ y _actuar_|**Desactivado** <br/><br/> `-Enable $false` y `-Action Block`|**Bloquear** <br/><br/> `-Enable $true` y `-Action Block`|**Bloquear** <br/><br/> `-Enable $true` y `-Action Block`|**Bloquear** <br/><br/> `-Enable $true` y `-Action Block`|Cuando se $false el parámetro _Enable_ , el valor del parámetro _Action_ no importa.|
|**Directiva de cuarentena** (_QuarantineTag_)|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Al crear una nueva directiva de datos adjuntos de Caja fuerte, un valor en blanco significa que la directiva de cuarentena predeterminada se usa para definir las funcionalidades históricas de los mensajes que Caja fuerte Attachments (AdminOnlyAccessPolicy) pusieron en cuarentena. <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definan más funcionalidades para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Redireccionamiento de datos adjuntos con datos adjuntos detectados** : **habilitación del redireccionamiento** <br/><br/> _Redirigir_ <br/><br/> _RedirectAddress_|No seleccionado y no se ha especificado ninguna dirección de correo electrónico. <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress_ está en blanco (`$null`)|No seleccionado y no se ha especificado ninguna dirección de correo electrónico. <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress_ está en blanco (`$null`)|Seleccionado y especifique una dirección de correo electrónico. <br/><br/> `$true` <br/><br/> una dirección de correo electrónico|Seleccionado y especifique una dirección de correo electrónico. <br/><br/> `$true` <br/><br/> una dirección de correo electrónico|Redirigir mensajes a un administrador de seguridad para su revisión. <br/><br/> **Nota**: Esta configuración no está configurada en las directivas de seguridad preestablecidas **de protección estándar**, **estricta** o **integrada** . Los valores **Estándar** y **Estricto** indican los valores **recomendados** en las nuevas directivas de datos adjuntos de Caja fuerte que se crean.|
|**Aplicar la respuesta de detección de datos adjuntos Caja fuerte si no se puede completar el examen (tiempo de espera o errores)** <br/><br/> _ActionOnError_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||

### <a name="safe-links-settings"></a>configuración de vínculos de Caja fuerte

Caja fuerte Vínculos de Defender para Office 365 incluye la configuración global que se aplica a todos los usuarios que se incluyen en las directivas activas de vínculos de Caja fuerte y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, consulte [vínculos de Caja fuerte en Defender para Office 365](safe-links.md).

Aunque no hay ninguna directiva de vínculos de Caja fuerte predeterminada, la directiva de seguridad preestablecida de **protección integrada** proporciona protección de vínculos Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas personalizadas de vínculos de Caja fuerte). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

#### <a name="global-settings-for-safe-links"></a>Configuración global de vínculos de Caja fuerte

> [!NOTE]
> La configuración global de Caja fuerte Links se establece mediante la directiva de seguridad preestablecida **de protección integrada**, pero no por las directivas de seguridad preestablecidas **Estándar** o **Estricta**. En cualquier caso, los administradores pueden modificar esta configuración global de vínculos de Caja fuerte en cualquier momento.
>
> La columna **Predeterminado** muestra los valores anteriores a la existencia de la directiva de seguridad preestablecida **de protección integrada** . La columna **Protección integrada** muestra los valores establecidos por la directiva de seguridad preestablecida **de protección integrada** , que también son nuestros valores recomendados.

Para configurar estas opciones, consulte [Configuración global de vínculos de Caja fuerte en Defender para Office 365](configure-global-settings-for-safe-links.md).

En PowerShell, se usa el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

|Nombre de la característica de seguridad|Predeterminado|Protección integrada|Comentario|
|---|:---:|:---:|---|
|**Bloquear las siguientes direcciones URL** <br/><br/> _ExcludedUrls_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Para obtener más información, consulte [la lista "Bloquear las siguientes direcciones URL" para Caja fuerte Vínculos](safe-links.md#block-the-following-urls-list-for-safe-links).
|**Uso de vínculos de Caja fuerte en aplicaciones de Office 365** <br/><br/> _EnableSafeLinksForO365Clients_|Activado <br/><br/> `$true`|Activado <br/><br/> `$true`|Use vínculos de Caja fuerte en aplicaciones de escritorio y dispositivos móviles (iOS y Android) compatibles con Office 365. Para obtener más información, consulte [configuración de vínculos de Caja fuerte para aplicaciones de Office 365](safe-links.md#safe-links-settings-for-office-365-apps).|
|**No realizar un seguimiento cuando los usuarios hacen clic en vínculos protegidos en Office 365 aplicaciones** <br/><br/> _TrackClicks_|Activada <br/><br/> `$false`|Desactivada <br/><br/> `$true`|Al desactivar esta configuración (establecer _TrackClicks_ `$true`en ) se realiza un seguimiento de los clics del usuario en las aplicaciones Office 365 admitidas.|
|**No permitir que los usuarios hagan clic en la dirección URL original en Office 365 aplicaciones** <br/><br/> _AllowClickThrough_|Activado <br/><br/> `$false`|Activado <br/><br/> `$false`|Al activar esta configuración (establecer _AllowClickThrough_ `$false`en ) se impide hacer clic en la dirección URL original en las aplicaciones Office 365 admitidas.|

#### <a name="safe-links-policy-settings"></a>Configuración de directiva de vínculos seguros

Para configurar estas opciones, consulte [Configuración de directivas de vínculos de Caja fuerte en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

En PowerShell, se usan los [cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) y [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva de vínculos de Caja fuerte predeterminada, pero la directiva [de seguridad preestablecida de **protección integrada**](preset-security-policies.md) asigna la protección de vínculos Caja fuerte a todos los destinatarios.
>
> La columna **Predeterminado en personalizado** hace referencia a los valores predeterminados de las directivas de vínculos Caja fuerte nuevas que se crean. Las columnas restantes indican (a menos que se indique lo contrario) los valores configurados en las directivas de seguridad preestablecidas correspondientes.

|Nombre de la característica de seguridad|Valor predeterminado en personalizado|Protección integrada|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|:---:|---|
|**Configuración de la protección de & hacer clic en la dirección URL**||||||
|**Acción en direcciones URL potencialmente malintencionadas en correos electrónicos**||||||
|**Activado: Caja fuerte Vínculos comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en el correo electrónico** <br/><br/> _EnableSafeLinksForEmail_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Aplicar vínculos Caja fuerte a mensajes de correo electrónico enviados dentro de la organización** <br/><br/> _EnableForInternalSenders_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Aplicar el examen de direcciones URL en tiempo real en busca de vínculos y vínculos sospechosos que apunten a archivos** <br/><br/> _ScanUrls_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje** <br/><br/> _DeliverMessageAfterScan_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**No volver a escribir direcciones URL, realizar comprobaciones solo a través de Caja fuerte API de vínculos** <br/><br/> _DisableURLRewrite_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**No volver a escribir las siguientes direcciones URL en el correo electrónico** <br/><br/> _DoNotRewriteUrls_|No seleccionada <br/><br/> Blanco|No seleccionada <br/><br/> Blanco|No seleccionada <br/><br/> Blanco|No seleccionada <br/><br/> Blanco|No tenemos ninguna recomendación específica para esta configuración. Para obtener más información, consulte [las listas "No volver a escribir las siguientes direcciones URL" en Caja fuerte Directivas de vínculos](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).|
|**Acción para direcciones URL potencialmente malintencionadas en Microsoft Teams**||||||
|**Activado: Caja fuerte Vínculos comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Configuración de protección de clics**||||||
|**Seguimiento de clics de usuario** <br/><br/> _TrackUserClicks_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Permitir que los usuarios haga clic en la dirección URL original** <br/><br/> _AllowClickThrough_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|Desactivar esta configuración (establecer _AllowClickThrough_ `$false`en ) impide hacer clic en la dirección URL original.|
|**Mostrar la personalización de marca de la organización en las páginas de notificación y advertencia** <br/><br/> _EnableOrganizationBranding_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Antes de activar esta configuración, debe seguir las instrucciones de [Personalización del tema de Microsoft 365 para que su organización](../../admin/setup/customize-your-organization-theme.md) cargue el logotipo de la empresa.|
|**Notificación**||||||
|**¿Cómo desea notificar a los usuarios?**|**Uso del texto de notificación predeterminado**|**Uso del texto de notificación predeterminado**|**Uso del texto de notificación predeterminado**|**Uso del texto de notificación predeterminado**|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Puede seleccionar **Usar texto de notificación personalizado** (_CustomNotificationText_) para escribir el texto de notificación personalizado que se va a usar. También puede seleccionar **Usar Traductor de Microsoft para la localización automática** (_UseTranslatedNotificationText_) para traducir el texto de notificación personalizado al idioma del usuario.

## <a name="related-articles"></a>Artículos relacionados

- ¿Está buscando procedimientos recomendados para **Exchange reglas de flujo de correo (también conocidas como reglas de transporte**)? Consulte [Procedimientos recomendados para configurar reglas de flujo de correo en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Los administradores y los usuarios pueden enviar falsos positivos (un buen correo electrónico marcado como incorrecto) y falsos negativos (se permite el correo electrónico incorrecto) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estos vínculos para obtener información sobre cómo **configurar** el [servicio EOP](/exchange/standalone-eop/set-up-your-eop-service) y **configurar** [Microsoft Defender para Office 365](defender-for-office-365.md). No olvide las instrucciones útiles de "[Proteger contra amenazas en Office 365](protect-against-threats.md)".

- **Las líneas base de seguridad para Windows** se pueden encontrar aquí: [¿Dónde puedo obtener las líneas base de seguridad?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO o locales y [Usar líneas base de seguridad para configurar dispositivos Windows en Intune](/intune/protect/security-baselines) para la seguridad basada en Intune. Por último, hay disponible una comparación entre las líneas base de seguridad Microsoft Defender para punto de conexión y Microsoft Intune en [Compare the Microsoft Defender para punto de conexión and the Windows Intune  líneas base de seguridad](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
